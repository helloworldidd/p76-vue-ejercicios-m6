<script setup>

</script>

<template>
  <nav>
    <ul>
      <li><a href="#">pagina 1</a></li>
      <li><a href="#">pagina 2</a></li>
      <li><a href="#">pagina 3</a></li>
    </ul>
  </nav>
</template>

<style scoped>
ul{
  display: flex;
  flex-direction: row;
  background-color: rgb(154, 145, 145);
  list-style: none;
  width: fit-content;
}

ul li {
  display: flex;
}

ul li a{
  padding: 10px;
  text-decoration: none;
  transition: 0.5s;
}

ul li a:hover{
  background-color: #b0b055;
  transform: scale(1.2);
}

</style>