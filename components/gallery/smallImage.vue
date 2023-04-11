<template>
    <div class="gallery">
         <img class="img" :src="image" />
    </div>
   
</template>
<script>
export default {
    name: 'SmallImage',
    props: {
        image: {
            type: String,
            default: () => 'Pusty string'
        }
    },
    data() {
        return {
            
        }
    },

    created (){
        console.log(this.image)
    }
  }
</script>
<style scoped>
.img{
    width: 150px;
    height: 100px;
    margin-top: 5px;
    margin-right: 5px;
    border: solid black;
}
</style>
