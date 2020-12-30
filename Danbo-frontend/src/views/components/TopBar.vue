<template>
  <v-app-bar
    bottom
    color="#6A76AB"
    dark
    shrink-on-scroll
    prominent
    src="https://picsum.photos/1920/1080?random"
    fade-img-on-scroll
    scroll-target="#scrolling-techniques-3"
  >

    <v-toolbar-title>
      <router-link to="/home">Danbo</router-link>
    </v-toolbar-title>

    <v-spacer></v-spacer>
    <v-text-field
      v-model="keyword"
      label="Search Something"
      dark
      flat
      solo-inverted
      hide-details
      clearable
      clear-icon="mdi-close-circle-outline"
    ></v-text-field>
    <v-btn icon @click="this.search">
      <v-icon>mdi-magnify</v-icon>
    </v-btn>
  </v-app-bar>
</template>

<script>
export default {
  name: "TopBar",

  components: {},

  data: () => ({
    now: "",
    keyword: "",
  }),
  mounted: function() {
    console.log(this.$route.path);
    this.now = "topic";
  },

  computed: {},

  methods: {
    change: function(path) {
      this.$router.push("/" + path);
    },
    async search() {
      this.$router.push({ path: "/blank", query: { keyword: this.keyword } });
    },
  },
};
</script>

<style scoped>
.router-link-active {
  text-decoration: none;
  color: rgb(255, 255, 255);
}
.router-link {
  text-decoration: none;
  color: rgb(255, 255, 255);
}
.router-link-hover {
  text-decoration: none;
  color: black;
}
a {
  text-decoration: none;
}
.v-application a {
  color: white;
}
</style>
