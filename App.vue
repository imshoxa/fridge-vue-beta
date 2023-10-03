<template>
    <div>
      <h2>{{ editing ? 'Редактирование продукта' : 'Добавление продукта' }}</h2>
      <form @submit.prevent="saveProduct">
        <div>
          <label for="productName">Название продукта:</label>
          <input type="text" v-model="product.name" required />
        </div>
        <div>
          <label for="productPrice">Цена:</label>
          <input type="number" v-model="product.price" required />
        </div>
        <div>
          <label for="productQuantity">Количество:</label>
          <input type="number" v-model="product.quantity" required />
        </div>
        <div>
          <label for="productExpiryDate">Срок годности:</label>
          <input type="date" v-model="product.expiryDate" required />
        </div>
        <button type="submit">{{ editing ? 'Сохранить' : 'Добавить' }}</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      product: {
        type: Object,
        default: () => ({
          name: '',
          price: 0,
          quantity: 0,
          expiryDate: ''
        })
      },
      editing: {
        type: Boolean,
        default: false
      }
    },
    methods: {
      saveProduct() {
        // добавить логику сохранения/редактирования продукта
        // например, вызвать соответствующий метод из Vuex
        if (this.editing) {
          this.$store.commit('editProduct', this.product);
        } else {
          this.$store.commit('addProduct', this.product);
        }
        // сбросить форму после сохранения
        this.product = {
          name: '',
          price: 0,
          quantity: 0,
          expiryDate: ''
        };
      }
    }
  };
  </script>
  