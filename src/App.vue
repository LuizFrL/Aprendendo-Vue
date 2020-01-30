<template>
  <div id="center">
    <div class="row">
      <b-img id="image" src="./assets/logo.png" class="mx-auto" fluid alt="Responsive image"></b-img>
    </div>
    <CoisasParaFazer />
    <FormDo />
  </div>
</template>

<script>
import FormDo from "./components/form/FormDo.vue";
import CoisasParaFazer from "./components/Layout/CoisasParaFazer.vue";

export default {
  name: "app",
  components: {
    FormDo,
    CoisasParaFazer
  }
};
</script>

<style scoped>
#center {
  height: 100%;
  margin: 0;
  padding: 0;
}
</style>
