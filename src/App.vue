<template>
  <div>
    <div class="row">
      <b-img id="image" src="./assets/logo.png" class="mx-auto" fluid alt="Responsive image"></b-img>
    </div>
    <div class="row">
      <p class="col-sm-auto mx-auto">Coisas Para Fazer</p>
    </div>
    <FormDo />
  </div>
</template>

<script>
import FormDo from "./components/form/FormDo.vue";
export default {
  name: "app",
  components: {
    FormDo
  }
};
</script>

<style scoped>
#image {
  padding: 10px;
}
</style>
