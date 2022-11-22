<template>
    <div class="container mt-3">
        <div class="row">
          <div class="col">
            <p class="h3 text-success fw-bold">View Contact</p>
            <p class="fst-italic">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Eum amet nesciunt animi commodi iste. Natus quasi nulla tempora sit. Itaque, vero similique? Perferendis sunt officia blanditiis officiis laudantium similique rem.</p>
        </div>
        </div>
      </div>

      <div v-if="loading">
        <div class="container">
          <div class="row">
            <div class="col">
              <Spinner />
            </div>
          </div>
        </div>
       </div>
    
       <div v-if="!loading && errorMessage">
        <div class="container mt-3">
          <div class="row">
            <div class="col">
             <p class="h4 text-danger fw-bold">{{errorMessage}}</p>
            </div>
          </div>
        </div>
       </div>

       <div class="container"  v-if="!loading && isDone()">
        <div class="row align-items-center">
            <div class="col-md-4">
                <img :src="contact.photo" alt="" class="contact-img-big">
            </div>
            <div class="col-md-6">
                <ul class="list-group">
                    <li class="list-group-item">Name : <span class="fw-bold">{{contact.name}}</span> </li>
                    <li class="list-group-item">Email : <span class="fw-bold">{{contact.email}}</span> </li>
                    <li class="list-group-item">Phone : <span class="fw-bold">{{contact.phone}}</span> </li>
                    <li class="list-group-item">Username : <span class="fw-bold">{{contact.username}}</span> </li>
                  </ul>
            </div>
        </div>
        <div class="row mt-3">
            <div class="col">
                <router-link to="/" class="btn btn-success"><i class="fa fa-arrow-alt-circle-left"></i>Back</router-link>
            </div>  
        </div>
      </div>
</template>

<script>
import Spinner from '@/components/Spinner.vue';
import {ContactService } from '@/services/ContactServise'

export default {
    name: "ViewContact",
    components: { Spinner },
    data: function () {
        return {
            contactID: this.$route.params.contactID,
            loading: false,
            contact: {},
            errorMesage: null
        };
    },
    created: async function () {
        try {
            this.loading = true;
            let response = await ContactService.getContact(this.contactID);
            this.contact = response.data;
            this.loading = false;
        }
        catch (error) {
            this.errorMesage = error;
            this.loading = false;
        }
    },
   methods: {
    isDone: function() {
      return Object.keys(this.contact).length > 0;
    
    }
   }
}

</script>

<style>
  
</style>