<template>
  <a-list item-layout="horizontal" :data-source="props.apiList">
    <template #renderItem="{ item }">
      <a-list-item>
        <a-list-item-meta>
          {{ item }}
          <template #title>
            <a href="http://api.ctian-api.top">
              <span v-html="item.name"></span>
            </a>
          </template>
          <template #avatar>
            <a-avatar :src="wft" />
          </template>
          <template #description>
            <p v-text="item.description" style="color: black"></p>
          </template>
        </a-list-item-meta>
      </a-list-item>
    </template>
  </a-list>
</template>

<script setup lang="ts">
import wft from "@/assets/wft.jpg";
import { withDefaults, defineProps } from "vue";

interface Props {
  apiList: any[];
}

const props = withDefaults(defineProps<Props>(), {
  apiList: () => [],
});
</script>

<style scoped></style>
