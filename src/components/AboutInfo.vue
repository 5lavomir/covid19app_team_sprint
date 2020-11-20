<template>
  <!-- Some of the classes are bootstrap - "Alex" -->
  <main id="contributors" class="d-inline-block">
    <h3>{{ msg }}</h3>
      <ul class="list-group text-left">
        <li class="list-group-item">
          Lewis Brogan: <a class="float-right" href="https://www.linkedin.com/in/lewis-brogan-14325b138/" target="_blank" rel="noopener">LinkedIn</a>
                        <a class="float-right" href="https://github.com/iLewisBrogan" target="_blank" rel="noopener">Github</a>
        </li>
        <li class="list-group-item">
          Alex Duthie:  <a class="float-right" href="https://www.linkedin.com/in/alexduthielnkdn/" target="_blank" rel="noopener">LinkedIn</a>
                        <a class="float-right" href="https://github.com/AlexDuthie" target="_blank" rel="noopener">Github</a>
        </li>
        <li class="list-group-item">
          Sławomir Szakalinis: <a class="float-right" href="https://www.linkedin.com/in/slaw-s-13a0631b7/" target="_blank" rel="noopener">LinkedIn</a>
        </li>
        <li class="list-group-item">
          Andrew Ellen:  <a class="float-right" href="https://www.linkedin.com/in/andrew-ellen-3719361b5/" target="_blank" rel="noopener">LinkedIn</a>
                         <a class="float-right" href="https://github.com/AndyE77" target="_blank" rel="noopener">Github</a>
        </li>
        <li class="list-group-item">
          Grant Johnstone: <a class="float-right" href="https://www.linkedin.com/in/grant-johnstone-81b2ba1b6/" target="_blank" rel="noopener">LinkedIn</a>
                           <a class="float-right" href="https://github.com/GrantJ2" target="_blank" rel="noopener">Github</a>
        </li>
      </ul>
  </main>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<style scoped>
main{
  color: black;
  color: #eee;
}

li {
  color: black;
}

a {
  color: #42b983;
}

.list-group-item:hover{
  background-color: rgb(133, 213, 233);
}

.list-group-item a{
  margin-left: 15px;
}

.list-group-item a:hover{
  color: white;
}
</style>
