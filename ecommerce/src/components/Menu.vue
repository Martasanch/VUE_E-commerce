<template>
  <div class="ui secondary menu">
      <div class="ui container">
            <div class="left menu">
              <router-link class="item" to="/">
              <img class="ui small image" src="../assets/logo.svg" alt="Ecommerce"/>
              <p>Categorías</p>
              </router-link>
            </div>
            <div class="right menu">
                <router-link v-if="!token" class="item" to="/login">Iniciar sesión</router-link>
                <template v-if="token">
                    <router-link class="item" to="/orders">Pedidos</router-link>
                    <span class="ui item cart">
                        <i class="shopping cart icon"></i>
                    </span>
                      <span class="ui item logout">
                        <i class="sign-out icon" @click="logout"></i>
                    </span> 
                </template>

            </div>
      </div>
  </div>
</template>

<script>
import { ref, onMounted } from "vue"
import { getTokenApi, deleteTokenApi} from "../api/token"
import { getCategoriesApi } from "../api/category"
export default {
    name: "Menu",
    setup() {
        let categories = ref(null)
        const token = getTokenApi()

        onMounted( async () =>{
           const response = await getCategoriesApi()
           categories.value = response

        })
        const logout = () => { 
            deleteTokenApi()
            location.replace("/")
         }

    
     return {
        token,
        logout,
        categories
    }

    }
   
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