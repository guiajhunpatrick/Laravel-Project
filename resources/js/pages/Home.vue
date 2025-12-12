<script setup>
import { Link } from '@inertiajs/vue3';
import { router } from '@inertiajs/vue3';
import AppLayout from '@/layouts/AppLayout.vue';
import { Truck, Shield, Package, ArrowRight, Zap, Award, HeartHandshake } from 'lucide-vue-next';

const navigateToShop = () => {
  router.visit('/products');
};
</script>

<template>
  <AppLayout>
    <div class="relative">

      <section class="relative min-h-screen flex items-center justify-center overflow-hidden">

        <div class="absolute inset-0 bg-gradient-to-br from-indigo-600 via-purple-600 to-pink-600 opacity-90"></div>
        <div
          class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjAiIGhlaWdodD0iNjAiIHZpZXdCb3g9IjAgMCA2MCA2MCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZyBmaWxsPSJub25lIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiPjxnIGZpbGw9IiNmZmYiIGZpbGwtb3BhY2l0eT0iMC4xIj48cGF0aCBkPSJNMzYgMzRjMC0yLjIxLTEuNzktNC00LTRzLTQgMS43OS00IDQgMS43OSA0IDQgNCA0LTEuNzkgNC00em0wLTEwYzAtMi4yMS0xLjc5LTQtNC00cy00IDEuNzktNCA0IDEuNzkgNCA0IDQgNC0xLjc5IDQtNHptLTEwIDBjMC0yLjIxLTEuNzktNC00LTRzLTQgMS43OS00IDQgMS43OSA0IDQgNCA0LTEuNzkgNC00eiIvPjwvZz48L2c+PC9zdmc+')] opacity-20">
        </div>

        <div class="relative z-10 max-w-6xl mx-auto px-4 py-32 text-center">

          <h1 class="text-6xl md:text-7xl font-bold mb-6 leading-tight text-white drop-shadow-lg">
            Elevate Your Lifestyle
            <span class="block bg-gradient-to-r from-yellow-300 to-pink-300 bg-clip-text text-transparent">
              With Premium Products
            </span>
          </h1>
          <p class="text-xl md:text-2xl mb-10 text-white/90 max-w-3xl mx-auto font-light">
            Discover curated collections that blend innovation, style, and sustainability.
            Your perfect purchase is just a click away.
          </p>
          <div class="flex flex-col sm:flex-row gap-4 justify-center">
            <button @click="navigateToShop"
              class="group bg-white text-indigo-600 px-8 py-4 rounded-2xl font-bold hover:bg-gray-100 transition-all flex items-center justify-center gap-2 shadow-2xl hover:shadow-3xl transform hover:-translate-y-1">
              Get Yours
              <ArrowRight :size="24" class="group-hover:translate-x-1 transition-transform" />
            </button>
            <Link href="/about"
              class="bg-white/10 backdrop-blur-sm text-white border-2 border-white/30 px-8 py-4 rounded-full font-bold hover:bg-white/20 transition-all inline-block text-center">
            Learn More
            </Link>
          </div>

          <div class="mt-20 grid grid-cols-3 gap-8 max-w-3xl mx-auto">
            <div class="text-center">
              <div class="text-4xl font-bold text-white mb-2">10K+</div>
              <div class="text-white/80">Satisfied Customers</div>
            </div>
            <div class="text-center">
              <div class="text-4xl font-bold text-white mb-2">200+</div>
              <div class="text-white/80">Premium Products</div>
            </div>
            <div class="text-center">
              <div class="text-4xl font-bold text-white mb-2">4.7</div>
              <div class="text-white/80">Average Rating</div>
            </div>
          </div>
        </div>

        <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce">
          <div class="w-8 h-12 border-2 border-white/30 rounded-full flex justify-center">
            <div class="w-1.5 h-3 bg-white rounded-full mt-2"></div>
          </div>
        </div>
      </section>

      <section class="py-24 px-4 bg-gray-950">
        <div class="max-w-7xl mx-auto">
          <div class="text-center mb-16">
            <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">Why Choose Novus?</h2>
            <p class="text-gray-400 text-lg">Experience excellence in every interaction</p>
          </div>

          <div class="grid md:grid-cols-3 gap-8">

            <div
              class="group relative bg-gradient-to-br from-gray-900 to-gray-800 p-8 rounded-3xl border border-gray-800 hover:border-indigo-500 transition-all duration-300 overflow-hidden">
              <div
                class="absolute inset-0 bg-gradient-to-br from-indigo-600/10 to-purple-600/10 opacity-0 group-hover:opacity-100 transition-opacity">
              </div>
              <div class="relative z-10">
                <div
                  class="bg-indigo-500/10 w-16 h-16 rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
                  <Truck class="text-indigo-400" :size="32" />
                </div>
                <h3 class="text-2xl font-bold text-white mb-3"> Fast Delivery</h3>
                <p class="text-gray-400 leading-relaxed">Free express shipping on orders over $25. Track your package in
                  real-time from our warehouse to your doorstep.</p>
              </div>
            </div>

            <div
              class="group relative bg-gradient-to-br from-gray-900 to-gray-800 p-8 rounded-3xl border border-gray-800 hover:border-emerald-500 transition-all duration-300 overflow-hidden">
              <div
                class="absolute inset-0 bg-gradient-to-br from-emerald-600/10 to-teal-600/10 opacity-0 group-hover:opacity-100 transition-opacity">
              </div>
              <div class="relative z-10">
                <div
                  class="bg-emerald-500/10 w-16 h-16 rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
                  <Shield class="text-emerald-400" :size="32" />
                </div>
                <h3 class="text-2xl font-bold text-white mb-3">Secure Payments</h3>
                <p class="text-gray-400 leading-relaxed">Shop with confidence using our encrypted payment system. Your
                  data is protected by industry-leading security.</p>
              </div>
            </div>

            <!-- Feature Card 3 -->
            <div
              class="group relative bg-gradient-to-br from-gray-900 to-gray-800 p-8 rounded-3xl border border-gray-800 hover:border-purple-500 transition-all duration-300 overflow-hidden">
              <div
                class="absolute inset-0 bg-gradient-to-br from-purple-600/10 to-pink-600/10 opacity-0 group-hover:opacity-100 transition-opacity">
              </div>
              <div class="relative z-10">
                <div
                  class="bg-purple-500/10 w-16 h-16 rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
                  <HeartHandshake class="text-purple-400" :size="32" />
                </div>
                <h3 class="text-2xl font-bold text-white mb-3">10-Day Returns</h3>
                <p class="text-gray-400 leading-relaxed">Not satisfied? Return any product within 10 days for a full
                  refund. No questions asked, customer satisfaction guaranteed.</p>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>
  </AppLayout>
</template>