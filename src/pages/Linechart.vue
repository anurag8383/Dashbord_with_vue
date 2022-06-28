<template>
  <div class="deter">
    <div id="chart">
      <h4><b> Awaiting Payment Report </b></h4>
      <apexchart
        class="net"
        type="line"
        width="750"
        height="300"
        :options="optionsNew"
        :series="seriesNew"
      ></apexchart>
    </div>
  </div>
</template>

<script>
import { defineComponent } from "vue";
import VueApexCharts from "vue3-apexcharts";

export default defineComponent({
  name: "LineChart",
  components: {
    apexchart: VueApexCharts,
  },
  data: function () {
    return {
      seriesNew: [
        {
          name: "Community",

          data: [30, 40, 45, 50],
        },

        { name: "Pro", data: [32, 85, 101, 98] },

        { name: "Elite", data: [35, 41, 36, 26] },
      ],
      optionsNew: {
        chart: {
          height: 350,
          width: 5,
          type: "line",
          zoom: {
            enabled: false,
          },
        },
        dataLabels: {
          enabled: false,
        },
        stroke: { width: 1 },
        markers: {
          size: [4, 4, 4],
        },
        title: {
          text: "Product Trends by Month",
          align: "left",
        },
        grid: {
          row: {
            colors: ["#f3f3f3", "transparent"], // takes an array which will be repeated on columns
            opacity: 0.5,
          },
        },
        colors: ["#8B0000", "#00008B", "#006400"],
        xaxis: {
          categories: [
            "1-7 days",
            "8-14 days",
            "15-21 days",
            "22-30 days",
            ">30 days",
          ],
        },
      },
    };
  },
});
</script>
<style scoped>
</style>
