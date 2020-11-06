<template>
<div>
  <h1 class="title" v-if="text0" v-html="text0" />
  <div class="subtitle-wrapper">
  <span class="subtitle green"><h2>{{text1}}</h2></span>
  <span class="subtitle blue"><h2>{{text2}}</h2></span>
  </div>
  </div>
</template>

<script>
export default {
  props: {
    text0: {
      type: String,
      required: false
    },
    text1: {
      type: String,
      required: false
    },
    text2: {
      type: String,
      required: false
    }
  }
}
</script>

<style scoped>
  .title {
    text-align: center;
    font-size: calc(21px + (48 - 14) * ((100vw - 300px) / (1600 - 300)));
    font-weight: 300;
    line-height: 1.25;
    letter-spacing: 0.1rem;
    width: 800px;
    max-width: 100%;
    margin: 18vw auto 7vw auto;
  }
    .subtitle{
    font-weight: 300;
    line-height: 1.25;
    letter-spacing: 0.1rem;
    padding: 2rem;
    min-height: 300px;
    border-radius: 40px;
    color: white;
  }
  .subtitle:not(:last-child){
    margin-bottom: 2rem;
  }
  .subtitle.green{
    background-color: #9ABFB0;
  }
  .subtitle.blue{
    background-color: #9ABDBF;
  }
  .subtitle-wrapper{
      display: flex;
      flex-wrap: wrap;
      margin-bottom: 2rem;
    }


  @media screen and (min-width: 600px) {
    .title {
      margin: 12vw auto 7vw auto;
    }
    .subtitle-wrapper{
      flex-wrap: nowrap;
    }
    .subtitle:not(:last-child){
    margin-right: 2rem;
    margin-bottom: 0;
  }
  }

</style>
