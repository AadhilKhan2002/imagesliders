<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Slider</title>
    <link rel="stylesheet" href="imageslider.css">
    <style>
      body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f0f0f0;
    margin: 0;
}
.slider {
    position: relative;
    width: 80%;
    max-width: 600px;
    overflow: hidden;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}
.slides {
    display: flex;
    transition: transform 0.5s ease-in-out;
}
.slide {
    min-width: 100%;
    box-sizing: border-box;
}
.slide img {
    width: 100%;
    display: block;
}
.prev, .next {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background-color: rgba(0, 0, 0, 0.5);
    color: white;
    border: none;
    padding: 10px;
    cursor: pointer;
    border-radius: 50%;
}
.prev {
    left: 10px;
}
.next {
    right: 10px;
}
.prev:hover, .next:hover {
    background-color: rgba(0, 0, 0, 0.8);
}

   </style>
</head>
<body>
    <div class="slider">
        <div class="slides">
            <div class="slide"><img src="https://images.pexels.com/photos/1667427/pexels-photo-1667427.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" alt="Image 1"></div>
            <div class="slide"><img src="https://images.pexels.com/photos/8605817/pexels-photo-8605817.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" alt="Image 2"></div>
            <div class="slide"><img src="https://images.pexels.com/photos/2067430/pexels-photo-2067430.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" alt="Image 3"></div>
            <div class="slide"><img src="https://images.pexels.com/photos/11495850/pexels-photo-11495850.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" alt="Image 4"></div>
        </div>
        <button class="prev" onclick="moveSlide(-1)">&#10097;</button>
        <button class="next" onclick="moveSlide(1)">&#10098;</button>
        
  </div>
    
   <script src="">
     let currentIndex = 0;

function moveSlide(n) {
    const slides = document.querySelector('.slides');
    const totalSlides = slides.children.length;

    currentIndex += n;

    if (currentIndex >= totalSlides) {
        currentIndex = 0;
    } else if (currentIndex < 0) {
        currentIndex = totalSlides - 1;
    }

    const offset = -currentIndex * 100;
    slides.style.transform = `translateX(${offset}%)`;
}

document.addEventListener('DOMContentLoaded', () => {
    moveSlide(0); // Initialize slider to the first image
});

   </script>
</body>
</html>
