<template>
  <div class="bg-white isolate shadow-sky-400">
    <!-- <div
      class="
        absolute
        inset-x-0
        top-[-10rem]
        -z-10
        transform-gpu
        overflow-hidden
        blur-3xl
        sm:top-[-20rem]
      "
    >
      <svg
        class="
          relative
          left-[calc(50%-11rem)]
          -z-10
          h-[21.1875rem]
          max-w-none
          -translate-x-1/2
          rotate-[30deg]
          sm:left-[calc(50%-30rem)] sm:h-[42.375rem]
        "
        viewBox="0 0 1155 678"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          fill="url(#45de2b6b-92d5-4d68-a6a0-9b9b2abad533)"
          fill-opacity=".3"
          d="M317.219 518.975L203.852 678 0 438.341l317.219 80.634 204.172-286.402c1.307 132.337 45.083 346.658 209.733 145.248C936.936 126.058 882.053-94.234 1031.02 41.331c119.18 108.451 130.68 295.337 121.53 375.223L855 299l21.173 362.054-558.954-142.079z"
        /> -->
    <defs>
      <linearGradient
        id="45de2b6b-92d5-4d68-a6a0-9b9b2abad533"
        x1="1155.49"
        x2="-78.208"
        y1=".177"
        y2="474.645"
        gradientUnits="userSpaceOnUse"
      >
        <stop stop-color="#9089FC" />
        <stop offset="1" stop-color="#FF80B5" />
      </linearGradient>
    </defs>
    <!-- </svg> -->
    <!-- </div> -->
    <div class="px-6 pt-6 lg:px-8">
      <nav class="flex items-center justify-between" aria-label="Global">
        <div class="flex lg:flex-1">
          <a href="#" class="-m-1.5 p-1.5">
            <!-- <span class="sr-only">Your Company</span> -->
            <img
              class="inline h-10"
              src="https://tailwindui.com/img/logos/mark.svg?color=indigo&shade=600"
              alt=""
            />
          </a>
        </div>
        <div class="flex lg:hidden">
          <button
            type="button"
            class="
              -m-2.5
              inline-flex
              items-center
              justify-center
              rounded-md
              p-2.5
              text-gray-700
            "
            @click="mobileMenuOpen = true"
          >
            <span class="sr-only">Open main menu</span>
            <Bars3Icon class="w-6 h-6" aria-hidden="true" />
          </button>
        </div>
        <div class="hidden lg:flex lg:gap-x-12">
          <a
            v-for="item in navigation"
            :key="item.name"
            :href="item.href"
            class="text-sm font-semibold leading-6 text-gray-900"
            >{{ item.name }}</a
          >
        </div>
        <div class="hidden lg:flex lg:flex-1 lg:justify-end">
          <!-- <a href="#" class="text-sm font-semibold leading-6 text-gray-900"
            >Log in <span aria-hidden="true">&rarr;</span></a
          > -->

          <ButtonComponent />
        </div>
      </nav>
      <Dialog as="div" @close="mobileMenuOpen = false" :open="mobileMenuOpen">
        <DialogPanel
          focus="true"
          class="
            fixed
            inset-0
            z-10
            px-6
            py-6
            overflow-y-auto
            bg-white
            lg:hidden
          "
        >
          <div class="flex items-center justify-between">
            <a href="#" class="-m-1.5 p-1.5">
              <span class="sr-only">Your Company</span>
              <img
                class="h-8"
                src="https://tailwindui.com/img/logos/mark.svg?color=indigo&shade=600"
                alt=""
              />
            </a>
            <button
              type="button"
              class="-m-2.5 rounded-md p-2.5 text-gray-700"
              @click="mobileMenuOpen = false"
            >
              <span class="sr-only">Close menu</span>
              <XMarkIcon class="w-6 h-6" aria-hidden="true" />
            </button>
          </div>
          <div class="flow-root mt-6">
            <div class="-my-6 divide-y divide-gray-500/10">
              <div class="py-6 space-y-2">
                <a
                  v-for="item in navigation"
                  :key="item.name"
                  :href="item.href"
                  class="
                    block
                    px-3
                    py-2
                    -mx-3
                    text-base
                    font-semibold
                    leading-7
                    text-gray-900
                    rounded-lg
                    hover:bg-gray-400/10
                  "
                  >{{ item.name }}</a
                >
              </div>
              <div class="py-6">
                <!-- <a href="#" class="-mx-3 block rounded-lg py-2.5 px-3 text-base font-semibold leading-6 text-gray-900 hover:bg-gray-400/10">Log in</a> -->
                <div class="text-center cursor-pointer">
                  <v-menu data-app offset-y>
                    <template v-slot:activator="{ on, attrs }">
                      <v-btn
                        data-app
                        color="#0652DD"
                        dark
                        v-bind="attrs"
                        v-on="on"
                      >
                        Language
                      </v-btn>
                    </template>
                    <v-list data-app>
                      <v-list-item
                        data-app
                        @click="changelg"
                        v-for="(item, index) in items"
                        :key="index"
                      >
                        <v-list-item-title data-app>{{
                          item.title
                        }}</v-list-item-title>
                      </v-list-item>
                    </v-list>
                  </v-menu>
                </div>
              </div>
            </div>
          </div>
        </DialogPanel>
      </Dialog>
    </div>
  </div>
</template>

<script>
// import { ref } from 'vue'
import { Dialog, DialogPanel } from "@headlessui/vue";
import { Bars3Icon, XMarkIcon } from "@heroicons/vue/24/outline";
import ButtonComponent from "./ButtonComponent.vue";

export default {
  components: { Dialog, DialogPanel, Bars3Icon, XMarkIcon, ButtonComponent },

  methods: {
    changelg() {
      location.reload();
    },
  },

  data: () => ({
    items: [{ title: "EN" }, { title: "CN" }],

    navigation: [
      { name: "Product", href: "#" },
      { name: "Features", href: "#" },
      { name: "Marketplace", href: "#" },
      { name: "Company", href: "#" },
    ],
    mobileMenuOpen: false,
  }),

  //     data() {
  //         return {
  //             navigation: [
  //                 { name: "Product", href: "#" },
  //                 { name: "Features", href: "#" },
  //                 { name: "Marketplace", href: "#" },
  //                 { name: "Company", href: "#" },
  //             ],
  //             mobileMenuOpen: false,
  //         };
  //   },
};
</script>
<style>
</style>