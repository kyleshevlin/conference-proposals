# Renderless Components: Invisible Logic & UIs

## Abstract

Have you ever needed application logic that didn't neatly fit into the current paradigm of container or presentational components? Ever wanted to add functionality that didn't require a UI to go with it? A "renderless component" might be the right pattern for solving your problem. Learn how you can use React's lifecycle methods to setup and teardown logic and discover some new possibilities for React components in the process.

## Details

It's not an easy task to change our mental models. Arguably, developers may do it better than most given the pace that new technology comes at us, but we still need an adjustment from time to time. One of those adjustments I want to talk about is the fact that there isn't always a 1-to-1 mapping from our application logic to our UI. Sometimes we need functionality without any form.

In my work using React to build digital interactives (think museum kiosks), I have been solving this problem with a pattern I call a "renderless component". These components contain application logic, such as event listeners or data subscribers that utilize React's lifecycle methods to update application state but have no rendered UI.

I plan to remind (or teach) the audience that the only requirement of a React component is that its `render()` method returns something and that returning `null` is a perfectly valid value to return. With this, I plan to show my first code example.

Recently, I built an Electron app powered by several React apps for a 65" 4K touchscreen environment. Its purpose is to be an information hub usable by up to 4 people simultaneously. One of the requirements was that the app state would update when it's not in use so that it could enter an artistic attraction mode for users. Thus, in one of the React apps, I created a `<DetectActivity />` component that binds event listeners to the `document` on `componentDidMount` with logic that determines if a user has physically interacted with the application for a set duration (that can be adjusted via props). Yet, this component has no need for any UI in the application. For those who can remember using jQuery, essentially, we use `componentDidMount` similar to `ready()` and add functionality to our app for as long as we might need it available.

In this same set of applications, a second renderless component, a `<SocketHandler />`, was created to dispatch actions to Redux stores across apps via websockets.

I would follow this up with some pre-emptive points regarding other options for similar situations, such as middlewares (for store updates) or HOCs (sharing functionality). I would counter by reasoning that in a component driven ecosystem, it makes sense to use components in reasonable ways to solve our problems.

Lastly, I would finish with an exploration of some other possibilities for renderless components, like drop-in analytics based on context or other possibilities.

## Pitch

Renderless components are a natural evolution of using components to build up application functionality that may not map 1-to-1 with UI elements. However, it might not be obvious to developers to use components in this way. My hope is to share with them a pattern I have found useful in my work and think the community at large would find useful in similar situations. At the very least, it will encourage developers to explore the boundaries of what a component can be used for in a React application. I'm an engaging speaker having spent years doing public speaking in my previous career as a pastor, and I hope to put those skills to good use at React Rally.
