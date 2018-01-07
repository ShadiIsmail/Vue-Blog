<template>
    <div id="show-blogs">
        <h1>All Blog Articles</h1>
        <input type="text" v-model="search" placeholder="Search Blogs">
        <div v-for="blog in filteredBlogs" class="single-blog">
   <router-link v-bind:to="/blog/ + blog.id"><h2>{{ blog.title | to-uppercase }}</h2></router-link>
            <article>{{ blog.body}}</article>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            blogs: [],
            search:""
        }
    },
    methods: {
    },

    computed: {
        filteredBlogs: function(){
            return this.blogs.filter((blog)=>{
             return blog.title.match(this.search);
            });    
        }
},

    created() {
        this.$http.get('http://jsonplaceholder.typicode.com/posts').then(function(data){
            this.blogs = data.body.slice(0,10);
        });
    }
}
</script>

<style>
#show-blogs{
    max-width: 800px;
    margin: 0px auto;
}
.single-blog{
    padding: 20px;
    margin: 20px 0;
    box-sizing: border-box;
    background:lightgrey;
}
</style>