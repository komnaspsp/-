<template>
<div class="app">
  <form @submit.prevent>
    <h4>Создание поста</h4>
       <input v-bind:value="title" @input="title = $event.target.value" class="input" type="text" placeholder="Название">
       <input v-bind:value="body" @input="body= $event.target.value" class="input" type="text" placeholder="Описание">
       <button class="btn" @click="createPost">Создать</button>
   </form>
  </div>
<div>
     <div class="post" v-for="(el,post) in posts" :key="post">
       <div><strong> Название:</strong>{{el.title}}</div>
   <div><strong> Описание:</strong>{{el.body}}</div>
  </div>
</div>
</template>
  


<script>
/* eslint-disable */
export default{
  data(){
    return{
      posts:[
        {id: 1, title: 'Javacript1', body: 'Описание Поста'},
        {id: 2, title: 'Javacript2', body: 'Описание Поста 2'},
        {id: 3, title: 'Javacript3', body: 'Описание Поста 3'},
        {id: 4, title: 'Javacript4', body: 'Описание Поста 4'},
      ],
      title: '',
      body: '',

    }
  },
  methods:{
    createPost(){
    const newPost = {
    id: Date.now(),
    title: this.title,
    body: this.body
 }
 this.posts.push(newPost)
    },
   
  }
}
</script>
  


<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}
.post{
    padding:15px;
    border:2px solid yellow;
    margin-top: 15px
}
.app{
    padding:20px
}
form{
    display:flex;
    flex-direction:column;
}
.input{
width:100%;
border:1px solid yellow;
padding: 10px 15px;
 margin-top: 15px
}
.btn{
    matgin-top:15px;
    align-self: flex-end;
    background: DarkRed;
    color: white;
    padding: 10px 15px;
    border: 1px solid yellow;

}

</style>

