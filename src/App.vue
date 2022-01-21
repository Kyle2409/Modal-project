<template>
  <h1>{{ title }}</h1>
  <p>have a look now</p>
  <teleport to=".modals" v-if="showModal">
    <modal theme="promotion" @close="toggleModal">
      <template v-slot:links>
        <a href="#">register</a>
        <a href="#">find out more</a>
      </template>
      <h1>whoopty scoop</h1>
      <p>blalalalalalala</p>
    </modal>
  </teleport>

  <teleport to=".modals" v-if="showModalTwo">
    <modal @close="toggleModalTwo">
      <h1>register for promotions</h1>
      <p>Do not miss out on upcoming promo codes!</p>
    </modal>
  </teleport>
  <button @click="toggleModal">info</button>
  &nbsp;
  <button @click="toggleModalTwo">register</button>
</template>

<script>

import Modal from "./components/Modal.vue";
export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "BOOOOOM",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgb(0, 0, 0);
  margin-top: 60px;
}
</style>