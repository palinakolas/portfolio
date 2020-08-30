<template>
  <div class="project-list">

    <router-link
      :to="post.path"
      tag="div"
      v-for="post in posts"
      :key="post.title"
      class="post"
      :style=""
    >
    <div class="image">
        <img :src="post.frontmatter.thumbnail" :alt="post.frontmatter.title">
      </div>
      <div class="info">
        <h2>{{ post.frontmatter.title }}</h2>
        <span v-if="post.frontmatter.subtitle">{{ post.frontmatter.subtitle }}</span>
        <span v-if="post.frontmatter.description">{{ post.frontmatter.description }}</span>
      </div>
    
    </router-link>
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
    background: rgb(243,243,243);
    margin-bottom: 2rem;
    cursor: pointer;
  }

  .image {
    max-height: 700px;
    overflow: hidden;
    padding: 4rem 2rem ;
  }
  .image img {
    max-height: 600px;
    max-width: 100%;
    margin-left: auto;
  margin-right: auto;
  display: block;
  }

  .info {
    padding-bottom: 4rem;
    padding-top: 2rem;
    padding-left:2rem;
  }

  .info h2 {
    display: inline-block;
    width: auto;
    padding-bottom: 1rem;
    margin: 0;
    text-decoration: underline;
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
