<template>
  <div>
    <div v-for="todo in todos" v-bind:key="todo.id">
     {{todo.title}}
    </div>
    <div>
      <input v-model="newStudent.nom" placeholder="ecrire le nom" />
      <input v-model="newStudent.prenom" placeholder="ecrire le prenom" />
      <button v-on:click="ajouterEtudiant">ajouter</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["etudiantMessage"],
  components: {},
  mounted(){
    this.getTodos();
  },
  data() {
    return {
      newStudent: {
        nom: "",
        prenom: "",
      },
      todos:[]
    };
  },
  methods: {
    ajouterEtudiant() {
      this.etudiants.push(this.newStudent);
      this.newStudent.nom="";
      this.newStudent.prenom="";
    },
    getTodos(){
        fetch("https://jsonplaceholder.typicode.com/todos").then(res=>res.json()).then((data)=>{
            this.todos=data;
        })
    }
  },
};
</script>

<style>
</style>