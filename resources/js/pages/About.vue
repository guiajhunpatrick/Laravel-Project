<script setup>
import AppLayout from '@/layouts/AppLayout.vue';
import { Check, Heart, Shield, Target, Users, TrendingUp, Package, Star } from 'lucide-vue-next';
</script>

<template>
  <AppLayout>
    <div class="min-h-screen bg-gray-950">
      <div class="relative py-24 px-4 overflow-hidden">
        <div class="absolute inset-0 bg-gradient-to-br from-indigo-600/20 via-purple-600/20 to-pink-600/20"></div>
        <div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjAiIGhlaWdodD0iNjAiIHZpZXdCb3g9IjAgMCA2MCA2MCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZyBmaWxsPSJub25lIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiPjxnIGZpbGw9IiNmZmYiIGZpbGwtb3BhY2l0eT0iMC4wNSI+PHBhdGggZD0iTTM2IDM0YzAtMi4yMS0xLjc5LTQtNC00cy00IDEuNzktNCA0IDEuNzkgNCA0IDQgNC0xLjc5IDQtNHptMC0xMGMwLTIuMjEtMS43OS00LTQtNHMtNCAxLjc5LTQgNCA0IDQgNC00em0tMTAgMGMwLTIuMjEtMS43OS00LTQtNHMtNCAxLjc5LTQgNCA0IDQgNC00eiIvPjwvZz48L2c+PC9zdmc+')] opacity-30"></div>
        
        <div class="relative z-10 max-w-7xl mx-auto text-center">
          <h1 class="text-5xl md:text-7xl font-bold mb-6 text-white">
            Redefining Online Shopping
          </h1>
          <p class="text-xl md:text-2xl text-gray-400 max-w-3xl mx-auto leading-relaxed">
            Since 2020, we've been on a mission to bring premium quality products and exceptional service to customers worldwide
          </p>
        </div>
      </div>

      <div class="max-w-7xl mx-auto px-4 pb-24">
        
        <div class="mb-24">
          <div class="bg-gray-900 border border-gray-800 rounded-3xl p-12">
            <div class="flex items-center gap-3 mb-8">
              <div class="w-12 h-1 bg-gradient-to-r from-indigo-600 to-purple-600 rounded-full"></div>
              <h2 class="text-4xl font-bold text-white">Our Story</h2>
            </div>
            
            <div class="space-y-6 text-lg">
              <p class="text-gray-300 leading-relaxed">
                Founded in 2020, Novus began with a simple yet powerful vision: to make premium quality products accessible to everyone, everywhere. What started as a small online store has evolved into a trusted destination for thousands of satisfied customers across the globe.
              </p>
              
              <p class="text-gray-300 leading-relaxed">
                We carefully curate every product in our collection, ensuring it meets our rigorous standards for quality, sustainability, and value. Our dedicated team is passionate about providing an exceptional shopping experience from the moment you start browsing to the day your order arrives at your doorstep.
              </p>

              <p class="text-gray-300 leading-relaxed">
                Today, we're proud to serve customers in over 25 countries, offering a diverse range of products that blend innovation with timeless design. Our commitment to excellence drives everything we do.
              </p>
            </div>
          </div>
        </div>

        <div class="mb-24">
          <div class="text-center mb-16">
            <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">Our Core Values</h2>
            <p class="text-gray-400 text-lg">The principles that guide everything we do</p>
          </div>

          <div class="grid md:grid-cols-3 gap-8">
            <div class="group bg-gray-900 border border-gray-800 hover:border-indigo-500/50 rounded-3xl p-8 transition-all duration-300">
              <div class="bg-indigo-500/10 w-20 h-20 rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
                <Check class="text-indigo-400" :size="40" />
              </div>
              <h3 class="text-2xl font-bold mb-4 text-white">Quality First</h3>
              <p class="text-gray-400 leading-relaxed">
                We never compromise on the quality of our products or service. Every item is handpicked and thoroughly vetted to ensure it exceeds expectations.
              </p>
            </div>

            <div class="group bg-gray-900 border border-gray-800 hover:border-emerald-500/50 rounded-3xl p-8 transition-all duration-300">
              <div class="bg-emerald-500/10 w-20 h-20 rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
                <Heart class="text-emerald-400" :size="40" />
              </div>
              <h3 class="text-2xl font-bold mb-4 text-white">Customer Care</h3>
              <p class="text-gray-400 leading-relaxed">
                Your satisfaction is our top priority, always. Our dedicated support team is here to ensure you have the best shopping experience possible.
              </p>
            </div>

            <div class="group bg-gray-900 border border-gray-800 hover:border-purple-500/50 rounded-3xl p-8 transition-all duration-300">
              <div class="bg-purple-500/10 w-20 h-20 rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
                <Shield class="text-purple-400" :size="40" />
              </div>
              <h3 class="text-2xl font-bold mb-4 text-white">Trust & Integrity</h3>
              <p class="text-gray-400 leading-relaxed">
                We build lasting relationships through honesty and transparency. Your trust is the foundation of our success.
              </p>
            </div>
          </div>
        </div>

        <div class="bg-gradient-to-br from-indigo-600 to-purple-600 rounded-3xl p-12 mb-24 relative overflow-hidden">
          <div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjAiIGhlaWdodD0iNjAiIHZpZXdCb3g9IjAgMCA2MCA2MCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZyBmaWxsPSJub25lIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiPjxnIGZpbGw9IiNmZmYiIGZpbGwtb3BhY2l0eT0iMC4xIj48cGF0aCBkPSJNMzYgMzRjMC0yLjIxLTEuNzktNC00LTRzLTQgMS43OS00IDQgMS43OSA0IDQgNCA0LTEuNzkgNC00em0wLTEwYzAtMi4yMS0xLjc5LTQtNC00cy00IDEuNzktNCA0IDEuNzkgNCA0IDQgNC0xLjc5IDQtNHptLTEwIDBjMC0yLjIxLTEuNzktNC00LTRzLTQgMS43OS00IDQgMS43OSA0IDQgNCA0LTEuNzkgNC00eiIvPjwvZz48L2c+PC9zdmc+')] opacity-10"></div>
          
          <div class="relative z-10">
            <div class="text-center mb-12">
              <h2 class="text-4xl font-bold text-white mb-4">Our Impact in Numbers</h2>
              <p class="text-white/80 text-lg">Real metrics that showcase our growth and commitment</p>
            </div>

            <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
              <div class="text-center">
                <div class="flex items-center justify-center mb-3">
                  <Users class="text-white/80" :size="32" />
                </div>
                <div class="text-5xl font-bold text-white mb-2">10,000+</div>
                <div class="text-white/80 font-medium">Satisfied Customers</div>
              </div>
              <div class="text-center">
                <div class="flex items-center justify-center mb-3">
                  <Package class="text-white/80" :size="32" />
                </div>
                <div class="text-5xl font-bold text-white mb-2">200+</div>
                <div class="text-white/80 font-medium">Premium Products</div>
              </div>
              <div class="text-center">
                <div class="flex items-center justify-center mb-3">
                  <Star class="text-white/80" :size="32" />
                </div>
                <div class="text-5xl font-bold text-white mb-2">4.7</div>
                <div class="text-white/80 font-medium">Average Rating</div>
              </div>
              <div class="text-center">
                <div class="flex items-center justify-center mb-3">
                  <TrendingUp class="text-white/80" :size="32" />
                </div>
                <div class="text-5xl font-bold text-white mb-2">10+</div>
                <div class="text-white/80 font-medium">Countries Served</div>
              </div>
            </div>
          </div>
        </div>

        <div class="bg-gray-900 border border-gray-800 rounded-3xl p-12 text-center">
          <div class="max-w-3xl mx-auto">
            <div class="bg-indigo-500/10 w-20 h-20 rounded-2xl flex items-center justify-center mx-auto mb-6">
              <Target class="text-indigo-400" :size="40" />
            </div>
            <h2 class="text-4xl font-bold text-white mb-6">Our Mission</h2>
            <p class="text-gray-300 text-xl leading-relaxed">
              To revolutionize online shopping by delivering exceptional products, outstanding service, and creating meaningful connections with our customers worldwide. We're committed to sustainability, innovation, and making a positive impact in everything we do.
            </p>
          </div>
        </div>

      </div>
    </div>
  </AppLayout>
</template>