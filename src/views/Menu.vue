<script setup>
import { ref } from "vue";
const menuItems = [
  {
    name: "Coffee",
    image:
      "https://images.immediate.co.uk/production/volatile/sites/30/2020/08/flat-white-3402c4f.jpg?quality=90&resize=500,454",
  },
  {
    name: "Tea",
    image:
      "https://twinings.co.uk/cdn/shop/articles/How_To_Taste_Tea.jpg?v=1622729251",
  },
  {
    name: "Sandwich",
    image:
      "https://www.watermelon.org/wp-content/uploads/2023/02/Sandwich_2023.jpg",
  },
  {
    name: "Salad",
    image:
      "https://hellolittlehome.com/wp-content/uploads/2022/08/garden-salad-recipe-2-500x500.jpg",
  },
  {
    name: "Cake",
    image:
      "https://ichef.bbci.co.uk/food/ic/food_16x9_832/recipes/rainbow_cake_20402_16x9.jpg",
  },
  {
    name: "Burger",
    image:
      "https://assets.epicurious.com/photos/5c745a108918ee7ab68daf79/1:1/w_2560%2Cc_limit/Smashburger-recipe-120219.jpg",
  },
  {
    name: "Pizza",
    image:
      "https://kauveryhospital.com/blog/wp-content/uploads/2021/04/pizza-5179939_960_720.jpg",
  },
  {
    name: "Smoothie",
    image:
      "https://www.thereciperebel.com/wp-content/uploads/2022/04/how-to-make-a-smoothie-TRR-1200-32-of-34.jpg",
  },
  {
    name: "Pasta",
    image:
      "https://savvybites.co.uk/wp-content/uploads/2023/12/Creamy-tomato-pasta-2.jpg",
  },
];

const isVisiable = ref(false);
const selectedItem = ref();

const showAlert = (item) => {
  selectedItem.value = item;
  isVisiable.value = true;
};

const closeModal = () => {
  selectedItem = null;
};
</script>

<template>
  <div class="container mx-auto mt-8">
    <h2 class="text-3xl font-bold mb-4 text-center">Menu</h2>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
      <div
        @click="showAlert(item)"
        v-for="(item, index) in menuItems"
        :key="index"
        class="bg-white rounded-lg shadow-md overflow-hidden transition duration-500 ease-in-out transform hover:scale-105"
      >
        <div class="relative">
          <img
            :src="item.image"
            :alt="item.name"
            class="w-full h-48 object-cover"
          />
          <div class="absolute inset-0 bg-black opacity-50"></div>
          <div class="absolute inset-0 flex items-center justify-center">
            <button
              class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-full focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2 focus:ring-offset-white"
            >
              {{ item.name }}
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div
    v-if="isVisiable"
    class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-50"
  >
    <div class="bg-white p-4 rounded-lg">
      <img
        :src="selectedItem.image"
        :alt="selectedItem.name"
        class="w-64 h-64 object-cover mx-auto mb-4"
      />
      <p class="text-lg font-semibold text-gray-900 text-center">
        {{ selectedItem.name }}
      </p>
      <button
        @click="isVisiable = false"
        class="block mx-auto mt-4 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
      >
        Close
      </button>
    </div>
  </div>
</template>
