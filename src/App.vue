<template>
  <div class="wrapper">
  <HeroImage />
  <Claim />
  <SearchInput v-model="searchValue" @input="handleInput"/>
  <div>
  <ul>
    <li v-for="item in results" :key="item.data[0].nasa_id">
      <p>{{item.data[0].description}}</p>
    </li>
  </ul>
  </div>
  </div>
</template>

<script>

import axios from 'axios';
import debounce from 'lodash.debounce'
import Claim from '@/components/Claim.vue'
import SearchInput from '@/components/SearchInput.vue'
import HeroImage from '@/components/HeroImage.vue'

const API = 'https://images-api.nasa.gov/search';

export default {
  name: 'App',
  components: {
    Claim,
    SearchInput,
    HeroImage,
  },
  data(){
    return{
      searchValue:'',
      results:[],
    };
  },
  methods: {
    handleInput:debounce(function(){
        axios.get(`${API}?q=${this.searchValue}&media_type=image`)
      .then((response) =>{
        this.results=response.data.collection.items;
      })
      .catch((error) =>{
        console.log(error);
      });
  },600),  
},
};

</script>

<style lang="scss" >

*{
  box-sizing: border-box;
}

body{
  margin:0;
  padding: 0;
  font-family: Arial, Helvetica, sans-serif;
}

  .wrapper{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin:0;
    padding:20px;
    height: 100vh;
    min-height: 100vh;
    width: 100%;
    color:white;
  
  }
</style>
