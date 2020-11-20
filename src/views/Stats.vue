<template>
  <main>
    <CountryTable/>
    <!--
    </graph>
    -->
  </main>
</template>

<script>
import CountryTable from '@/components/CountryTable.vue'
// import graph from '@/components/graph.vue'
export default {
  name: 'Stats',
  components: {
    CountryTable
    // graph
  }
}
</script>

<style scoped>
main{
  padding-top: 120px;
}
</style>
