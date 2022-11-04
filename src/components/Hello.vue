<template>
  <div class="home">
    <h1>{{ msg }}</h1>
    <p>The data from the Messari Bitcoin Website</p>
    <!-- <button @click="fetchMBCP">Click Me</button> -->

    <p>The data from the API is:</p>
    <!--The result has all the data & is displayed below-->
    <!-- <p>Result:{{ result }}</p> -->
    <div v-for="res_obj in result" :key="res_obj.id" class="result">
      <p>Data Id:{{ res_obj.id }}</p>
      <!--  <p>Assets:{{ assets }}</p>
      <p>Assets.value: {{}}</p> -->
      <p>Symbol: {{ res_obj.symbol }}</p>
      <p>Slug:{{ res_obj.slug }}</p>
      <p>Market Data:{{ res_obj.metrics.market_data }}</p>
      <p>Price_usd:{{ res_obj.metrics.market_data.price_usd }}</p>
    </div>
  </div>
</template>
<script>
// @ is an alias to /src
import { ref, unRef } from "vue";
export default {
  name: "Hello",
  props: {
    msg: String,
  },

  //setup() {
  data() {
    return {
      result: [],
    };
  },
  mounted() {
    const fetchMBCP = async () => {
      const error = ref(null);

      const dataJSRef = ref([]);
      try {
        const res = await fetch(
          "https://data.messari.io/api/v1/assets?fields=id,slug,symbol,metrics/market_data/price_usd"
        );
        if (!res.ok) {
          throw Error("No data available");
        }
        const msg = "Here is the data";
        const response = await res.json();
        //assets is a reference to response
        const assets = ref(response);

        console.log("Data from fetchMBCP,response", response);
        console.log("Data from fetchMBCP,assets", assets);
        console.log("Data from fetchMBCP, assets.value", assets.value);
        console.log("Data from fetchMBCP, values,status elapsed");
        console.log("Data from fetchMBCP, values,status timestamp");

        const dataJS = Object.values(response.data);
        console.log("dataJS is ", dataJS);
        // Use ref for displaying in the browser
        this.result = dataJS;

        dataJSRef.value = ref(dataJS);
        //Each djsObj is an object with some values

        for (let djsObj of dataJS) {
          console.log("data in dataJS", djsObj);
          console.log("Id is ", djsObj.id);
          const djsObjRefId = ref(djsObj.id);
          console.log("Symbol is", djsObj.symbol);
          const djsObjRefSymbol = ref(djsObj.symbol);
          console.log("Slug is", djsObj.slug);
          const djsObjRefIdSlug = ref(djsObj.slug);
          console.log("Metrics is ", djsObj.metrics);
          const djsObjRefIdMetrics = ref(djsObj.metrics);
          console.log("Market data is", djsObj.metrics.market_data);
          console.log(
            "Market data's price_usd is",
            djsObj.metrics.market_data.price_usd
          );
        }
      } catch (err) {
        error.value = err.message;
        console.log("error", error.value);
      }
    };
    /* return {
      dataJS,
      error,
    }; */
    fetchMBCP();
  }, //se
  //tup ends
  //data () ends
}; //export def ends
</script>
<style scoped>
* {
  margin: 0;
  padding: 0;
}
div.home {
  display: flex;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: green;
}
div.result {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: rgb(195, 137, 250);
  border: 2px solid green;
  border-radius: 15px;
  margin: 20px;
}
p {
  color: rgb(239, 120, 120);
  padding: 30px;
}
</style>
