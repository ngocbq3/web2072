<script setup>
import { ref } from "vue";
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import Content from "./components/Content.vue";
import ProductCard from "./components/ProductCard.vue";
import Component from "./components/Component.vue";
import AdvandComponent from "./components/AdvandComponent.vue";

import Child from "./components/Child.vue";

function handleMessage(msg) {
  alert(msg);
}

const products = ref([
  { id: 1, name: "Iphone 17 Pro Max", price: 2000 },
  { id: 2, name: "Xiao 17 Pro Max", price: 2500 },
  { id: 3, name: "Samsung Galaxy S26", price: 1000 },
]);

function handleDelete(id) {
  //   alert(id);
  products.value = products.value.filter((product) => {
    return product.id != id;
  });
}
</script>
<template>
  <Header />
  <Content />
  <ProductCard
    v-for="product in products"
    v-bind="product"
    :key="product.id"
    @delete="handleDelete"
  />

  <div>
    <Child @sayHello="handleMessage" />
  </div>
  <Footer />

  <!-- slot -->
  <Component>
    <div>Đây là vị trí được định sẵn trong component</div>
  </Component>
  <!-- Slot name -->
  <AdvandComponent>
    <template #header>
      <h2>Tiêu đề cho header</h2>
    </template>
    <template #footer>
      <h2>Tiêu đề cho footer</h2>
    </template>
  </AdvandComponent>
</template>
