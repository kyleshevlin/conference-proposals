# Renderless Components: For Invisible Logic & UIs

## Abstract

Remember the good old days before you knew about JavaScript bundling or what a component even was? When you would throw all your code into one massive file and start it as one large iife when the DOM was ready?

## Details

After a short introduction, I want to give a very brief history that most developers will have made coming to React. When you first learned about HTML, there was a 1-to-1 mapping of what you coded to the UI. You put a `<p>` tag, you got a paragraph. As you progressed, you learned about dynamic templating languages. Perhaps you can remember the first time you used a loop or `.map()` to create a list of dynamic items on a page. Our 1-to-1 mapping of code to UI was transformed into 1-to-many. Finally, we find ourselves in modern JavaScript, where we have learned to use component composition to separate concerns like the fetching and massaging of data from its presentation. Thus, we have components with no UI mapping whatsoever. Our mental model of code to UI can now be 1-to-any-or-none. Once we understand this concept, a set of new possibilities is opened up to us.

One of those possibilities is what I call a "renderless component". These components contain application logic, such as event listeners or data subscribers that utilize lifecycle methods to update application state but have no rendered UI. After a brief explanation that returning something from the `render()` method is the only requirement of a component, I want to show my first code example. In a React app I built for a physical interactive, I needed to detect whether users had stopped interacting with the app to put it into an inactive state. I created a `<DetectActivity />` component that binds event listeners to the `document` on `componentDidMount` and has logic that determines if a user has physically interacted with the application for a set duration.

## Pitch



