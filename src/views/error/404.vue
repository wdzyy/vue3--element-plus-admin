<script setup lang="ts">
import noExist from "/@/assets/status/404.svg?component";
</script>

<template>
  <div class="flex justify-center items-center h-screen-sm">
    <noExist />
    <div class="ml-12">
      <p
        v-motion
        class="font-medium text-4xl mb-4"
        :enter="{
          opacity: 1,
          y: 0,
          transition: {
            delay: 100
          }
        }"
        :initial="{
          opacity: 0,
          y: 100
        }"
      >
        404
      </p>
      <p
        v-motion
        class="mb-4 text-gray-500"
        :enter="{
          opacity: 1,
          y: 0,
          transition: {
            delay: 300
          }
        }"
        :initial="{
          opacity: 0,
          y: 100
        }"
      >
        抱歉，你访问的页面不存在
      </p>
      <el-button
        v-motion
        :enter="{
          opacity: 1,
          y: 0,
          transition: {
            delay: 500
          }
        }"
        :initial="{
          opacity: 0,
          y: 100
        }"
        type="primary"
        @click="$router.push('/')"
        >返回首页</el-button
      >
    </div>
  </div>
</template>
