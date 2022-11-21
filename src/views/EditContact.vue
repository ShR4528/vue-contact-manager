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
        <form>
          <div class="mb-2">
            <input type="text" class="form-control" placeholder="Name">
          </div>
          <div class="mb-2">
            <input type="text" class="form-control" placeholder="Photo Url">
          </div>
          <div class="mb-2">
            <input type="text" class="form-control" placeholder="Email">
          </div>
          <div class="mb-2">
            <input type="text" class="form-control" placeholder="Mobile">
          </div>
          <div class="mb-2">
            <input type="text" class="form-control" placeholder="Company">
          </div>
          <div class="mb-2">
            <input type="text" class="form-control" placeholder="Title">
          </div>
          <div class="mb-2">
            <select class="form-control">
              <option value="">Select Group</option>
            </select>
            <div class="mb-2">
              <input type="submit" class="btn btn-success" value="Update">
            </div>
          </div>
        </form>
      </div>
      <div class="col-md-4">
        <img src="../assets/585e4bcdcb11b227491c3396.png" alt="" class="contact-img">
      </div>
    </div>
  </div>
</template>
  
  
  <script>
  export default {
    name: 'EditContact'
  }
    
  </script>
  <style>
  
  </style>