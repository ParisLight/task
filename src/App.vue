<template>
  <div class="container">
    <Form 
      style="margin-bottom: 42px; margin-top: 52px;"
      @search="search"
    />
    <ListUsers 
      :users="list"
    />
  </div>
</template>

<script>
import ListUsers from './components/ListUsers.vue';
import Form from './components/Form.vue';

export default {
    components: { ListUsers, Form, },

  data() {
    return {
      list: [],
    }
  },

  methods:{
    async search(query){
      try{
        const data = await fetch(`http://127.0.0.1:3000?term=${query}`)
        this.list = await data.json();
      }
      catch(e){
        console.log(e);
      }
    },
  },
  
  async created(){
    try{
      const array = await fetch('http://127.0.0.1:3000');
      this.list = await array.json()
    }
    catch(e){
      console.log(e);
    }
  }
}
</script>

<style lang="scss">
*{
    box-sizing: border-box;
    padding: 0;
    margin: 0;
    font-family: 'Arial';
    font-size: 20px;
  }
  .container{
    max-width: 1160px;
    padding: 0 20px;
    margin: 0 auto;
  }
</style>