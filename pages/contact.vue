<template>
    <div class="container">
      <h1>FormSubmit Demo</h1>
      <form  action="http://localhost:3000/thankyou" method="POST" onSubmit="check()">
              <input type="text" name="name" class="form-control" placeholder="Full Name" required>
              <!-- <input type="hidden" name="_next" value="http://formsubmit.co/calcio.vita@gmail.com"> -->
              <input type="hidden" name="_subject" value="new email woooo!">
              <input type="email" name="email"  placeholder="Email Address" required>
          <textarea placeholder="Your Message" class="form-control" name="message" rows="" required></textarea>
        <button type="submit" class="btn btn-lg btn-dark btn-block">Submit Form</button>
      </form>
    </div>
</template>

<script>
// import { defineComponent } from '@vue/composition-api'

export default /*defineComponent*/({
    /*setup() {
    },
    */
    check() {
      console.log("check", 1)

      const flag = 0;

      if(document.form.name.value == ""){
          flag = 1;
      }
      else if(document.form.email.value == ""){
          flag = 1;
      }
      else if(document.form.message.value == ""){
          flag = 1;
      }

      if(flag){
          sindow.alert('必須項目に未入力があります');
          return false;
      }
      else{
          return true;
      }

    }


})
</script>
