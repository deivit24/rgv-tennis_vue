<template lang="pug">
v-card.mx-auto.overflow-hidden
  v-app-bar(
    color='white',
    fixed,
    )
    v-app-bar-nav-icon(@click='drawer = true')
    v-toolbar-title: v-img(src="../assets/logo2.png" width=100 )
  v-navigation-drawer(v-model='drawer', fixed, temporary)
    v-list(nav, dense)
      v-list-item-group(v-model='group', active-class='blue--text text--accent-4')
        v-list-item(v-for="link in links" :to="link.to")
          v-list-item-icon
            v-icon {{link.icon}}
          v-list-item-title {{link.title}}
       


</template>

<script>
export default {
  name: "NavBar",
  data: () => ({
    drawer: false,
    group: null,
    links: [
      {
        title: "Home",
        icon: "mdi-home",
        to: "/",
      },
      {
        title: "About",
        icon: "mdi-alpha-a-circle-outline",
        to: "/about",
      },
      {
        title: "Coaches",
        icon: "mdi-human-greeting",
        to: "/coaches",
      },
      {
        title: "Programs",
        icon: "mdi-tennis",
        to: "/programs",
      },
      {
        title: "Contact",
        icon: "mdi-phone",
        to: "/contact",
      },
    ],
  }),
};
</script>
