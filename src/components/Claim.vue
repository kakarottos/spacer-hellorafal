<template>
  <div class="claimWrapper">
    <h1 class="Claim">SPACER</h1>
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
    color:white;
    }

.Claim{
    margin:0;
    font-size: 50px;
    @media (min-width: 768px) {
        font-size: 80px;
    }

}

.subclaim{
    font-size: 13px;
    margin:20px 0 0 0;
    font-weight: 400;
    @media (min-width: 768px) {
        font-size: 17px;
        letter-spacing: 1px;
        line-height: 1px;
        width: 600px;
    }

}
</style>
