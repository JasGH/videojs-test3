<template>
  <div id="app">
    <video-player :options="videoOptions"/>
  </div>
</template>

<script>
import VideoPlayer from "@/components/VideoPlayer.vue";

export default {
  name: "VideoExample",
  components: {
    VideoPlayer
  },
  data() {
    return {
      videoOptions: {
        autoplay: true,
        controls: true,
        controlBar: {
          // currentTimeDisplay: true,
          TimeDivider: true,
          children: [
            'playToggle',
            'CurrentTimeDisplay',
            'progressControl',
            'TimeDivider',
            'RemainingTimeDisplay',
            'volumePanel',
            'PlaybackRateMenuButton',
            'SubtitlesButton',
            'qualitySelector',
            'PictureInPictureToggle',
            'fullscreenToggle',
          ],
        },
        playbackRates: [0.5, 0.75, 1, 1.25 , 1.5, 1.75 , 2 ,4],
        sources: [
          {
            src:
                "https://cdn.alaatv.com/media/1042/HD_720p/1042003xxxx.mp4",
            type: 'video/mp4',
            label: '720p',
            selected: true,
          },
          {
            src:
                "https://cdn.alaatv.com/media/1042/hq/1042003xxxx.mp4",
            type: 'video/mp4',
            label: '480P',
            selected: true,
          },
          {
            src:
                "https://cdn.alaatv.com/media/1042/240p/1042003xxxx.mp4",
            type: 'video/mp4',
            label: '240p',
            selected: true,
          }
        ]
      }
    }
  }
};
</script>
<style>
.video-js .vjs-current-time { display: block; }
</style>