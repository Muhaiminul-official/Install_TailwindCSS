# Install_TailwindCSS



---

## Install process with CLI

1. **Create Folders**:  
   - Dist => Contains `index.html` and `Output.css` (automatically created by the command).  
   - Src => Contains `input.css`.

2. **Initialize Tailwind CSS**:  
   Run the command:
   ```bash
   npx tailwindcss init
   ```

3. **Create `input.css` File**:  
   Inside `src/input.css`, add:
   ```css
   @tailwind base;
   @tailwind components;
   @tailwind utilities;
   ```

4. **Create Basic HTML File**:  
   In `dist/index.html`, include some Tailwind CSS classes.

5. **Configure Tailwind to Watch Files**:  
   Edit `tailwind.config.js` to include:
   ```javascript
   module.exports = {
     content: ["./dist/*.html"],
     theme: {
       extend: {},
     },
     plugins: [],
   }
   ```

6. **Run Tailwind CSS with Watch Mode**:  
   Use the command:
   ```bash
   npx tailwindcss -i ./src/input.css -o ./dist/Output.css --watch
   ```

7. **Optional: Modify `package.json`**:  
   The `package.json` file can include the following scripts:
   ```json
   {
     "name": "tailwind",
     "version": "1.0.0",
     "description": "",
     "main": "tailwind.config.js",
     "scripts": {
       "start": "npx tailwindcss -i ./src/input.css -o ./dist/Output.css --watch",
       "build": "npx tailwindcss -i ./src/input.css -o ./dist/Output.css"
     },
     "keywords": [],
     "author": "",
     "license": "ISC"
   }
   ```

---
---
## Tailwind CSS with Vite:

 1. **Initialize the Project**
Start by creating a new project directory and initializing it with `npm`:
```bash
npm init -y
```

### 2. **Install Dependencies**
Install Tailwind CSS, PostCSS, Autoprefixer, and Vite:
```bash
npm install -D tailwindcss postcss autoprefixer vite
```

### 3. **Initialize Tailwind CSS and PostCSS**
Generate the `tailwind.config.js` and `postcss.config.js` files by running:
```bash
npx tailwindcss init -p
```

 4. **Configure `tailwind.config.js`**
Open `tailwind.config.js` and configure the `content` option to include your files. For example:
```javascript
module.exports = {
  content: [
    './index.html',
    './src/**/*.{js,ts,jsx,tsx}',
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

 5. **Set Up Your CSS File**
Create a `src/input.css` file and include the Tailwind directives:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

 6. **Configure Vite**
In your `package.json`, add a script to start the Vite development server:
```json
{
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "serve": "vite preview"
  }
}
```

 7. **Create an HTML File**
Create an `index.html` file in the root of your project and link to the CSS file:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vite + Tailwind CSS</title>
    <link rel="stylesheet" href="/src/input.css">
</head>
<body class="bg-gray-100">
    <h1 class="text-3xl font-bold text-center text-blue-500">Hello, Vite + Tailwind CSS!</h1>
</body>
</html>
```

 8. **Start the Development Server**
Run the following command to start the Vite development server:
```bash
npm run dev
```

 9. **Build for Production**
When you're ready to build your project for production, use:
```bash
npm run build
```
---
