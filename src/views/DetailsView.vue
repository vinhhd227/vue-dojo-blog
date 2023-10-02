<template>
  <div v-if="post">
    <h1>{{ post.title }}</h1>
    <p>{{ post.body }}</p>
  </div>
  <div v-else>
    <h2>404</h2>
    <p>Page not found</p>
  </div>
</template>

<script>
import getPost from '../composables/getPost';

export default {
  name: 'DetailsView',
  props: ['id'],
  setup(props) {
    const { post, error, load } = getPost(props.id);
    load();
    return { post, error }
  }
}
</script>

<style></style>