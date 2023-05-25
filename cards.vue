<<template>
    <div id="app">
        <div class="container" id="phones-cards"  >
          <div class="card" v-for="todo in todos" :key="todo.id" >
            <img :src="todo.image" alt="sam">
            <h1>{{ todo.title }}</h1>
            <p class="price">{{ todo.price}} تومان</p>
            <p>{{ todo.category }}</p>
            <button>افزودن به سبد خرید</button>
          </div>
       </div>
    </div>
</template>

<script>
new Vue({
  el: "#app",
  data() {
    return {
      id: 0,
      todos: [
        { id: this.id++, text: 'Learn HTML' },
        { id: this.id++, text: 'Learn JavaScript' },
        { id: this.id++, text: 'Learn Vue' },
        { id: this.id++, text: 'Learn Vuetify' }
      ]
    }
  },
  mounted() {
   this.getAndShowCards()
  },
  methods: {
    getAndShowCards() {
      axios.get('https://fakestoreapi.com/products').then((response) => {
        console.log(response.data);
        this.todos = response.data;
      })
    }
  }
});
</script>

<style>
.container {
    text-align: center;
    direction: rtl;

}

.card {
  box-shadow: 2px 2px 2px 2px rgba(0, 0, 0, 0.356);
  display: inline-block;
  width: 15%;
  max-height: 400px;
  padding: 2%;
  margin: 2%;
}

img {
    width: 50%;
    height: 100px;
}

h1 {
    font-size: 15px;
    height: 50px;
}

p {
    height: 50px;
}

.price {
    color: teal;
}

button {
    width: 80%;
    height: 50px;
    background-color: cornflowerblue;
    color: black;
    margin: 20px;
    cursor: pointer;
}
</style>