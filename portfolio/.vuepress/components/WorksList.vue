<template>
  <div class="project-list">

    <div
      v-for="post in posts"
      :key="post.title"
      class="post"
      :style=""
    >

      <div class="info">
        <h2>{{ post.frontmatter.title }}</h2>
        <span v-if="post.frontmatter.description">{{ post.frontmatter.description }}</span>
        <img :src="post.frontmatter.thumbnail" :alt="post.frontmatter.title">
      </div>
      <router-link
      :to="post.path"
      tag="a">Link to study
      </router-link>
    </div>

  </div>
</template>

<script>
  export default {
    computed: {
      posts() {
        return this.$site.pages
          .filter(x => x.path.startsWith('/works/') && !x.frontmatter.works_index)
          .sort((a, b) => new Date(b.frontmatter.date) - new Date(a.frontmatter.date))
      }
    }
  }
</script>

<style scoped>

  .post {
    position: relative;
    width: 100%;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    margin-bottom: 5vw;
  }

  .info {
    top: 2rem;
    padding: 0.5rem 1rem;
    background: rgba(255,255,255, 1);
  }

  .info h2 {
    display: inline-block;
    width: auto;
    font-size: 0.8rem;
    font-weight: 700;
    margin: 0;
  }

  .info span {
    display: block;
    width: auto;
    margin: 0;
    font-size: 0.8rem;
  }

</style>
