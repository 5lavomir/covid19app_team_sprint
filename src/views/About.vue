<template>
  <main>
    <div class="about"><h1>Disclaimer:</h1></div>
    <div class="disclaimer"><p>This is a website developed as part of coursework at the University of the Highlands and Islands, to allow student teams to experiment with building websites based on open APIs.</p></div>

    <AboutInfo msg="UHI Covid API App Contributors:"/>
  </main>
</template>

<script>
// @ is an alias to /src
import AboutInfo from '@/components/AboutInfo.vue'

export default {
  name: 'About',
  components: {
    AboutInfo
  }
}
</script>

<style scoped>
main{
  padding-top: 120px;
}

.disclaimer {
    font-size: 20px;
    width: 50%;
    margin-left: 25%;
}
</style>
