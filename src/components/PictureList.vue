<template>
  <a-list
    item-layout="horizontal"
    :grid="{ gutter: 16, xs: 1, sm: 2, md: 4, lg: 4, xl: 6, xxl: 3 }"
    :data-source="props.pictureList"
  >
    <template #renderItem="{ item }">
      <a :href="item.url">
        <a-list-item>
          <a-card hoverable>
            <template #cover>
              <img :src="item.url" referrerpolicy="no-referrer" />
            </template>
            <a-card-meta :title="item.title" />
          </a-card>
        </a-list-item>
      </a>
    </template>
  </a-list>
</template>

<script setup lang="ts">
import { withDefaults, defineProps } from "vue";

interface Props {
  pictureList: any[];
}

const props = withDefaults(defineProps<Props>(), {
  pictureList: () => [],
});
</script>
<style scoped></style>
