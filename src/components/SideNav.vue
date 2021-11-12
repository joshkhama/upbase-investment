<template>
  <div
    class="
      w-1/6
      lg:w-1/4
      px-1
      lg:px-6
      py-2
      flex flex-col
      justify-between
      bg-gray-100
      rounded-lg
      filter
      drop-shadow-md
    "
  >
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
          <p class="text-lg font-semibold text-left hidden lg:block">LogOut</p>
        </button>
      </div>
    </div>
    <!-- End of sidebar -->
  </div>
</template>

<script>
export default {
  name: "SideNav",
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
};
</script>
