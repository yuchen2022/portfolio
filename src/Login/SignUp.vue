<template dir="rtl">
  <main>
    <form class="flex text-right flex-col h-screen justify-center w-1/2">
      <label for="name" class="m-2 font-bold"> نام کاربری </label>
      <input
        id="name"
        type="text"
        placeholder="نام کاربری خود را وارد کنید"
        class="border rounded-lg p-2 text-right"
      />
      
      <label for="email" class="m-2 font-bold">ایمیل</label>
      <input
        type="email"
        id="email"
        placeholder="ایمیل خود را وارد کنید"
        class="border rounded-lg p-2 text-right"
      />
      <label for="password" class="m-2 font-bold">رمز عبور</label>
      <input
        type="password"
        placeholder="رمزعبور را وار د کنید"
        class="border rounded-lg p-2 text-right"
      />
    </form>
    <div class="w-96 h-96">
      <img
        class="w-96 h-96"
        src="../assets/images/barg-sabz-derakht.jpg"
        alt=""
      />
    </div>
  </main>
</template>
