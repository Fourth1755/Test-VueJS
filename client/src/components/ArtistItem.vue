<template>
  <div class="container-item">
        <div class="front-item">
           <h3>1</h3>
        </div>
        <div>
             <h2>{{ data }}</h2>
        </div>
  </div>
</template>

<script>
export default {
    name: "ArtistItem",
    props:["data"]
}
</script>

<style scoped>
    .container-item{
        height: 180px;
        display: flex;
        background-color: #272727;
    }
    .front-item{
        display: flex;
        flex-direction: column-reverse;
        padding: 0px 30px 10px 30px;
        border-right-style: solid;
        border-width: 1px;
    }
    .front-item h3{
        color: #F37832;
    }
</style>