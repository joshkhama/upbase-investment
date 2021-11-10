<template>
  <div id="app" class="flex h-screen w-screen overflow-hidden p-4">
    <!-- 
      Width of 16 by default, 32 on medium screens, and 48 on large screens 
      <img class="w-16 md:w-32 lg:w-48" src="...">
   -->

    <!-- side nav -->
    <div class="lg:w-1/4 px-2 lg:px-6 py-2 flex flex-col justify-between">
      <!-- Profile Account -->
      <div class="lg:w-full relative">
        <button
          class="
            flex
            items-center
            w-full
            hover:bg-lightblue
            rounded-full
            p-2
            focus:outline-none
          "
        >
          <img
            src="avater.png"
            alt="profile picture"
            class="w-10 h10 rounded-lg border border-lighter"
          />
          <div class="hidden lg:block ml-4 text-left">
            <p class="text-sm font-bold leading-tight">Kristen Ramos</p>
            <p class="text-sm leading-tight">kristen.ramos@email.com</p>
          </div>
        </button>
      </div>

      <!-- Dashboard Tabs -->
      <div>
        <div>
          <button
            v-for="(tab, i) in tabs"
            :key="i"
            @click="id = tab.id"
            :class="`focus:outline-none hover:text-blue flex item-center py-2 px-4 hover:bg-light-blue rounded-full mr-auto mb-3 ${
              id === tab.id ? 'text-blue' : ''
            }`"
          >
            <i :class="`${tab.icon} text-2xl mr-4 text-left`"></i>
            <p class="text-lg font-semibold text-left hidden lg:block">
              {{ tab.title }}
            </p>
          </button>
        </div>
      </div>

      <!-- Logout Tab -->
      <div>
        <div>
          <button
            class="
              flex
              item-center
              py-2
              px-4
              hover:bg-light-blue
              rounded-full
              mr-auto
              mb-3
            "
          >
            <i class="fas fa-sign-out-alt text-2xl mr-4 text-left"></i>
            <p class="text-lg font-semibold text-left hidden lg:block">
              LogOut
            </p>
          </button>
        </div>
      </div>
      <!-- End of sidebar -->
    </div>

    <!-- DASHBOARD -->

    <div
      class="
        w-screen
        lg:grid lg:grid-rows-5 lg:grid-flow-row lg:gap-4
        px-6
        md:overflow-y-auto
        sm:overflow-y-auto
        md:flex md:flex-col
        sm:flex sm:flex-col
      "
    >
      <div class="lg:row-span-2 bg-gray-200 rounded-tr-3xl rounded-bl-3xl">
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

        <div class="grid grid-cols-8 gap-16 h-4/5 mx-16">
          <div class="col-span-3 rounded-3xl bg-white text-center">
            <div class="mt-12 mb-2 text-3xl">
              <span>Upgrade your Account</span>
            </div>
            <div class="flex">
              <div class="flex-1 m-2">
                <img
                  src="img1.png"
                  class="w-52 h-full object-left-bottom -ml-16"
                />
              </div>
              <div class="flex-1 text-left mr-10 space-y-4">
                <div class="row-span-2 text-xl block">
                  <span class="text-gray-500"
                    >Access many other features and helpful insights.</span
                  >
                </div>
                <div
                  class="
                    p-2
                    bg-black
                    rounded-lg
                    h-16
                    w-16
                    items-center
                    justify-center
                    cursor-pointer
                    block
                    flex
                    float-right
                  "
                >
                  <i class="fas fa-arrow-right text-white text-3xl"></i>
                </div>
              </div>
            </div>
          </div>
          <div class="col-span-5 rounded-3xl bg-white">2</div>
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

        <div class="grid grid-cols-9 gap-8 h-4/5 mx-16">
          <div class="col-span-2 border-2 rounded-3xl"></div>
          <div class="col-span-2 border-2 rounded-3xl"></div>
          <div class="col-span-2 border-2 rounded-3xl"></div>
          <div class="col-span-3 bg-blue-600 rounded-3xl"></div>
        </div>
      </div>

      <!-- Money Table -->
      <div class="row-span-1 justify-center flex items-end">
        <table class="table-auto w-11/12 text-right px-6 border-l m-16">
          <thead>
            <tr>
              <th>SYMBOL</th>
              <th>PRICE</th>
              <th>%RETURN</th>
              <th>TOTAL NET COST</th>
              <th>MARKET VALUE</th>
              <th>TOTAL GAIN</th>
              <th>DAILY GAIN</th>
              <th>%PORTFOLIO</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>
                <span> <i class="fab fa-apple"></i> AAPL </span>
              </td>
              <td>= $ 234.00</td>
              <td>$ 45.43</td>
              <td>$ 1 234.00</td>
              <td>$ 1 345.87</td>
              <td>$ 456.34</td>
              <td>-$ 3.45</td>
              <td>13.45%</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},

  data() {
    return {
      tabs: [
        { icon: "fas fa-chart-pie", title: "Dashboard", id: "dashboard" },
        { icon: "far fa-save", title: "Holdings", id: "holdings" },
        { icon: "far fa-chart-bar", title: "Performance", id: "performance" },
      ],
      id: "dashboard",
    };
  },
  methods: {
    addNewTweet() {
      let newTweet = {
        content: this.tweet.content,
      };
      this.tweets.push(newTweet);
    },
  },
};
</script>

<style scoped>
#app {
  font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS", sans-serif;
}
</style>
