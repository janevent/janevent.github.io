---
layout: post
title:      "Final Project Overview: React And Redux"
date:       2020-07-07 05:18:17 +0000
permalink:  final_project_overview_react_and_redux
---


**What's new?**

I find the fuzzy parts about building an app in React to be the incorporation of links and switching components using React Router.  In the Javascript section we learnt to hide certain elements and show other elements in response to a user’s actions.  We used event listeners to initiate a change in what is rendered, and/or trigger fetch requests.  This could get a little messy if we want multiple independent views or features.  

Using React, we are still listening for events, but the logic and what is displayed on screen, is encapsulated inside components.

Components are basically little parts of the application.  A single component can act as a container passing along data as props to little pieces (components) to display the data.  These containers/ components can have a corresponding link, and switch from one to the other depending on what is typed into the URL bar, or what link a user clicks (which changes the url).

**Switch It Up**

To use the BrowserRouter, import BrowserRouter from 'react-router-dom' and wrap Router around another component.

Now everything nested inside the App component will have access to BrowserRouter.

```
import {
  BrowserRouter as Router
} from "react-router-dom"
```


```
<Provider store={store}>
    <Router><App /></Router>
  </Provider>,
```

In the App component, you can use Switch to wrap around Route components.  Don't forget to import the appropriate components.

```
import {
  BrowserRouter as Router,
  Switch,
  Route
} from "react-router-dom";
```

In each Route, you need to specify the url path.  You can display the corresponding content through the props of component or render.  You can pass in functions through props, as well as the default props.

```
<Switch>
              <Route path='/budgets/:id' render={(props) => <ShowBudgetContainer findAndSetBudget={this.findAndSetBudget} findBudget={this.findBudget} {...props} />} /> 
              <Route path='/' component={Home} />
</Switch>                      
```

Now when a user clicks on a link that matches a particular path, the content specified in Route should be displayed.

```
<Link to={this.props.link(i.id)} >{i.title}</Link>
```

**A Few Stumbling Blocks**

My final project is an app that functions to help users write, and store budgets and budget templates. There are two show pages: a template, and a budget.  A user can click on a template/budget from multiple templates/budgets in a drop down menu.  At first I built the app so that the link for one of these show pages was always either ‘/template’ or ‘/budget’, and with each rendering of a show page, a get fetch request was made to the backend in order to display the requested data.  With each fetch request for a single template, a dispatch would be fired and the template data would be stored globally under a singular template key.

There is a better way of doing this however.  What I ended up doing instead is creating a link with a params of id: ``` <Link to=’/templates/2’ />```, and passing props down to the component specified.  I use withRouter to gain access to certain props including a match prop.  Using react dev tools, I can see what is accessible in props, and in particular what is nested under match.  There I can find the id nested under params (this.props.match.params.id).

The other alteration I made to this app was to fetch all the budgets and templates with their nested attributes of expenses and incomes upon the App mounting, and dispatching them to the global state.  Previously, I was sending a fetch request and storing the budgets and templates in the store, but at a shallow level, hence the need to retrieve the full object with nested attributes from the backend upon every subsequent rendering of the template or budget show page.

Now, I just use the id found in params and find the desired object in the store.  The show container then passes the template object on to the show page to display the requested information.

It is simpler, cleaner, and because of less fetch requests, more efficient.  It took me a little while to get there, but I had fun along the way!

