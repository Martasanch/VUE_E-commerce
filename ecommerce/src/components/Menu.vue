<template>
  <div class="ui secondary menu">
      <div class="ui container">
            <div class="left menu">
              <router-link class="item" to="/">
              <img class="ui small image" src="../assets/logod.jpg" alt="Ecommerce"/>
              <p>Categorías</p>
              </router-link>
            </div>
            <div class="right menu">
                <router-link class="item" to="/login">Iniciar sesión</router-link>

            </div>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.ui.menu.secondary {
    background-color: goldenrod;

    .item {
        color: black;
        &:hover {
            color: grey;
        }
    }

    .menu.left {
        width: 50%;
        .ui.image {
        width: 50px;
        }
    }
    
    .menu.right {
        width: 50%;
        justify-content: flex-end;

        .logout,
        .cart {
            &:hover {
            cursor: pointer;
        }
        }
    }
   
}

</style>