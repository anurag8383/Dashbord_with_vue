<template>
  <div class="detter">
    <div id="chart">
      <h4><b>Membership Plans</b></h4>
      <apexchart
        type="line"
        width="750"
        height="300"
        :options="chartOptions"
        :series="series"
      ></apexchart>
    </div>
    <div class="deter">
      <div id="chart">
        <h4><b> Awaiting Payment Report </b></h4>
        <apexchart
          class="net"
          type="line"
          width="450"
          height="300"
          :options="optionsNew"
          :series="seriesNew"
        ></apexchart>
      </div>
    </div>
  </div>
</template>
8

<script>
import { defineComponent } from "vue";
import VueApexCharts from "vue3-apexcharts";
import { getCssVar } from "quasar";

export default defineComponent({
  name: "NewGraphs",
  components: {
    apexchart: VueApexCharts,
  },
  data: function () {
    return {
      series: [
        {
          name: "Community",

          data: [30, 40, 45, 50, 49, 60],
        },

        { name: "Pro", data: [32, 85, 101, 98, 87, 95] },

        { name: "Elite", data: [35, 41, 36, 26, 45, 48] },
      ],
      chartOptions: {
        chart: {
          height: 350,
          width: 5,
          type: "line",
          zoom: {
            enabled: false,
          },
          toolbar: {
            show: false,
          },
        },
        dataLabels: {
          enabled: false,
        },
        stroke: { width: 1 },
        markers: {
          size: [4, 4, 4],
        },

        grid: {
          borderColor: "#000",
          strokeDashArray: 2,
        },
        colors: [
          getCssVar("negative"),
          getCssVar("primary"),
          getCssVar("positive"),
        ],
        xaxis: {
          categories: [
            "Jan",
            "Feb",
            "Mar",
            "Apr",
            "May",
            "Jun",
            "Jul",
            "Aug",
            "Sep",
          ],
        },
      },
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
          toolbar: {
            show: false,
          },
        },
        dataLabels: {
          enabled: false,
        },
        stroke: { width: 1 },
        markers: {
          size: [4, 4, 4],
        },

        grid: {
          borderColor: "#000",
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
        yaxis: {
          opposite: true,
          title: {
            text: "Amount",
          },
        },
      },
    };
  },
});
</script>
<style>
.detter {
  margin-top: 50px;
  display: flex;
  flex-direction: row;

  gap: 100px;
  margin-bottom: 140px;
  margin-left: 35px;
}
</style>

