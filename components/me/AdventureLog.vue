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
          :color="item.current ? item.color : '#808080'"
          :icon="item.current ? 'mdi-map-marker-circle' : 'mdi-lock-open'"
          large
        >
          <template v-slot:opposite>
            <span
              :class="`headline font-weight-bold ${item.color}--text`"
              v-text="item.year"
            ></span>
          </template>
          <v-row class="my-2">
            <h2 :class="`headline font-weight-bold mb-4 ${item.color}--text`">
              {{ item.title }}
            </h2>
            <div class="subtitle-1">
              {{ item.description }}
            </div>
          </v-row>
          <v-row class="my-2">
            <v-col cols="12" sm="6" lg="4" md="4" xl="4" class="py-0">
              <span
                :class="`subtitle-1 font-weight-light mb-4 ${item.color}--text`"
              >
                Language
              </span>
            </v-col>
            <v-col cols="12" sm="6" lg="8" md="8" xl="8" class="pt-0">
              <v-avatar
                v-for="tool in item.lang"
                :key="tool.tooltips"
                size="40"
              >
                <v-img :src="tool.src"></v-img>
                <template> </template>
              </v-avatar>
            </v-col>
          </v-row>
          <v-row class="my-2">
            <v-col cols="12" sm="6" lg="4" md="4" xl="4" class="py-0">
              <span
                :class="`subtitle-1 font-weight-light mb-4 ${item.color}--text`"
              >
                Framework
              </span>
            </v-col>
            <v-col cols="12" sm="6" lg="8" md="8" xl="8" class="pt-0">
              <v-avatar
                v-for="tool in item.framework"
                :key="tool.tooltips"
                size="40"
              >
                <v-img :src="tool.src"></v-img>
                <template> </template>
              </v-avatar>
            </v-col>
          </v-row>
          <v-row class="my-2">
            <v-col cols="12" sm="6" lg="4" md="4" xl="4" class="py-0">
              <span
                :class="`subtitle-1 font-weight-light mb-4 ${item.color}--text`"
              >
                Database
              </span>
            </v-col>
            <v-col cols="12" sm="6" lg="8" md="8" xl="8" class="pt-0">
              <v-avatar
                v-for="tool in item.database"
                :key="tool.tooltips"
                size="40"
              >
                <v-img :src="tool.src"></v-img>
                <template> </template>
              </v-avatar>
            </v-col>
          </v-row>
          <v-row class="my-2">
            <v-col cols="12" sm="6" lg="4" md="4" xl="4" class="py-0">
              <span
                :class="`subtitle-1 font-weight-light mb-4 ${item.color}--text`"
              >
                ETC Tools
              </span>
            </v-col>
            <v-col cols="12" sm="6" lg="8" md="8" xl="8" class="pt-0">
              <v-avatar
                v-for="tool in item.toolsIcon"
                :key="tool.tooltips"
                size="40"
              >
                <v-img :src="tool.src"></v-img>
                <template> </template>
              </v-avatar>
            </v-col>
          </v-row>
        </v-timeline-item>
      </v-timeline>
    </v-col>
  </v-row>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";

interface IconDetail {
  src: string;
  tooltips: string;
}

interface Adventure {
  color: string;
  year: number;
  current: boolean;
  title?: string;
  description?: string;
  toolsIcon?: IconDetail[];
  lang?: IconDetail[];
  framework?: IconDetail[];
  database?: IconDetail[];
}

