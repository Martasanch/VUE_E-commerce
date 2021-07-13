<template>
  <BasicLayout>
      <h1>categorias</h1>
  </BasicLayout>
</template>

<script>
import BasicLayout from "../layouts/BasicLayout"
export default {

name: "Category",
components: {
    BasicLayout
},
watch: {
    $route(to, from){
        console.log(to)
    }
}
}
</script>

<style>

</style>