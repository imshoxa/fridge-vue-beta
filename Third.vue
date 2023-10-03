<template>
    <div>
      <h2>Список продуктов</h2>
      <ul>
        <li v-for="product in products" :key="product.id">
          {{ product.name }} - {{ product.expiryDate }}
          <button @click="viewProduct(product)">Просмотреть</button>
          <button @click="editProduct(product)">Редактировать</button>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    computed: {
      products() {
        return this.$store.state.products;
      }
    },
    methods: {
      viewProduct(product) {
        // реализовать отображение продукта
        this.$router.push(`/product/${product.id}`);
      },
      editProduct(product) {
        // реализовать редактирование продукта
        this.$router.push(`/product/${product.id}/edit`);
      }
    }
  };
  </script>
  