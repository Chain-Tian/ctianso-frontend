<template>
  <a-list
    item-layout="horizontal"
    :grid="{ gutter: 16, xs: 1, sm: 2, md: 4, lg: 4, xl: 6, xxl: 3 }"
    :data-source="props.videoList"
    v-if="props.videoList"
  >
    <template #renderItem="{ item }">
      <a :href="item.url">
        <a-list-item>
          <a-card hoverable>
            <template #cover>
              <img :src="item.pic" referrerpolicy="no-referrer" />
            </template>
            <a-card-meta :title="item.author">
              <template #description>
                <span v-html="item.title"></span>
              </template>
            </a-card-meta>
          </a-card>
        </a-list-item>
      </a>
    </template>
  </a-list>
  <MyHint v-else></MyHint>
</template>

<script setup lang="ts">
import wft from "../assets/wft.jpg";
import { withDefaults, defineProps } from "vue";
import MyHint from "@/components/MyHint.vue";

interface Props {
  videoList: any[];
}

const props = withDefaults(defineProps<Props>(), {
  videoList: () => [],
});
</script>

<style scoped></style>
