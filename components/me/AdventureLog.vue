<template>
  <v-row class="py-5" align="center" justify="center">
    <v-col cols="12">
      <v-timeline
        align-center
        :dense="$vuetify.breakpoint.smAndDown"
        class="px-5"
      >
        <v-timeline-item
          v-for="(item, i) in items"
          :key="i"
          :color="item.color"
          :icon="item.icon"
          large
        >
          <template v-slot:opposite>
            <span
              :class="`headline font-weight-bold ${item.color}--text`"
              v-text="item.year"
            ></span>
          </template>
          <div class="py-4">
            <h2 :class="`headline font-weight-light mb-4 ${item.color}--text`">
              {{ item.title }}
            </h2>
            <div>
              {{ item.description }}
            </div>
          </div>
        </v-timeline-item>
      </v-timeline>
    </v-col>
  </v-row>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";

interface IconDetail {
  icon: string;
  tooltips: string;
}

interface Adventure {
  color: string;
  year: number;
  icon: string;
  title?: string;
  description?: string;
  toolsIcon?: IconDetail[];
}

@Component
export default class AdventureLog extends Vue {
  items: Adventure[] = [
    {
      color: "cyan",
      year: 2019,
      icon: "mdi-star",
      title: "Krungthai Bank",
      description: "test",
    },
    {
      color: "green",
      year: 2016,
      icon: "mdi-star",
      title: "Kiatnakin Bank",
      description: "test",
    },
    {
      color: "pink",
      year: 2015,
      icon: "mdi-star",
      title: "Krungsri Bank",
      description: "test",
    },
    {
      color: "amber",
      year: 2012,
      icon: "mdi-star",
      title: "Ecart Studio",
      description: "test",
    },
    {
      color: "orange",
      year: 2011,
      icon: "mdi-star",
      title: "Soft Gear",
      description: "test",
    },
  ];
}
</script>
