<template>
  <article>
    <div class="row">
        <div class="col-md-12">
            <div  class="card">
            <div class="card-header">
                {{title}}
            </div>
            <div class="card-body">
                <blockquote class="blockquote mb-0">
                <div v-html="content" />
                <footer class="blockquote-footer">
                    Someone famous in <cite title="Source Title">Source Title</cite>
                    <nuxt-link :to="'/'">Back</nuxt-link>
                </footer>
                </blockquote>
            </div>
            </div>
        </div>
    </div>
  </article>
</template>

<script>
import axios from "axios";

export default {
  validate({ params }) {
    return !isNaN(+params.id);
  },
  async asyncData({ params, error }) {
    const { data } = await axios.get(
      `http://localhost/lumen-api/public/article/${+params.id}`
    );
    return data;
  }
};
</script>
