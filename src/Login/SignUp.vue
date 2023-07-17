<template dir="rtl">
  <main class="flex h-full">
    <div
      class="flex-1 hidden lg:block bg-cover rounded-l-3xl bg-center bg-[url('/src/assets/images/Jowhareh_galleries_5_poster_ff249aa4-676f-43ef-aad2-e06c446b6291.png')]"
    ></div>
    <div class="flex-1 flex flex-col gap-2 relative justify-center p-4">
      <!--title-->
      <span class="font-bold text-xl text-center drop-shadow-md">
        ! خوش آمدید
      </span>
      <!--form-->
      <form
        @submit.prevent="submintForm"
        class="flex flex-col gap-2 text-right text-sm px-4 md:px-8 lg:px-16"
      >
        <!-- name  -->
        <label for="name"> نام کاربری </label>
        <input
          id="name"
          type="text"
          placeholder="نام کاربری خود را وارد کنید"
          class="border focus:outline-[#3A5B22] overflow-ellipsis rounded-3xl text-sm p-3 text-right mb-3 shadow-xl shadow-[#EDF2F7]"
        />
        <span class="text-xs font-bold pr-3 text-red-500"
          >این فیلد الزامی است</span
        >

        <!-- email  -->
        <label for="email">ایمیل</label>
        <input
          v-model="email"
          type="email"
          id="email"
          placeholder="ایمیل خود را وارد کنید"
          class="border focus:outline-[#3A5B22] overflow-ellipsis rounded-3xl text-sm p-3 text-right mb-3 shadow-xl shadow-[#EDF2F7]"
        />
        <span class="text-xs font-bold pr-3 text-red-500"
          >این فیلد الزامی است</span
        >
        <!-- password  -->
        <label for="password">رمز عبور</label>
        <div class="relative">
          <input
            v-model="password"
            type="password"
            placeholder="رمزعبور را وارد کنید"
            class="border focus:outline-[#3A5B22] overflow-ellipsis rounded-3xl text-sm p-3 text-right mb-3 w-full shadow-xl shadow-[#EDF2F7]"
          />

          <span class="absolute top-3 left-4">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-5 h-5"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M3.98 8.223A10.477 10.477 0 001.934 12C3.226 16.338 7.244 19.5 12 19.5c.993 0 1.953-.138 2.863-.395M6.228 6.228A10.45 10.45 0 0112 4.5c4.756 0 8.773 3.162 10.065 7.498a10.523 10.523 0 01-4.293 5.774M6.228 6.228L3 3m3.228 3.228l3.65 3.65m7.894 7.894L21 21m-3.228-3.228l-3.65-3.65m0 0a3 3 0 10-4.243-4.243m4.242 4.242L9.88 9.88"
              /></svg
          ></span>

          <span class="absolute top-3 left-4">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-5 h-5"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M2.036 12.322a1.012 1.012 0 010-.639C3.423 7.51 7.36 4.5 12 4.5c4.638 0 8.573 3.007 9.963 7.178.07.207.07.431 0 .639C20.577 16.49 16.64 19.5 12 19.5c-4.638 0-8.573-3.007-9.963-7.178z"
              />
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"
              /></svg
          ></span>
        </div>

        <span class="text-xs font-bold pr-3 text-red-500"
          >این فیلد الزامی است</span
        >

        <!-- phone number  -->
        <label for="phoneNo">شماره همراه</label>
        <input
          v-model="phoneNo"
          id="phoneNo"
          type="tel"
          placeholder="شماره همراه خود را وار د کنید"
          class="border focus:outline-[#3A5B22] overflow-ellipsis rounded-3xl text-sm p-3 text-right mb-3 shadow-xl shadow-[#EDF2F7]"
        />
        <span v-if="validPhoneNo" class="text-xs font-bold pr-3 text-red-500"
          >این فیلد الزامی است</span
        >
        <!-- sign up button  -->
        <PrimaryBtn
          @click="submintForm()"
          :isLoading="isLoading"
          title="ثبت نام "
        ></PrimaryBtn>
      </form>
    </div>
  </main>
</template>
<script>
import PrimaryBtn from "../components/buttons/PrimaryBtn.vue";

export default {
  //variable
  data() {
    return {
      name: null,
      email: null,
      password: null,
      phoneNo: null,
      isLoading: null,
      phoneNoRegex: /^(\+98|0)?9\d{9}$/,
      passwordRegex:
        /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[!@#$%^&*()\-_=+{};:,<.>]).{6,}$/,
      emailRegex: /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,})+$/,
    };
  },
  //computed

  computed: {
    validPhoneNo() {
      if (this.phoneNoRegex.test(this.phoneNo)) return true;
      else return false;
    },
    validEmail() {
      if (this.emailRegex.test(this.email)) return true;
      else return false;
    },
    validPassword() {
      if (this.passwordRegex.test(this.password)) return true;
      else return false;
    },
    submintForm() {
      if (
        this.validEmail &&
        this.validPassword &&
        this.name &&
        this.validPhoneNo
      ) {
        console.log("submit");
      } else return false;
    },
  },

  components: { PrimaryBtn },
};
</script>
