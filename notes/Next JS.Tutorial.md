---
id: rikfe3qd9gvj5o6a6l92cx8
title: Tutorial
desc: ''
updated: 1744318952892
created: 1742910002085
---


### Intro 

- The DOM is an object representation of the HTML elements. It acts as a bridge between your code and the user interface, and has a tree-like structure with parent and child relationships.

- You can use DOM methods and JavaScript, to listen to user events and manipulate the DOM by selecting, adding, updating, and deleting specific elements in the user interface. DOM manipulation allows you to not only target specific elements, but also change their style and content.

- Updating the DOM with plain JavaScript is very powerful but verbose. You've written all this code to add an `<h1>` element with some text:

- As the size of an app or team grows, it can become increasingly challenging to build applications this way - writing code that manuipulates the DOM to perform business logic.

- With this approach, developers spend a lot of time writing instructions to tell the computer how it should do things. But wouldn't it be nice to describe what you want to show and let the computer figure out how to update the DOM?

### Trees in React

- Trees are a common way to represent the relationship between entities. They are often used to model UI.

- Render trees represent the nested relationship between React components across a single render.

- With conditional rendering, the render tree may change across different renders. With different prop values, components may render different children components.

- Render trees help identify what the top-level and leaf components are. Top-level components affect the rendering performance of all components beneath them and leaf components are often re-rendered frequently. Identifying them is useful for understanding and debugging rendering performance.

- Dependency trees represent the module dependencies in a React app.

- Dependency trees are used by build tools to bundle the necessary code to ship an app.

- Dependency trees are useful for debugging large bundle sizes that slow time to paint and expose opportunities for optimizing what code is bundled.Trees are a common way to represent the relationship between entities. They are often used to model UI.


- Render trees represent the nested relationship between React components across a single render.

- With conditional rendering, the render tree may change across different renders. With different prop values, components may render different children components.

- Render trees help identify what the top-level and leaf components are. Top-level components affect the rendering performance of all components beneath them and leaf components are often re-rendered frequently. Identifying them is useful for understanding and debugging rendering performance.

- Dependency trees represent the module dependencies in a React app.

- Dependency trees are used by build tools to bundle the necessary code to ship an app.

- Dependency trees are useful for debugging large bundle sizes that slow time to paint and expose opportunities for optimizing what code is bundled.

### Advantages of React

- **Keeping a button’s rendering logic and markup together ensures that they stay in sync with each other on every edit. Conversely, details that are unrelated, such as the button’s markup and a sidebar’s markup, are isolated from each other, making it safer to change either of them on their own.** - this is one of the main advantages of React, along with... 

- **The main performance advantage comes from React's Virtual DOM approach: In vanilla JS: When you add a new tag, you'd typically: Get a reference to the dropdown, Create a new element, Set its properties, Append it to the DOM, This triggers a complete recalculation of layout, styles, and page rendering (reflow and repaint) which is expensive, especially if your dropdown has many items. In React: When a tag is added: React updates its virtual DOM first (which is just a JavaScript object), Compares it with the previous state (diffing), Only applies the minimal necessary changes to the real DOM.**

- Components allow you to build self-contained, reusable snippets of code. If you think of components as LEGO bricks, you can take these individual bricks and combine them together to form larger structures. If you need to update a piece of the UI, you can update the specific component or brick.

- This modularity allows your code to be more maintainable as it grows because you can add, update, and delete components without touching the rest of our application.

### Working with JSX

- To return multiple elements from a component, wrap them with a single parent tag.

- For example, you can use a `<div>`:

- If you don’t want to add an extra `<div>` to your markup, you can write <> and </> instead:

- This empty tag is called a **Fragment**. Fragments let you group things without leaving any trace in the browser HTML tree.

- JSX looks like HTML, but under the hood it is transformed into plain _JavaScript objects_. You can’t return two objects from a function without wrapping them into an array. This explains why you also can’t return two JSX tags without wrapping them into another tag or a Fragment.

