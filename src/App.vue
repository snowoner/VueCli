<template>
  <div id="app">
    <h1>My Bookstore</h1>
    <input type="text" placeholder="Search a Book.." id="search" v-model="searchValue"/>
    <div v-for="(book,index) in books" :key="index">{{book.titulo}}</div>
    <p>Hola</p>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import MyTitle from './components/MyTitle.vue'

export default {
  name: 'app',
  data() {
    return {
      url:"https://api.myjson.com/bins/p803g",
      books:[],
      searchValue:""
    }
  },
  methods:{
    getData(){
      fetch(this.url)
      .then(data=>data.json())
      .then(data=>{
        this.books=data.books;
      })
      .catch(error => alert(error));
    },
  },
  computed: {
    printbooks(){
      if(this.searchValue){
        return this.books.filter(book=>{
          return book.titulo.includes(this.searchValue) || book.descripcion.includes(this.searchValue);
         });
      }
      else{
        return this.books;
      }
    }
  },
  created() {
    this.getData();
  },
  components: {
    // HelloWorld,
    // MyTitle
  }
}
</script>

<style>


</style>
