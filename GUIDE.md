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
- Click **+ New** to create new Railway project
- Select the GitHub repo.
- Add Build command.
- Select your Service in the project canvas.
- Select the **Settings** tab
- Scroll down to **Build**
- Click **+ Build Command** under **Custom Build Command**
- Type in your build command. For example `npm run build`
- Click to **✓** to Save.
- Click **Deploy**
- Wait for your project to be built and deployed.
- Scroll to the **Networking** section in the **Settings** tab.
- Click **Generate Domain** under **Public Networking**.
- Type in the port your app is listening on. For example `3000`.
- Click **Generate Domain**.
- Click the generated domain to test if it gives the desired output


Add Dockerfile
```sh
touch Dockerfile
```

Add the following to `Dockerfile`:
```Dockerfile
FROM node:22-alpine

WORKDIR /app

COPY package.json ./
RUN npm install

COPY . .

RUN npm run build

EXPOSE 8080

CMD ["npm", "start"]
```
