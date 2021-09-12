<template>
  <div class="home">
    <section class="header">
      <Header />
    </section>
    <section class="hero">
        <sidebar />
        <div>
          <products />
        </div>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
import Sidebar from '@/components/Sidebar'
import Header from '@/components/Header'
import Products from '@/components/Products'


export default {
  name: 'Home',
  components: {
    Header,
    Sidebar,
    Products
  }
}
</script>
