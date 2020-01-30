<template>
  <div disable>
    <b-list-group>
      <b-list-group-item
        href="#"
        class="col-xs-auto flex-column rounded-pill align-items-start"
        fluid
        v-b-toggle="tarefa.id"
      >{{ tarefa.tarefa }}</b-list-group-item>
      <b-collapse v-bind:id="tarefa.id" class="mt-1">
        <div id="button">
          <b-button pill @click="deleteComp" class="col-sm-auto" variant="outline-success">
            Feito!
            <b-icon font-scale="1" class="p-10" icon="check-circle" />
          </b-button>
          <!--
          <b-button pill class="col-sm-auto" variant="outline-danger">
            Descartar
            <b-icon font-scale="1" icon="trash" />
          </b-button>-->
        </div>
      </b-collapse>
    </b-list-group>
  </div>
</template>

<script>
export default {
  props: {
    tarefa: {
      type: Object,
      required: true
    }
  },
  methods: {
    deleteComp() {
      console.log('asdsadsadsad')
    },
  }
};
</script>

<style scoped>
#button {
  text-align: right;
}
</style>
