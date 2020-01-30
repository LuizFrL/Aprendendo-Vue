<template>
  <div class="mx-auto col-8 label-cols-sm-16">
    <b-form-tags
      id="formulario"
      v-model="tasks"
      class="label-cols-sm-16 mb-2"
      remove-on-delete
      placeholder="Tarefas para fazer..."
      tag-variant="info"
      tag-pills
      add-button-variant="info"
    ></b-form-tags>
    <div class="row">
      <b-button class="col-sm-3 p-2" pill @click="buildTasks" variant="outline-success">
        <b-icon font-scale="1" class="p-10" icon="check-box" />Adicionar
      </b-button>
      <p class="col-sm-6"></p>
      <b-button class="col-sm-3 p-2" pill @click="clearValue" variant="outline-danger">
        <b-icon font-scale="1" icon="trash-fill" />Limpar
      </b-button>
    </div>
    <p>Value: {{ tasks }}</p>
    <p>Tarefas: {{ allTasks }}</p>

    <div v-for="Task in allTasks" :key="Task.id" class="p-2">
      <ListaCoisasParaFazer tarefa="Task.tarefa" />
    </div>
  </div>
</template>

<script>
import ListaCoisasParaFazer from "../Layout/lists/ListaCoisasParaFazer.vue";

export default {
  data() {
    return {
      tasks: [],
      allTasks: []
    };
  },
  components: {
    ListaCoisasParaFazer
  },
  methods: {
    clearValue() {
      this.tasks = [];
      document.querySelector("input").focus();
    },
    buildTasks() {
      let i = 0;
      this.tasks.forEach(task => {
        i++;
        this.allTasks.push({
          id: Date.now() - i,
          tarefa: String(task),
          checked: false
        });
      });
      this.clearValue();
    }
  }
};
</script>
