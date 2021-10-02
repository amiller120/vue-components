<template>
  <div>
    <button v-if="!isOpen" class="modal-button" @click="toggleModal">
      Open
    </button>
    <button v-else class="modal-button" @click="toggleModal">Close</button>
  </div>
    <SimpleModal v-bind:modalOpen="isOpen">
      <h1>Test</h1>
      <p>using a slot to add content to the modal.</p>
    </SimpleModal>
  
</template>

<script>
import SimpleModal from "./components/modal.vue";

export default {
  name: "App",
  data() {
    return {
      isOpen: false,
    };
  },
  methods: {
    toggleModal: function () {
      this.isOpen = !this.isOpen;
    },
  },
  components: {
    SimpleModal,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.modal-button {
  background-image: linear-gradient(144deg, #00ffb3, #9ae60e 50%, #00ffb3);
  border: 0;
  border-radius: 8px;
  box-shadow: rgba(151, 65, 252, 0.2) 0 15px 30px -5px;
  box-sizing: border-box;
  color: #ffffff;
  font-family: Phantomsans, sans-serif;
  font-size: 20px;
  line-height: 1em;
  max-width: 100%;
  min-width: 140px;
  padding: 19px 24px;
  text-decoration: none;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  white-space: nowrap;
  cursor: pointer;
}

.modal-button:active,
.modal-button:hover {
  outline: 0;
}

@media (min-width: 768px) {
  .modal-button {
    font-size: 24px;
    min-width: 196px;
  }
}
</style>
