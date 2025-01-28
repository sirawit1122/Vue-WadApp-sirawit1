<script setup>
import { ref, computed, onMounted } from 'vue';
import { useRoute } from 'vue-router';

const route = useRoute();
const id = route.params.id;
const items = ref([]);
const product = computed(() =>
  items.value.find((item) => item.id === parseInt(id))
);

onMounted(() => {
  fetch(`https://fakestoreapi.com/products/${id}`)
    .then((res) => res.json())
    .then((data) => {
      items.value = [data];
    })
    .catch((error) => {
      console.error("Error fetching products:", error);
    });
});

const getImageUrl = (path) => {
  return new URL(`/${path}`, import.meta.url).href;
};
</script>

<template>
  <div v-if="product" class="container">
    <div class="left-column">
      <img :src="product.image" alt="product.title" />
    </div>
    <div class="right-column">
      <div class="product-description">
        <h1>{{ product.title }}</h1>
        <p>{{ product.description }}</p>
        <p class="product-price">Price: {{ product.price }} $</p>
        <router-link to="/products">
          <button class="cart-btn">Back to Products</button>
        </router-link>
      </div>
    </div>
  </div>
  <div v-else>
    <h1>Product not found or loading...</h1>
    <router-link to="/products">
      <button>Go back to the product list</button>
    </router-link>
  </div>
</template>
<script scoped>
export default {
  name: "Products",
  Component: {
    MyCard,
  },
  data() {
    return {
      items : [],
    };
  },
created() {
  fetch("https://fakestoreapi.com/products")
    .then((res) => res.json())
    .then(json => {
      this.items = json;
    })
      .catch(error => {
        console.error('Error fetching products:', error);
      });
  }
};
</script>
<style scoped>
.tx {
  position: static;
  top: 0;
  left: 0;
  width: 100%;
  height: 60px;
  margin-top: 2px;
  display: flex;
  align-items: center;
  padding: 0 0px;
  font-size: 20px;
  font-weight: 600;
}

main {
  margin-top: 60px;
  /* Offset for the fixed header */
  padding: 1rem;
}

.grid-container {
  display: grid;
  padding-top: 50%;
  margin-top: 5px;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  /* Responsive grid */
  gap: 1rem;
  /* Space between items */
  padding: 1rem;
  /* Add padding around the grid */
}

@media (min-width: 400px) {
  .grid-container {
    grid-template-columns: repeat(1, 1fr);
  }
}

.tx {
  position: static;
  top: 0;
  left: 0;
  width: 100%;
  height: 80px;
  margin-top: 2px;
  display: flex;
  align-items: center;
  padding: 0 0px;
  font-size: 16px;
  font-weight: 600;
  /* Reduce navbar height for smaller screens */
}
main {
  margin-top: 100px;
  /* Match the header height */
}

@media (min-width: 576px) {
  .grid-container {
    grid-template-columns: repeat(1, 1fr);
  }

  .tx {
    position: static;
    top: 0;
    left: 0;
    width: 100%;
    height: 100px;
    margin-top: 2px;
    display: flex;
    align-items: center;
    padding: 0 90px;
    font-size: 18px;
    font-weight: 600;
    /* Reduce navbar height for smaller screens */
  }

  main {
    margin-top: 100px;
    /* Match the header height */
  }
}

@media (min-width: 992px) {
  .grid-container {
    grid-template-columns: repeat(3, 1fr);
  }
}
.tx {
  position: static;
  top: 0;
  left: 0;
  width: 100%;
  height: 120px;
  margin-top: 2px;
  display: flex;
  align-items: center;
  padding: 0 90px;
  font-size: 20px;
  font-weight: 600;
  /* Reduce navbar height for smaller screens */
}

main {
  margin-top: 120px;
  /* Match the header height */
}
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); /* สร้างการจัดเรียงแบบตาราง */
  gap: 1rem;
  padding: 1rem;
}

</style>