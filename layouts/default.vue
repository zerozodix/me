<template>
  <v-app dark>
    <v-navigation-drawer v-model="drawer" app>
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
    </v-app-bar>
    <v-main>
      <v-container>
        <v-row justify="center" align="center">
          <v-col class="my-auto" cols="12" sm="10" lg="10" md="10" xl="8">
            <nuxt />
          </v-col>
        </v-row>
      </v-container>
    </v-main>
    <v-footer>
      <v-btn fab dark depressed x-small href="https://github.com/zerozodix">
        <v-icon>mdi-github</v-icon>
      </v-btn>
      <v-btn
        fab
        dark
        depressed
        x-small
        href="https://www.facebook.com/kentanew"
      >
        <v-icon>mdi-facebook</v-icon>
      </v-btn>
    </v-footer>
  </v-app>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";

@Component
export default class DefaultLayout extends Vue {
  drawer: boolean = false;
  title: string = "Nuttapon Tonout";

  get items(): any {
    let data = [
      {
        icon: "mdi-apps",
        title: "Me",
        to: "/",
      },
    ];
    return data;
  }
}
</script>
