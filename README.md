## Next 14 Server Actions

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

## Anime Vault

A modern Next 14 server side Japanese anime list app with server actions, inifinite scroll & framer motion animations.

![anime-vault01](https://github.com/Bear29ers/anime-vault/assets/39920490/090b0dc5-679e-40e7-a167-6f5afb0001f8)

![anime-vault02](https://github.com/Bear29ers/anime-vault/assets/39920490/80f048e6-590b-4d45-a273-89a3fa7f6857)

[Deployed App](https://anime-vault-nine-psi.vercel.app/)

### Prerequisite

- Node.js 18.17.0 or later
- A basic understanding of JavaScript and React

### Cloning the repository

```bash
git clone https://github.com/Bear29ers/anime-vault.git
```

### Install packages

```bash
npm install
```

### Start the app

```bash
npm run dev
```
