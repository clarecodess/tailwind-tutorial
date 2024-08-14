# How to Install and Set Up Tailwind CSS from Scratch # 
**Tailwind CSS** is a popular CSS framework that enables developers to style within their HTML. It simplifies styling through pre-defined classes. If you want to build a personal portfolio website to share your skills and projects, this tutorial will guide you to quickly set up and configure Tailwind CSS.

### Step 1: Setting Up the Project

- Create a new project folder and set up the basic structure:

```bash
mkdir portfolio-website
cd portfolio-website
```

- Confirm that you have Node.js installed:

```
node -v
```
- Create a `package.json` file:

```
npm init
```

### Step 2: Install and Set Up Tailwind CSS 
- Install Tailwind CSS. If you’re using `npm`, you can install it via:

```
npm i tailwindcss

```
- Create a `tailwind.config.js` file to configure Tailwind CSS:

```
npx tailwindcss init

```
- Create a folder called `src` and in it create a file  `index.html`.

- Add the paths to all the template files in `tailwind.config.js`. In this example, the path is: `"./src/*.{html,js}"`

```
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

- In `src` create another file, `input.css`, and add the Tailwind directives:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

- Next, build your CSS file:

```bash
npx tailwindcss -i ./src/input.css -o ./src/output.css --watch
```

This command will generate `output.css` where the Tailwind classes are compiled into a single CSS file that you can include in your HTML.

- Next, if you are on VS Code, install the extension `Tailwind CSS Intellisense` to get class suggestions.

### Step 3: Designing the Layout

In your `index.html` file, add `output.css` in the header. Continue by creating the basic structure of your portfolio website. The layout typically includes:

- A **Header** with your name and navigation links.
- A **Hero Section** with a brief introduction.
- A **Projects Section** showcasing your work.
- An **About Section** with your bio.
- A **Contact Section** with a form to reach out to you.

Here’s a simplified example of the HTML structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio</title>
    <link href="output.css" rel="stylesheet">
</head>
<body class="bg-gray-100 text-gray-900">
    <header class="bg-white shadow-md">
        <nav class="container mx-auto flex justify-between items-center p-5">
            <h1 class="text-2xl font-bold">Your Name</h1>
            <ul class="flex space-x-5">
                <li><a href="#home" class="hover:text-blue-500">Home</a></li>
                <li><a href="#projects" class="hover:text-blue-500">Projects</a></li>
                <li><a href="#about" class="hover:text-blue-500">About</a></li>
                <li><a href="#contact" class="hover:text-blue-500">Contact</a></li>
            </ul>
        </nav>
    </header>
    <section id="home" class="container mx-auto p-10 text-center">
        <h2 class="text-4xl font-semibold">Welcome to My Portfolio</h2>
        <p class="mt-4 text-xl">I am a frontend developer.</p>
    </section>
    <!-- Add more sections here -->
</body>
</html>
```

### Step 4: Making It Responsive

- Tailwind CSS makes it easy to create responsive designs using utility classes. For example, you can adjust padding, margins, and font sizes based on the screen size:

```html
<section id="home" class="container mx-auto p-10 text-center md:text-left">
    <h2 class="text-4xl font-semibold md:text-6xl">Welcome to My Portfolio</h2>
    <p class="mt-4 text-xl md:text-2xl">I am a frontend web developer.</p>
</section>
```

- To make your portfolio more interactive, use **JavaScript**. For example, you can create a smooth scrolling effect when navigation links are clicked:

```javascript
document.querySelectorAll('nav a').forEach(anchor => {
    anchor.addEventListener('click', function(e) {
        e.preventDefault();
        document.querySelector(this.getAttribute('href')).scrollIntoView({
            behavior: 'smooth'
        });
    });
});
```

## In Conclusion
Using this guide, you’ve created a modern, responsive personal portfolio website using Tailwind CSS and JavaScript. Keep experimenting with different designs and features to make your portfolio truly unique.
