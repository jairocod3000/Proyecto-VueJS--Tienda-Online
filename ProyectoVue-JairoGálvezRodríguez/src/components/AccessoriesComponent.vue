<script setup>
import ProductComponent from "./ProductComponent.vue";
import { productsCollection } from "../firebase.js";

const productos = productsCollection.value.filter(
  (producto) => producto.categoria === "accesorios"
);
</script>

<template>
  <div class="container">
    <section id="products">
      <div class="products--text">
        <h1>Accesorios</h1>
      </div>
      <div class="products--container">
        <ProductComponent
          v-for="producto in productos"
          :key="producto.id"
          :producto="producto"
        />
      </div>
    </section>
  </div>
</template>
