
# 🌐 Interactive JavaScript Website

![Website Screenshot](images/preview.png)
*Example of the fully interactive website with modal, slider, and dynamic content.*

---

## **Table of Contents**

1. [Project Overview](#project-overview)
2. [Live Demo](#live-demo)
3. [Features](#features)
4. [Technologies Used](#technologies-used)
5. [Project Structure](#project-structure)
6. [Installation & Setup](#installation--setup)
7. [Usage Instructions](#usage-instructions)
8. [Code Highlights](#code-highlights)
9. [Screenshots](#screenshots)
10. [Contributing](#contributing)
11. [License](#license)

---

## **Project Overview**

This project is a **modern, interactive front-end website** built using **vanilla JavaScript, HTML, and CSS**. It demonstrates **dynamic UI components** and advanced JavaScript concepts for **learning and prototyping interactive web features**.

The website is designed to be fully responsive, interactive, and visually appealing. It includes **modals, smooth scrolling, lazy loading, sliders, sticky navigation, tabbed components**, and **menu hover effects**.

**Goal:** Showcase practical applications of **DOM manipulation, events, and modern JavaScript features** in a real-world website.

---

## **Live Demo**

You can view a live demo of this project here:
[🔗 Live Demo Link](https://your-demo-link.com)

---

## **Features**

### **1. Modal Window**

* Opens/closes with buttons, overlay click, or `Escape` key.
* Smooth animations and overlay background.

### **2. Cookie Consent Banner**

* Dismissible cookie message with dynamic height.
* Styled using CSS variables for flexibility.

### **3. Smooth Scrolling**

* Smooth scroll to sections on button click or nav link click.
* Works for both top buttons and internal page navigation.

### **4. Tabbed Component**

* Switch between multiple tabs in the operations section.
* Dynamically updates content without page reload.

### **5. Sticky Navigation**

* Navbar sticks to the top after scrolling past the header.
* Implemented using **Intersection Observer API** for performance.

### **6. Section Reveal**

* Sections appear with animation when entering viewport.
* Enhances user experience and site interactivity.

### **7. Lazy Loading Images**

* Optimizes page load speed by loading images only when needed.
* Uses `data-src` attributes and smooth fade-in effect.

### **8. Slider / Carousel**

* Horizontal image/content slider with arrows and navigation dots.
* Keyboard navigation: `ArrowLeft` and `ArrowRight`.
* Dynamically updates active dot based on current slide.

### **9. Menu Fade Animation**

* Hover effect dims sibling nav links and logo.
* Adds visual depth and improves navigation clarity.

---

## **Technologies Used**

* **HTML5** — Semantic structure for content.
* **CSS3** — Flexbox, Grid, animations, and transitions.
* **JavaScript (ES6+)** — DOM manipulation, events, Intersection Observer API, sliders, and animations.

Optional tools:

* Can use **Sass** for advanced styling.
* Deployable on **GitHub Pages, Netlify, or Vercel**.

---

## **Project Structure**

```
interactive-js-website/
│
├─ index.html               # Main HTML file
├─ style.css                # Styling for the website
├─ script.js                # All JS functionality
├─ images/                  # Images for slider, sections, and preview
├─ README.md                # Project documentation
└─ assets/                  # Optional: icons, fonts, other media
```

---

## **Installation & Setup**

1. Clone the repository:

```bash
git clone https://github.com/your-username/interactive-js-website.git
```

2. Navigate to the project folder:

```bash
cd interactive-js-website
```

3. Open `index.html` in your browser:

```bash
open index.html   # Mac
start index.html  # Windows
```

4. Or deploy using GitHub Pages/Netlify for live hosting.

---

## **Usage Instructions**

* **Modal:** Click "Open Modal" to open. Close with close button, overlay, or `Escape`.
* **Cookie Banner:** Click "Got it!" to dismiss.
* **Smooth Scrolling:** Use nav links or top buttons to scroll to sections.
* **Tabs:** Click on tabs to switch content dynamically.
* **Slider:** Navigate using arrows, dots, or keyboard (`ArrowLeft`/`ArrowRight`).
* **Lazy Loading Images:** Scroll down to load images dynamically.
* **Sticky Nav:** Scroll past the header to see navbar stick.

---

## **Code Highlights**

### **Modal**

```javascript
btnsOpenModal.forEach(btn => btn.addEventListener('click', openModal));
btnCloseModal.addEventListener('click', closeModal);
overlay.addEventListener('click', closeModal);

document.addEventListener('keydown', e => {
  if (e.key === 'Escape' && !modal.classList.contains('hidden')) closeModal();
});
```

### **Slider**

```javascript
const nextSlide = () => {
  currentSlide = currentSlide === maxSlide - 1 ? 0 : currentSlide + 1;
  goToSlide(currentSlide);
  activateDot(currentSlide);
};
```

### **Sticky Navbar**

```javascript
const stickyNav = entries => {
  const [entry] = entries;
  nav.classList.toggle('sticky', !entry.isIntersecting);
};
```

### **Lazy Loading Images**

```javascript
const loadImg = (entries, observer) => {
  const [entry] = entries;
  if (!entry.isIntersecting) return;
  entry.target.src = entry.target.dataset.src;
  entry.target.addEventListener('load', () => entry.target.classList.remove('lazy-img'));
  observer.unobserve(entry.target);
};
```

---

## **Screenshots**

![Modal](images/modal-screenshot.png) — Example modal window
![Slider](images/slider-screenshot.png) — Interactive slider
![Tabs](images/tabs-screenshot.png) — Tabbed content

---

## **Contributing**

Contributions are welcome!

1. Fork the repository.
2. Create a new branch: `git checkout -b feature/your-feature`.
3. Make changes and commit: `git commit -m "Add new feature"`.
4. Push to branch: `git push origin feature/your-feature`.
5. Open a Pull Request for review.

---

