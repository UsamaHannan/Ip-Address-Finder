<template>
  <div>
    <!--     <v-content>
      <v-container>

      </v-container>
    </v-content> -->
    <v-footer dark padless>
      <v-card flat tile width="100%" class="dark white--text text-center">
        <v-card-text>
          <h1 class="pb-4 white--text">You can find us at</h1>
          <a target="_blank" v-bind:key="social.url" v-for="social in socials">
            <v-btn class="mx-4 white--text" icon>
              <v-icon size="24px">{{ social.icon }}</v-icon>
            </v-btn>
          </a>
        </v-card-text>
        <v-row>
          <v-col>
            <v-card-text>
              <h3 class="text ma-4">Product</h3>
              <p><a href="">Create Websites</a></p>
              <p><a href="">Secure Cloud Hosting</a></p>
              <p><a href="">Engage Your Audience</a></p>
              <p><a href="">Website Support</a></p>
            </v-card-text>
          </v-col>
          <v-col>
            <v-card-text>
              <h3 class="text ma-4">Company</h3>
              <p><a href="">About</a></p>
              <p><a href="">Careers</a></p>
              <p><a href="">Support</a></p>
              <p><a href="">Pricing</a></p>
            </v-card-text>
          </v-col>
          <v-col>
            <v-card-text>
              <h3 class="text ma-4">Resources</h3>
              <p><a href="">Website Grader</a></p>
              <p><a href="">Website Support</a></p>
              <p><a href="">eBooks</a></p>
              <p><a href="">Blog</a></p>
            </v-card-text>
          </v-col>
          <v-col>
            <v-card-text>
              <h3 class="text ma-4">Get Help</h3>
              <p><a href="">Help Center</a></p>
              <p><a href="">Contact Us</a></p>
              <p><a href="">Terms</a></p>
              <p><a href="">Login</a></p>
            </v-card-text>
          </v-col>
        </v-row>

        <v-divider></v-divider>

        <v-card-text class="white--text">
          Copyright 1993 - {{ new Date().getFullYear() }}
          <a class="white--text" href="#">Usama Hannan</a>
        </v-card-text>
      </v-card>
    </v-footer>
  </div>
</template>
<script>
export default {
  data: () => ({
    panel: [],
    socials: [
      {
        name: "facebook",
        icon: "mdi-facebook",
        url: "https://codepen.io/jettaz",
      },
      {
        name: "twitter",
        icon: "mdi-twitter",
        url: "https://codepen.io/jettaz",
      },
      { name: "google", icon: "mdi-google", url: "https://codepen.io/jettaz" },
      {
        name: "linkedin",
        icon: "mdi-linkedin",
        url: "https://codepen.io/jettaz",
      },
      {
        name: "instagram",
        icon: "mdi-instagram",
        url: "https://codepen.io/jettaz",
      },
    ],
  }),

  beforeDestroy() {
    if (typeof window !== "undefined") {
      window.removeEventListener("resize", this.onResize, { passive: true });
    }
  },

  mounted() {
    this.onResize();
    window.addEventListener("resize", this.onResize, { passive: true });
  },

  methods: {
    onResize() {
      if (window.innerWidth >= 960) {
        this.panel = [...Array(4).keys()].map((k, i) => i);
      } else {
        this.panel = [];
      }
    },
  },
};
</script>

<style>
@media (min-width: 960px) {
  .v-expansion-panel:before {
    box-shadow: none !important;
  }
  .v-expansion-panel:not(:first-child)::after {
    border-top: none;
  }
}
.resize {
  text-align: center;
}
.resize {
  margin-top: 3rem;
  font-size: 1.25rem;
}
/*RESIZESCREEN ANIMATION*/
.right {
  animation: rightanime 1s linear infinite;
}

.left {
  animation: leftanime 1s linear infinite;
}
@keyframes rightanime {
  50% {
    transform: translateX(10px);
    opacity: 0.5;
  }
  100% {
    transform: translateX(10px);
    opacity: 0;
  }
}
@keyframes leftanime {
  50% {
    transform: translateX(-10px);
    opacity: 0.5;
  }
  100% {
    transform: translateX(-10px);
    opacity: 0;
  }
}

a {
  color: white !important;
}
.text {
  color: white !important;
  font-size: x-large;
}
</style>
