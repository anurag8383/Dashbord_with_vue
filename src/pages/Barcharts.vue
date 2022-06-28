<template>
  <div id="myClass">
    <div class="columnchart">
      <Lastgraph />
    </div>
    <!-- <div id="chart">
      <h4><b>Total Active Users</b></h4>
      <apexchart
        type="bar"
        width="750"
        height="300"
        :options="chartOptions"
        :series="series"
      ></apexchart>
    </div> -->
    <div id="chart2">
      <q-card>
        <q-card-section>
          <p><b>Mobile Registration Report</b></p>
          <apexchart
            type="pie"
            :options="optionsPie"
            :series="seriesPie"
          ></apexchart>
        </q-card-section>
      </q-card>
    </div>
  </div>
</template>

<script>
import { defineComponent } from "vue";
import VueApexCharts from "vue3-apexcharts";
import { getCssVar } from "quasar";
import Lastgraph from "src/pages/Lastgraph.vue";

export default defineComponent({
  name: "BarCharts",
  components: {
    apexchart: VueApexCharts,
    Lastgraph,
  },
  data: function () {
    return {
      seriesPie: [76, 55],

      optionsPie: {
        angle: {
          startAngle: 120,
          endAngle: 360,
        },
        chart: {
          startAngle: 120,
          endAngle: 360,
          width: 380,
          type: "pie",
        },

        labels: ["Non Registered", "Registered"],
        responsive: [
          {
            breakpoint: 480,
            options: {
              chart: {
                width: 200,
              },
              legend: {
                position: "bottom",
              },
            },
          },
        ],
        dataLabels: {
          enabled: false,
        },
        colors: ["#77DD77", "#FF0000"],
      },
      chartOptions: {
        chart: {
          type: "bar",
          height: 350,
          toolbar: {
            show: false,
          },
        },

        plotOptions: {
          bar: {
            horizontal: false,
            columnWidth: "55%",
            endingShape: "rounded",
          },
        },
        dataLabels: {
          enabled: false,
        },
        colors: [
          getCssVar("negative"),
          getCssVar("primary"),
          getCssVar("positive"),
        ],
        stroke: {
          show: true,
          width: 2,
          colors: ["transparent"],
        },
        xaxis: {
          categories: [
            "01 Feb",
            "02 Feb",
            "03 Feb",
            "04 Feb",
            "05 Feb",
            "06 Feb",
            "07 Feb",
          ],
        },
        yaxis: {
          opposite: true,
          title: {
            text: "Users",
          },
        },
        fill: {
          opacity: 1,
        },
        tooltip: {
          y: {
            formatter: function (val) {
              return "$ " + val + " thousands";
            },
          },
        },
      },
    };
  },
});
</script>
<style>
.columnchart {
  width: 65%;
}
#myClass {
  display: flex;
  justify-content: space-between;
  margin: 5% 2%;
  /* flex-direction: row; */
  /* padding-left: 30px; */
}
#chart2 {
  margin-top: +80px;
  /* padding-left: 220px; */
  width: 28%;
  /* margin: 0% 1%; */
}
p {
  font-size: large;
  text-align: center;
}
</style>
