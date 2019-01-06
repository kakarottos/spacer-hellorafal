<template>
     <div class="searchWrapper">
      <input 
        id="search" name="search" 
        placeholder="Put text" 
        :class="{dark:dark}"
        :value="value"
        @input="handleChange"
        />
  
    </div>
</template>

<script>
export default {
name: 'SearchInput',
props: {
  value: {
    type:String,
    required:true,
    },
  dark:{
    type: Boolean,
    default: false
    },
  },
methods:{
  handleChange(e){
    this.$emit('input',e.target.value)
  },
}
}
</script>
<style lang="scss" scoped>

 .searchWrapper{
    margin-top: 50px;
    display: flex;
    flex-direction: column;
    width: 300px;

      input{
        font-size: 20px;
        color:white;
        text-align: center;
        height: 30px;
        border:0;
        background: none;
        border-bottom: 1px solid white;
        transition: box-shadow 0.5s;

      }

      input:focus{
        outline:none;
        box-shadow: 0 20px 20px -10px white;
      }
      .dark{
        color : #1e3d4a;
        border-bottom-color: #1e3d4a;
        
        .dark:focus{
          box-shadow: 0 20px 20px -10px rgba(#1e3d4a, .2);
        }
      }
  }

</style>

