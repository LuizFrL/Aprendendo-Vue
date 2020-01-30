<template>
  <div>
    <b-list-group>
      <b-list-group-item class="col-xs-auto" fluid>{{ tarefa }}</b-list-group-item>
    </b-list-group>
  </div>
</template>

<script>
export default {
  props: ["tarefa"]
};
</script>

<style scoped>
</style>