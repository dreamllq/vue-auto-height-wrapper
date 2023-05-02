# lc-vue-auto-height-wrapper

ResizeObserver封装， 能够方便的在template中获取父容器的尺寸

常用场景：

- 配合 element-plus 中的 table 组件实现动态容器固定表头

## Demo

[demo](https://unpkg.com/lc-vue-auto-height-wrapper/docs/.vitepress/dist/index.html) 

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

## API

### Slots

| 插槽名 | 说明 | 参数 |
| ---- | ---- | ---- | 
| default | 自定义内容 | size: \{ width: number, height: number \} |