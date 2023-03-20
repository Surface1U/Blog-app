<template>
    <div id = "add-blog">
        <h2>Add a new blog</h2>
        <form>
            <label>Blog title: </label>
            <input type = "text" v-model.lazy="blog.title" required/>
            <label> Blog content</label>
            <textarea v-model.lazy="blog.content"></textarea>
            <div id = "checkboxes">
                 <label>Davil</label>
                 <input type = "checkbox" value="davil" v-model="blog.categories"/>
                 <label>David</label>
                 <input type = "checkbox" value="david" v-model="blog.categories"/>
                 <label>Dab</label>
                 <input type = "checkbox" value="dab" v-model="blog.categories"/>
                 <label>Killer</label>
                 <input type = "checkbox" value="killer" v-model="blog.categories"/>

            </div>

            <label>Author:</label>
            <select v-model="blog.author">
                <option v-for = "author in authors">{{ author }}</option>
            </select>
        </form>
        <div id = "preview">
            <h3>preview blog</h3>
            <p>Blog title: {{ blog.title }}</p>
            <p>Blog content:</p>
            <p>{{ blog.content }}</p>
            <p>Blog categories</p>
            <ul>
                <li v-for="category in blog.categories">{{ category }}</li>
            </ul>
            <p>Author: {{ blog.author }}</p>
        </div>
    </div>
  </template>


  <script>


  export default {
    data() {
      return{
        blog: {
            title: "",
            content: "",
            categories: [],
            author: ""
        },
        authors:['The Nigger', 'Nigger1', 'I am a not rasist' ]
      }
    },
    methods: {

    }
  }

  </script>


  <style>
  body {
    margin: 0;
    font-family: Arial, Helvetica, sans-serif;
  }
  </style>
