<template>
  <div class="post">
    <div class="post__title">
      {{ post.title }}
    </div>
    <div class="post__body">
      {{ post.body }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    post: Object,
  }
}
</script>

<style scoped>
.post {
  padding: 10px 15px;
  margin: 5px 15px;

  display: flex;
  flex-direction: column;
  gap: 10px;

  background: #77B6EA;
  color: black;
  border-radius: 10px;
}

.post__title {
  font-weight: bold;
}
</style>