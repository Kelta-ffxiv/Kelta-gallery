<template>
  <div class="home">
    <VideoHeadline />

    <div class="gallery-section visit-gallery">
      Scroll to discover the gallery
      <Icon icon="bi:arrow-down-short"></Icon>
    </div>
    <!-- <YoutubePlayer /> -->
  </div>
</template>

<script>
// @ is an alias to /src
import YoutubePlayer from "@/components/YoutubePlayer.vue";
import VideoHeadline from "@/components/VideoHeadline.vue";
import { Icon } from "@iconify/vue";

export default {
  name: "HomeView",
  components: {
    // YoutubePlayer,
    VideoHeadline,
    Icon,
  },
};
</script>

<style lang="scss" scoped>
.gallery-section {
  display: inline-block;
  width: 100%;
}
.visit-gallery {
  height: 15vh;
  text-align: center;
  font-size: 50px;
  background: black;
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;

  svg {
    display: inline-block;
    /* margin: auto; */
    width: 100%;
    animation: 0.5s ease-in-out 1s infinite alternate bounce;

    @keyframes bounce {
      from {
        /* pushes the sun down past the viewport */
        transform: translateY(0vh);
      }
      to {
        /* returns the sun to its default position */
        transform: translateY(0.5vh);
      }
    }
  }
}
</style>
