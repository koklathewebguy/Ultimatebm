<template>
    <div>
        <h1>Dashboard</h1>

        <!-- Icon Cards-->
            <div class="row">
                
                <div class="col-xl-4 col-sm-6 col-lg-4 col-md-4  mb-3">
                <div class="card text-white bg-primary o-hidden h-100">
                    <div class="card-body">
                    <div class="card-body-icon">
                        <i class="fas fa-fw fa-users"></i>
                    </div>
                    <div class="mr-5">Customers</div>
                    </div>
                    <a class="card-footer text-white clearfix small z-1" href="javascript:void(0)" @click="changeComponent('viewCustomers')">
                    <span class="float-left">Go</span>
                    <span class="float-right">
                        <i class="fas fa-angle-right"></i>
                    </span>
                    </a>
                </div>
                </div>

                <div class="col-xl-4 col-sm-6 col-lg-4 col-md-4 mb-3">
                <div class="card text-white bg-warning o-hidden h-100">
                    <div class="card-body">
                    <div class="card-body-icon">
                        <i class="fas fa-fw fa-credit-card"></i>
                    </div>
                    <div class="mr-5">Payments</div>
                    </div>
                    <a class="card-footer text-white clearfix small z-1" href="javascript:void(0)" @click="changeComponent('viewPayments')">
                    <span class="float-left">Go</span>
                    <span class="float-right">
                        <i class="fas fa-angle-right"></i>
                    </span>
                    </a>
                </div>
                </div>

                <div class="col-xl-4 col-sm-12 col-lg-4 col-md-4 mb-3">
                <div class="card text-white bg-success o-hidden h-100">
                    <div class="card-body">
                    <div class="card-body-icon">
                        <i class="fas fa-box"></i>
                    </div>
                    <div class="mr-5">Services</div>
                    </div>
                    <a class="card-footer text-white clearfix small z-1" href="javascript:void(0)" @click="component = 'statistics'">
                    <span class="float-left">Go</span>
                    <span class="float-right">
                        <i class="fas fa-angle-right"></i>
                    </span>
                    </a>
                </div>
                </div>
                
            </div>
    </div>
</template>

<script>
export default {
    name: 'dashboard',
    
    computed: {
        component() {
            return this.$store.state.component
        }
    },

  methods: {
    changeComponent: function(amount) {
      this.$store.dispatch('changeComponent', amount)
    }
  }
}
</script>

<style scoped>
    .card-body-icon {
        position: absolute;
        z-index: 0;
        top: -1rem;
        right: 1rem;
        opacity: 0.4;
        font-size: 5rem;
        -webkit-transform: rotate(15deg);
        transform: rotate(15deg);
    }

    .card {
        overflow: hidden;
    }

    .card-footer {
        z-index: 1;
    }
</style>
