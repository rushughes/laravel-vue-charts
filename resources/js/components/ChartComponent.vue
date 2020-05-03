<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Example Component</div>

                    <div class="card-body">
                        I'm an example component.
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

  import {Line} from 'vue-chartjs';

    export default {
      name: "ChartComponent",
      extends: Line,
      data() {
        return {
            url: '/products',
            years: [],
            labels: [],
            prices: [],
            data: ''
        }
      },
      methods: {
        getProducts() {
          axios.get(this.url).then((response)=>{
            console.log(response.data);
          });
        }
      },
      mounted() {
          this.getProducts();
      }
    }
</script>
