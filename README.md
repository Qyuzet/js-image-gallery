# JavaScript Image Gallery

![Image Gallery](https://img.shields.io/badge/Image%20Gallery-JavaScript-blue)

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Demo](#demo)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Overview

This repository contains a simple and elegant image gallery implemented with JavaScript, HTML, and CSS. The gallery allows users to scroll through images with smooth transitions and hover effects.
[TRY NOW!](https://qyuzet.github.io/js-image-gallery/)

![image](https://github.com/user-attachments/assets/99da7f4e-26e0-4fa5-9c5e-897d66edbe37)


## Features

- **Smooth Scrolling:** Users can scroll through the gallery horizontally using the mouse wheel or navigation buttons.
- **Hover Effects:** Images turn from grayscale to color and slightly enlarge when hovered over.
- **Navigation Buttons:** `Back` and `Next` buttons for easy navigation.

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/Qyuzet/js-image-gallery.git
    ```
2. Navigate to the project directory:
    ```bash
    cd js-image-gallery
    ```

## Usage

1. Open the `index.html` file in your web browser to view and interact with the image gallery.

### HTML Structure

The HTML file sets up the structure of the image gallery, including the gallery container and navigation buttons:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <div class="gallery-wrap">
      <img src="images/back.png" id="backBtn" alt="" />
      <div class="gallery">
        <div>
          <span><img src="images/image-1.jpg" alt="" /></span>
          <span><img src="images/image-2.jpg" alt="" /></span>
          <span><img src="images/image-3.jpg" alt="" /></span>
        </div>
        <div>
          <span><img src="images/image-4.jpg" alt="" /></span>
          <span><img src="images/image-5.jpg" alt="" /></span>
          <span><img src="images/image-6.jpg" alt="" /></span>
        </div>
      </div>
      <img src="images/next.png" id="nextBtn" alt="" />
    </div>

    <script src="scripts.js"></script>
  </body>
</html>
```

### CSS Styling

The CSS file provides the styling for the gallery, including layout, transitions, and hover effects:

```css
* {
  margin: 0;
  padding: 0;
  font-family: Arial, Helvetica, sans-serif;
  box-sizing: border-box;
}

body {
  background-color: #191919;
}

.gallery {
  width: 900px;
  display: flex;
  overflow-x: scroll;
}

.gallery div {
  width: 100%;
  display: grid;
  grid-template-columns: auto auto auto;
  grid-gap: 20px;
  padding: 10px;
  flex: none;
}

.gallery div img {
  width: 100%;
  filter: grayscale(100%);
  transition: transform 0.5s;
}

.gallery::-webkit-scrollbar {
  display: none;
}

.gallery-wrap {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 10% auto;
}

#backBtn,
#nextBtn {
  width: 50px;
  cursor: pointer;
  margin: 40px;
}

.gallery div img:hover {
  filter: grayscale(0);
  cursor: pointer;
  transform: scale(1.1);
}
```

### JavaScript Functionality

The JavaScript file handles the gallery's scrolling behavior and button interactions:

```javascript
let scrollContainer = document.querySelector(".gallery");
let backBtn = document.getElementById("backBtn");
let nextBtn = document.getElementById("nextBtn");

scrollContainer.addEventListener("wheel", (evt) => {
  evt.preventDefault();
  scrollContainer.scrollLeft += evt.deltaY;
  scrollContainer.style.scrollBehavior = "auto";
});

nextBtn.addEventListener("click", () => {
  scrollContainer.style.scrollBehavior = "smooth";
  scrollContainer.scrollLeft += 900;
});

backBtn.addEventListener("click", () => {
  scrollContainer.style.scrollBehavior = "smooth";
  scrollContainer.scrollLeft -= 900;
});
```

### Important Snippets

1. **Scrolling with the Mouse Wheel:**
    ```javascript
    scrollContainer.addEventListener("wheel", (evt) => {
      evt.preventDefault();
      scrollContainer.scrollLeft += evt.deltaY;
      scrollContainer.style.scrollBehavior = "auto";
    });
    ```
    - This snippet allows horizontal scrolling using the mouse wheel.

2. **Navigation Buttons:**
    ```javascript
    nextBtn.addEventListener("click", () => {
      scrollContainer.style.scrollBehavior = "smooth";
      scrollContainer.scrollLeft += 900;
    });

    backBtn.addEventListener("click", () => {
      scrollContainer.style.scrollBehavior = "smooth";
      scrollContainer.scrollLeft -= 900;
    });
    ```
    - These snippets handle the `Next` and `Back` button functionality, enabling smooth scrolling when clicked.

## Demo

You can view a live demo of the image gallery [here](https://qyuzet.github.io/js-image-gallery/).

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request or open an Issue if you have any improvements or suggestions.

## License

This project is licensed under the MIT License.

## Acknowledgements

- [Font Awesome](https://fontawesome.com/) for the icons used in validation feedback.
- [Poppins](https://fonts.google.com/specimen/Poppins) for the font.

