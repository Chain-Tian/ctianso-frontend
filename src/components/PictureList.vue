<template>
  <a-list
    item-layout="horizontal"
    :grid="{ gutter: 16, xs: 1, sm: 2, md: 4, lg: 4, xl: 6, xxl: 3 }"
    :data-source="props.pictureList"
    v-if="props.pictureList && props.pictureList.length !== 0"
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
  <MyHint v-else></MyHint>
</template>

<script setup lang="ts">
import { withDefaults, defineProps } from "vue";
import MyHint from "@/components/MyHint.vue";

interface Props {
  pictureList: any[];
}

const props = withDefaults(defineProps<Props>(), {
  pictureList: () => [],
});
</script>
<style scoped></style>
