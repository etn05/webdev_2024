# Final Project

Built off of midterm portfolio website

## Additions
- 2 project pages
- new bootstrap toggle nav bar

## Features Within The New Pages
- bootstrap carousel
- javascript zoom on hover over images
- smooth scrolling with GSAP
- embed pages to figma

### Bootstrap Uses
- carousel in project 1
- hamburger toggle menu
- home icon on project pages

### GSAP Uses
- split type in index
- smooth scrolling

### Java Uses
- image zoom on hover
- cursor effect
- image scroll transition
- blinking image
- nav bar scrolling function

### Code Snippet: Image Zoom

    document.addEventListener("DOMContentLoaded", () => {
    const ufcZoom = document.getElementById("ufcchart");
    const ufcImg = ufcZoom.querySelector("img");

    ufcZoom.addEventListener("mousemove", (event) => {
        const bounds = ufcZoom.getBoundingClientRect();
        const offsetX = event.clientX - bounds.left;
        const offsetY = event.clientY - bounds.top;

        const percentX = (offsetX / bounds.width) * 100;
        const percentY = (offsetY / bounds.height) * 100;

        ufcImg.style.transformOrigin = `${percentX}% ${percentY}%`;
        
        ufcZoom.classList.add("zoomed");
    });

    ufcZoom.addEventListener("mouseleave", () => {
        ufcZoom.classList.remove("zoomed");
    });
    });

attach event listener to DOMContent Loaded

then selects the container and image it contains

mousemove calculates the mouse position relative to the container and adjusts img zoom origin

there is a bounding box (bounds) which is obtained with getBoundingClientRect(); this provides the dimensions and position of the container relative to the viewport

const offsetX  = event.clientX - bounds.left; calcs the cursor's X / Y positions relative to the top left corner

then the cursor position is converted into the percentages of the containers W and H 

transformOrigin is based on the percentages and centers the zoom around the user's cursor

css class .zoomed is added to container to activate the increase of the scale of the image

when "mouseleave" the container, the .zoomed class is removed