<template>
  <div>
    <Navbar />

    <main class="container">
      <nuxt/>
    </main>
    
  </div>
</template>

<script>
import Navbar from '@/components/Navbar'
export default {
  components: {
    Navbar, 
  }
}
</script>


<style>

</style>

