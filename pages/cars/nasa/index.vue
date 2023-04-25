<template>
    <div>
        <h1>Nasa</h1>
        <input v-model="message" placeholder="search.." />
        <button @click = find()> Search </button>
        <div class="gallery">
            <template v-for= "value in dataArr">
                <template v-for = "(link, index) in value.links">
                    <img 
                    v-if = "index == 0"
                    :data-index = "index"
                    :src = "link.href"/>
                </template>
            </template>
            <!-- <img 
            v-for="(value, index) in dataArr" 
            v-if="index == 0 " 
            :src = "value.links[0].href" 
            :key = "index"/> -->
        </div>
    </div>
</template>

<script>
import axios from "axios"



export default {
    name: "index",   

    created(){
        this.fetchData()
    },

    data(){
        return{
            dataArr: [],
            message: ""
        }
    },

    methods: {

        async fetchData(){
            await axios.get("https://images-api.nasa.gov/search?q="+this.message)
            .then(res => {
                // console.log(res)
                this.dataArr = res.data.collection.items;
            })
            .catch(error => {
                console.log(error)
            })
        },

        find(){
            this.fetchData();
        },
    }

}

</script>

<style scoped>

.gallery{
    display: flex;
    flex-wrap: wrap;
    width: 100vm;
    justify-content: center;
}

img{

width: 100px;
height: 100px;
object-fit: cover;
padding: 5px;

}

</style>