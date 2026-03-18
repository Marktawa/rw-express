- Add package.json
```json
{
    "scripts": {
        "dev": "next dev",
        "build": "next build",
        "start": "next start",
        "lint": "eslint",
        "lint:fix": "eslint --fix"
    }
}
```

- install next
```sh
npm i next@latest react@latest react-dom@latest
```

- Create app directory
```sh
mkdir app
```

- Create a `layout.jsx` file in `app` folder:
```sh
touch app/layout.js
```

- Add this to `app/layout.js`:
```js
export default function RootLayout({ children }) {
    return (
        <html lang="en">
            <body>{children}</body>
        </html>
    )
}
```

- Create `app/page.js` file:
```sh
touch app/page.js
```

Add the following to `app/page.js`:
```js
export default function Page() {
    return <h1>Hello, Next.js</h1>
}
```

Run dev server:
```shell
npm run dev
```

Deploy to Railway
Stage changes
```sh
git add .
```

Commit changes
```sh
git commit -m "Hello Next"
```

Push changes
```sh
git push
```

- Login Railway
- Visit dashboard
- Create new Railway project
- Link GitHub repo
- Add Build command.
- Select your Service in the project canvas.
- Select the **Settings** tab
- Scroll down to Build commands
- Click to edit
- Type in your build command
- Click to **✓** to Save.
- Click **Deploy**
- Wait for your project to be built and deployed

Add Dockerfile
```sh
touch Dockerfile
```

Add the following to `Dockerfile`:
```Dockerfile
FROM node:18-alpine

WORKDIR /app
```
