<template>
  <section class="section" id="contact">
    <div class="section-heading">
      <h2>Let's Chat</h2>
    </div>
    <p class="relocate">
      Currently based in San Diego, California.
    </p>
    <div class="form-wrapper">
      <form
        name="contact"
        method="post"
        v-on:submit.prevent="handleSubmit"
        action="/success/"
        data-netlify="true"
        data-netlify-honeypot="bot-field"
      >
        <input type="hidden" name="form-name" value="contact" />
        <p hidden>
          <label> Don’t fill this out: <input name="bot-field" /> </label>
        </p>
        <div class="sender-info">
          <div>
            <label class="form-label" for="name">Name*</label>
            <input type="text" name="name" v-model="formData.name" />
          </div>
          <div>
            <label class="form-label" for="email">Email*</label>
            <input type="email" name="email" v-model="formData.email" />
          </div>
        </div>

        <div class="message-wrapper">
          <label class="form-label" for="message">Message*</label>
          <textarea name="message" v-model="formData.message"></textarea>
        </div>

        <button type="submit">Submit</button>
      </form>
    </div>
    <Footer />
  </section>
</template>

<script>
import Footer from '~/components/Footer.vue';

export default {
  name: 'Contact',
  data() {
    return {
      formData: {},
    };
  },
  components: {
    Footer,
  },
  methods: {
    encode(data) {
      return Object.keys(data)
        .map(
          (key) => encodeURIComponent(key) + '=' + encodeURIComponent(data[key])
        )
        .join('&');
    },
    handleSubmit(e) {
      fetch('/', {
        method: 'POST',
        headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
        body: this.encode({
          'form-name': e.target.getAttribute('name'),
          ...this.formData,
        }),
      })
        .then(() => alert('Success! That worked :)'))
        .catch((error) => alert(error));
    },
  },
};
</script>

<style lang="scss" scoped>
.relocate {
  //text-align: center;
  margin-bottom: 3rem;
  margin-right: auto;
  margin-left: auto;
  color: #ffffffb9;
  width: 90%;
}

#contact {
  background: #424242;
}

.form-wrapper {
  margin: auto;
  padding-bottom: 5rem;
  width: 90%;
  @media only screen and (max-width: 600px) {
    width: 100%;
    margin: auto;
  }
}
form {
  width: 100%;
  overflow: hidden;
  margin: 0 auto;
  label {
    display: block;
    margin-bottom: 8px;
    font-size: 1.25rem;
    color: black;
  }
  fieldset {
    width: 100%;
    padding: 0;
    border: none;
  }
  input,
  textarea {
    background-color: #d4d4d4;
    //display: inline;
    //border-radius: 5px;
    border: none;
    font-size: 1rem;
    height: 6rem;
    padding: 0.25rem;
    background: none;
    border: 1.25px solid black;
    border-radius: 10px;
    color: #ffffff;
    width: 50%;
    @media only screen and (max-width: 600px) {
      width: 90%;
      margin: auto;
    }
  }
  input {
    height: 3.25rem;
    margin-bottom: 1rem;
  }
  .input-container {
    display: flex;
    justify-content: center;
  }
  .button-wrapper {
    display: flex;
    margin: auto;
  }
  button {
    width: 11rem;
    height: 3.25rem;
    border: none;
    border-radius: 5px;
    background-color: #ff3f80;
    color: white;
    font-size: 1.25rem;
    margin-top: 1rem;
    &:hover {
      cursor: pointer;
    }
  }
}

//Light mode styles
.light-mode {
  #contact {
    background: #ffffff;
  }
  .relocate {
    color: rgb(32, 32, 32);
  }
  input,
  textarea {
    color: rgb(32, 32, 32);
  }
  .section-heading {
    h2 {
      color: rgb(32, 32, 32);
    }
  }
}
</style>
