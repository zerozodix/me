<template>
  <v-card flat>
    <v-parallax height="550" class="py-10" src="/images/godzilla.jpg">
      <v-row align="center" justify="space-around">
        <v-avatar size="128">
          <v-img
            src="https://avatars.githubusercontent.com/u/10502651"
            alt="Ken Noize"
          ></v-img>
        </v-avatar>
      </v-row>
      <v-row class="py-5" align="center" justify="center">
        <v-col cols="12">
          <v-row align="center" justify="center">
            <h1>Hi !</h1>
          </v-row>
        </v-col>
      </v-row>
      <v-row class="py-5" align="center" justify="center">
        <v-col cols="12">
          <p class="text-center">My name is Ken</p>
          <p class="text-center">I'm lazy developer</p>
        </v-col>
      </v-row>

      <v-row class="py-5" align="center" justify="center">
        <v-col cols="12">
          <p class="text-center">
            <v-btn fab dark href="https://github.com/zerozodix">
              <v-icon x-large>mdi-github</v-icon>
            </v-btn>
            <v-btn fab dark href="https://www.facebook.com/kentanew">
              <v-icon x-large>mdi-facebook</v-icon>
            </v-btn>
          </p>
        </v-col>
      </v-row>
    </v-parallax>

    <v-row class="py-5" align="center" justify="center">
      <v-col cols="12">
        <h1 class="text-center">Adventure Log</h1>
      </v-col>
    </v-row>

    <MeAdventureLog></MeAdventureLog>
  </v-card>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";

@Component
export default class IndexPage extends Vue {}
</script>
