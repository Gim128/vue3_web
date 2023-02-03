<template>
  <div class="bg-white py-24 sm:py-32">
    <div class="mx-auto max-w-7xl px-6 lg:px-8">
      <div class="mx-auto max-w-2xl lg:text-center">
        <h2 class="text-lg font-semibold leading-8 tracking-tight text-sky-600">
          Lorem, ipsum.
        </h2>
        <p
          class="
            text-3xl
            mt-2
            font-bold
            tracking-tight
            text-gray-900
            sm:text-4xl
          "
        >
          Lorem ipsum dolor sit amet.
        </p>
        <p class="text-lg mt-6 text-gray-600">Lorem ipsum dolor sit amet.</p>
      </div>

      <div class="mt-20 max-w-lg sm:mx-auto md:max-w-none">
        <div
          class="
            grid grid-cols-1
            gap-y-16
            md:grid-cols-2 md:gap-x-12 md:gap-y-16
          "
        >
          <div
            v-for="feature in features"
            :key="feature.name"
            class="
              realtive
              flex flex-col
              gap-6
              sm:flex-row
              md:flex-col
              lg:flex-row
            "
          >
            <div
              class="
                flex
                h-12
                w-12
                items-center
                justify-center
                rounded-xl
                bg-indigo-100
                text-white
                sm:shrink-0
              "
            >
              <img class="max-h-[30px]" :src="feature.icon" />
            </div>
            <div class="sm:min-w-0 sm:flex-1">
              <p class="text-lg font-semibold leading-8 text-gray-900">
                {{ feature.name }}
              </p>
              <p class="mt-2 text-base leading-7 text-gray-600">
                {{ feature.description }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeroDescription",

  data() {
    return {
      features: [
        {
          // name: this.$t("msgtwtwo"),
          name: "Finance reimagined",
          // description: this.$t("msgtwthree"),
          description:
            "CNT takes the abilities of cash to the next level. Unlock opportunities in crypto markets for trading, cross border payments, shop overseas – accessible globally. The possibilities are just beginning.",
          // icon: require("../assets/dollar.png"),
          icon: "ShoppingCartIcon",
        },
        {
          name: "Finance reimagined",
          description:
            "CNT takes the abilities of cash to the next level. Unlock opportunities in crypto markets for trading, cross border payments, shop overseas – accessible globally. The possibilities are just beginning.",
          icon: "CurrencyYenIcon",
        },
        {
          name: "Finance reimagined",
          description:
            "CNT takes the abilities of cash to the next level. Unlock opportunities in crypto markets for trading, cross border payments, shop overseas – accessible globally. The possibilities are just beginning.",
          icon: "ChatBubbleLeftIcon",
        },
        {
          name: "Finance reimagined",
          description:
            "CNT takes the abilities of cash to the next level. Unlock opportunities in crypto markets for trading, cross border payments, shop overseas – accessible globally. The possibilities are just beginning.",
          //   icon: require(""),
        },
      ],
    };
  },
};
</script>

<style>
</style>