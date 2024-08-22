# Install_TailwindCSS



---

### Install process with CLI

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
