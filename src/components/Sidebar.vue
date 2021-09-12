<template>
  <div>
    <b-button v-b-toggle.sidebar-no-header>Toggle Sidebar</b-button>
    <b-sidebar id="sidebar-no-header" aria-labelledby="sidebar-no-header-title" no-header shadow>
      <template #default="{ hide }">
        <div class="p-3">
          <h4 id="sidebar-no-header-title">Categorías</h4>
          
          <nav class="mb-3">
            <b-nav vertical>

              <b-nav-item v-for="(category, index) in categories" :key="index" >{{category.name}}</b-nav-item>
            </b-nav>
          </nav>
          <b-button variant="primary" block @click="hide">Cerrar</b-button>
        </div>
      </template>
    </b-sidebar>
  </div>
</template>


<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
	name: 'Sidebar',
	components: {},
  data () {
    return {
      categories: []
    }
  },
  methods: {
    async getCategories() {
      const data = await fetch('http://sva.talana.com:8000/api/product-category/')
      const array = await data.json()
      this.categories = array
    }
  },
  created() {
    this.getCategories()
  }
};
</script>