- But browsers don't understand JSX out of the box, so you'll need a JavaScript compiler, such as a Babel, to transform your JSX code into regular JavaScript.

### Passing data with props

- Regular HTML elements have attributes that you can use to pass pieces of information that change the behavior of those elements. For example, changing the src attribute of an ``<img>`` element changes the image that is shown. Changing the href attribute of an `<a>` tag changes the destination of the link.

- In the same way, you can pass pieces of information as properties to React components. These are called props. Take for instance, the possible variations of a button:

- Note: In React, data flows down the component tree. This is referred to as one-way data flow. State, which will be discussed in the next chapter, can be passed from parent to child components as props.

- You can think of curly braces as a way to enter "JavaScript land" while you are in "JSX land". You can add any JavaScript expression (something that evaluates to a single value) inside curly braces.

### Managing state with hooks

- React has a set of functions called hooks. Hooks allow you to add additional logic such as state to your components. You can think of state as any information in your UI that changes over time, usually triggered by user interaction.

- Sharing state between components 

- Sometimes, you want the state of two components to always change together. To do it, remove state from both of them, move it to their closest common parent, and then pass it down to them via props. This is known as “lifting state up”, and it’s one of the most common things you will do writing React code.

- You can use Context and Reducer to share state between Parent and deep child components.


### Responding to events 

- You can handle events by passing a function as a prop to an element like `<button>`.

- Event handlers must be passed, not called! onClick={handleClick}, not onClick={handleClick()}.

- You can define an event handler function separately or inline.

- Event handlers are defined inside a component, so they can access props.

- You can declare an event handler in a parent and pass it as a prop to a child.

- You can define your own event handler props with application-specific names.

- Events propagate upwards. Call e.stopPropagation() on the first argument to prevent that.

- Events may have unwanted default browser behavior. Call `e.preventDefault()` to prevent that.

- Explicitly calling an event handler prop from a child handler is a good alternative to propagation.

### Server and Client Components
 
- The Network Boundary is a conceptual line that separates the different environments.

- In React, you choose where to place the network boundary in your component tree. For example, you can fetch data and render a user's posts on the server (using Server Components), then render the interactive LikeButton for each post on the client (using Client Components).

- Similarly, you can create a Nav component that is rendered on the server and shared across pages, but if you want to show an active state for links, you can render the list of Links on the client.

### Optimizing fonts and images

- Fonts play a significant role in the design of a website, but using custom fonts in your project can affect performance if the font files need to be fetched and loaded.

- **Cumulative Layout Shift(CLS)** is a metric used by Google to evaluate the performance and user experience of a website. With fonts, layout shift happens when the browser initially renders text in a fallback or system font and then swaps it out for a custom font once it has loaded. This swap can cause the text size, spacing, or layout to change, shifting elements around it.

- Next.js automatically optimizes fonts in the application when you use the next/font module. It downloads font files at build time and hosts them with your other static assets. This means when a user visits your application, there are no additional network requests for fonts which would impact performance.

- However, this means you have to manually:
    - Ensure your image is responsive on different screen sizes.
    - Specify image sizes for different devices.
    - Prevent layout shift as the images load.
    - Lazy load images that are outside the user's viewport.
    - Image Optimization is a large topic in web development that could be considered a specialization in itself. Instead of manually implementing these optimizations, you can use the next/image component to automatically optimize your images.

- By adding Inter to the `<body>` element, the font will be applied throughout your application. Here, you're also adding the Tailwind antialiased class _which smooths out the font. It's not necessary to use this class, but it adds a nice touch._
Next.js can serve static assets, like images, under the top-level /public folder. Files inside /public can be referenced in your application.

### Using Layouts

- Dashboards have some sort of navigation that is shared across multiple pages. In Next.js, you can use a special layout.tsx file to create UI that is shared between multiple pages. Let's create a layout for the dashboard pages!

- First, you're importing the `<SideNav />` component into your layout. Any components you import into this file will be part of the layout.

- The `<Layout />` component receives a children prop. This child can either be a page or another layout.

