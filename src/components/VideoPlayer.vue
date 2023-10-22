<template> 
    <div @dblclick="toggleFullScreen" class="video-preview">
        <video ref="videoPlayer" controls>
          <source src="../assets/phygitalCouture.mp4" type="video/mp4">
          Il tuo browser non supporta la riproduzione video.
        </video>
    </div>
</template>
  
<script>
export default {
    data() {
      return {
        isFullScreen: false,
      };
    },
    methods: {
      toggleFullScreen() {
            const videoPlayer = this.$refs.videoPlayer;
  
            if (!this.isFullScreen) {
                if (videoPlayer.requestFullscreen) {
                    videoPlayer.requestFullscreen();
                } else if (videoPlayer.mozRequestFullScreen) {
                    videoPlayer.mozRequestFullScreen();
                } else if (videoPlayer.webkitRequestFullscreen) {
                    videoPlayer.webkitRequestFullscreen();
                } else if (videoPlayer.msRequestFullscreen) {
                    videoPlayer.msRequestFullscreen();
                }
                this.isFullScreen = true;
            }
        },
    },
};
</script>
  
<style scoped>
.video-preview {
    cursor: pointer;
    width: 100%; /* Imposta le dimensioni della preview come desideri */
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}
  
.video-preview video {
    max-width: 100%;
    max-height: 100%;
}
</style>
  
  