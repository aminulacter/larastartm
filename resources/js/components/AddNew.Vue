<template>
<modal name="add-new" transition="pop-out" :width="modalWidth" :height="450">
    <div class="modalContainer">
        <form @submit.prevent="createUser">
             <div class="title" >
                 <h1 class="blue">Add New User</h1>
            </div>
            <div class="modal-body">
                <div class="form-group">
                    <input type="text" class="form-control" id="name" name ="name" v-model="form.name" aria-describedby="nameHelp" :class="{'is-invalid': form.errors.has('name') }" placeholder="name"> 
                    <has-error :form="form" field="name"></has-error>
                </div>
                <div class="form-group">
                 
                    <input type="email" class="form-control" id="email" name="email" 
                    v-model="form.email" aria-describedby="emailHelp" :class="{'is-invalid': form.errors.has('email') }" placeholder="email"> 
                    <has-error :form="form" field="name"></has-error>
                </div>
                <div class="form-group">
                    
                    <input type="password" name="password" class="form-control"  :class="{'is-invalid': form.errors.has('password') }" id="exampleInputPassword1" 
                    v-model="form.password" placeholder="password">
                    <has-error :form="form" field="name"></has-error>
                </div>
                <div class="form-group">
                    
                    <textarea  name="bio" class="form-control"  :class="{'is-invalid': form.errors.has('bio') }" id="examplebio"
                     v-model="form.bio" placeholder="biography"></textarea>
                    <has-error :form="form" field="bio"></has-error>
                </div>
                 <div class="form-group">
                    
                    <select  name="type" class="form-control"  
                    :class="{'is-invalid': form.errors.has('type') }" id="type" v-model="form.type">
                    <option value="">SElect User Role</option>
                    <option value="admin">Admin</option>
                    <option value="user">Standard user</option>
                    <option value="author">Author</option>
                    </select>
                    <has-error :form="form" field="name"></has-error>
                </div>
                
               
            </div>
            <div class="modal-footer">
                    <button type="button" class="btn btn-danger" @click="$emit('close')">Close</button>
                    <button type="button" class="btn btn-primary">Create</button>
            </div>
        </form>
       
    </div>
</modal>
</template>

<script>
const MODAL_WIDTH = 656
    export default {
        name: 'AddUser',
  data () {
    return {
      modalWidth: MODAL_WIDTH,
      form: new Form({
          name : '',
          email: '',
          password: '',
          type: '',
          bio: '',
          photo: ''
      })
    }
  },
  created () {
    this.modalWidth = window.innerWidth < MODAL_WIDTH
      ? MODAL_WIDTH / 2
      : MODAL_WIDTH
  }
    }
</script>

<style lang="scss" scoped>
    .title{
        display: flex;
        padding-top: 20px;
        justify-content: center
    }
    .modal-footer{
        display: flex;
        justify-content: center;
    }
</style>