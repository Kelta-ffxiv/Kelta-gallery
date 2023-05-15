<template>
  <div class="gallery-container">
    <div class="gallery-offsetter" :style="{width: images.length * 355 / 2 + 177.5 + 'px'}">
    <div class="spacer"/> 
    <div
      class="image"
      v-for="image, imageIndex in images"
      :key="imageIndex"
      @click="openImage(imageIndex)"
      :style="{ backgroundImage: 'url(' + image.thumbnailUrl + ')', ...image.addStyle}"
    ></div>
    </div>
  </div>
</template>

<script>
import ImageViewer from 'awesome-image-viewer'  
  export default {
    data() {
      return {
        images: [
         {
            mainUrl: 'https://pbs.twimg.com/media/FlP5FODXkAgDCY9?format=jpg&name=large',
            thumbnailUrl: 'https://pbs.twimg.com/media/FlP5FODXkAgDCY9?format=jpg&name=large',
            description: 'Dancing',
            addStyle: { 'background-position': '33% center'},
          },
          {
            mainUrl: 'https://pbs.twimg.com/media/FqJrz65WACMKgfO?format=jpg&name=large',
            thumbnailUrl: 'https://pbs.twimg.com/media/FqJrz65WACMKgfO?format=jpg&name=large',
            description: 'Bamboo',
          },
          {
            mainUrl: 'https://pbs.twimg.com/media/FrDANB0WYAAjf4d?format=jpg&name=large',
            thumbnailUrl: 'https://pbs.twimg.com/media/FrDANB0WYAAjf4d?format=jpg&name=large',
            description: 'Bamboo',
          },
          {
            mainUrl: 'https://pbs.twimg.com/media/FhTWG50WABcjdhU?format=jpg&name=large',
            thumbnailUrl: 'https://pbs.twimg.com/media/FhTWG50WABcjdhU?format=jpg&name=large',
            description: 'Bamboo',
          },
          {
            mainUrl: 'https://pbs.twimg.com/media/FgAqQZNX0AA21E-?format=jpg&name=large',
            thumbnailUrl: 'https://pbs.twimg.com/media/FgAqQZNX0AA21E-?format=jpg&name=large',
            description: 'Bamboo',
          },
          {
            mainUrl: 'https://pbs.twimg.com/media/FfYFgoWXEAofJrj?format=jpg&name=large',
            thumbnailUrl: 'https://pbs.twimg.com/media/FfYFgoWXEAofJrj?format=jpg&name=large',
            description: 'annly',
          },
          {
            mainUrl: 'https://drive.google.com/uc?id=1A17pVkmsZ5dvPa7nuNlz5XcvWQYmAGW5',
            thumbnailUrl: 'https://drive.google.com/uc?id=1A17pVkmsZ5dvPa7nuNlz5XcvWQYmAGW5',
            description: 'god emperor'
          }
        ],
        selectedImage: null
      };
    },


    methods: {
      openImage(selectedImage) {
        this.selectedImage = selectedImage;

         new ImageViewer({
          images: this.images,
          currentSelected: this.selectedImage,
        });
      }
    }

  }
</script>
<style scoped>

  .gallery-container {
    width: 100%;
    height: 400px;
    overflow: auto;
    background: black;
  scrollbar-width: none;
            overflow-x: auto;
            
  }

  .gallery-container::-webkit-scrollbar {
    height: 0px;
  }

  .gallery-offsetter {
    height: 400px;
    text-align: left;
    position: relative;
    
  }

  .spacer {
    height: 200px;
    display: inline-block;
    position: relative;
    width: 177.5px;
    flex-grow: 1;
  }

  .image {  
    height: 200px;
    position: relative;
    display: inline-block;
    width: 355px;
    cursor: pointer;
    box-sizing: border-box;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center center; 
  }
</style>