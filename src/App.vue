<script setup>
  import { ref, onMounted } from 'vue';
  import Modal from './components/Modal.vue';

  // reactive state
  // const count = ref(0)

  const title = 'My First Vue App!';
  const header = 'Sign up for the giveaway!';
  const text = 'Grab you ninja swag for half price!';
  const showModal = ref(false);

  function toggleModal() {
    showModal.value = !showModal.value;
  }
  // name.value is null until the component is mounted
  // const name = ref(null);

  // function handleClick() {
  //   console.log(name.value);
  //   name.value.classList.add('active');
  // }

  // onMounted(() => {
  //   name.value.focus();
  // });
</script>

<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <!-- <input type="text" ref="name">
  <button @click="handleClick">Click Me</button> -->
  <Modal v-if="showModal"
    v-bind:header="header"
    :text="text"
    theme="sale"
    @toggle-modal="toggleModal"
  />

  <button @click="toggleModal">Click Me</button>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  --webkit-font-smoothing: antialiased;
  --moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