@Component
export default class AdventureLog extends Vue {
  items: Adventure[] = [
    {
      current: true,
      color: "cyan",
      year: 2019,
      title: "Krungthai Bank",
      description: "",
      lang: [
        {
          src: "/images/skills/typescript.svg",
          tooltips: "Typescript",
        },
        {
          src: "/images/skills/c_sharp.svg",
          tooltips: "C#",
        },
        {
          src: "/images/skills/cpp.svg",
          tooltips: "C++",
        },
        {
          src: "/images/skills/golang.svg",
          tooltips: "GoLang",
        },
        {
          src: "/images/skills/java.svg",
          tooltips: "Java",
        },
      ],
      framework: [
        {
          src: "/images/skills/vue.svg",
          tooltips: "Vue.js",
        },
        {
          src: "/images/skills/dotnet.svg",
          tooltips: ".Net Framework",
        },
      ],
      database: [
        {
          src: "/images/skills/microsoft_sql_server.jpg",
          tooltips: "MS Sql server",
        },
        {
          src: "/images/skills/oracle_db.png",
          tooltips: "Oracle Database",
        },
      ],
      toolsIcon: [
        {
          src: "/images/skills/IIS.svg",
          tooltips: "IIS",
        },
        {
          src: "/images/skills/apache_kafka.png",
          tooltips: "Apache Kafka",
        },
        {
          src: "/images/skills/kubernetes.svg",
          tooltips: "K8S",
        },
        {
          src: "/images/skills/microsoft_sql_server.jpg",
          tooltips: "MS Sql server",
        },
        {
          src: "/images/skills/nginx.svg",
          tooltips: "nginx",
        },
        {
          src: "/images/skills/redis.png",
          tooltips: "Redis",
        },
      ],
    },
    {
      current: false,
      color: "indigo",
      year: 2016,
      title: "Kiatnakin Bank",
      description: "",
      lang: [
        {
          src: "/images/skills/c_sharp.svg",
          tooltips: "C#",
        },
        {
          src: "/images/skills/java.svg",
          tooltips: "Java",
        },
      ],
      framework: [
        {
          src: "/images/skills/dotnet.svg",
          tooltips: ".Net Framework",
        },
      ],
      database: [
        {
          src: "/images/skills/microsoft_sql_server.jpg",
          tooltips: "MS Sql server",
        },
      ],
      toolsIcon: [
        {
          src: "/images/skills/IIS.svg",
          tooltips: "IIS",
        },
      ],
    },
    {
      current: false,
      color: "amber",
      year: 2015,
      title: "Krungsri Bank",
      description: "",
      lang: [
        {
          src: "/images/skills/c_sharp.svg",
          tooltips: "C#",
        },
      ],
      framework: [
        {
          src: "/images/skills/dotnet.svg",
          tooltips: ".Net Framework",
        },
      ],
      database: [
        {
          src: "/images/skills/microsoft_sql_server.jpg",
          tooltips: "MS Sql server",
        },
      ],
      toolsIcon: [
        {
          src: "/images/skills/IIS.svg",
          tooltips: "IIS",
        },
      ],
    },
    {
      current: false,
      color: "blue",
      year: 2012,
      title: "Ecartstudio",
      description: "",
      lang: [
        {
          src: "/images/skills/coffeescript.jpg",
          tooltips: "CoffeeScript",
        },
        {
          src: "/images/skills/c_sharp.svg",
          tooltips: "C#",
        },
      ],
      framework: [
        {
          src: "/images/skills/dotnet.svg",
          tooltips: ".Net Framework",
        },
      ],
      database: [
        {
          src: "/images/skills/microsoft_sql_server.jpg",
          tooltips: "MS Sql server",
        },
      ],
      toolsIcon: [
        {
          src: "/images/skills/IIS.svg",
          tooltips: "IIS",
        },
      ],
    },
    {
      current: false,
      color: "orange",
      year: 2011,
      title: "Soft Gear",
      description: "",
      lang: [
        {
          src: "/images/skills/c_sharp.svg",
          tooltips: "C#",
        },
      ],
      framework: [
        {
          src: "/images/skills/dotnet.svg",
          tooltips: ".Net Framework",
        },
      ],
      database: [
        {
          src: "/images/skills/microsoft_sql_server.jpg",
          tooltips: "MS Sql server",
        },
      ],
      toolsIcon: [
        {
          src: "/images/skills/IIS.svg",
          tooltips: "IIS",
        },
      ],
    },
  ];
}
</script>
