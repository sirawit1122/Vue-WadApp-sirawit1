<template>
  <div>
    <ul class="navbar">
      <li><a href="#home">Home</a></li>
      <li><a href="#mycard">MyCard</a></li>
      <li><a href="#about">About</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  // Add any component logic here if needed
}
</script>

<style>
/* Set basic styling for the navbar */
.navbar {
  list-style-type: none;
  margin: 0;
  padding: 10px;
  overflow: hidden;
  background: linear-gradient(135deg, #8a2be2, #ff69b4, #ba55d3); /* Gradient color */
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.3);
  border-radius: 10px;
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1000;
  display: flex;
  justify-content: center; /* Center the navbar items */
}

/* Style each menu item */
.navbar li {
  margin: 0 10px; /* Add margin between items */
}

.navbar li a {
  display: block;
  color: white;
  text-align: center;
  padding: 10px 15px;
  text-decoration: none;
  font-family: 'Poppins', sans-serif;
  font-size: 18px;
  transition: all 0.3s ease;
  position: relative;
  border-radius: 5px;
}

/* Add hover effect for each link */
.navbar li a:hover {
  background-color: #df4190;
  color: #ffffff;
  text-shadow: 0 0 10px rgba(255, 255, 255, 0.8);
  transform: scale(1.1);
  box-shadow: 0 0 15px rgba(204, 73, 187, 0.7), inset 0 0 5px rgba(102, 190, 212, 0.7);
}

/* Add underline animation on hover */
.navbar li a::after {
  content: '';
  display: block;
  width: 0;
  height: 3px;
  background: #ffffff;
  transition: width 0.4s;
  margin-top: 5px;
}

.navbar li a:hover::after {
  width: 100%;
}

/* Add gradient border on hover */
.navbar li a:hover {
  border: 2px solid transparent;
  border-image: linear-gradient(45deg, #d40a25, #be1586);
  border-image-slice: 1;
}

/* Add padding to ensure content is visible below navbar */
body {
  padding-top: 70px; /* Adjust according to the height of the navbar */
}
</style>