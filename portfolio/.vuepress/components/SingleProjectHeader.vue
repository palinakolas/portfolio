<template>
  <div class="header">

    <div class="column">
      <Label class="label">Project</Label>
      <span class="value">{{ title }}</span>
    </div>

    <div class="column">
      <Label class="label">Year</Label>
      <span class="value">{{ year }}</span>
    </div>

    <div class="column">
      <Label class="label">Client</Label>
      <span class="value">{{ client }}</span>
    </div>
    <div class="row">
      <Label class="label">What it is</Label>
      <span class="value">{{ short_description }}</span>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      title: {
        type: String,
        required: true
      },
      year: {
        type: String,
        required: true
      },
      client: {
        type: String,
        required: true
      },
      short_description: {
        type: String,
        required: true
      }
    }
  }
</script>

<style scoped>

  .header {
    display: flex;
    padding: 2rem 0;
    width: 100%;
    max-width: 800px;
    margin: 0 auto 3rem auto;
    flex-wrap: wrap;
  }

  .column {
    flex: 0 0 33.33%;
  }
  .row{
    margin-top: 2rem;
  }
  
  .label {
    margin-bottom: 0.5rem;
    font-weight: 700;
  }

  .value {
    font-weight: 400;
  }

</style>
