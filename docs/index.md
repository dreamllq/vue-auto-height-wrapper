
# hello-world

<script setup lang="ts">
  import { AutoHeightWrapper } from '@/index.ts'
</script>

<div style='height: 300px;'>
  <AutoHeightWrapper>
    <template #default="{size}">
      {{size}}
    </template>
  </AutoHeightWrapper>  
</div>