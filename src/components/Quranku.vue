<template>
<div>
   <md-toolbar>
    <h1 class="md-title" style="flex: 1">{{title}}</h1>
    <md-button class="md-icon-button">
      <md-icon>more_vert</md-icon>
    </md-button>
    </md-toolbar>
    <daftarsurah></daftarsurah>
    <md-bottom-bar>
    <md-bottom-bar-item md-icon="home" md-active>Home</md-bottom-bar-item>
    <md-bottom-bar-item md-icon="search" >Search</md-bottom-bar-item>
  
    </md-bottom-bar>
</div>
</template>

<script>
  import MugenScroll from 'vue-mugen-scroll'
  import daftarsurah from '../components/DaftarSurah'

  import axios from 'axios';
   export default {
       name : 'quranku',
       data() {
           return{
                title : 'Welcome to MyQuran',
                

          
          }
         },
        components: {
         
             daftarsurah
        }

       

   }   
</script>
<style scoped>
</style>