<template>     
  <div  class="wrap" 
    style="height:  80vh;  overflow: auto;">
 
   <md-list class="list" v-if="daftarSurah && daftarSurah.length">
   <div >
    <md-list-item   layout="row" layout-align="center center" v-for="surah of daftarSurah">
      <span center flex >{{surah.englishName}} ({{surah.name}})</span> 
     <md-divider class="md-inset"></md-divider>
      </md-list-item>
     </div>

  </md-list>
   
  <mugen-scroll :handler="fetchData" :should-handle="!loading" scroll-container="wrap">
   
    </mugen-scroll>




</div>
</template> 

<script>
  import MugenScroll from 'vue-mugen-scroll'

  import axios from 'axios';
   export default {
       name : 'daftarsurah',
       data() {
           return{
              
                daftarSurah : [
                   {
                       number: '',
                       name:'',
                       englishName:'',
                       englishNameTranslation:'',
                       numberOfAyahs:'',
                       revelationType:''
                   }  
                ] ,
                loading : false,
                hover : false


          
          }
         },
         methods: {

            mouseOver(){
                 this.hover = !this.hover;   
            } ,
             
           fetchData() {
          this.loading = true
            axios.get('http://api.alquran.cloud/surah')
          .then(response => {
              // JSON responses are automatically parsed.
            this.daftarSurah= response.data.data
            })
         .catch(e => {
                console.log('error')
           this.loading = false       
        })
         
      },
    }, 
        components: {
             MugenScroll,
        }
   }      


</script>    
<style scoped>
.wrap {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
 
}

span {
display:table;
margin:0 auto;
}

</style>