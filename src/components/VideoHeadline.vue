<template>
  <div class="videoheadline-wrapper">
    <video class="videoheadline-video" ref="video" autoplay :muted="muted" loop>
      <source
        src="https://drive.google.com/uc?export=download&id=1uE7slCw5ESIGHC98L-i3qL7zEPZFF7lR"
        type="video/mp4"
      />
    </video>

    <div class="videoheadline-content">
      <div class="videoheadline-socials-wrapper">
        <div class="videoheadline-socials">
          <a href="https://www.youtube.com/@keltaffxiv">
            <Icon icon="bi:youtube" class="youtube-icon" />
          </a>
          <a href="https://www.instagram.com/kelta_ffxiv/">
            <Icon icon="bi:instagram" class="insta-icon" />
          </a>
          <a href="https://twitter.com/home">
            <Icon icon="bi:twitter" class="twitter-icon" />
          </a>
        </div>
      </div>
    </div>

    <button class="videoheadline-mute" @click="unmute">
      <Icon icon="bi:volume-mute" v-if="muted"></Icon
      ><Icon icon="bi:volume-up" v-if="!muted"></Icon>
    </button>
  </div>
</template>

<script>
import { Icon } from "@iconify/vue";

export default {
  components: { Icon },

  data: () => ({
    muted: true,
    socials: [{ message: "Foo" }, { message: "Bar" }, { message: "Bar" }],
  }),
  mounted() {},
  methods: {
    unmute() {
      this.muted = !this.muted;
    },
  },
};
</script>
<style scoped lang="scss">
.videoheadline-wrapper {
  position: relative;
  height: auto;
  display: inline-block;
  width: 100%;
  overflow: hidden;
  height: 85vh;
}
.videoheadline-video {
    display: flex;
    top: -25%;
    left: 50%;
    top: 50%;
    transform: translate(-50%,-50%);
    position: absolute;
}

.videoheadline-mute {
  position: fixed;
  bottom: 20px;
  right: 20px;
  z-index: 99;
  padding: 5px;
  cursor: pointer;
  font-size: 0;

  svg {
    font-size: 50px;
  }
}

.videoheadline-content {
  top: 0;
  left: 0;
  position: relative;
  right: 0;
  bottom: 0px;
  z-index: 2;
  width: 100%;
  height: 100%;
}

.videoheadline-socials-wrapper {
  bottom: 13.5%;
  position: absolute;
  width: 100%;
  display: block;
  top: auto;
}
.videoheadline-socials {
  background: black;
  display: inline-block;

  svg {
    font-size: 100px;
    color: white;
    padding: 20px;
    border-radius: 3px;
    cursor: pointer;

    &.youtube-icon:hover {
      background-color: #ff0000;
    }
    &.insta-icon:hover {
      background: radial-gradient(
        circle at 30% 107%,
        #fdf497 0%,
        #fdf497 5%,
        #fd5949 45%,
        #d6249f 60%,
        #285aeb 90%
      );
    }
    &.twitter-icon:hover {
      background-color: #1da1f2;
    }
  }
}
</style>
