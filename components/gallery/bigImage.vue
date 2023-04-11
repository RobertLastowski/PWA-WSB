<template>
    <div class="BigImg">
        <img :src="imageUrl" :alt="imageAlt" />
    </div>
   
</template>
<script>
export default {
  name: "BigImage",
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
};
</script>
<style scoped>
.BigImg {
  overflow: hidden;
}
.BigImg img {
  width: 100%;
  transition: transform 1s ease;
}

.BigImg img:hover {
  transform: scale(1.1);
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  cursor: pointer;
}
</style>
