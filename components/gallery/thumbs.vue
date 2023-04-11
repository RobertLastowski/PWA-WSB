<template>
    <div class="thumbs">
         <img :src="imageUrl" :alt="imageAlt" @click="setImageActive(imageId)" />
    </div>
</template>
<script>
export default {
    name: 'thumbs',
    emits: ["setActiveImage"],
    props: {
        imageId: {
            type: Number,
            required: true,
    },
        imageUrl: {
            type: String,
            required: true,
    },
        imageAlt: {
            type: String,
            required: true,
    },
},

    methods: {
        setImageActive(id) {
      this.$emit("setActiveImage", id);
        },
    },
  }
</script>

<style scoped>
.thumbs img{
    border: 0.5px solid black;
    cursor: pointer;
    max-width: 100%;
    transition: transform 0.5s ease;
}

.thumbs img:hover {
    border: 1px solid black;
    cursor: pointer;
    transition: transform 0.5s ease;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
}

.thumbs{
    display: inline-block;
    width: 150px;
    overflow: hidden;
}
</style>
