<template>
  <div class="card card-outline-secondary" style="width: 20rem;">
    <div class="card-block">
      <div class="p-3">
        <h4 class="card-title"><slot></slot></h4>
      </div>
    </div>
  </div>
</template>

<script>
  export default {

  }
</script>

<style scoped>
  .card-title{
    font-family: "Arizonia", cursive;
  }

  .card{
    cursor: pointer;
  }

  .card:hover{
    background-color: #ffe2e2;
  }
</style>