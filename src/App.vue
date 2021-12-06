<template>
  <v-app>
    <v-flex xs12 sm6 offset-sm3>
      <v-card>
        <v-card-title primary-title class="title">
          <div>
            <h3 class="mat-h2 mb-0">Todo List</h3>
          </div>
        </v-card-title>
        <v-card-text>
          <Search>  </Search>
          <TodoItem v-for="(todo, index) in todos"
                    :key="index"
                    :todo="todo">
          </TodoItem>
          <InputField ref="inputFeild"></InputField>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="success" @click="addTodo">Save Item</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-app>
</template>

<script>
import TodoItem from './components/TodoItem'
import InputField from './components/InputField'
import Search from './components/Search'

export default {
  name: 'App',
  components: {
    TodoItem,
    InputField,
    Search
  },
  data () {
    return {
    }
  },
  computed: {
    todos () {
        //console.log(this.$store.state.search);
  return this.$store.state.todos.filter(item => {
  return this.$store.state.search.toString().toLowerCase().split(' ').every(v => item.title.toLowerCase().includes(v))})
      
      
    }
  },
  methods: {
    addTodo () {
      this.$refs.inputFeild.addTodo()
    }
  }
}
</script>

<style>
  .title {
    display: flex;
    justify-content: center;
  }
</style>
