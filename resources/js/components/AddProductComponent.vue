<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Add Products</div>

                    <div class="card-body">

                          <form action ="">
                            <div class="form-group">
                              <label for="name">Name</label>
                              <input type="text" id="name" class="form-control" />
                            </div>
                            <div class="form-group">
                              <label for="year">Year</label>
                              <input type="number" id="year" class="form-control" />
                            </div>
                            <div class="form-group">
                              <label for="price">Price</label>
                              <input type="number" id="price" class="form-control" />
                            </div>
                            <div class="form-group">
                              <button class="btn btn-primary">Create Product</button>
                            </div>
                          </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "AddProductComponent",
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
