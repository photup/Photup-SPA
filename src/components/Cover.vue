<script setup>
import { ref } from 'vue'
const CoverLinks = ref([
  { title: '文章', link: 'https://tripper.press/' },
  { title: '摄影', link: '#/gallery' },
  { title: '视频', link: '/videos' },
  { title: '实验室', link: '/codelab' },
])
console.log(CoverLinks);
</script>
<template>
  <div class="cover">
    <div class="cover-area md:m-[0] grid shadow-itp grid-cols-1 md:grid-cols-2 ">
      <div class="cover-1 w-[auto] md:min-w-[300px] md:h-[300px] flex">
        <div class="font-[900] text-[28px] md:text-[48px]">Photup.
        </div>
        <span>Cherish every moment</span>
      </div>
      <div class="cover-2 w-[auto] md:min-w-[300px] md:h-[300px] grid grid-cols-2 grid-rows-2">
        <div v-for="(item, index) in CoverLinks">
          <div class="cover-items">
            <a class="cover-links" :href="item.link" :title="item.title">
              {{ item.title }}
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<CoverStyle />
<style scoped>
.cover {
  height: calc(100vh - 80px);
  background:
    radial-gradient(circle at 10% 10%,
      #90caaf80 10%,
      #ffffff00 100%),
    radial-gradient(circle at 90% 90%,
      #71afdd80 10%,
      #ffffff00 100%) !important;
  background-position: center;
  background-attachment: fixed;
  background-size: cover;
}

.cover-1 {
  padding: 24px 24px 12px 48px;
  flex-direction: column;
  justify-content: center;
}

.cover-items {
  font-size: 18px;
  justify-content: center;
  transition: all 0.3s ease-in-out;
  display: flex;
}

.cover-items:hover {
  box-shadow: inset 1px 1px 9px .1px #81858884;
  transition: all 0.3s ease-in-out;
}

.cover-area {
  backdrop-filter: blur(20px);
  background-color: rgba(255, 255, 255, 0.6);
  color: #304A5E;
}

a.cover-links {
  line-height: 96px;
  text-decoration: none;
}

@media (min-width: 800px) {
  .cover-area {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    min-width: 600px
  }

  .cover-1 {
    padding-bottom: 48px;
  }

  a.cover-links {
    line-height: 150px;
    text-decoration: none;
    color: #304A5E;
    margin: 0 auto;
    display: block;
    text-align: center;
  }
}

@media (max-width: 800px) {
  .title-area {
    position: static;
    padding: 36px 0px 12px 48px;
  }


}
</style>
