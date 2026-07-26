<template>
  <div class="glass-card ticker-card">
    <div class="ticker-wrapper">
      <div v-for="(item, index) in tickerItems" :key="index" class="ticker-item">
        <span>{{ item.text }}</span>
        <span style="color: var(--success-color); font-weight: bold;">[生成完成]</span>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const tickerItems = ref([
  {
    "text": "用户 139****1102 完成了产品经理简历 STAR 法则重构，量化指标增加 3 处"
  },
  {
    "text": "用户 186****9928 生成了 985 应届生跨界投递咨询公司精修简历"
  },
  {
    "text": "用户 152****3341 优化了 5 年 Java 开发工程师简历关键词匹配度"
  },
  {
    "text": "用户 133****4519 完成了外企市场经理双语简历亮点挖掘"
  },
  {
    "text": "用户 177****8890 生成了中高层运营总监数据化成果履历"
  }
]);
</script>
