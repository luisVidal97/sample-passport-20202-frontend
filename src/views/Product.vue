<template>
  <v-container>
      <br>
      <h1> <small> Productos de la categoría</small> {{category}}</h1>
      <br>
        <v-row>
          <v-col cols="4" v-for="(item,index) in products" :key="index">
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
            <br>
             <v-card-text class="text--primary">
              <h1>${{item.price}}</h1>
            </v-card-text>

            <v-card-actions>
              <v-btn
                color="orange"
                text
               
              >
                Ver producto
              </v-btn>
            </v-card-actions>
          </v-card>

          </v-col>
        </v-row>
  </v-container>
</template>

<script>
export default {
    name: 'Product',
    data(){
        return{
            category: '',
            products: []
        }
    },
    methods:{
        getCategoryWithProducts(){
            this.axios.get("http://localhost:1337/categories/"+this.$route.params.id).then( response =>{
                console.log(response);
                this.category = response.data.name;
                this.products =response.data.products;
            })
        }
    },
    created(){
        this.getCategoryWithProducts();
    }
}
</script>

<style>

</style>