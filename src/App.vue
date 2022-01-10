<template>
  <div id="app">
   <Header/>
   <List v-bind:etudiantMessage="etudiants" />
   <Footer/>
   
  </div>
</template>

<script>
import Header from "./components/Header"
import Footer from "./components/Footer"
import List from './components/List'
export default {
  components: {
     Header ,
     Footer,
     List
     },
  name: 'App',
  data(){
   return {
     text:"",
     nom:"ensa",
     technologie:"vue js",
     etudiants:
     [
       {nom:"mohamed",prenom:"bing",note:8},
       {nom:"yousf",prenom:"boukir",note:17},
       {nom:"wadie",prenom:"amrouch",note:11},

     ]
   }
  },
  methods:{
    checkIfMark(){
      return false;
    },
    afficherNom(){
      alert(this.text)
    }
  },

}
</script>

<style>

</style>
