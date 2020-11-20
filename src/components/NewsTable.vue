<template>
  <main>
    <table id="uk-news-table" class="table table-bordered table-striped">
      <thead class="thead-dark">
        <tr>
          <th>UK News</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="uk in ukArticlesList" :key="uk.id">
          <td class="w-25">
            Publisher: {{ uk.source.name }}
            <br><br>
            Link:
            <a :href="uk.url">
              {{ uk.title }}
            </a>
          </td>
        </tr>
      </tbody>
    </table>

    <table id="uk-news-table" class="table table-bordered table-striped">
      <thead class="thead-dark">
        <tr>
          <th>World News</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="world in worldArticlesList" :key="world.id">
          <td class="w-25">
            Publisher: {{ world.source.name }}
            <br><br>
            Link:
            <a :href="world.url">
              {{ world.title }}
            </a>
          </td>
        </tr>
      </tbody>
    </table>
  </main>
</template>

<script>
import axios from 'axios'

export default {
  name: 'NewsTable',
  props: {
    msg: String
  },
  data () {
    return {
      worldArticlesList: undefined,
      ukArticlesList: undefined
    }
  },
  // pass parameter !!!
  // Fetches posts when the component is created.
  created () {
    axios.get('https://newsapi.org/v2/everything?q=covid-19&apiKey=' + 'd735b5609e9040598f2fa58f1b375c28')
      .then(response => {
        this.worldArticlesList = response.data.articles
      })
      .catch(err => {
        console.log(err)
      })
    axios.get('https://newsapi.org/v2/everything?q=covid-uk&apiKey=' + 'd735b5609e9040598f2fa58f1b375c28')
      .then(response => {
        this.ukArticlesList = response.data.articles
      })
      .catch(err => {
        console.log(err)
      })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
main{
  padding-top: 120px;
}

td img {
  height: 100px;
  width: 100px;
}

.table {
  width: 25%;
  float: left;
}

th {
  font-size: 25px;
}

tr, td {
  font-size: 20px;
  border-color: black;
  color: #eee;
}

td:hover{
  background-color: #596f76;
}

a{
  color: #eee;
}

a:hover {
  color: rgb(151, 231, 151);
  text-decoration: none;
}
</style>
