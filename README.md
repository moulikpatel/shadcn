
# Shadcn

Create project
Start by creating a new React project using vite:





 To deploy this project run

```bash
  npm create vite@latest
```

# 1. Add Tailwind and its configuration

Install tailwindcss and its peer dependencies, then generate your tailwind.config.js and postcss.config.js files:

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p

```
Configure your template paths
Add the paths to all of your template files in your tailwind.config.js file.
```bash
tailwind.config.js

/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

Add the Tailwind directives to your CSS
Add the @tailwind directives for each of Tailwind’s layers to your ./src/index.css file.

```bash
@tailwind base;
@tailwind components;
@tailwind utilities;

```

Start your build process
```bash
npm run dev

```
# 2. Edit jsconfig.json file
The current version of Vite splits TypeScript configuration into three files, two of which need to be edited. Add the baseUrl and paths properties to the compilerOptions section of the jsconfig.json and jsconfig.app.json files:

```bash
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"]
    }
  }
}



```
# 3. Update vite.config.js
Add the following code to the vite.config.js so your app can resolve paths without error

```bash

import path from "path"
import react from "@vitejs/plugin-react"
import { defineConfig } from "vite"

export default defineConfig({
  plugins: [react()],
  resolve: {
    alias: {
      "@": path.resolve(__dirname, "./src"),
    },
  },
})

```
# 4. Run the CLI
Run the shadcn-ui init command to setup your project:

```bash
npx shadcn@latest init


```

# 5. Configure components.json
you will be asked a few questions to configure components.json:

```bash
1 Which style would you like to use? › New York
2 Which color would you like to use as base color? › Zinc
3 Do you want to use CSS variables for colors? › no / yes


```

# 6. That's it
You can now start adding components to your project.

```bash
npx shadcn@latest add button

```
The command above will add the Button component to your project. You can then import it like this:
```bash
import { Button } from "@/components/ui/button"

export default function Home() {
  return (
    <div>
      <Button>Click me</Button>
    </div>
  )
}


```



