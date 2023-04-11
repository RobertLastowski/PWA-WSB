<template>
    <div class="gallery-container">
      <div class="gallery-wrapper">
        <BigImage
          :image-id="activeImageId"
          :image-url="bigImageUrl"
          :image-alt="bigImageAlt"
          @click.native="showModal"
        />
        <div class="thumbs">
          <thumbs
            v-for="image in images"
            :key="image.id"
            :image-id="image.id"
            :image-url="image.url"
            :image-alt="image.alt"
            @setActiveImage="setActiveImage"
          />
        </div>
      </div>
      <GalleryModal
        v-if="isModalShown"
        :images="images"
        :main-image-id="activeImageId"
        :main-image-url="bigImageUrl"
        :main-image-alt="bigImageAlt"
        @setActiveImage="setActiveImage"
        @closeModal="closeModal"
      />
    </div>
  </template>


<script>

import thumbs from "./thumbs.vue";
import BigImage from "./bigImage.vue";
import GalleryModal from "/components/modals/GalleryModal.vue";

export default {
  components: { thumbs, BigImage, GalleryModal },
  data() {
    return {
      isModalShown: false,
      activeImageId: 1,
      images: [
        {
          id: 1,
          url: "https://img.freepik.com/darmowe-zdjecie/happy-easter-day-wielkanocni-jajka-na-drewnianym-tle_74952-2987.jpg?size=626&ext=jpg&ga=GA1.1.40587456.1680441979",
          alt: "Description of the image 1",
        },
        {
          id: 2,
          url: "https://img.freepik.com/darmowe-zdjecie/happy-bunny-z-wielu-pisanek-na-trawie-szczesliwego-tla-dla-projektu-dekoracyjnego_90220-1229.jpg?size=626&ext=jpg&ga=GA1.1.40587456.1680441979",
          alt: "Description of the image 2",
        },
        {
          id: 3,
          url: "https://img.freepik.com/darmowe-zdjecie/zajaczek-wielkanocny-z-malowanymi-jajkami-na-niebieskiej-scianie_155003-35891.jpg?size=626&ext=jpg&ga=GA1.2.40587456.1680441979",
          alt: "Description of the image 3",
        },
        {
          id: 4,
          url: "https://img.freepik.com/darmowe-zdjecie/wesolych-swiat-wielkanocnych-pisanki-w-koszyku-na-drewnianym-rustykalnym-stole-do-dekoracji-na-wakacje_74952-2955.jpg?size=626&ext=jpg&ga=GA1.1.40587456.1680441979",
          alt: "Description of the image 4",
        },
        {
          id: 5,
          url: "https://img.freepik.com/premium-zdjecie/sliczny-krolik-wielkanocny-wewnatrz-peknietego-jajka-generative-ai_601748-44450.jpg?size=626&ext=jpg&ga=GA1.1.40587456.1680441979",
          alt: "Description of the image 5",
        },
        {
          id: 6,
          url: "https://img.freepik.com/premium-zdjecie/wielkanocny-kosz-z-wiosennymi-kwiatami-i-jajkami_136595-23075.jpg?size=626&ext=jpg&ga=GA1.1.40587456.1680441979",
          alt: "Description of the image 6",
        },
      ],
    };
  },
  computed: {
    bigImageUrl() {
      return this.images.find((image) => image.id === this.activeImageId).url;
    },
    bigImageAlt() {
      return this.images.find((image) => image.id === this.activeImageId).alt;
    },
  },
  methods: {
    setActiveImage(id) {
      this.activeImageId = id;
    },
    showModal() {
      this.isModalShown = true;
    },
    closeModal() {
      this.isModalShown = false;
    },
  },
};
</script>

<style>
.gallery-container {
  margin: 0;
  padding: 0;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: flex-start;
}

.gallery-wrapper {
  margin: 0;
  padding: 0;
  width: 50%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  row-gap: 1rem;
}

.thumbs {
  margin: 0;
  padding: 0;
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: flex-start;
  gap: 0.5rem;
}
</style>
