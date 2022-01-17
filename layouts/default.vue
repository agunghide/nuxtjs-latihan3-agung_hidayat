<template>
  <div>
    <nav 
      class="
      bg-white 
        flex 
        justify-between 
        py-4
        pl-8
        pr-10
        shadow-sm
      "
    >
      <div class="flex items-center font-bold text-3xl px-3">
        The<span class="text-green-500">Ranch</span>
      </div>
      <ul 
        class="
          flex 
          text-green-700 
          space-x-4 
          font-medium
          items-center
        "
      >
        <li v-for="(menu, index) in menus" :key="`menu-${index}`" class="group">
          <nuxt-link class="nav-item" :class="{'active' : $nuxt.$route.path === menu.route }" :to="menu.route">
            {{ menu.title }}
          </nuxt-link>

          <div v-if="menu.submenu != 0" class="submenu group-hover:block z-10">
            <nuxt-link 
              v-for="(sub, index) in menu.submenu" 
              :to="sub.route" 
              :key="index" 
              class="submenu-item flex" 
              :class="{'active' : $nuxt.$route.path === sub.route || JSON.stringify(sub.route.params) === JSON.stringify($nuxt.$route.params) }"
            >
                {{ sub.title }}
            </nuxt-link>
          </div>
        </li>
      </ul>
    </nav>
    <div class="w-full">
      <nuxt />
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      menus: [
        { title: 'Home', route: '/', submenu: [] },
        { title: 'About', route: '/about', submenu: [] },
        { title: 'Kategori', route: '', submenu: [
          { title: 'Wisata Alam', route: {name:'category-slug', params: { slug: 'wisata-alam'}}},
          { title: 'Wisata Buatan', route: {name:'category-slug', params: { slug: 'wisata-buatan'}}}
        ] },
        { title: 'Gallery', route: '/gallery', submenu: [] },
      ]
    }
  },
}
</script>
