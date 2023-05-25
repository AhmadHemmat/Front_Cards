<<template>
  <!-- <script src="https://unpkg.com/axios/dist/axios.min.js"></script> -->

  <div id="app">
          <v-app id="inspire">
                 <v-card
            class="mx-auto"
            
          >
            <v-container fluid>
              <v-row dense dir="rtl" class="text-center">
                <v-col
                  v-for="card in cards"
                  :key="card.title"
                  cols="3"
                >
                  <v-card
                  class="mx-4 mb-4 pa-2"
                  height="90%"
                          rounded="lg"
                  >
                    <v-img
                           class="ma-2"
                      :src="card.image"
                      gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                    height="60%"
                    >
                     
                    </v-img>
              <div class="title text-truncate">{{card.title}}</div>
              <div class="title text-truncate mt-4" style="color: teal">{{card.price * 50000}} تومان</div>
  
              
        
              <v-btn class="mt-8 mb-2" color="orange">
                خرید
              </v-btn>
                  </v-card>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
         
          </v-app>
        </div>
</template>

<script>
new Vue({
  el: "#app",
  vuetify: new Vuetify(),
  data() {
    return {
      collapseOnScroll: true,
      title: "Vue-2 Appssssssss",
      cards: null
  
    };
  },
  mounted() {
   this.getAndShowCards()
  },
  
   methods: {
    getAndShowCards() {
      axios.get('https://fakestoreapi.com/products').then((response) => {
        console.log(response.data);
        this.cards = response.data;
      })
    }
  }
});

</script>