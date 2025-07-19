<route lang="jsonc" type="page">
{
  "layout": "tabbar",
  "style": {
    "navigationBarTitleText": "瀑布流"
  }
}
</route>

<script lang="ts" setup>
import { random, toast } from 'sard-uniapp'
import { nextTick, onMounted, ref } from 'vue'
import { text } from './mockApi'
import SimulatedImage from './SimulatedImage.vue'

interface ListItem {
  title: string
  img: {
    width: number
    height: number
  }
}

const list = ref<ListItem[]>([])

function getData() {
  return new Promise<ListItem[]>((resolve) => {
    const data = Array.from({ length: 20 })
      .fill(0)
      .map(() => {
        const min = 20
        const max = 50
        const startIndex = random(0, text.length - max)
        const length = random(min, max)
        return {
          title: text.slice(startIndex, startIndex + length),
          img: {
            width: random(100, 500),
            height: random(100, 500),
          },
        }
      })
    resolve(data)
  })
}

function onWaterfallLoad() {
  toast.hide()
}

onMounted(async () => {
  nextTick(() => {
    toast.loading('加载中')
  })
  list.value.push(...(await getData()))
})
</script>

<template>
  <view>
    <sar-waterfall class="mx-2" @load="onWaterfallLoad">
      <sar-waterfall-item v-for="(item, index) in list" :key="index">
        <template #default="{ onLoad }">
          <SimulatedImage :meta="item.img" @load="onLoad" />
          <view class="mt-2">
            {{ item.title }}
          </view>
        </template>
      </sar-waterfall-item>
    </sar-waterfall>
  </view>
</template>

<style lang="scss" scoped>
//
</style>
