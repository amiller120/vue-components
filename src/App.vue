<template>
  <button v-if="!isOpen" class="modal-button" @click="toggleModal">Open</button>
  <button v-else class="modal-button" @click="toggleModal">Close</button>

  <form class="form-top">
    <BasicInput v-model="input1" label="input1Title" />

    <BasicInput v-model="input2" label="input2Title" />
  </form>

  <SimpleModal v-bind:modalOpen="isOpen">
    <SimpleCard
      imageUri="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fd.newsweek.com%2Fen%2Ffull%2F1119776%2Fgettyimages-159044749.jpg&f=1&nofb=1"
    >
      <h4><b>John Doe</b></h4>
      <p>Architect & Engineer</p>
    </SimpleCard>
  </SimpleModal>
</template>

<script>
import SimpleModal from "./components/modal.vue";
import BasicInput from "./components/Form/BaseInput.vue";
import SimpleCard from "./components/SimpleCard.vue";

export default {
  name: "App",
  data() {
    return {
      isOpen: false,
      input1: "",
      input1Title: "title",
      input2Title: "title",
      input2: 0,
    };
  },
  methods: {
    toggleModal: function () {
      this.isOpen = !this.isOpen;
    },
  },
  components: {
    SimpleModal,
    BasicInput,
    SimpleCard,
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

.form-top {
  margin-top: 2rem;
}

.field {
  margin-bottom: 2rem;
}
</style>
