<template>
  <nav>
    <div class="wrapper">
      <!-- Logo Section -->
      <div class="logo">
        <router-link to="/">
          <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQNcMocjHBuNuGPTOfCTFmeFU8MgUfruwULmA&s" alt="App Logo" />
        </router-link>
      </div>

      <ul class="nav-links">
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/products">My Card</router-link></li>
        <li><router-link to="/about">About</router-link></li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: "MyNavbar",
};
</script>

<style scoped>

nav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;  
  background: linear-gradient(45deg, #39393a, #222122); 
  padding: 15px 0;
  z-index: 1000;
  border-radius: 0; 
  box-shadow: none; 
  display: flex;
  justify-content: center; 
  align-items: center;
  animation: slideDown 1s ease-in-out;
}


@keyframes slideDown {
  0% {
    opacity: 0;
    transform: translateY(-50px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.wrapper {
  display: flex;
  justify-content: center; 
  align-items: center;    
  width: 100%;             
  padding: 0 20px;         
}

.logo img {
  height: 60px;
  border-radius: 50%;
  transition: transform 0.3s ease-in-out; 
}


.logo img:hover {
  transform: scale(1.1); 
}


.nav-links {
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;
  gap: 30px;
}

.nav-links li {
  list-style: none;
}

.nav-links li a {
  text-decoration: none;
  color: #fff;
  font-size: 20px;
  font-weight: 600;
  font-family: 'Roboto', sans-serif;
  padding: 12px 30px;
  border-radius: 25px;
  background-color: rgba(250, 250, 250, 0.15);
  transition: all 0.4s ease;
  position: relative;
  display: inline-block;
}


.nav-links li a:hover,
.nav-links li a:focus {
  background-color: rgba(255, 255, 255, 0.3);
  text-shadow: 0 0 15px rgba(255, 255, 255, 0.8);
  transform: translateY(-5px);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
}


.nav-links li a::before {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 50%;
  transform: translateX(-50%);
  width: 0;
  height: 2px;
  background-color: #fff;
  transition: width 0.3s ease;
}

.nav-links li a:hover::before {
  width: 100%;
}


.nav-links li a.active {
  color: #ff7e5f;
  font-weight: 700;
}


@media (max-width: 768px) {
 
  .nav-links {
    display: none;
    width: 100%;
    flex-direction: column;
    text-align: center;
    margin-top: 20px;
  }

  nav {
    justify-content: center;
  }

  .logo img {
    height: 50px;
  }


  .nav-links li {
    margin: 10px 0;
  }

  .nav-links li a {
    padding: 10px 20px;
  }


  .nav-links.active {
    display: flex;
  }


  .hamburger {
    display: flex;
    flex-direction: column;
    gap: 5px;
    cursor: pointer;
    display: none;
  }

  .hamburger div {
    width: 30px;
    height: 4px;
    background-color: #fff;
    border-radius: 10px;
  }

  .hamburger.active div {
    background-color: #ff7e5f; 
  }
}


@media (max-width: 768px) {
  .hamburger {
    display: flex;
  }
}
</style>