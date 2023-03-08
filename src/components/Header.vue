<!-- eslint-disable vue/multi-word-component-names -->
<template>
<header>
    <h1>{{ title }}</h1>
    <Button v-show="homePage"
    @btn-click="$emit ('toggle-add-task')"
    :text="showAddTask ? 'Close' : 'Add Task'"
     :color="showAddTask ? 'pink' : 'violet'"/>
    
</header>
</template>


<script>
import Button from './Button'

export default{
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Header',
    props:{
        title: String,
    },
    components: {
        Button,
    },
    computed: {
        homePage(){
            if(this.$router.path==='/'){
                return true

            } else{
                return false
            }
        }
    }
}
</script>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}
</style>