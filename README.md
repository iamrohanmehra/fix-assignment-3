﻿# Fixing TailwindCSS Setup Issues

Follow these steps to fix and properly set up TailwindCSS in your project:

## Steps to Fix the Issue

### 1. Remove Unnecessary Files

- Delete the `index.html` file **outside** the `src` folder.
- Move the original `index.html` **from** the `src` folder **to the root directory**.

### 2. Update TailwindCSS Import

- Since you are using **TailwindCSS v4**, update your CSS imports:
  ```css
  @import "tailwindcss";
  ```
  Replace the old imports:
  ```css
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
  ```

### 3. Modify `index.html`

- Locate **line 6** and update the stylesheet link:
  ```html
  <link href="./src/output.css" rel="stylesheet" />
  ```
  Replace:
  ```html
  <link href="./output.css" rel="stylesheet" />
  ```

### 4. Fix `package.json` Scripts

Update the `scripts` section in `package.json`:

```json
"scripts": {
  "test": "echo \"Error: no test specified\" && exit 1",
  "dev": "npx tailwindcss -i ./src/input.css -o ./src/output.css --watch"
}
```

### 5. Install the Latest TailwindCSS CLI

Run the following command to install TailwindCSS CLI:

```sh
npm install @tailwindcss/cli
```

### 6. Run the Project

Start the development server:

```sh
npm run dev
```

Then, launch the **Live Server** to see the changes.

---
