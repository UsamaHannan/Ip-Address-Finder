<template>
  <v-app>
    <div class="check1">
      <MainHeader />
      <v-main>
        <MainSection />
      </v-main>
      <MainInfo />
      <MainSecurity />

      <MainFooter />
    </div>
  </v-app>
</template>

<script>
import MainSection from "./components/MainSection";
import MainHeader from "./components/MainHeader";
import MainFooter from "./components/MainFooter";
import MainInfo from "./components/MainInfo";
import MainSecurity from "./components/MainSecurity";

export default {
  name: "App",

  components: {
    MainSection,
    MainHeader,
    MainFooter,
    MainInfo,
    MainSecurity,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
.check1 {
  background-color: rgb(232, 235, 234) !important;
}
</style>
