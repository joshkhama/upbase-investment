<template>
  <div id="app" class="flex h-screen w-screen overflow-hidden p-4">
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

    <div class="w-screen grid grid-rows-5 grid-flow-row gap-4 px-6">
      <div class="row-span-2 bg-gray-200">
        <div class="flex justify-end space-x-16">
          <div>
            <span>
              <i class="far fa-sun"></i>
              <span>US Stock market opens in 3 hours</span>
            </span>
          </div>
          <div>
            <span>
              <span>Main Wallet</span>
              <i class="fas fa-sort-down"></i>
            </span>
          </div>
          <div>
            <i class="far fa-bell"></i>
          </div>
          <div>
            <i class="fas fa-plus"></i>
          </div>
        </div>

        <div class="grid grid-cols-8 gap-16 h-full m-16">
          <div class="col-span-3 rounded-3xl bg-white">1</div>
          <div class="col-span-5 rounded-3xl bg-white">2</div>
        </div>
      </div>

      <!-- Portfolio History -->
      <div class="row-span-2">
        <div class="flex justify-between space-x-16">
          <div class="">
            <span>Portfolio History</span>
          </div>
          <div class="">
            <span>Per Industry</span>
          </div>
        </div>

        <div class="grid grid-cols-9 gap-8 h-full m-16">
          <div class="col-span-2 border-2 rounded-3xl"></div>
          <div class="col-span-2 border-2 rounded-3xl"></div>
          <div class="col-span-2 border-2 rounded-3xl"></div>
          <div class="col-span-3 bg-blue-600 rounded-3xl"></div>
        </div>
      </div>

      <!-- Money Table -->
      <div class="row-span-1 justify-center flex items-end">
        <table class="table-auto w-full text-right px-6 mx-12 flex-shrink">
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
