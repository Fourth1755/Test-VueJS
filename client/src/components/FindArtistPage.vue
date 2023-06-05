<template>
    <div class="container">
        <div class="content-container">
            <h1>Find your artist</h1>
            <SearchBox/>
            <div v-for="(item,index) in artist" :key="index">
                <ArtistItem data="bts"/>
                <p>{{ item.name }}</p>
            </div>
        </div>
        
    </div>
</template>

<script>
import ArtistItem from './ArtistItem.vue';
import SearchBox from './SearchBox.vue';
export default {
    name: "FindArtistPage",
    props: {
        msg: String,
    },
    components:{
        ArtistItem,
        SearchBox,
    },
    data(){
        return {
            artist:[
                {name:"BTS",country:"korea"},
                {name:"BTS",country:"korea"},
                {name:"BTS",country:"korea"},
                {name:"BTS",country:"korea"},
                {name:"BTS",country:"korea"},
                {name:"BTS",country:"korea"}
            ]
        }
    }
}
</script>

<style scoped>
    .container{
        width: 100%;
    }
    .content-container{
        width: 60%;
        margin: auto;
    }
</style>