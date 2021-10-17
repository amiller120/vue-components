<template>
  <div>
    <div class="card" v-bind:style="{ width: cardWidth }">
      <img v-bind:src="imageUri" style="width:100%"/>
      <div class="container">
        <slot></slot>
      </div>
    </div>
  </div>
</template>
<script>
export default {
    props: {
        imageUri:{
            type: String,
            required: true
        },
        cardWidth:{
          type: String,
          required: false,
          default: '100%'
        }
    }
};
</script>
<style scoped>
.card {
  /* Add shadows to create the "card" effect */
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
}

/* On mouse-over, add a deeper shadow */
.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}

/* Add some padding inside the card container */
.container {
  padding: 2px 16px;
}
</style>