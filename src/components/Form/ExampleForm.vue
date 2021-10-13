<template>
<div>
      <form class="form-top">
      <BasicInput
        v-model="input1"
        label="input1Title"
        />

        <BasicInput
        v-model="input2"
        label="input2Title"
         />
    </form>
    </div>
</template>
<script>
import BasicInput from './BaseInput.vue'

export default {
  data() {
    return {
      input1: "",
      input1Title: "title",
      input2Title: "title",
      input2: 0,
    };
  },
  components:{
    BasicInput
  }
};
</script>
<style>
.form-top{
    margin-top: 2rem;
}
.field {
  margin-bottom: 24px;
}
</style>