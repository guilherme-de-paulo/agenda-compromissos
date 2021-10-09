<template>
  <header>
      <h1><u>{{ valor }}</u></h1>
  </header>
</template>

<script>
export default {
  props:["valor"],
};
</script>

<style>
header {
  height: 60px;
  background-color: royalblue;
  color: white;
  width: 100%;
  display: flex;
  top: 0;
}

</style>