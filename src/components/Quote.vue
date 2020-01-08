<template>
        <div class="col-md-4">
            <div class="card">
                <div class="card-body">
                    <slot>{{quote}}</slot>
                </div>
            </div>
        </div>
      
</template>
<script>
  export default{
    props : ["quote"],
  }
</script>
<style scoped>
    .col-md-4 {
        float:left ;
    }
    .card {
        margin-top: 10px;
    }
</style>