<template>
  <div class="wrapper">
    <Claim />
    <SearchInput />
    <ul>
      <li v-for="item in results" :key="item.data[0].nasa_id">
        <p>{{item.data[0].description}}</p>
      </li>
    </ul>
    </div>
</template>

<script>

import axios from 'axios';
import debounce from 'lodash.debounce'
import Claim from '@/components/Claim.vue'
import SearchInput from '@/components/SearchInput.vue'

const API = 'https://images-api.nasa.gov/search';

export default {
  name: 'Search',
  components: {
    Claim,
    SearchInput,
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


<style lang="scss" scoped>

  .wrapper{
    display: flex;
    flex-direction: column;
    align-items: center;
    margin:0;
    padding:30px;
    height: 100vh;
    width: 100%;
    background-image: url('../assets/heroimage.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: 80% 0%;
  }

</style>
