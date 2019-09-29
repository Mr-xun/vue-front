<template>
    <div id="app">
        <ul>
            <li v-for="(item,index) in users" :key="index">{{item.name}}</li>
        </ul>
    </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import axios from 'axios'
export default {
    name: 'app',
    data() {
        return {
            users: []
        }
    },
    mounted() {
        axios.get('http://localhost:3000/api/user').then(res => {
            this.users = res.data
            console.log(res)
        })
    }
}
</script>

<style>
</style>
