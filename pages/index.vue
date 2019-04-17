<template>
  <article>
    <div class="container">
      <h1>Index</h1>
      <div class="grid">
        <div v-for="article in articles" class="item">
          <div class="row">
            <div class="col-md-12">
              <div  class="card">
                <div class="card-header">
                  <nuxt-link :to="'/article/' + article.id" class="">{{ article.title }}</nuxt-link>
                </div>
                <div class="card-body">
                  <blockquote class="blockquote mb-0">
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
                    <footer class="blockquote-footer">Someone famous in <cite title="Source Title">Source Title</cite></footer>
                  </blockquote>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </article>
</template>


<script>
import axios from 'axios'

export default {
  title: 'Hey there',
  async asyncData () {
    const {data} = await axios.get('http://localhost/lumen-api/public/article')
    // https://jsonplaceholder.typicode.com/posts
    // const {data} = await axios.get('https://jsonplaceholder.typicode.com/posts')
    return {articles:data}
  }
}

</script>

<style scoped>
  
</style>