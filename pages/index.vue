<template>
  <div id="app">
    <div class="container">
      <h1>FormSubmit Demo</h1>
      <form target="_blank" action="http://localhost:3000/thankyou" method="POST">
              <input type="text" name="name" class="form-control" placeholder="Full Name" required>
              <!-- <input type="hidden" name="_next" value="http://formsubmit.co/calcio.vita@gmail.com"> -->
              <input type="hidden" name="_subject" value="new email woooo!">
              <input type="email" name="email"  placeholder="Email Address" required>
          <textarea placeholder="Your Message" class="form-control" name="message" rows="" required></textarea>
        <button type="submit" class="btn btn-lg btn-dark btn-block">Submit Form</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>
