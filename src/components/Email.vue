<template>
  <div class="email-wrapper">
    <h1>Contact Me</h1>

    <div class="input-container">
      <div class="input-wrap">
        <label
          for="name"
        >你的名字：</label>
        <input
          id="name"
          v-model="name"
          type="text"
        >
      </div>
      <div class="input-wrap">
        <label
          for="email"
        >你的email：</label>
        <input
          id="email"
          v-model="email"
          type="text"
        >
      </div>
      <div class="input-wrap">
        <label
          for="message"
        >想說什麼：</label>
        <textarea
          id="message"
          v-model="message"
          type="text"
          max-length="200"
        />
      </div>
      <button class="send-button" @click="sendEmail">
        <p v-show="!loading">
          送出
        </p>
        <img v-show="loading" class="loading-img" src="https://i.gifer.com/origin/34/34338d26023e5515f6cc8969aa027bca_w200.gif" alt="loading">
      </button>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import emailjs from '@emailjs/browser';

const loading = ref<boolean>(false);
const name = ref<string>();
const email = ref<string>();
const message = ref<string>();

const columnValidate = () => {
    return (name.value && email.value && message.value);
  };


const sendEmail = () => {
  const columnVerified = columnValidate();
  loading.value = true;
  if(columnVerified) {
    const emailTemplate = {
      from_name: name.value,
      from_email: email.value,
      message: message.value,
    };
    emailjs.send('service_mon31on', 'template_suhf3bh', emailTemplate, 'yE33VyUELCrKCqeAL').then((result) => {
      if(result.status === 200) {
        alert('信件已送出。');
        loading.value = false;
      }}, (error) => {
        alert(error.text);
        loading.value = false;
      });
    } else {
      alert('請填寫所有的欄位哦～');
    }
};

</script>

<style lang="scss" scoped>
.email-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 60px 0;

  h1 {
    margin-bottom: 30px;
    text-align: center;
    font-size: 50px;
    color: #2D4D42;
  }

  .input-wrap {
    display: flex;
    width: 100%;
    margin: 15px 0;

    label {
      display: inline-block;
      min-width: 120px;
    }
    input, textarea {
      width: 180px;
      padding: 10px;
      border-radius: 8px;
      box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
    }

    textarea {
      resize: none;
    }
  }

  .send-button {
    width: 100px;
    padding: 8px;
    border-radius: 10px;
    margin-top: 20px;
    float: right;
    cursor: pointer;
    text-align: center;
  }

  .loading-img {
    margin-top: 3px;
    width: 15px;
    height: 15px;
  }
}

@media screen and (min-width: 914px) {
  .skill-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    .skill-cards {
      justify-content: center;
    }
  }
}
</style>