<template>
  <transition name="page">
    <v-app dark>
      <v-parallax src="https://i.ibb.co/D1zN0g9/parallax.jpg" height="100%">
        <v-navigation-drawer
          v-model="drawer"
          :mini-variant="miniVariant"
          :clipped="clipped"
          fixed
          app
        >
          <v-list>
            <v-list-item
              v-for="(item, i) in items"
              :key="i"
              :to="item.to"
              router
              fixed
              exact
            >
              <v-list-item-action>
                <v-icon>{{ item.icon }}</v-icon>
              </v-list-item-action>
              <v-list-item-content>
                <v-list-item-title>{{ item.title }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </v-navigation-drawer>
        <v-app-bar :clipped-left="clipped" collapse fixed app>
          <v-app-bar-nav-icon @click.stop="drawer = !drawer" />

          <v-toolbar-title class="px-8">{{ title }}</v-toolbar-title>
        </v-app-bar>
        <v-main>
          <v-container style="min-height: 93.5vh; overflow-y: hidden">
            <Nuxt />
          </v-container>
        </v-main>
      </v-parallax>
    </v-app>
  </transition>
</template>

<script>
export default {
  name: "DefaultLayout",
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "mdi-account-tie",
          title: "Главная",
          to: "/",
        },
        {
          icon: "mdi-chart-bubble",
          title: "Вдохновение JS",
          to: "/inspire",
        },
        {
          icon: "mdi-video-vintage",
          title: "CSS-свойство",
          to: "/sem",
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "",
    };
  },
};
</script>