- One benefit of using layouts in Next.js is that on navigation, only the page components update while the layout won't re-render. This is called partial rendering which preserves client-side React state in the layout when transitioning between pages.

- This is called a root layout and is required in every Next.js application. Any UI you add to the root layout will be shared across all pages in your application. You can use the root layout to modify your `<html>` and `<body>` tags, and add metadata (you'll learn more about metadata in a later chapter).

### Routing and code-splitting

- Code splitting allows you to split your application code into smaller bundles to be downloaded and executed by the browser. This reduces the amount of data transferred and execution time for each request, leading to improved performance.

- Server Components allow your application code to be automatically code-split by route segments. This means only the code needed for the current route is loaded on navigation.


- The App Router uses a hybrid approach for routing and navigation. On the server, your application code is automatically code-split by route segments. And on the client, Next.js prefetches and caches the route segments. This means, when a user navigates to a new route, the browser doesn't reload the page, and only the route segments that change re-render - improving the navigation experience and performance.


- To improve the navigation experience, Next.js automatically code splits your application by route segments. This is different from a traditional React SPA, where the browser loads all your application code on the initial page load.

- Splitting code by routes means that pages become isolated. If a certain page throws an error, the rest of the application will still work. This is also less code for the browser to parse, which makes your application faster.

- Furthermore, in production, whenever `<Link>` components appear in the browser's viewport, Next.js automatically prefetches the code for the linked route in the background. By the time the user clicks the link, the code for the destination page will already be loaded in the background, and this is what makes the page transition near-instant!


### Fetching Data 

API layer
- APIs are an intermediary layer between your application code and database. There are a few cases where you might use an API:
    - If you're using third-party services that provide an API.
    - If you're fetching data from the client, you want to have an API layer that runs on the server to avoid exposing your database secrets to the client.

- In Next.js, you can create API endpoints using Route Handlers.

- Database queries
    - When you're creating a full-stack application, you'll also need to write logic to interact with your database. For relational databases like Postgres, you can do this with SQL or with an ORM.

- There are a few cases where you have to write database queries:
    - When creating your API endpoints, you need to write logic to interact with your database.
    - If you are using React Server Components (fetching data on the server), you can skip the API layer, and query your database directly without risking exposing your database secrets to the client.

- Using Server Components to fetch data. By default, Next.js applications use React Server Components. Fetching data with Server Components is a relatively new approach and there are a few benefits of using them:

- Server Components support JavaScript Promises, providing a solution for asynchronous tasks like data fetching natively. You can use async/await syntax without needing useEffect, useState or other data fetching libraries.

- Server Components run on the server, so you can keep expensive data fetches and logic on the server, only sending the result to the client.

- Since Server Components run on the server, you can query the database directly without an additional API layer. This saves you from writing and maintaining additional code.

### Project structure for a Next JS app

- `/app`: Contains all the routes, components, and logic for your application, this is where you'll be mostly working from.

- `/app/lib`: Contains functions used in your application, such as reusable utility functions and data fetching functions.

- `/app/ui`: Contains all the UI components for your application, such as cards, tables, and forms. To save time, we've pre-styled these components for you.

- `/public`: Contains all the static assets for your application, such as images.

- Config Files: You'll also notice config files such as next.config.ts at the root of your application. Most of these files are created and pre-configured when you start a new project using create-next-app. You will not need to modify them in this course.

### Working with images in Next JS

- Next.js can serve static assets, like images, under the top-level /public folder. Files inside /public can be referenced in your application.

- With regular HTML, you would add an image as follows:
    ```
    <img
    src="/hero.png"
    alt="Screenshots of the dashboard project showing desktop version"
    />
    ```

- However, this means you have to manually:
    - Ensure your image is responsive on different screen sizes.
    - Specify image sizes for different devices.
    - Prevent layout shift as the images load.
    - Lazy load images that are outside the user's viewport.
    - Image Optimization is a large topic in web development that could be considered a specialization in itself. Instead of manually implementing these optimizations, you can use the next/image component to automatically optimize your images.

- The `<Image>` Component is an extension of the HTML `<img>` tag, and comes with automatic image optimization, such as:
    - Preventing layout shift automatically when images are loading.
    - Resizing images to avoid shipping large images to devices with a smaller viewport.
    - Lazy loading images by default (images load as they enter the viewport).
    - Serving images in modern formats, like WebP and AVIF, when the browser supports it.

- It's good practice to set the width and height of your images to avoid layout shift, these should be an aspect ratio *identical* to the source image. These values are not the size the image is rendered, but instead the size of the actual image file used to understand the aspect ratio.

### Static Rendering vs Dynamic Rendering

- With **static rendering**, data fetching and rendering happens on the server at build time (when you deploy) or when revalidating data. Whenever a user visits your application, the cached result is served.

- There are a couple of benefits of static rendering:
    - Faster Websites - Prerendered content can be cached and globally distributed when deployed to platforms like Vercel. This ensures that users around the world can access your website's content more quickly and reliably.
    - Reduced Server Load - Because the content is cached, your server does not have to dynamically generate content for each user request. This can reduce compute costs.
    - SEO - Prerendered content is easier for search engine crawlers to index, as the content is already available when the page loads. This can lead to improved search engine rankings.
    - Static rendering is useful for UI with no data or data that is shared across users, such as a static blog post or a product page. It might not be a good fit for a dashboard that has personalized data which is regularly updated.

- With **dynamic rendering**, content is rendered on the server for each user at request time (when the user visits the page). There are a couple of benefits of dynamic rendering:

    - Real-Time Data - Dynamic rendering allows your application to display real-time or frequently updated data. This is ideal for applications where data changes often.
    - User-Specific Content - It's easier to serve personalized content, such as dashboards or user profiles, and update the data based on user interaction.
    - Request Time Information - Dynamic rendering allows you to access information that can only be known at request time, such as cookies or the URL search parameters.
 
### Streaming and Suspense

- Deciding where to place your Suspense boundaries:
    - You could stream the whole page like we did with loading.tsx... but that may lead to a longer loading time if one of the components has a slow data fetch.
    - You could stream every component individually... but that may lead to UI popping into the screen as it becomes ready.
    - You could also create a staggered effect by streaming page sections. But you'll need to create wrapper components.
    - Where you place your suspense boundaries will vary depending on your application. In general, it's good practice to move your data fetches down to the components that need it, and then wrap those components in Suspense. But there is nothing wrong with streaming the sections or the whole page if that's what your application needs.

### Search and Pagination

- As mentioned above, you'll be using URL search params to manage the search state. This pattern may be new if you're used to doing it with client side state.

- There are a couple of benefits of implementing search with URL params:
    - **Bookmarkable and shareable URLs**: Since the search parameters are in the URL, users can bookmark the current state of the application, including their search queries and filters, for future reference or sharing.
    - **Server-side rendering**: URL parameters can be directly consumed on the server to render the initial state, making it easier to handle server rendering.
    - **Analytics and tracking**: Having search queries and filters directly in the URL makes it easier to track user behavior without requiring additional client-side logic.

- When to use the useSearchParams() hook vs. the searchParams prop?
    - You might have noticed you used two different ways to extract search params. Whether you use one or the other depends on whether you're working on the client or the server.
    - `Search` is a Client Component, so you used the useSearchParams() hook to access the params from the client.
    - `Table` is a Server Component that fetches its own data, so you can pass the searchParams prop from the page to the component.
    - As a general rule, if you want to read the params from the client, use the useSearchParams() hook as this avoids having to go back to the server.

- Revalidate and redirect
    - Next.js has a client-side router cache that stores the route segments in the user's browser for a time. Along with prefetching, this cache ensures that users can quickly navigate between routes while reducing the number of requests made to the server.

    - Since you're updating the data displayed in the invoices route, you want to clear this cache and trigger a new request to the server. You can do this with the revalidatePath function from Next.js.