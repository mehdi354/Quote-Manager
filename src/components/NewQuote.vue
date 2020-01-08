<template>
  <div class="row">
    <div class="col-md-12">
      
       <div class="col-md-8 offset-md-2">
        <div class="card">
          <div class="card-body">
           <form action="">
              <div class="form-group">
                  <label for="exampleInputEmail1">Enter New Quote</label>
                  <input type="email" class="form-control"  placeholder="Enter New Quote" v-model="quote">
              </div>
              <div class="form-group text-center">
                 <button class="btn btn-primary btn-xs" @click.prevent="addNew">Add New</button>
              </div>
           </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
  export default{
    data() {
        return {
            quote: ""
        }
    },
    methods : {
        addNew(){
          
            this.$emit("addNew",this.quote);
            this.quote = ""
        }
    }
  }
</script>
<style>
  .card {
        margin-top: 10px;
    }
</style>