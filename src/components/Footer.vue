<template>
  <div class="footer flex">
      <span class="first">SEE WHAT'S NEXT.</span>
      <span class="second">Watch anywhere. Cancel anytime.</span>
      <span class="filler"></span>
      <span class="third"><a href="#">JOIN FREE FOR A MONTH</a></span>
  </div>
</template>

<script>
export default {
    name: "Footer",
}
</script>

<style lang="scss" scoped>
@import "../styles/general.scss"; 
@import "../styles/vars.scss";
@import "../styles/utilities.scss";

.footer {
    height: 80px;
    padding: 1rem;
    background-color: $deepblue;
    justify-content: flex-start;
    align-items: center;
   .first {
        font-size: 1.5rem;
   }
    .second {
       padding: 1rem;
       font-size: 1.2rem ;
   }
   .third {
       margin-right: 8rem;
       padding: 0.7rem 2rem;
       background-color: $purple-1;
   }
}

</style>