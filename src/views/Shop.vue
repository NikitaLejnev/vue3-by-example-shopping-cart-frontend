<template>
  <h1>Shop</h1>
  <div>
    <router-link to="/order-form">Check Out</router-link>
  </div>
  <button type="button" @click="clearCart()">Clear Shopping Cart</button>
  <p>{{ cartItemsAdded.length }} item(s) added to cart.</p>
  <div v-for="shopItem of shopItems" :key="shopItem.shop_item_id">
    <h2>{{ shopItem.name }}</h2>
    <p>Description: {{ shopItem.description }}</p>
    <p>Price: ${{ shopItem.price }}</p>
    <img :src="shopItem.image_url" :alt="shopItem.name" />
    <br />
    <button type="button" @click="addCartItem(shopItem)">Add to Cart</button>
  </div>
</template>
