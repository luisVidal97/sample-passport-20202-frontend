<template>
    <v-container>
      <br>
      <h1>Categorias</h1>
      <br>
      <v-container grid-list-md fluid>
        <v-row>
          <v-col cols="4" v-for="(item,index) in categories" :key="index">
            

                <v-card
            class="mx-auto"
            max-width="400"
          >
              <v-img
                class="white--text align-end"
                height="200px"
                :src="item.urlImage"
              >
               
              </v-img>

            <v-card-title>{{item.name}}</v-card-title>

            <v-card-text class="text--primary">
              <div>{{item.description}}</div>
            </v-card-text>

            <v-card-actions>
              <v-btn
                color="orange"
                text
                @click="goProductsView(item.id)"
              >
                Ver productos
              </v-btn>
            </v-card-actions>
          </v-card>
          </v-col>
        </v-row>

      </v-container>
    </v-container>
</template>

<script>

export default {
  name: 'Home',
  data(){
    return{
      categories: []
    }
  },
  methods:{
    getCaterogies(){
      this.axios.get("http://localhost:1337/categories").then(
        response =>{
          this.categories = response["data"];
          console.log(this.categories)
        }
      )
    },
    goProductsView(id){
      this.$router.push("/products/"+id);
    }
  },
  created(){
      this. getCaterogies();
  },
}
</script>
