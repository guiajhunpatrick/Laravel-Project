<script setup>
import AppLayout from '@/layouts/AppLayout.vue';
import { ShoppingCart, Star, Filter } from 'lucide-vue-next';
import { ref, computed } from 'vue';

const selectedCategory = ref('All');

const categories = ['All', 'Electronics', 'Clothing', 'Accessories'];

const products = [
  {
    id: 1,
    name: 'Premium Wireless Headphones',
    price: '2,499',
    category: 'Electronics',
    image: 'https://images.unsplash.com/photo-1505740420928-5e560c06d30e?w=500&q=80',
    rating: 4.8,
    reviews: 124,
    badge: 'Bestseller'
  },
  {
    id: 2,
    name: 'Smart Fitness Watch',
    price: '1,499',
    category: 'Electronics',
    image: 'https://images.unsplash.com/photo-1523275335684-37898b6baf30?w=500&q=80',
    rating: 4.6,
    reviews: 89,
    badge: 'New'
  },
  {
    id: 3,
    name: 'Leather Messenger Bag',
    price: '3,999',
    category: 'Accessories',
    image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRft7oP-gz0gv7GVBk9ruP8lMV7ox4rkNFtkA&s',
    rating: 4.9,
    reviews: 156,
    badge: 'Featured'
  },
  {
    id: 4,
    name: 'Organic Cotton T-Shirt',
    price: '1,150',
    category: 'Clothing',
    image: 'https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?w=500&q=80',
    rating: 4.7,
    reviews: 203
  },
  {
    id: 5,
    name: 'Stainless Steel Water Bottle',
    price: 949,
    category: 'Accessories',
    image: 'data:image/jpeg;base64,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',
    rating: 4.5,
    reviews: 167
  },
  {
    id: 6,
    name: 'Wireless Bluetooth Speaker',
    price: '2,999',
    category: 'Electronics',
    image: 'https://images.unsplash.com/photo-1608043152269-423dbba4e7e1?w=500&q=80',
    rating: 4.7,
    reviews: 94
  },
];

const filteredProducts = computed(() => {
  return selectedCategory.value === 'All'
    ? products
    : products.filter(p => p.category === selectedCategory.value);
});
</script>

<template>
  <AppLayout>
    <div class="min-h-screen bg-gray-950 py-16 px-4">
      <div class="max-w-7xl mx-auto">

        <div class="text-center mb-16">
          <h1 class="text-5xl md:text-6xl font-bold mb-4 text-white">
            The New Standard
          </h1>
          <p class="text-gray-400 text-xl max-w-2xl mx-auto">
            Forget the ordinary. Experience shopping reimagined.
          </p>
        </div>

        <div class="bg-gray-900 border border-gray-800 rounded-2xl p-6 mb-12">
          <div class="flex flex-wrap gap-4 items-center justify-between">
            <div class="flex items-center gap-3">
              <Filter class="text-indigo-400" :size="20" />
              <span class="font-semibold text-white">Filter by Category:</span>
            </div>
            <div class="flex flex-wrap gap-3">
              <button v-for="cat in categories" :key="cat" @click="selectedCategory = cat" :class="[
                'px-6 py-2.5 rounded-xl font-medium transition-all duration-300',
                selectedCategory === cat
                  ? 'bg-indigo-600 text-white shadow-lg shadow-indigo-500/50'
                  : 'bg-gray-800 text-gray-300 hover:bg-gray-700 border border-gray-700'
              ]">
                {{ cat }}
              </button>
            </div>
          </div>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div v-for="product in filteredProducts" :key="product.id"
            class="group bg-gray-900 rounded-2xl border border-gray-800 hover:border-indigo-500/50 transition-all duration-300 overflow-hidden">

            <div class="relative aspect-square overflow-hidden bg-gray-800">
              <img :src="product.image" :alt="product.name"
                class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500" />

              <div v-if="product.badge" class="absolute top-4 right-4">
                <span class="px-3 py-1 bg-indigo-600 text-white text-sm font-semibold rounded-full">
                  {{ product.badge }}
                </span>
              </div>

              <div
                class="absolute inset-0 bg-gradient-to-t from-gray-900 via-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300">
              </div>
            </div>

            <div class="p-6">

              <div class="flex items-center gap-2 mb-3">
                <div class="flex items-center gap-1">
                  <Star :size="16" class="fill-yellow-400 text-yellow-400" />
                  <span class="text-sm font-semibold text-white">{{ product.rating }}</span>
                </div>
                <span class="text-sm text-gray-400">({{ product.reviews }} reviews)</span>
              </div>

              <h3 class="font-bold text-xl mb-2 text-white group-hover:text-indigo-400 transition-colors">
                {{ product.name }}
              </h3>

              <p class="text-sm text-gray-400 mb-4">{{ product.category }}</p>

              <div class="flex items-center justify-between">
                <div>
                  <span class="text-3xl font-bold text-white">₱{{ product.price }}</span>
                </div>
                <button
                  class="bg-indigo-600 text-white px-6 py-3 rounded-xl hover:bg-indigo-700 transition-all flex items-center gap-2 font-semibold shadow-lg shadow-indigo-500/30 hover:shadow-indigo-500/50">
                  <ShoppingCart :size="18" />
                  Add
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </AppLayout>
</template>