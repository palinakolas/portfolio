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
        <span v-if="post.frontmatter.subtitle">{{ post.frontmatter.subtitle }}</span>
        <span v-if="post.frontmatter.description">{{ post.frontmatter.description }}</span>
        <router-link
      :to="post.path"
      tag="a">Link to study
      </router-link>
      </div>
      <div class="image">
        <img :src="post.frontmatter.thumbnail" :alt="post.frontmatter.title">
      </div>
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
    display: flex;
  }

  .image {
    flex: 0 0 70%;
  }

  .info {
    top: 2rem;
    padding: 0.5rem 1rem;
    background: rgba(255,255,255, 1);
  }

  .info h2 {
    display: inline-block;
    width: auto;
    padding-bottom: 1rem;
    margin: 0;
  }

  .info span {
    display: block;
    width: auto;
    margin: 0;
    padding-bottom: 1rem;
  }
  a{
    color: black;
  }

</style>
