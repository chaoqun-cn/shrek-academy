<template>
  <div class="container">
    <video-player class="video-player vjs-custom-skin"
        ref="videoPlayer"
        :playsinline="true"
        :options="playerOptions"
        @play="onPlayerPlay($event)"
        @pause="onPlayerPause($event)"
    ></video-player>
  </div>
</template>

<script>
import { videoPlayer } from 'vue-video-player'

import 'video.js/dist/video-js.css'
import 'vue-video-player/src/custom-theme.css'

export default {
    name: 'VuePlayer',
    data () {
        return {
            playerOptions: {
                // videojs options
                muted: true,
                language: 'en',
                playbackRates: [0.7, 1.0, 1.5, 2.0, 2.5, 3.0],
                sources: [{
                    type: "video/mp4",
                    src: "https://jxjjxy-my.sharepoint.com/personal/chaoqun_t_odmail_cn/Documents/20190818_162957.mp4"
                }],
                aspectRatio: '16:9', 
                poster: "../../assets/logo.png",
                // controlBar: {
                //   timeDivider: true,
                //   durationDisplay: true,
                //   remainingTimeDisplay: false,
                //   fullscreenToggle: true //全屏按钮
                //  }
            }
        }
    },
    components: {
    videoPlayer
  },
  methods: {
    onPlayerPlay(player) {
      console.log(player);
    },
    onPlayerPause(player){
      console.log(player);
    },
  }
}
</script>

<style>
  .container {
    width: 1200px;
  }

  .video-js .vjs-big-play-button {
	  width: 72px;
	  height: 72px;
	  border-radius: 100%;
	  z-index: 100;
	  background-color: #ffffff;
	  border: solid 1px #979797;
	}
</style>
