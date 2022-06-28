<template>
  <div class="my-last">
    <div class="ner">
      <div class="heading">
        <h5><b>First Look & Cyber Talk Registration</b></h5>
        <div class="dates">
          <div class="fromdate">
            <p>From</p>
            <q-btn icon="event" flat>
              <q-popup-proxy
                @before-show="updateProxy"
                cover
                transition-show="scale"
                transition-hide="scale"
              >
                <q-date v-model="proxyDate">
                  <div class="row items-center justify-end q-gutter-sm">
                    <q-btn label="Cancel" flat v-close-popup />
                    <q-btn
                      label="OK"
                      color="primary"
                      flat
                      @click="save"
                      v-close-popup
                    />
                  </div>
                </q-date>
              </q-popup-proxy>
            </q-btn>
          </div>
          <div class="q-pa-md fromdate">
            <p>To</p>
            <q-btn icon="event" flat>
              <q-popup-proxy
                @before-show="updateProxy"
                cover
                transition-show="scale"
                transition-hide="scale"
              >
                <q-date v-model="proxyDate">
                  <div class="row items-center justify-end q-gutter-sm">
                    <q-btn label="Cancel" flat v-close-popup />
                    <q-btn
                      label="OK"
                      color="primary"
                      flat
                      @click="save"
                      v-close-popup
                    />
                  </div>
                </q-date>
              </q-popup-proxy>
            </q-btn>
          </div>
        </div>
      </div>
      <apexchart
        type="bar"
        height="240"
        :options="chartOptions"
        :series="series"
      ></apexchart>
    </div>
  </div>
</template>
<script>
import VueApexCharts from "vue3-apexcharts";
import { defineComponent } from "vue";
import { getCssVar } from "quasar";
import { ref } from "vue";

export default defineComponent({
  name: "LastGraph",

  components: {
    apexchart: VueApexCharts,
  },

  data: function () {
    return {
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
            columnWidth: "40%",
            endingShape: "rounded",
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
        colors: [
          getCssVar("primary"),
          getCssVar("positive"),
          // getCssVar("positive"),
        ],
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
          min: 0,
          max: 40,
          tickAmount: 8,
          title: {
            text: "Users",
          },
        },
        fill: {
          opacity: 1,
        },
        // colors: ["#77DD77", "#FF0000"],
        // legend: { position: "bottom" },
      },
      series: [
        {
          name: "First Look",
          data: [12, 14, 20, 17, 18, 18, 18],
        },
        {
          name: "Cyber Talk",
          data: [15, 17, 18, 21, 22, 22, 21],
        },
      ],
    };
  },
  setup() {
    const date = ref("2019/03/01");
    const proxyDate = ref("2019/03/01");

    return {
      date,
      proxyDate,

      updateProxy() {
        proxyDate.value = date.value;
      },

      save() {
        date.value = proxyDate.value;
      },
    };
  },
});
</script>

<style scoped>
.my-last {
  margin-top: 50px;
  display: flex;
  flex-direction: row;

  gap: 100px;
  margin-bottom: 140px;
  margin-left: 35px;
}
.heading {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.dates {
  display: flex;
  width: 20%;
  margin-right: 7%;
}
p {
  margin-right: 10%;
}
.fromdate {
  display: flex;
  /* margin-right: 2%; */
  align-items: center;
}
.iconss {
  cursor: pointer;
  background-color: red;
}
.ner {
  width: 100%;
}
</style>
 <!-- <div class="ner">
      <p><b>Pro & Elite Comparison</b></p>
      <apexchart
        type="bar"
        height="240"
        width="385"
        :options="chartOptions"
        :series="series"
      ></apexchart>
    </div>
    <div class="ner">
      <p><b>Community To Paid Upgrade</b></p>
      <apexchart
        type="bar"
        height="240"
        width="385"
        :options="chartOptions"
        :series="series"
      ></apexchart>
    </div> -->
