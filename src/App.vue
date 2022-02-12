<template>
    <div class="app">
        <post-form/>
        <post-list :posts="posts"/>
    </div>
</template>
<script>
import PostForm from "./components/PostForm";
import PostList from "./components/PostList";

export default {
    components: {
        PostList, PostForm
    },
    data(){
        return{
            posts:[
                {id: 1, title:'Ticket', body:'Description'},
                {id: 2, title:'Buy Ticket', body:'Description 2'},
                {id: 3, title:'Why you must to buy Ticket', body:'Description 3'},
            ],
            title: '',
            body: ''
        }
    },
    methods:{
      createPost(){
          const newPost = {
              id: Date.now(),
              title: this.title,
              body: this.body,
          }
          this.posts.push(newPost);
          this.title = '';
          this.body = '';
      },
    }
}
</script>
<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.app{
    padding: 20px;
}


</style>