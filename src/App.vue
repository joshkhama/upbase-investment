<template>
  <div id="app" class="flex h-screen w-screen overflow-hidden p-4">
    <SideNav />

    <!-- DASHBOARD -->
    <div
      class="
        w-full
        lg:grid lg:grid-rows-5 lg:grid-flow-row lg:gap-4
        md:flex md:flex-col
        sm:flex sm:flex-col
        mx-2
        overflow-y-auto
        lg:overflow-y-hidden
        md:flex md:flex-col
        sm:flex sm:flex-col
      "
    >
      <!-- Upgrade your Account -->
      <div class="lg:row-span-2 bg-gray-200 rounded-tr-3xl rounded-bl-3xl">
        <!-- mini header -->
        <div class="flex justify-end lg:space-x-16 lg:mx-16 my-8 lg:text-xl">
          <div>
            <span class="cursor-pointer">
              <i class="far fa-sun mr-4"></i>
              <span>US Stock market opens in 3 hours</span>
            </span>
          </div>
          <div>
            <span class="cursor-pointer">
              <span>Main Wallet</span>
              <i class="fas fa-sort-down pl-2"></i>
            </span>
          </div>
          <div class="cursor-pointer">
            <i class="far fa-bell w-8 h-8"></i>
          </div>
          <div
            class="
              p-2
              bg-black
              rounded-full
              h-8
              w-8
              flex
              items-center
              justify-center
              cursor-pointer
            "
          >
            <i class="fas fa-plus text-white text-sm"></i>
          </div>
        </div>

        <!-- upgrade your account -->
        <div class="lg:grid grid-cols-8 gap-16 h-4/5 mx-1">
          <div class="lg:col-span-3 rounded-3xl bg-white text-center mb-4">
            <div class="mt-12 mb-2 text-2xl font-bold">
              <span>Upgrade your Account</span>
            </div>
            <div class="flex flex-row">
              <img
                src="img1.png"
                class="m-2 w-1/2 h-auto lg:object-left-bottom lg:-ml-16"
              />

              <div class="flex flex-col text-left mx-2">
                <div class="text-lg">
                  <span class="text-gray-500"
                    >Access many other features and helpful insights.</span
                  >
                </div>
                <div
                  class="
                    flex
                    items-center
                    justify-center
                    p-2
                    my-2
                    bg-black
                    rounded-lg
                    w-1/2
                    cursor-pointer
                  "
                >
                  <i class="fas fa-arrow-right text-white text-3xl"></i>
                </div>
              </div>
            </div>
          </div>
          <div class="lg:col-span-5 rounded-3xl bg-white">2</div>
        </div>
      </div>

      <!-- Portfolio History -->
      <div class="lg:row-span-2">
        <div class="flex justify-between space-x-16 mx-16 mt-8 mb-2 lg:text-xl">
          <div class="">
            <span>Portfolio History</span>
          </div>
          <div class="underline">
            <span>Per Industry</span>
          </div>
        </div>

        <div class="lg:grid grid-cols-9 gap-8 h-4/5 mx-16">
          <div class="lg:col-span-2 border-2 rounded-3xl">1</div>
          <div class="lg:col-span-2 border-2 rounded-3xl">2</div>
          <div class="lg:col-span-2 border-2 rounded-3xl">3</div>
          <div class="lg:col-span-3 bg-blue-600 rounded-3xl">4</div>
        </div>
      </div>

      <!-- Money Table -->
      <Table />
    </div>
  </div>
</template>

<script>
import SideNav from "./components/SideNav.vue";
import Table from "./components/Table";

export default {
  name: "App",
  components: {
    Table,
    SideNav,
  },

  data() {
    return {};
  },
};
</script>

<style scoped>
#app {
  font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS", sans-serif;
}
</style>
