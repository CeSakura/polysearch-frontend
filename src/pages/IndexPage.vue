<template>
  <div @click.stop>
    <a-input-search
      class="searchInput"
      v-model:value="searchText"
      placeholder="input search text"
      allowClear
      enter-button
      @search="onSearch"
      size="large"
    />
  </div>

  <a-tabs v-model:activeKey="activeKey">
    <a-tab-pane key="1" tab="文章">
      <ArticleList />
    </a-tab-pane>
    <a-tab-pane key="2" tab="视频">
      <VideoList />
    </a-tab-pane>
    <a-tab-pane key="3" tab="用户">
      <UserList />
    </a-tab-pane>
  </a-tabs>
</template>

<script lang="ts" setup>
import { ref } from "vue";
import ArticleList from "../components/ArticleList.vue";
import UserList from "../components/UserList.vue";
import VideoList from "../components/VideoList.vue";

let activeKey = ref("1");

let searchText = ref("");

const onSearch = (value: string) => {
  alert(value);
};
</script>

<style scoped lang="less">
.searchInput {
  width: 50%;
  margin-bottom: 50px;
}
</style>
