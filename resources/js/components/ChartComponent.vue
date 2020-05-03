<script>

  import { Line } from 'vue-chartjs';

    export default {
      name: "ChartComponent",
      extends: Line,
      data() {
        return {
            url: '/products',
            years: [],
            labels: [],
            prices: [],
            data: []
        }
      },
      methods: {
        getProducts() {
          axios.get(
            this.url,
            {
              responseType: 'json',
              headers: {
                'Accept': 'application/json',
                'Content-Type': 'application/json',
              }
            },
          ).then((response)=>{
            console.log(response);
            this.data = response.data;

            if (this.data) {
              for (var i = 0; i < this.data.length; i++) {
                var element = this.data[i];
                this.labels.push(element.name);
                this.years.push(element.year);
                this.prices.push(element.price);
              }

              this.renderChart({
                labels: this.years,
                datasets: [
                  {
                    label: 'Sales',
                    backgroundColor: '#f87979',
                    data: this.prices
                  }
                ]
              }, {
                responsive: true,
                maintainAspectRatio: false
              });
            } else {
              console.log("No data");
            }
          });
        }
      },
      mounted() {
          this.getProducts();
      }
    }
</script>
