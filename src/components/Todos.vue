<template>
  <div>
    <h3>Todos</h3>
    <div class="todos">
      <div v-for="todo in allTodos" :key="todo.id" class="todo">
        {{ todo.title }}
        <button @click="deleteTodo(todo.id)">
          Borrar
        </button> 
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex';

export default {
  name: 'Todos',
  created() {
    this.fetchTodos();
  },
  computed: mapGetters(['allTodos']),
  methods: {
    ...mapActions(['fetchTodos', 'deleteTodo'])
  }
}
</script>

<style scoped>


</style>