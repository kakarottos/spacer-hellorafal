<template>
     <div class="searchWrapper">
      <input 
        id="search" name="search" 
        v-model="searchValue"
        placeholder="Put text" 
        @input="handleInput"
        />
  
    </div>
</template>

<script>
export default {
name: 'SearchInput',
}
</script>
<style lang="scss" scoped>

 .searchWrapper{
    margin-top: 50px;
    display: flex;
    flex-direction: column;
    width: 300px;

      input{
        text-align: center;
        height: 30px;
        border:0;
        background: none;
        border-bottom: 1px solid black;
      }
  }

</style>

