<template>
    <div>
      <h2>Просмотр продукта</h2>
      <div>
        <strong>Название продукта:</strong> {{ product.name }}
      </div>
      <div>
        <strong>Цена:</strong> {{ product.price }}
      </div>
      <div>
        <strong>Количество:</strong> {{ product.quantity }}
      </div>
      <div>
        <strong>Срок годности:</strong> {{ product.expiryDate }}
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      product: {
        type: Object,
        required: true
      }
    }
  };
  </script>
  