<template>
  <h1>Order Form</h1>
  <div v-for="(cartItem, index) of cartItemsAdded" :key="cartItem.cartItemId">
    <h2>{{ cartItem.name }}</h2>
    <p>Description: {{ cartItem.description }}</p>
    <p>Price: ${{ cartItem.price }}</p>
    <br />
    <button type="button" @click="removeCartItem(index)">
      Remove From Cart
    </button>
  </div>
  <Form :validationSchema="schema" @submit="submitOrder">
    <div>
      <label for="name">Name</label>
      <br />
      <Field name="name" type="text" placeholder="Name" />
      <ErrorMessage name="name" />
    </div>
    <br />
    <div>
      <label for="phone">Phone</label>
      <br />
      <Field name="phone" type="text" placeholder="Phone" />
      <ErrorMessage name="phone" />
    </div>
    <br />
    <div>
      <label for="address">Address</label>
      <br />
      <Field name="address" type="text" placeholder="Address" />
      <ErrorMessage name="address" />
    </div>
    <br />
    <input type="submit" />
  </Form>
</template>
