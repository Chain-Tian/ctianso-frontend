<script setup lang="ts">
import wft from "../assets/wft.jpg";
import { withDefaults, defineProps } from "vue";

interface Props {
  postList: any[];
}

const props = withDefaults(defineProps<Props>(), {
  postList: () => [],
});
</script>

<template>
  <a-list item-layout="horizontal" :data-source="props.postList">
    <template #renderItem="{ item }">
      <a-list-item>
        <a-list-item-meta>
          {{ item }}
          <template #title>
            <a href="http://so.ctian-api.top/hint">
              <span v-html="item.title"></span>
            </a>
          </template>
          <template #avatar>
            <a-avatar :src="wft" />
          </template>
          <template #description>
            <p v-html="item.content" style="color: black"></p>
          </template>
        </a-list-item-meta>
      </a-list-item>
    </template>
  </a-list>
</template>

<style scoped></style>
