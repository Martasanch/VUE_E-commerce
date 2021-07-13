<template>
<div class="ui card product">
  <div class="image">
    <img :src="API_URL + product.image.url" :alt="product.name" />
  </div>
</div>
</template>

<script>
import { API_URL } from "../utils/constants"
export default {
    name: "Product",
    props: {
      product: Object
    },
    setup(props) {
      console.log(props.product)

      return {
        API_URL,
      }
    }

}
</script>

<style>

</style>