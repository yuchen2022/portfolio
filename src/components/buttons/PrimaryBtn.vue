<template>
  <button
    :class="{ 'bg-gray-400': isLoading }"
    class="bg-[#3A5B22] p-2 rounded-3xl text-white font-bold mt-4 border shadow-xl shadow-[#EDF2F7]"
  >
    <svg
      class="mx-auto"
      v-if="isLoading"
      width="30"
      height="30"
      viewBox="0 0 38 38"
      xmlns="http://www.w3.org/2000/svg"
      stroke="#fff"
    >
      <g fill="none" fill-rule="evenodd">
        <g transform="translate(1 1)" stroke-width="2">
          <circle stroke-opacity=".5" cx="18" cy="18" r="18" />
          <path d="M36 18c0-9.94-8.06-18-18-18">
            <animateTransform
              attributeName="transform"
              type="rotate"
              from="0 18 18"
              to="360 18 18"
              dur="1s"
              repeatCount="indefinite"
            />
          </path>
        </g>
      </g>
    </svg>
    <span v-if="!isLoading"> {{ title }}</span>
    <slot></slot>
  </button>
</template>
<script>
export default {
  props: {
    isLoading: {
      type: Boolean,
      default: null,
    },
    isActive: {
      type: Boolean,
    },
    title: {
      type: String,
    },
  },
};
</script>
