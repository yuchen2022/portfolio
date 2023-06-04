<template dir="rtl">
  <main class="flex">
    <div
      class="flex-1 hidden md:block bg-cover rounded-l-3xl bg-[url('/src/assets/images/Jowhareh_galleries_5_poster_ff249aa4-676f-43ef-aad2-e06c446b6291.png')]"
    ></div>
    <div class="flex-1 py-7">
      <h2 class="font-bold text-2xl text-center py-4 drop-shadow-md">
        ! خوش آمدید
      </h2>
      <form class="flex w-2/3 mx-auto text-right flex-col">
        <!-- name  -->
        <label for="name" class="m-2 font-bold"> نام کاربری </label>
        <input
          id="name"
          type="text"
          placeholder="نام کاربری خود را وارد کنید"
          class="border focus:outline-[#3A5B22] rounded-3xl text-sm p-4 text-right mb-3 shadow-xl shadow-[#EDF2F7]"
        />

        <!-- email  -->
        <label for="email" class="m-2 font-bold">ایمیل</label>
        <input
          type="email"
          id="email"
          placeholder="ایمیل خود را وارد کنید"
          class="border focus:outline-[#3A5B22] rounded-3xl text-sm p-4 text-right mb-3 shadow-xl shadow-[#EDF2F7]"
        />

        <!-- password  -->
        <label for="password" class="m-2 font-bold">رمز عبور</label>
        <input
          type="password"
          placeholder="رمزعبور را وار د کنید"
          class="border focus:outline-[#3A5B22] rounded-3xl text-sm p-4 text-right mb-3 shadow-xl shadow-[#EDF2F7]"
        />

        <!-- phone number  -->
        <label for="phoneNo" class="m-2 font-bold">شماره همراه</label>
        <input
          id="phoneNo"
          type="number"
          placeholder="شماره همراه خود را وار د کنید"
          class="border focus:outline-[#3A5B22] rounded-3xl text-sm p-4 text-right mb-3 shadow-xl shadow-[#EDF2F7]"
        />
        <!-- sign up button  -->
        <button
          :class="{ 'bg-gray-400': loading }"
          class="bg-[#3A5B22] p-2 rounded-3xl text-white font-bold mt-4 border shadow-xl shadow-[#EDF2F7]"
        >
          ثبت نام
        </button>
      </form>
    </div>
  </main>
</template>
<script>
export default {
  //variable
  data() {
    return {
      name: null,
      email: null,
      password: null,
      phoneNo: null,
      isLoading: null,
      passwordRegex:
        /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[!@#$%^&*()\-_=+{};:,<.>]).{6,}$/,
      emailRegex: /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,})+$/,
    };
  },
  //computed

  //functions
};
</script>
