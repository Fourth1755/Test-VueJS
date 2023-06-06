<template>
    <div class="search-container">
        <div class="search-box">
            <input/>
        </div>
        <div>
            
        </div>
        <div>
            <SelectBoxDrpodown :list="country"/>
        </div>
    </div>
</template>

<script>
import SelectBoxDrpodown from './SelectBoxDrpodown.vue';
export default {
    name:"SearchBox",
    components:{
        SelectBoxDrpodown
    },
    data(){
        return{
            country:["Korea","Thailand","Japan","USA","UK","Chaina","Cannada"]
        }
    }
}
</script>

<style>
    .search-container{
        display: flex;
        width: 100%;
        height: 80px;
        justify-content: space-between;
    }
    .search-box{
        display: flex;
        align-items: center;
    }
    .search-box input{
        width: 420px;
        height: 30px;
    }


</style>