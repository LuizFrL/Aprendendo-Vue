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
        <b-icon font-scale="1" class="p-10" icon="pen" />Adicionar
      </b-button>
      <p class="col-sm-6"></p>
      <b-button class="col-sm-3 p-2" pill @click="clearValue" variant="outline-danger">
        <b-icon font-scale="1" icon="trash-fill" />Limpar
      </b-button>
    </div>
    <p>Value: {{ tasks }}</p>
    <p>Tarefas: {{ allTasks }}</p>

    <ListaCoisasParaFazer v-for="Task in allTasks" :key="Task.id" :tarefa="Task" class="p-1" />
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
          id: String(Date.now() - i),
          tarefa: String(task),
          checked: false
        });
      });
      this.clearValue();
    }
  }
};
</script>

<style scoped>
.slide-fade-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active em versões anteriores a 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}
</style>