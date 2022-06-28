<template>
  <div id="Stress">
    <q-card class="my-card next">
      <q-card-section>
        <h5 class="heading">User Reports</h5>
        <apexcharts
          type="donut"
          height="235"
          :options="optionsDonut"
          :series="seriesDonut"
        ></apexcharts>
      </q-card-section>
    </q-card>
    <!-- <q-card class="next">
      <q-card-section>
        <div id="chart">
          <h5>Registration Reports</h5>
          <apexcharts
            type="donut"
            height="235"
            :options="optionsDonut1"
            :series="seriesDonut1"
          ></apexcharts>
        </div>
      </q-card-section>
    </q-card> -->
    <!-- <q-card class="next">
      <q-card-section>
        <div id="chart">
          <h5>Earning Reports</h5>
          <apexcharts
            type="donut"
            height="235"
            :options="optionsDonut2"
            :series="seriesDonut2"
          ></apexcharts>
        </div>
      </q-card-section>
    </q-card> -->
    <q-card class="next">
      <q-card-section bordered class="bg-white-9">
        <q-separator dark inset />
        <div id="chart">
          <h5 class="heading">Verification Reports</h5>
          <apexcharts
            type="donut"
            height="235"
            :options="optionsDonut3"
            :series="seriesDonut3"
          ></apexcharts>
        </div>
      </q-card-section>
    </q-card>
    <q-card class="next">
      <q-card-section>
        <div id="chart">
          <h5 class="heading">Platform Reports</h5>
          <apexcharts
            type="donut"
            height="235"
            :options="optionsDonut4"
            :series="seriesDonut4"
          ></apexcharts>
        </div>
      </q-card-section>
    </q-card>
  </div>

  <Barcharts />
  <newgraphs-vue />
</template>

<script>
import { defineComponent, ref } from "vue";
import VueApexCharts from "vue3-apexcharts";
import Barcharts from "../pages/Barcharts.vue";
// import NewgraphsVue from "src/pages/Newgraphs.vue";
// import Lastgraph from "src/pages/Lastgraph.vue";

// import EssentialLink from "components/EssentialLink.vue";

export default defineComponent({
  name: "MainLayout",
  components: {
    // EssentialLink,
    apexcharts: VueApexCharts,
    Barcharts,
    // NewgraphsVue,
    // Lastgraph,
  },
  data: function () {
    return {
      optionsDonut: {
        dataLabels: {
          enabled: false,
        },
        labels: ["Active Users", "InActive Users"],
        plotOptions: {
          pie: {
            donut: {
              size: "80%",
              labels: {
                show: true,
                total: {
                  show: true,
                  showAlways: true,
                  fontSize: "20px",
                  // color: "#03fc14",
                },
              },
            },
          },
        },
        colors: ["#8B0000", "#00008B"],
        legend: {
          show: true,
          position: "bottom",
          horizontalAlign: "center",
        },
      },
      seriesDonut: [57, 43],

      optionsDonut1: {
        dataLabels: {
          enabled: false,
        },
        labels: ["Community", "Elite", "Pro"],
        plotOptions: {
          pie: {
            donut: {
              size: "80%",
              labels: {
                show: true,
                total: {
                  show: true,
                  showAlways: true,
                  fontSize: "20px",
                  // color: "#03fc14",
                },
              },
            },
          },
        },
        colors: ["#8B0000", "#00008B", "#006400"],
        legend: {
          show: true,
          position: "bottom",
          horizontalAlign: "center",
        },
      },
      seriesDonut1: [67, 23, 10],
      optionsDonut2: {
        dataLabels: {
          enabled: false,
        },
        labels: ["Elite", "Skill Pack", "Pro"],
        plotOptions: {
          pie: {
            donut: {
              size: "80%",
              labels: {
                show: true,
                total: {
                  show: true,
                  showAlways: true,
                  fontSize: "20px",
                  // color: "#03fc14",
                },
              },
            },
          },
        },
        colors: ["#8B0000", "#00008B", "#006400"],
        legend: {
          show: true,
          position: "bottom",
          horizontalAlign: "center",
        },
      },
      seriesDonut2: [60, 60, 60],
      optionsDonut3: {
        dataLabels: {
          enabled: false,
        },
        labels: ["Verified", "Non-Verified"],
        plotOptions: {
          pie: {
            donut: {
              size: "80%",
              labels: {
                show: true,
                total: {
                  show: true,
                  showAlways: true,
                  fontSize: "20px",
                  // color: "#03fc14",
                },
              },
            },
          },
        },
        colors: ["#8B0000", "#00008B", "#006400"],
        legend: {
          show: true,
          position: "bottom",
          horizontalAlign: "center",
        },
      },
      seriesDonut3: [60, 40],
      optionsDonut4: {
        dataLabels: {
          enabled: false,
        },
        labels: ["Web", "Ios", "Android"],
        plotOptions: {
          pie: {
            donut: {
              size: "80%",
              labels: {
                show: true,
                total: {
                  show: true,
                  showAlways: true,
                  fontSize: "20px",
                  // color: "#03fc14",
                },
              },
            },
          },
        },
        colors: ["#8B0000", "#00008B", "#006400"],
        legend: {
          show: true,
          position: "bottom",
          horizontalAlign: "center",
        },
      },
      seriesDonut4: [67, 23, 10],
    };
  },
});
</script>
<style>
#Stress {
  display: flex;
  justify-content: space-evenly;
  flex-direction: row;
  gap: 3em;
  margin-top: 40px;
  padding-left: 30px;
  background-color: rgb(232, 232, 232);
  padding: 4% 0%;
}
.heading {
  text-align: center;
}
.next {
  /* justify-content: center; */
  border-radius: 10%;
  /* box-shadow: 2px solid gray; */
  width: 20%;
  /* border: 1px solid black; */
}
.next:hover {
  background-color: black;
}
#chart .h5 {
  text-align: center;
}
</style>
