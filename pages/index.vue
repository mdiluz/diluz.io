<template>
  <v-container fill-height fluid class="container">
    <v-row align="center" justify="center">
      <v-col class="column"
        ><v-card class="services">
          <v-row justify="center">
            <img
              class="service"
              src="~assets/images/services/GitHub/GitHub-Mark-Light-120px-plus.png"
              @click="gotoGithub"
            />
          </v-row>
        </v-card>
        <v-card class="card">
          <v-card-title class="headline justify-center">Check out the diluz.ios</v-card-title>
          <v-card-text>
            <v-row class="pa-2" align="center" justify="center">
              <nuxt-link to="sebastian" class="unstyled-link">
                <v-btn>Sebastian Di Luzio</v-btn>
              </nuxt-link>
            </v-row>
            <v-row class="pa-2" align="center" justify="center">
              <nuxt-link to="marc" class="unstyled-link">
                <v-btn>Marc Di Luzio</v-btn>
              </nuxt-link>
            </v-row>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
    <v-snackbar v-model="snackbar" color="green" light centered
      >{{ alert }}
      <template v-slot:action="{ attrs }">
        <v-btn text v-bind="attrs" @click="snackbar = false"> Close </v-btn>
      </template></v-snackbar
    >
  </v-container>
</template>

<script lang="ts">
import { Component } from 'nuxt-property-decorator';
import Vue from 'vue';
import Logo from '~/components/Logo.vue';
import VuetifyLogo from '~/components/VuetifyLogo.vue';

@Component({
  components: {
    Logo,
    VuetifyLogo,
  },
  layout: 'dvd',
})
export default class homePage extends Vue {
  gotoGithub() {
    window.open('https://github.com/T0TProduction/diluz.io', '_blank');
  }

  snackbar = false;

  alert: string | false = false;

  /* underConstructionNotice() {
    this.alert = 'Still under construction.';
    this.snackbar = true;
  } */
}
</script>

<style lang="scss" scoped>
.unstyled-link {
  text-decoration: none;
}
.container {
  background-color: none;
}
.column {
  max-width: 400px;
}
.card {
  margin-top: 2rem;
  text-align: center;
}
.services {
  background: none;
  box-shadow: none !important;
}
.service {
  height: 96px;
  cursor: pointer;
}
@media screen and (max-width: 600px) {
  .service {
    height: 64px;
  }
}
</style>
