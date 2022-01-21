<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ promotion: theme === 'promotion' }">
      <slot></slot>
      <div class="actions">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>

<script>
import Modal from "./Modal.vue";
export default {
  props: ["header", "text", "theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style scope>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: rgb(202, 101, 101);
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(128, 128, 128, 0.788);
  width: 100%;
  height: 100%;
}
.modal h1 {
  color: indigo;
  border: none;
  padding: 0;
}
.modal.promotion {
  background: rgb(0, 0, 0);
  color: rgb(255, 255, 255);
}
.modal.promotion h1 {
  color: white;
}
.modal .actions {
  text-align: center;
  margin: 30px 0 10px 0;
}
.modal .actions a {
  color: #333;
  padding: 8px;
  border: 1px solid #eee;
  border-radius: 4px;
  text-decoration: none;
  margin: 10px;
}
.modal.promotion {
  background: paleturquoise;
  color: black;
}
.modal.promotion h1 {
  color: white;
}
.modal.promotion .actions {
  color: white;
}
.modal.promotion .actions a {
  color: white;
}
</style>