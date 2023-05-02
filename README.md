# lc-vue-auto-height-wrapper

自动适配外层容器容器尺寸
## 文档

文档 [unpkg](https://unpkg.com/lc-vue-auto-height-wrapper/docs/.vitepress/dist/index.html) `unpkg原因，需要点击左上角跳转文档`】

## 安装 

```
npm i lc-vue-auto-height-wrapper 
```

## 例子

```vue
<script setup lang="ts">
  import { ref, computed } from 'vue';
  import { AutoHeightWrapper } from 'lc-vue-auto-height-wrapper';
  const width = ref(100);
  const height = ref(100);
  const style = computed(()=>({
    width: `${width.value}px`,
    height: `${height.value}px`
  }))
</script>

<template>
  <el-slider v-model="width" :min='100' :max='500' />
  <el-slider v-model="height" :min='100' :max='500' />
  <div style='border: 1px solid #000; display: inline-block'>
    <div :style='style'>
      <AutoHeightWrapper>
        <template #default="{size}">
          {{size}}
        </template>
      </AutoHeightWrapper>  
    </div>
  </div>
</template>
```