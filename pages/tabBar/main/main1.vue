<template>
  <div id="app">
    <header class="app-header">
      <div class="top-bar">
        <div class="left-actions">
          <button>乐园</button>
        </div>
        <div class="center-actions">
          <span>04:57</span>
        </div>
        <div class="right-actions">
          <span>67%</span>
        </div>
      </div>
      <nav class="nav-bar">
        <button>乐园广场</button>
        <button>牵红线</button>
        <button>分享乐园</button>
        <button>防骗指南</button>
      </nav>
    </header>
    <div class="banner">
      <p>New 你想要的个性来啦~</p>
    </div>
    <section class="content">
      <div class="recommendations">
        <h2>优质推荐</h2>
        <div class="recommendation-list">
          <div class="recommendation-item" v-for="item in recommendations" :key="item.id">
            <img :src="item.image" :alt="item.name">
            <p>{{ item.name }}</p>
          </div>
        </div>
      </div>
      <div class="live-section">
        <h2>正在活跃</h2>
        <div class="live-list">
          <div class="live-item" v-for="item in liveUsers" :key="item.id">
            <img :src="item.image" :alt="item.name">
            <p>{{ item.name }}</p>
          </div>
        </div>
      </div>
      <div class="video-section">
        <h2>视频1v1</h2>
        <div class="video-list">
          <div class="video-item" v-for="item in videos" :key="item.id">
            <img :src="item.image" :alt="item.name">
            <p>{{ item.name }}</p>
          </div>
        </div>
      </div>
      <div class="group-section">
        <h2>最热群组</h2>
        <div class="group-list">
          <div class="group-item" v-for="item in groups" :key="item.id">
            <img :src="item.image" :alt="item.name">
            <p>{{ item.name }}</p>
          </div>
        </div>
      </div>
      <div class="audio-section">
        <h2>语音直播间</h2>
        <div class="audio-list">
          <div class="audio-item" v-for="item in audios" :key="item.id">
            <img :src="item.image" :alt="item.name">
            <p>{{ item.name }}</p>
          </div>
        </div>
      </div>
      <div class="banner">
        <p>New 你想要的个性来啦~</p>
      </div>
      <div class="comic-section">
        <h2>圈内漫画</h2>
        <div class="comic-list">
          <div class="comic-item" v-for="item in comics" :key="item.id">
            <img :src="item.image" :alt="item.name">
            <p>{{ item.name }}</p>
          </div>
        </div>
      </div>
      <div class="reading-section">
        <h2>圈内读物</h2>
        <div class="reading-list">
          <div class="reading-item" v-for="item in readings" :key="item.id">
            <img :src="item.image" :alt="item.name">
            <p>{{ item.name }}</p>
          </div>
        </div>
      </div>
    </section>
    <footer class="app-footer">
      <p>&copy; 2024 Sank. 保留所有权利。</p>
    </footer>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue';

export default defineComponent({
  name: 'App',
  setup() {
    const recommendations = reactive([
      { id: 1, name: '未', image: 'path/to/image1.png' },
      { id: 2, name: '小柒夹肉很安好', image: 'path/to/image2.png' },
      { id: 3, name: '七七七撸', image: 'path/to/image3.png' },
      { id: 4, name: '酒爷', image: 'path/to/image4.png' }
      // 其他推荐项...
    ]);

    const liveUsers = reactive([
      { id: 1, name: '丸美猫惠', image: 'path/to/live1.png' },
      { id: 2, name: '南风知我意', image: 'path/to/live2.png' },
      // 其他活跃用户...
    ]);

    const videos = reactive([
      { id: 1, name: '你嫂', image: 'path/to/video1.png' },
      { id: 2, name: '奶瓶', image: 'path/to/video2.png' },
      // 其他视频...
    ]);

    const groups = reactive([
      { id: 1, name: '有福同享', image: 'path/to/group1.png' },
      { id: 2, name: '择金处世', image: 'path/to/group2.png' },
      // 其他群组...
    ]);

    const audios = reactive([
      { id: 1, name: '进来听她骂', image: 'path/to/audio1.png' },
      { id: 2, name: '不要长片了', image: 'path/to/audio2.png' },
      // 其他语音直播间...
    ]);

    const comics = reactive([
      { id: 1, name: '漫画1', image: 'path/to/comic1.png' },
      { id: 2, name: '漫画2', image: 'path/to/comic2.png' },
      // 其他漫画...
    ]);

    const readings = reactive([
      { id: 1, name: '读物1', image: 'path/to/reading1.png' },
      { id: 2, name: '读物2', image: 'path/to/reading2.png' },
      // 其他读物...
    ]);

    return {
      recommendations,
      liveUsers,
      videos,
      groups,
      audios,
      comics,
      readings
    };
  }
});
</script>

<style lang="scss" scoped>
#app { font-family: Arial, sans-serif; background-color: #f4f4f4; margin: 0; padding: 0; display: flex; flex-direction: column; align-items: center; }
.app-header { background-color: #4CAF50; color: white; padding: 10px 0; width: 100%; text-align: center; }
.top-bar { display: flex; justify-content: space-between; align-items: center; padding: 0 10px; }
.center-actions { font-size: 20px; }
.right-actions { font-size: 20px; }
.nav-bar { display: flex; justify-content: space-around; background-color: #333; color: white; }
.nav-bar button { background-color: transparent; border: none; color: white; cursor: pointer; padding: 10px; }
.banner { background-color: #FFA500; color: white; padding: 10px; text-align: center; width: 100%; margin-bottom: 20px; }
.content { width: 100%; background: white; padding: 20px; margin: 20px auto; box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); }
.recommendations, .live-section, .video-section, .group-section, .audio-section, .comic-section, .reading-section { margin-bottom: 20px; }
.recommendation-list, .live-list, .video-list, .group-list, .audio-list, .comic-list, .reading-list { display: flex; flex-wrap: wrap; gap: 10px; }
.recommendation-item, .live-item, .video-item, .group-item, .audio-item, .comic-item, .reading-item { flex: 1 1 calc(33.333% - 10px); box-sizing: border-box; text-align: center; }
.recommendation-item img, .live-item img, .video-item img, .group-item img, .audio-item img, .comic-item img, .reading-item img { width: 100%; }
.app-footer { background-color: #333; color: white; padding: 10px 0; width: 100%; text-align: center; }
</style>
