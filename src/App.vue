<template>
  <div id="app">
    <el-row :gutter="24">
      <el-col :span="24">
        <h2 class="text-center">Articles</h2>
      </el-col>

      <el-col :sm="24" :lg="18">
        <el-row :gutter="24">
          <el-col
            v-for="article in articles"
            :key="article._id"
            :sm="24"
            :md="12"
          >
            <ArticleCard v-bind="article" />
          </el-col>
        </el-row>
      </el-col>
      <el-col :sm="24" :lg="6">
        <div class="advertisement"></div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import ArticleCard from "./components/ArticleCard.vue";

export default {
  name: "app",
  components: {
    ArticleCard,
  },

  computed: {
    articles() {
      return this.$store.getters["articles/articles"];
    },
  },
};
</script>

<style lang="scss" scoped>
* {
  font-family: sans-serif;
}

.text-center {
  text-align: center;
}

.advertisement {
  height: 250px;
  width: 100%;
  background: #dedede;
}
</style>
