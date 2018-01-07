<template>
    <div>
        <app-header></app-header>
        <router-view></router-view>
        
    </div>
</template>

<script>
// Imports
import showBlogs from './components/showBlogs.vue';
import addBlogs from './components/addBlog.vue';
import header from './components/header.vue';
export default {
    components: {
        'show-blogs': showBlogs,
        'add-blog':addBlogs,
        'app-header':header

    },
    data () {
        return {
        }
    },
    methods: {
    }
}
</script>
<style>
body {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  margin:0;
  background: #30E8BF;  /* fallback for old browsers */
background: -webkit-linear-gradient(to right, #FF8235, #30E8BF);  /* Chrome 10-25, Safari 5.1-6 */
background: linear-gradient(to right, #FF8235, #30E8BF); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}
</style>
