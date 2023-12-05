<template>
  <div class="video-card-grid-container">
    <div class="video-card-grid-row" v-for="(row, index) in grid">
      <VideoCard class="video-card-grid-video" :title="item.title" :time="item.time" :img="item.img" :video="item.video"
                 @click="clickOnVideoCard(item)"  v-for="(item, index) in row"  />
    </div>
  </div>

</template>

<style lang="scss">
.video-card-grid-row{
  display: flex;
  flex-direction: row;
  width: 100%;
  margin-bottom: 25px;
}

.video-card-grid-video {
  flex: 1;
}

.video-card-grid-video:not(:first-child){
  margin-left: 70px;
}
</style>

<script >
import VideoCard from './VideoCard.vue';

export default {
    props: {
        videoSet: {
            type: Array,
            required: true
        },
        rowCount: {
            type: Number,
            required: false,
            default: 2
        },
        columnCount: {
            type: Number,
            required: false,
            default: 2
        },
    },
    computed: {
        grid() {
            let gridVideos = [];
            for (let i = 0; i < this.rowCount; i++) {
                const elementRow = this.videoSet[i * this.rowCount];
                let gridRowVideos = [];
                gridVideos.push(gridRowVideos);
                for (let j = 0; j < this.columnCount; j++) {
                  const elementColumn = this.videoSet[i * this.rowCount + j];
                  if (elementColumn == null) break;
                  gridVideos[i][j] = elementColumn;
                }
            }
            return gridVideos;
        }
    },
    methods:
    {
      clickOnVideoCard(videoData) {
        this.$router.push("/work/" + videoData.url);
        this.$emit('click', videoData)
      }
    },
    components: { VideoCard }
}
</script>
