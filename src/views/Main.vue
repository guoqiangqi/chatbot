<script setup lang="ts">
import { ref } from "vue"
import type { TabsPaneContext } from "element-plus"
// import Battle from "./Battle.vue"
import Side from "./Side.vue"
import Header from "@/components/Header/index.vue"
import Footer from "@/components/Footer/index.vue"

defineProps<{ msg: string }>()

const activeName = ref("first")

const handleClick = (tab: TabsPaneContext, event: Event) => {
  console.log(tab, event)
}

const imgList = ref<any>([
  "",
  "https://img.jsdesign2.com/assets/img/652cb2002b09ab958d49fa0d.jpg",
  "https://img.js.design/assets/img/64ec601883c447c7d84b119f.png",
  "https://img.jsdesign2.com/assets/img/64a8e46657a545dde1879ce7.png#225fd61cf571879ed27fbc6f08cb912a",
])
</script>

<template>
  <div class="w-full overflow-auto h-full flex flex-col justify-between relative">
    <Header />
    <section class="flex-1 max-w-[1240px] w-full mx-auto my-5 px-5">
      <div class="h-60 flex items-center flex-col justify-center">
        <div class="text-4xl font-bold">Compass AI模型评估</div>
        <div class="text-[#86909c] mt-4">这里提供各种AI模型的点评和使用体验</div>
      </div>
      <div class="items-center flex-col">
        <div class="text-4xl font-bold">文本分类模型</div>
        <div class="text-[#86909c] mt-4">
          基于深度学习技术，通过对文本语义进行分析，实现高精度文本分类
        </div>
      </div>
      <div class="flex justify-center mt-10">
        <div class="h-60 w-[1000px]">
          <el-carousel :interval="4000000" type="card" height="240px">
            <el-carousel-item v-for="item in 3" :key="item">
              <img :src="imgList[item]" />
            </el-carousel-item>
          </el-carousel>
        </div>
      </div>
      <div class="flex items-center flex-col justify-center mt-20">
        <div class="text-4xl font-bold">LLMs排行榜</div>
        <div class="text-[#86909c] mt-4">以下是我们基于人工评测和自动评测完成的排行榜</div>
      </div>
      <div class="grid grid-cols-2 gap-6 mt-20">
        <div class="bg-[#f7f8fa] rounded-xl p-6">
          <div class="flex justify-between items-center">
            <div class="text-2xl font-bold">榜单一</div>
            <div>查看更多</div>
          </div>
          <div
            class="mt-4 flex justify-between cursor-pointer py-3 last:border-0"
            v-for="item in 6"
            :key="item"
          >
            <div class="col-span-3 flex">
              <div class="h-10 w-10">
                <div class="h-10 w-10 overflow-hidden rounded-full border border-gray-100">
                  <img
                    alt="logo"
                    loading="lazy"
                    width="40"
                    height="40"
                    decoding="async"
                    data-nimg="1"
                    src="https://github.com/THUDM.png"
                    style="object-fit: cover"
                  />
                </div>
              </div>
              <div class="ml-4 min-w-0 flex-1">
                <div class="mb-1 truncate font-bold">ChatGLM-6B</div>
                <div class="flex items-center">
                  <span class="text-secondary text-xs">THUDM</span>
                </div>
              </div>
            </div>
            <div class="flex items-center mr-4">1223</div>
          </div>
        </div>
        <div class="bg-[#f7f8fa] rounded-xl p-6">
          <div class="flex justify-between items-center">
            <div class="text-2xl font-bold">榜单二</div>
            <div>查看更多</div>
          </div>
          <div
            class="mt-4 flex justify-between cursor-pointer py-3 last:border-0"
            v-for="item in 6"
            :key="item"
          >
            <div class="col-span-3 flex">
              <div class="h-10 w-10">
                <div class="h-10 w-10 overflow-hidden rounded-full border border-gray-100">
                  <img
                    alt="logo"
                    loading="lazy"
                    width="40"
                    height="40"
                    decoding="async"
                    data-nimg="1"
                    src="https://github.com/THUDM.png"
                    style="object-fit: cover"
                  />
                </div>
              </div>
              <div class="ml-4 min-w-0 flex-1">
                <div class="mb-1 truncate font-bold">ChatGLM-6B</div>
                <div class="flex items-center">
                  <span class="text-secondary text-xs">THUDM</span>
                </div>
              </div>
            </div>
            <div class="flex items-center mr-4">1223</div>
          </div>
        </div>
      </div>
      <div class="flex items-center flex-col justify-center mt-20">
        <div class="text-4xl font-bold">用户评价</div>
        <div class="text-[#86909c] mt-4">以下是部分用户对该AI模型点评页面的评价：</div>
      </div>
      <div class="mt-20 w-full">
        <el-carousel :interval="5000000" arrow="always">
          <el-carousel-item v-for="item in 1" :key="item">
            <div class="px-40 py-10 text-center flex flex-col items-center">
              <div class="text-xl text-center font-semibold">
                这个AI模型点评页面真是太棒了！设计简洁大方，用户体验很好。我喜欢它提供的模型介绍、参数、相关产品和用户评价等功能，非常实用！
              </div>
              <div class="h-16 w-16 mt-8">
                <img
                  src="https://img.jsdesign2.com/assets/element/ai_AheJcMcjCpO/image/2184303fa24312bc9b749c25c9187c99a09cf309.png"
                  alt=""
                />
              </div>
              <div class="text-xl font-semibold mt-6">葛志强</div>
            </div>
          </el-carousel-item>
        </el-carousel>
      </div>
      <!-- <el-tabs class="mb-0" type="border-card" v-model="activeName" @tab-click="handleClick">
        <el-tab-pane label="Chatbot Compass (battle)" name="first">
          <Battle />
        </el-tab-pane>
        <el-tab-pane label="Chatbot Compass (side-by-side)" name="second"> <Side /></el-tab-pane>
      </el-tabs> -->
    </section>
    <Footer />
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
.el-carousel__item h3 {
  /* color: #475669; */
  opacity: 0.75;
  margin: 0;
  text-align: center;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  /* background-color: #d3dce6; */
}
.el-carousel__item {
  border-radius: 12px;
  /* width: 351px; */
}
.is-active {
  /* width: 546px; */
}
</style>
