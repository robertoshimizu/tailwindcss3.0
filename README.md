<h1 align="center">
	<a 
    href="https://tailwindcss.com/">
    <img
		width="400"
		alt="Tailwind logo"
		src="https://miro.medium.com/max/700/0*nGTqAcuGJb118YAO.png">
    </a>        
</h1>

# Tailwindcss 3.0

### The most basic and quick way to start using tailwind is via CDN

```html
<link href="https://unpkg.com/tailwindcss@^2/dist/tailwind.min.css" rel="stylesheet">
```

Just add it in your `index.html`:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body>
    <h1 class="text-4xl font-bold text-center text-blue-500">Hello World</h1>
</body>
</html>
```

## Tailwind is a PostCSS Plugin

PostCSS is a tool for transforming CSS with JavaScript plugins. It provides features via its extensive plugin ecosystem to help improve your CSS writing experience. You can pick the plugins you need or even write a custom one for yourself. Tailwindcss and autoprefixer are PostCSS plugins, and they should be added to your PostCSS configuration. Check them in your `postcss.config.js` file.
This is a reason why postcss-cli and autoprefixer are installed together with tailwindcss. Check them in the `package.json` file.

Together with autoprefixer, the build will replace all css custom markers with tailwindcss generated code, which are all tailwindcss base styles, components and utility classes. Check the file  `/build/taiwind.css` as a result of `build-tailwind` script in `package.json`. You should check for that in your Starter project. Now it is just link the stylesheet in the `index.html` and voilá! Below you find a complete setup workflow.

## Setup

- **Create a project folder** Move inside the project folder and initiate the project using pnpm, npm or yarn.
```sh
cd <project folder>
pnpm init
```
- **Install tailwindcss using CLI.** It deals already with the installation of Postprocesser, autoprefixers and vite.

Instructions pretty clear in the documentation:
https://tailwindcss.com/docs/installation

## Linking to html

In the public folder, create a new `index.html` file. Scaffold a html template. Link to the `/build/tailwind.css` and add a ``Hello World`` h1 tag, and style it using tailwind utility classes.
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="output.css">
</head>
<body>
    <h1 class="text-4xl font-bold text-center text-blue-500">Hello World! </h1>
</body>
</html>
```
To keep it simple, use Live Preview in VSCode.

Let tailwindcss watch changes and update the `output.css` file:
```
npx tailwindcss -i ./input.css -o ./output.css --watch
```


### References:
- [Designing with Tailwind CSS](https://tailwindcss.com/course): [GETTING UP AND RUNNING](https://tailwindcss.com/course/setting-up-tailwind-and-postcss)