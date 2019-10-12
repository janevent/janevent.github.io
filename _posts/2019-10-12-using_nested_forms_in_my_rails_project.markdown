---
layout: post
title:      "Using Nested Forms In My Rails Project"
date:       2019-10-12 21:00:36 +0000
permalink:  using_nested_forms_in_my_rails_project
---

Schooler is a website that facilitates parents in organizing their children's homeschooling or extracurricular activities.  In one form (a nested form) a user is able to create a course, and it's potentially many materials, enrollments which are associated with students, and meetings. 

Let's look at how the enrollments are created in a nested form.  In the CoursesController's new action:

```
       @course = Course.new
        
        
        3.times do
            @enrollment = @course.enrollments.build
        end 
```

This code provides the option of adding up to three enrollments for the course.  

In the models, a course has many enrollments, and many students through enrollments.  A student has many enrollments, and many courses through enrollments.   

Within the form_for FormHelper is the fields_for FormHelper :

```
<p>Enroll Your Studious Children:</p>
    <%= f.fields_for :enrollments do |enroll| %>
        <%= enroll.collection_select :student_id, Student.all, :id, :name, include_blank: true %>
        <%= enroll.label :start_date %>
        <%= enroll.text_field :start_date %>
        <%= enroll.label :end_date %>
        <%= enroll.text_field :end_date  %>
    <%end%>

```

Check out the API docs: [https://apidock.com/rails/ActionView/Helpers/FormHelper/fields_for]

In the params  the desired attributes should come through as  `enrollments_attributes: [:id, :start_date, :end_date, :student_id]`and not enrollments. (Note that as course has a has many relationship with enrollments the plural is used. )  To do this, in the Course Model I define an attribute writer.

The Ruby On Rails documents explains this beautifully:
> Nested attributes allow you to save attributes on associated records through the parent. By default nested attribute updating is turned off and you can enable it using the #accepts_nested_attributes_for class method. When you enable nested attributes an attribute writer is defined on the model. https://api.rubyonrails.org/classes/ActiveRecord/NestedAttributes/ClassMethods.html

Lastly, I account for these nested attributes in the strong parameters. 

***Tip** It is helpful to inspect elements in the form to check the params.

Nested routes is another way of establishing associations between parent and child.  I wanted to give users the option of adding a meeting to an already created course.  This is how the nested routes look like in the routes.rb file:
```
resources :courses do 
  resources :meetings, only: [:new, :create, :show, :index, :destroy]
end

```

[https://guides.rubyonrails.org/routing.html#nested-resources]

I put a link on the course show page to a new meeting form:

`<%= link_to "Add One More Meeting", new_course_meeting_path(@course) %>``

```

***Tip**** Run rake routes in your terminal to help you*

In the MeetingsController is where the relationship is created between a course and a meeting.  From the browser we recieve the params[:course_id].   It is with what comes through in params that we are able to find the course and build a meeting off of this course.

@course = Course.find_by(id: params[:course_id])
@meeting = @course.meetings.build(meeting_params)

In conclusion I liked using nested forms for the appearance of being one form.  However, I can only ever create up to a certain maximum children that are set in the controller. For the user to have the ability to create more, an edit page or a new form in a nested route is required.  Honestly, I enjoyed the clarity and relative simplicity that comes with the nested routes and associating objects that way, over nested forms.  Only one meeting can be made at a time using nested resources, which could be percieved as it's downfall. 








