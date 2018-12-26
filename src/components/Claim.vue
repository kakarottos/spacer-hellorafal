<template>
  <div class="claimWrapper">
    <h1 class="Claim">Spacer</h1>
    <p class="subclaim">
        begin your journey through our amazing galaxy.
    </p>
    <p class="subclaim">
        Type anything space related to start
    </p>

  </div>
</template>

<script>
export default {
  name: 'Claim',
};
</script>

<style lang="scss" scoped>

.claimWrapper{
    display: flex;
    flex-direction: column;
    justify-content: center;  
    align-items: center;
    text-align: center;
    }

.Claim{
    margin:0;
    font-size: 50px;
}

.subclaim{
    font-size: 13px;
    margin:20px 0 0 0 ;
}
</style>
