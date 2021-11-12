<template>
  <div
    class="
      md:row-span-1
      flex flex-col
      justify-center
      items-center
      filter
      drop-shadow-md
      mt-8
    "
  >
    <!-- div -->
    <div class="md:flex md:flex-row w-full text-right lg:border-l">
      <div class="flex flex-row md:flex-col m-4 w-full text-left bg-gray-100">
        <div class="font-bold w-1/2">SYMBOL</div>
        <div class="w-1/2">
          <span> <i class="fab fa-apple"></i> AAPL </span>
        </div>
      </div>

      <div
        class="flex flex-row md:flex-col m-4 w-full text-left bg-gray-100"
        v-for="(table, i) in tables"
        :key="i"
      >
        <div class="font-bold w-1/2">{{ table.name }}</div>
        <div class="w-1/2">{{ table.amount }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Table",
  data() {
    return {
      tables: [
        {
          name: "PRICE",
          amount: "= $ 234.00",
        },
        { name: "%RETURN", amount: "$ 45.43" },
        { name: "TOTAL NET COST", amount: "$ 1 234.00" },
        { name: "MARKET VALUE", amount: "$ 1 345.87" },
        { name: "TOTAL GAIN", amount: "$ 456.34" },
        { name: "DAILY GAIN", amount: "-$ 3.45" },
        { name: "%PORTFOLIO", amount: "13.45%" },
      ],
    };
  },
};
</script>
