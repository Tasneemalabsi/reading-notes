# React 3

## React Context 

*React context allows us to pass down and use (consume) data in whatever component we need in our React app without using props.*

React context is great when you are passing data that can be used in any component in your application.

**These types of data include:**

- Theme data. 
- User data.
- Location-specific data.

## What problems does React context solve?

**Props drilling** is a term to describe when you pass props down multiple levels to a nested component, through components that don't need it.

```
export default function App({ theme }) {
  return (
    <>
      <Header theme={theme} />
      <Main theme={theme} />
      <Sidebar theme={theme} />
      <Footer theme={theme} />
    </>
  );
}

function Header({ theme }) {
  return (
    <>
      <User theme={theme} />
      <Login theme={theme} />
      <Menu theme={theme} />
    </>
  );
}
```
*What is the issue with this example?*

The issue is that we are drilling the theme prop through multiple components that don't immediately need it.

## How to use React context?

**There are four steps to using React context:**

- Create context using the createContext method.
- Take your created context and wrap the context provider around your component tree.
- Put any value you like on your context provider using the value prop.
- Read that value within any component by using the context consumer.

## What is the useContext hook?

Another way of consuming context became available in React 16.8 with the arrival of React hooks. We can now consume context with the useContext hook.

```
import React from 'react';

export const UserContext = React.createContext();

export default function App() {
  return (
    <UserContext.Provider value="Reed">
      <User />
    </UserContext.Provider>
  )
}

function User() {
  const value = React.useContext(UserContext);  
    
  return <h1>{value}</h1>;
}
```

**The mistake many developers make is reaching for context when once they have to pass props down several levels to a component.**

Here is an application with a nested Avatar component that requires two props username and avatarSrc from the App component.

```
export default function App({ user }) {
  const { username, avatarSrc } = user;

  return (
    <main>
      <Navbar username={username} avatarSrc={avatarSrc} />
    </main>
  );
}

function Navbar({ username, avatarSrc }) {
  return (
    <nav>
      <Avatar username={username} avatarSrc={avatarSrc} />
    </nav>
  );
}

function Avatar({ username, avatarSrc }) {
  return <img src={avatarSrc} alt={username} />;
}
```

Instead of immediately resorting to context because we are prop drilling, we should better compose our components.

## Does React context replace Redux?

For many React beginners, Redux is a way of more easily passing around data. This is because Redux comes with React context itself.

However, if you are not also updating state, but merely passing it down your component tree, you do not need a global state management library like Redux.

### React context caveats

While it is possible to combine React context with a hook like useReducer and create a makeshift state management library without any third-party library, it is generally not recommended for performance reasons.

If you are passing down an object on your React context provider and any property on it updates, what happens? Any component which consumes that context will re-render.

## Create a Next.js App

*Next.js aims to have best-in-class developer experience and many built-in features, such as:*

- An intuitive page-based routing system (with support for dynamic routes)
- Pre-rendering, both static generation (SSG) and server-side rendering (SSR) are supported on a per-page basis
- Automatic code splitting for faster page loads
- Client-side routing with optimized prefetching
- Built-in CSS and Sass support, and support for any CSS-in-JS library
- Development environment with Fast Refresh support
- API routes to build API endpoints with Serverless Functions
- Fully extendable

### Setup

**Create a Next.js app**

`npx create-next-app nextjs-blog --use-npm --example "https://github.com/vercel/next-learn/tree/master/basics/learn-starter"`

**Run the development server**

`npm run dev`

### Assets, Metadata, and CSS

**Assets**

Next.js can serve static assets, like images, under the top-level public directory. Files inside public can be referenced from the root of the application similar to pages.

The public directory is also useful for robots.txt, Google Site Verification, and any other static assets. Check out the documentation for Static File Serving to learn more.

**Unoptimized Image**

With regular HTML, you would add your profile picture as follows:

`<img src="/images/profile.jpg" alt="Your Name" />`

**However, this means you have to manually handle:**

- Ensuring your image is responsive on different screen sizes
- Optimizing your images with a third-party tool or library
- Only loading images when they enter the viewport

### Image Component and Image Optimization

Next.js has support for Image Optimization by default. This allows for resizing, optimizing, and serving images in modern formats like WebP when the browser supports it. 

### Using the Image Component

Instead of optimizing images at build time, Next.js optimizes images on-demand, as users request them. Unlike static site generators and static-only solutions, your build times aren't increased, whether shipping 10 images or 10 million images.

Images are lazy loaded by default. That means your page speed isn't penalized for images outside the viewport. Images load as they are scrolled into viewport.

```
import Image from 'next/image'

const YourComponent = () => (
  <Image
    src="/images/profile.jpg" // Route of the image file
    height={144} // Desired size with correct aspect ratio
    width={144} // Desired size with correct aspect ratio
    alt="Your Name"
  />
)
```

### Metadata

`<title>` is part of the `<head>` HTML tag, so let's dive into how we can modify the `<head>` tag in a Next.js page.

Open pages/index.js in your editor and find the following lines:

```
<Header>
  <title>Create Next App</title>
  <link rel="icon" href="/favicon.ico" />
</Head>
```

otice that `<Head>` is used instead of the lowercase `<head>`. `<Head>` is a React Component that is built into Next.js. It allows you to modify the `<head>` of a page.

You can import the Head component from the next/head module.

Adding Head to first-post.js
We haven't added a `<title>` to our /posts/first-post route. Let's add one.

Open the pages/posts/first-post.js file and add an import for Head from next/head at the beginning of the file:

`import Head from 'next/head'`

### Writing and Importing CSS

Next.js has built-in support for CSS and Sass which allows you to import .css and .scss files.

Using popular CSS libraries like Tailwind CSS is also supported.

As you can see, our index page `(http://localhost:3000)` already has some styles. If you take a look at pages/index.js, you should see code like this:

```
<style jsx>{`
  …
`}</style>
```
