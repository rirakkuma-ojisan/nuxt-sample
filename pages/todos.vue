<template>
    <div style="padding-left:50px;">
        <ul>
            <li v-for="todo in todos">
                <input type="checkbox" @change="toggle(todo)">
                <span :class="{done: todo.done}">{{todo.text}}</span>
            </li>
        </ul>
        <input 
            placeholder="add task"
            @keyup.enter="addTodo"
        />
    </div>
</template>

<script>
import {mapMutations} from 'vuex'
export default {
    computed: {
        todos () {
            return this.$store.state.todos.list
        }
    },
    methods: {
        addTodo(e) {
            this.$store.commit('todos/add', e.target.value)
        },
        ...mapMutations({
            toggle: 'todos/toggle'
        }) 
    }
}
</script>

<style scoped>
.done {
    text-decoration: line-through;
}
</style>