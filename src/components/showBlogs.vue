<template>
    <div v-theme:column = "'narrow'" id = "show-blogs">
        <h1>All Blog Articles</h1>
        <input type="text" v-model="search" placeholder="search blogs"/>
        <div v-for="blog in filteredBlogs" class = "single-blog">
            <h2 v-rainbow>{{ blog.title | to-uppercase }}</h2>
            <article>{{ blog.body | snippet }}</article>
        </div>
    </div>
  </template>


  <script>


  export default {


    data() {
      return{
        blogs: [],
        search:'abc'
      }
    },
    methods: {

    },
    created() {
        this.$http.get('https://jsonplaceholder.typicode.com/posts').then(function(data){
            console.log(data);
           this.blogs = data.body.slice(0,10);
        })
    },

    computed: {
        filteredBlogs: function(){
            return this.blogs.filter((blog) => {
                return blog.title.match(this.search);
            })
        }
    }
  }

  </script>


  <style>
    #show-blogs{
        max-width: 800px;
        margin: 0 auto;
    }

    .single-blog{
        padding: 20px;
        margin: 20px 0;
        box-sizing: border-box;
        background: #eee;
    }

  </style>
