## Server Actions

In Next.js client components, fetching from client to server should be written as follows...

```jsx
'use client';

async function requestUsername(formData) {
  const response = await fetch('some_url', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      // Add other headers as needed
    },
    body: JSON.stringify({
      username: formData.get('username');
      // Add other key-value pairs for your request payload
    }),
  });
}

export default function App() {
  return (
    <form action={requestUsername}>
      <input type="text" name="username" />
      <button type="submit">Request</button>
    </form>
  );
}
```

However, using server actions in Next.js 14 reduces the amount of code and allows you to focus more on business logic.

Furthermore, when considering API, you need to think about not only makeing requests from the client, but also listening to requests on the server.

In Next.js 14, you don't have to think about API, because Next.js automatically handle this.

```jsx
'use client';

async function requestUsername(formData) {
  'use server';
  const username = formData.get('username');
  // ...
}

export default function App() {
  return (
    <form action={requestUsername}>
      <input type='text' name='username' />
      <button type='submit'>Request</button>
    </form>
  );
}
```

Offloading the burden of processing client data has some advantages.

- Pages will load faster
- They'll respond better
- Search engines will favor them

It will further improve...

- Core Web Vitals
- Crawl budget
- Crawl ranking

Ultimatelly, the user experience.

# Build Modern Next 14 Server Side App with Server Actions, Infinite Scroll & Framer Motion Animations

![Anime Website](https://i.ibb.co/MG1nbqt/YT-Thumbnails-2.png)

### [🌟 Become a top 1% Next.js 14 developer in only one course](https://jsmastery.pro/next14)

### [🚀 Land your dream programming job in 6 months](https://jsmastery.pro/masterclass)

### [📙 Free Three.js Cheatsheet](https://resource.jsmastery.pro/threejs-cheatsheet)

### [🌐 Best Hosting for Your Websites](https://hostinger.com/javascript10)
