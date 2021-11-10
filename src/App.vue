<template>
  <div id="app">
    <h1>QandA参考サイト</h1>
    <div v-for="post in posts" :key="post.id">
      <div>質問:{{post.question}}</div>
      <div>回答:{{post.setDate}}</div>
    </div>
  </div>
</template>

<script>
import axios from "axios"

export default {
  data() {
    return{
      posts:[]
    };   
  },
  created(){
    axios.get("http://localhost:8080/main/QuestionInfo")
    .then((response) =>{
      this.posts = response.data;
      // this.posts = response.data.documents;
    })
    }
  }

</script>


