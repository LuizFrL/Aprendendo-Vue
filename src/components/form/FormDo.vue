<template>
  <div class="mx-auto col-8 label-cols-sm-16">
    <b-form-tags
      v-model="value"
      class="label-cols-sm-16 mb-2"
      remove-on-delete
      placeholder="Tarefas para fazer..."
      tag-variant="info"
      tag-pills
      add-button-variant="info"
    ></b-form-tags>
    <div class="row">
      <b-button class="col-sm-3 p-2" pill variant="outline-success">
        <b-icon font-scale="1" class="p-10" icon="check-box" />Adicionar
      </b-button>
      <p class="col-sm-6"></p>
      <b-button class="col-sm-3 p-2" pill @click="clearValue" variant="outline-danger">
        <b-icon font-scale="1" icon="trash-fill" />Limpar
      </b-button>
    </div>
    <p>Value: {{ value }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      value: []
    };
  },
  methods: {
    clearValue() {
      this.value = [];
    }
  }
};
</script>
