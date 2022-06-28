<template>
  <div class="q-pa-md items-start q-gutter-md" id="mycard">
    <q-card bordered class="bg-white-9 my-card">
      <q-separator dark inset />

      <q-card-section class="chart-section">
        <apexchart
          height="235"
          width="235"
          type="donut"
          :options="options"
          :series="series"
          class="chart"
        ></apexchart>
      </q-card-section>
    </q-card>
  </div>
</template>
<script>
import { defineComponent } from "vue";

import { getCssVar } from "quasar";

import VueApexCharts from "vue3-apexcharts";

export default defineComponent({
  name: "NewPie",

  components: {
    apexchart: VueApexCharts,
  },

  data() {
    return {
      options: {
        title: {
          text: "Earning Report",

          align: "center",

          style: {
            color: "black",
          },
        },

        labels: ["Elie", "Skill Pack", "Pro"],

        plotOptions: {
          pie: {
            donut: {
              size: "78%",

              labels: { show: true, total: { show: true, showAlways: true } },
            },
          },
        },
        dataLabels: {
          enabled: false,
        },

        colors: [
          getCssVar("positive"),

          getCssVar("negative"),

          getCssVar("primary"),
        ],

        legend: {
          show: true,
          position: "bottom",
          horizontalAlign: "center",
        },
        markers: {
          size: 4,
          hover: {
            sizeOffset: 6,
          },
        },
        xaxis: {
          categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998],
        },
      },
      series: [60, 60, 60],
    };
  },
});
</script>
