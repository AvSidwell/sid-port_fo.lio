<template>
  <NavBar />
  <SideBar />
  <router-view />
</template>
<script>
import SideBar from '@/components/Side-Bar.vue'
import NavBar from '@/components/Nbar.vue'

export default {
  components: {
    SideBar,
    NavBar
  }
}
</script>