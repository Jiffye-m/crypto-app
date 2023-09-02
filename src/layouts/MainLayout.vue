<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="frosted-glass" elevated>
      
      <q-btn
      v-if="$route.path.includes('details')"
      flat
      round
      icon="mdi-chevron-left"
      @click="$router.go(-1)"
      ></q-btn>
      
      <q-toolbar>

        <q-toolbar-title>
          Crypto-Currency App
        </q-toolbar-title>

      </q-toolbar>
    </q-header>

    <q-page-container>
      
      <transition
      mode="in-out"
      enter-active-class="animate__animated animate__slideInLeft"
      leave-active-class="animate__animated animate__slideOutRight"
      >
        <router-view />
      </transition>

    </q-page-container>


    <q-footer class="frosted-glass">
      <q-toolbar>
        <q-toolbar-title>
          <div class="flex flex-center">Crypto-App | Miratech</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>

  </q-layout>
</template>

<script>
import "animate.css"

export default {
  name: 'MainLayout'
}
</script>

<style scoped>
.frosted-glass{
  backdrop-filter: blur(7px);
  background-color: #0000001a;
  color: black;
}
</style>