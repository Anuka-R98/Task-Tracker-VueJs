<template>
    <header>
        <h1>{{ title }}</h1>
        <Button v-show="homePage" @btn-click="$emit('toggle-add-task')" :text="showAddTask ? 'Close' : 'Add Task '" 
        :color="showAddTask ? 'red' : 'green'"/>
    </header>
</template>

<script>
import Button from './Button'

export default {
    name: 'Header',
    props: {
        title: String,
        showAddTask: Boolean,
    },
    components: {
        Button,
    },
    // computed property is used for reactivity ( to combine things )
    computed: {
        homePage() {
            if(this.$route.path === '/') {
                return true
            } else {
                return false
            }
        }
    }
}
</script>

//scope = only for this specifi component
<style>
    header {
         display: flex;
         justify-content: space-between;
         align-items: center;
         margin-bottom: 20px;
    }
</style>