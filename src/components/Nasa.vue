<template>
  <div class="Nasa">
    <h2>Input Type You Search</h2>
    <form v-on:submit.prevent="getResult(query)">
      <input type="text" placeholder="input type (ex.moon ,sun)" v-model="query" />
      <b-button-group class="mr-1">
        <b-button title="Save file">
          <b-icon icon="cloud-upload" aria-hidden="true"></b-icon>
        </b-button>
        <b-button title="Load file">
          <b-icon icon="cloud-download" aria-hidden="true"></b-icon>
        </b-button>
        <b-button title="New document">
          <b-icon icon="file-earmark" aria-hidden="true"></b-icon>
        </b-button>
      </b-button-group>
    </form>
    <div class="results" v-if="results">
      <div v-for="result in results" v-bind:key="result">
        <img v-bind:src="result.links[0].href" />
      </div>
    </div>
    <div class="p-4">
      <b-icon icon="archive-fill" animation="throb" font-scale="4"></b-icon>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "nasa",
  data() {
    return {
      msg: "Nasa",
      query: "",
      results: "",
    };
  },
  methods: {
    getResult(query) {
      axios
        .get(
          "https://images-api.nasa.gov/search?q=" + query + "&media_type=image"
        )
        .then((response) => {
          console.log(response.data.collection.items);
          this.results = response.data.collection.items;
        });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.results img {
  height: 300px;
  margin: 10px;
}
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
