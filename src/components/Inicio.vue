<template>
  <v-container>
    <div class="text-right">
      <span class="badge bg-secondary">{{ user.nombre }}</span>
      <button type="button" class="btn btn-success" v-on:click="cerrarSesion">Cerrar Sesión</button>
    </div>
    <v-layout wrap>
      <v-flex  xs12>
        <br>
          <div class="alert alert-primary" role="alert">
          INICIO
          </div>
        <v-carousel cycle>
          <v-carousel-item v-for="(item,i) in items" :key="i" :src="item.src" reverse-transition="fade-transition" transition="fade-transition">

          </v-carousel-item>
        </v-carousel>
      </v-flex>
    </v-layout>
    <v-layout  mt-10 justify-center >
      <v-flex xs9 >
        <h1 class="display-1 text-md-center">
          Quienes somos
        </h1>
        <p class="text-md-center">
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Qui laboriosam quos commodi voluptate facilis blanditiis nam, accusantium veniam eaque architecto? Ratione excepturi magni perspiciatis eveniet sit aliquam nobis beatae repellat.
        </p>
      </v-flex>
    </v-layout>
    <v-layout mt-10 align-center justify-space-around row fill-height>
      <v-flex xs3>
          <v-card class="mx-auto" max-width="344">
            <v-img src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg" height="200px"> </v-img>

            <v-card-title>
              Servicio 1
            </v-card-title>

            <v-card-subtitle>
              Categoría 2
            </v-card-subtitle>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn icon @click="show = !show">
                <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
              </v-btn>
            </v-card-actions>

            <v-expand-transition>
              <div v-show="show">
              <v-divider></v-divider>

              <v-card-text>
                I'm a thing. But, like most politicians, he promised more than he could deliver. You won't have time for sleeping, soldier, not with all the bed making you'll be doing. Then we'll go with that data file! Hey, you add a one and two zeros to that or we walk! You're going to do his laundry? I've got to find a way to escape.
              </v-card-text>
              </div>
            </v-expand-transition>
          </v-card>

      </v-flex>
      <v-flex xs3>
          <v-card class="mx-auto" max-width="344">
            <v-img src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg" height="200px"> </v-img>

            <v-card-title>
              Servicio 2
            </v-card-title>

            <v-card-subtitle>
              Categoria 2
            </v-card-subtitle>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn icon @click="show = !show">
                <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
              </v-btn>
            </v-card-actions>

            <v-expand-transition>
              <div v-show="show">
              <v-divider></v-divider>

              <v-card-text>
                I'm a thing. But, like most politicians, he promised more than he could deliver. You won't have time for sleeping, soldier, not with all the bed making you'll be doing. Then we'll go with that data file! Hey, you add a one and two zeros to that or we walk! You're going to do his laundry? I've got to find a way to escape.
              </v-card-text>
              </div>
            </v-expand-transition>
          </v-card>
      </v-flex>
      <v-flex xs3>
          <v-card class="mx-auto" max-width="344">
            <v-img src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg" height="200px"> </v-img>

            <v-card-title>
              Servicio 3
            </v-card-title>

            <v-card-subtitle>
              Categoria 3
            </v-card-subtitle>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn icon @click="show = !show">
                <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
              </v-btn>
            </v-card-actions>

            <v-expand-transition>
              <div v-show="show">
              <v-divider></v-divider>

              <v-card-text>
                I'm a thing. But, like most politicians, he promised more than he could deliver. You won't have time for sleeping, soldier, not with all the bed making you'll be doing. Then we'll go with that data file! Hey, you add a one and two zeros to that or we walk! You're going to do his laundry? I've got to find a way to escape.
              </v-card-text>
              </div>
            </v-expand-transition>
          </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>
<script>

import Swal from 'sweetalert2';

  export default {
      name: "Inicio",
      methods: {
        cerrarSesion(){
          localStorage.removeItem("token");
          localStorage.removeItem("user");
          this.user = [];
          Swal.fire({
            title: 'Sesion Cerrada',
            text: "Vuelva Pronto",
            icon: 'success',
            confirmButtonText: 'Ok'
          });
        },
        imprimirNombre(){
          let user = localStorage.getItem("user");
          if(user){
            user = JSON.parse(user)
            this.user = user;
            console.log(this.user);
          }
        }
      },
   data () {
     return {
       show: false,
       user: [],
        items: [
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg',
          },
        ],
      }
    },
    created() {
      this.imprimirNombre();
    }
  }
</script>


<style>
.v-card {
transition: opacity .4s ease-in-out;
}

.v-card:not(.on-hover) {
opacity: 0.6;
 }

.show-btns {
color: rgba(255, 255, 255, 1) !important;
}
</style>
