
<template>
<div>
<Nav/>

<ApiGet/> 
<br>
<ApiPost/>
</div>
</template>

<script>
import Nav from './Nav';
import ApiGet from './ApiGet';
import ApiPost from './ApiPost';
  export default {
    
    name: 'app',
    components:{Nav,ApiGet,ApiPost},

    data(){
      return {
        
      }
    },
    methods: {
     
    },
  }
  
</script>
    
<style>
  @import 'https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css';
  
</style>
