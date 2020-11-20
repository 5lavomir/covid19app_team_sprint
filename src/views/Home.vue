<template>
  <main>
    <h1>Welcome to Team 1's Covid App</h1>
    <h1>Informational Site.</h1>
    <!-- Hiding Home Table for now as it has not been used - "Alex" -->
    <!-- <HomeTable/> -->
    <CovidInfo/>
  </main>
</template>

<script>
// import HomeTable from '@/components/HomeTable.vue'
import CovidInfo from '@/components/CovidInfo.vue'

export default {
  name: 'Home',
  components: {
    // HomeTable,
    CovidInfo
  }
}

/*
Added code thats not working for Douglas and Tom to have a look at.
import axios from 'axios'

export default {
  name: 'Globals',
  data: function () {
    return {
      globals: {
        totalConfirmed: '',
        totalDeaths: '',
        totalRecovered: ''
      }
    }
  },
   async created () {
    // On Vue creating component, fetch all the data we need
    const { data } = await axios.get('https://api.covid19api.com/summary')
    this.globals = {
      totalConfirmed: data.Global.TotalConfirmed,
      totalDeaths: data.Global.TotalDeaths,
      totalRecovered: data.Global.TotalRecovered
    }
  }
  */
</script>

<style scoped>
main{
  padding-top: 120px;
}
</style>
