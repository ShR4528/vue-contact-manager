<template>
    <div class="container mt-3">
        <div class="row">
          <div class="col">
            <p class="h3 text-success fw-bold">View Contact</p>
            <p class="fst-italic">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Eum amet nesciunt animi commodi iste. Natus quasi nulla tempora sit. Itaque, vero similique? Perferendis sunt officia blanditiis officiis laudantium similique rem.</p>
        </div>
        </div>
      </div>
      <div class="container">
        <div class="row align-items-center">
            <div class="col-md-4">
                <img src="../assets/585e4bcdcb11b227491c3396.png" alt="" class="contact-img-big">
            </div>
            <div class="col-md-6">
                <ul class="list-group">
                    <li class="list-group-item">Name : <span class="fw-bold">Name</span> </li>
                    <li class="list-group-item">Email : <span class="fw-bold">Email</span> </li>
                    <li class="list-group-item">Mobile : <span class="fw-bold">Mobile</span> </li>
                    <li class="list-group-item">Company : <span class="fw-bold">Company</span> </li>
                    <li class="list-group-item">Title : <span class="fw-bold">title</span> </li>
                    <li class="list-group-item">Group : <span class="fw-bold">Group</span> </li>
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
  export default {
    name: 'ViewContact'
  }
    
  </script>
  <style>
  
  </style>