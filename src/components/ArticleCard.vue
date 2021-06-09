<template>
  <div class="card-container">
    <el-card :body-style="{ padding: '0px' }">
      <el-image class="card-image" :src="image" fit="cover"></el-image>

      <div class="card-title">
        <el-link :to="'/articles/' + _id">
          <h3>{{ title }}</h3>
        </el-link>
      </div>

      <div class="card-meta">
        <span class="card-author">{{ author }}</span>
        <span class="card-date">{{ date }}</span>
      </div>

      <div class="card-summary">{{ summary }}</div>
    </el-card>
  </div>
</template>

<script>
export default {
  name: "ArticleCard",
  props: {
    _id: String,
    image: String,
    title: String,
    author: String,
    date: String,
    summary: String,
  },
};
</script>

<style lang="scss" scoped>
.card-container {
  margin-bottom: 24px;

  font-family: sans-serif;

  .card-image {
    width: 100%;
    height: 250px;
  }

  .card-title {
    padding: 10px;
    background: #e8f6fa;
    width: 85%;

    h3 {
      margin-top: 5px;
      margin-bottom: 5px;
      font-weight: 900;
    }
  }

  .card-meta {
    padding: 10px;

    font-size: 0.8em;
    text-transform: uppercase;

    .card-author {
      font-weight: bold;
      color: #343434;

      padding-right: 14px;
      margin-right: 14px;
      border-right: 1px solid black;
    }

    .card-date {
      font-weight: lighter;
      color: #565656;
    }
  }

  .card-summary {
    padding: 10px;
  }
}
</style>
