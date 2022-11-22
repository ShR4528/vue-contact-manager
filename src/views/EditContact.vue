<template>
  <div class="container mt-3">
    <div class="row">
      <div class="col">
        <p class="h3 text-success fw-bold">Edit Contact</p>
        <p class="fst-italic">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Eum amet nesciunt animi commodi iste. Natus quasi nulla tempora sit. Itaque, vero similique? Perferendis sunt officia blanditiis officiis laudantium similique rem.</p>
      </div>
    </div>
  </div>
  <div class="container mt-3">
    <div class="row">
      <div class="col-md-3">
        <form @submit.prevent="updateSubmit()">
          <div class="mb-2">
            <input required  v-model="contact.name" type="text" class="form-control" placeholder="Name">
          </div>
          <div class="mb-2">
            <input required   v-model="contact.photo" type="text" class="form-control" placeholder="Photo Url">
          </div>
          <div class="mb-2">
            <input required  v-model="contact.email" type="text" class="form-control" placeholder="Email">
          </div>
          <div class="mb-2">
            <input required  v-model="contact.phone" type="text" class="form-control" placeholder="Phone">
          </div>
          <div class="mb-2">
            <input required  v-model="contact.company" type="text" class="form-control" placeholder="Company">
          </div>
          <div class="mb-2">
            <input required  v-model="contact.title" type="text" class="form-control" placeholder="Title">
          </div>
          <div class="mb-2">

            <div class="mb-2">
              <input type="submit" class="btn btn-success" value="Update">
            </div>
          </div>
        </form>
      </div>
      <div class="col-md-4">
        <img src="contact.photo" alt="" class="contact-img">
      </div>
    </div>
  </div>
</template>
  
<script>
import { ContactService } from '@/services/ContactServise';

  export default {
    name: 'EditContact',
    data: function (){
     return {
       contactID: this.$route.params.contactID,
       loading: false,
       contact: {
        name: '',
          photo: '',
          email: '',
          company: '',
          title: ''

      },
      errorMessage: null 
    }
  },
  created: async function() {
   try {
    this.loading = true;
    let response = await ContactService.getContact(this.contactID);
    this.contact = response.data;
    this.loading = false;
   } 
   catch (error) {
    this.errorMessage = error;
    this.loading = false;
   }
  },
  methods: {
    updateSubmit: async function() {
      try {
          let response = await ContactService.updateContact(this.contact, this.contactID);
          if(response){
            return this.$router.push('/');
          } 
          else {
           return this.$router.push(`/contacts/edit/${this.contactID}`);
          }
        } 
        catch (error) {
          console.log(error)
        }
      }
    }
  }

    
</script>

<style>
  
</style>