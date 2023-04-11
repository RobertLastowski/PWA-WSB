<!-- NOWA DZIALAJACA WEDLUG WYMAGAN GALERIA Z MODALEM -->
<template>
    <div> 
      <TopNav/>
      <GalleryComponent/>

    </div>
  </template>


<script>

import GalleryComponent from '~/components/gallery/GalleryComponent.vue';
import TopNav from '../components/nav/TopNav.vue';

export default {
  name: 'GalleryPage',
  components: { GalleryComponent , TopNav},
}
</script>

<style scoped>

</style>
