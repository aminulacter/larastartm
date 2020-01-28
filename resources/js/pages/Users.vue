<template>
    <div class="container">
        <div class="row mt-5">
          <div class="col-12">
            <div class="card">
              <div class="card-header">
                <h3 class="card-title">Users Table</h3>
                
                <div class="card-tools">
                 <button class="btn btn-success" @click="show">Add New <i class="fas fa-user-plus fa-fw" ></i></button>
                </div>
              </div>
              <!-- /.card-header -->
              <div class="card-body table-responsive p-0">
                <table class="table table-hover text-nowrap">
                  <thead>
                    <tr>
                      <th>ID</th>
                      <th>Name</th>
                      <th>Email</th>
                      <th>Type</th>
                      <th>Modify</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr>
                      <td>183</td>
                      <td>John Doe</td>
                      <td>11-7-2014</td>
                      <td><span class="tag tag-success">Approved</span></td>
                      <td>
                          <a href="#"><i class="fas fa-edit blue"></i></a>
                          /
                          <a href="#"><i class="fas fa-trash red"></i></a>

                      </td>
                    </tr>
                    
                  </tbody>
                </table>
              </div>
              <!-- /.card-body -->
            </div>
            <!-- /.card -->
          </div>
        </div>
        <add-new @close="hide"/>
    </div>
</template>

<script>
import AddNew  from '../components/AddNew.vue'
    export default {
        components:{
            AddNew
        },
       methods: {
  show() {
    this.$modal.show('add-new');
    
  },
  hide () {
    this.$modal.hide('add-new');
  }
}
    }
</script>
