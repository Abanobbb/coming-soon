# Abanoub is under development now!

#### In the meantime, enjoy some kittens!

<div id="image-container"></div> <!-- Initially empty -->

<div style="margin-top: 20px;">
    <button id="show-more" style="background-color: #FF69B4; color: white; border: none; padding: 10px 15px; cursor: pointer; float: left;">show me kittens</button>
</div>

<!-- Fixed position button container -->
<div style="position: fixed; bottom: 20px; right: 20px;">
    <button id="next-cat" style="background-color: #008CBA; color: white; border: none; padding: 10px 15px; cursor: pointer; display: none;">more cats</button>
</div>

<script>
const images = [
    "images/cat1.jpg",
    "images/cat2.jpg",
    "images/cat3.jpg",
    "images/cat4.jpg",
    "images/cat5.jpg",
    "images/cat6.jpg",
    "images/cat7.jpg"
];

let currentIndex = 0;

// Show the first cat image when 'Show More Kittens' is clicked
document.getElementById("show-more").onclick = function() {
    const imageContainer = document.getElementById("image-container");
    const newImage = document.createElement("img");
    newImage.src = images[currentIndex]; // Show the first image
    newImage.alt = `Image ${currentIndex + 1}`;
    newImage.style.width = "500px"; // Adjust the image size
    newImage.style.display = "block"; // Ensure images are displayed as block elements
    newImage.style.margin = "10px auto"; // Center images and add margin
    imageContainer.appendChild(newImage); // Add the image to the container

    this.style.display = "none"; // Hide the 'Show More' button
    document.getElementById("next-cat").style.display = "inline-block"; // Show 'Next Cat' button
};

// Change image when 'Next Cat' button is clicked
document.getElementById("next-cat").onclick = function() {
    currentIndex = (currentIndex + 1) % images.length; // Loop back to the first image
    const currentImage = document.querySelector("#image-container img");
    currentImage.src = images[currentIndex]; // Update the image source
    currentImage.alt = `Image ${currentIndex + 1}`; // Update the alt text
};
</script>
