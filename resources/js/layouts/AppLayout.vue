<script setup>
import { ref } from 'vue';
import { Link } from '@inertiajs/vue3';
import { Menu, X, ShoppingCart, User, Search, Facebook, Instagram, Twitter,} from 'lucide-vue-next';

const mobileMenuOpen = ref(false);
const cartCount = ref(0);

const navigation = [
  { name: 'Home', href: '/' },
  { name: 'Products', href: '/products' },
  { name: 'About', href: '/about' },
  { name: 'Contact', href: '/contact' },
];
</script>

<template>
  <div class="min-h-screen bg-gray-50 font-sans">

    <header class="sticky top-0 z-50 bg-white/90 backdrop-blur-md border-b border-gray-100 shadow-sm transition-all duration-300">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex items-center justify-between h-20">

          <Link href="/" class="flex items-center gap-2 group">
            <div class="p-2 bg-indigo-50 rounded-xl group-hover:bg-indigo-100 transition-colors">
                 <ShoppingCart :size="24" class="text-indigo-600" />
            </div>
            <span class="text-2xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-indigo-600 to-violet-600">
              Novus
            </span>
          </Link>

          <nav class="hidden md:flex items-center gap-1">
            <Link v-for="item in navigation" :key="item.name" :href="item.href"
              class="px-4 py-2 rounded-full text-sm font-medium text-gray-600 hover:text-indigo-600 hover:bg-indigo-50 transition-all duration-200">
            {{ item.name }}
            </Link>
          </nav>

          <div class="flex items-center gap-2">         
            
            <button class="hidden md:flex p-2.5 text-gray-500 hover:text-indigo-600 hover:bg-gray-100 rounded-full transition-all">
              <User :size="25" />
            </button>

            <button class="relative p-2.5 text-gray-500 hover:text-indigo-600 hover:bg-gray-100 rounded-full transition-all group">
              <ShoppingCart :size="25" />
           
            </button>

            <button class="md:hidden p-2 text-gray-600 hover:bg-gray-100 rounded-lg transition"
              @click="mobileMenuOpen = !mobileMenuOpen">
              <Menu v-if="!mobileMenuOpen" :size="24" />
              <X v-else :size="24" />
            </button>
          </div>
        </div>
      </div>

      <transition
        enter-active-class="transition duration-200 ease-out"
        enter-from-class="transform -translate-y-2 opacity-0"
        enter-to-class="transform translate-y-0 opacity-100"
        leave-active-class="transition duration-150 ease-in"
        leave-from-class="transform translate-y-0 opacity-100"
        leave-to-class="transform -translate-y-2 opacity-0"
      >
        <nav v-if="mobileMenuOpen" class="md:hidden border-t border-gray-100 bg-white absolute w-full shadow-lg">
          <div class="px-4 pt-2 pb-6 space-y-1">
            <Link v-for="item in navigation" :key="item.name" :href="item.href"
              class="block px-4 py-3 text-base font-medium text-gray-600 rounded-lg hover:bg-indigo-50 hover:text-indigo-600 transition-colors"
              @click="mobileMenuOpen = false">
            {{ item.name }}
            </Link>
          </div>
        </nav>
      </transition>
    </header>

    <main>
      <slot />
    </main>

    <footer class="bg-slate-900 text-white pt-16 pb-8 border-t border-slate-800">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid md:grid-cols-12 gap-8 mb-12">
          
          <div class="md:col-span-4">
            <div class="flex items-center gap-2 mb-4">
              <span class="text-2xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-indigo-400 to-violet-400">Novus</span>
            </div>
            <p class="text-slate-400 leading-relaxed mb-6 max-w-sm">
              Elevate your lifestyle with our curated collection of premium products. Quality meets innovation in every item.
            </p>
            <div class="flex gap-4">
              <a href="#" class="text-slate-400 hover:text-white transition-colors"><Facebook :size="20"/></a>
              <a href="#" class="text-slate-400 hover:text-white transition-colors"><Instagram :size="20"/></a>
              <a href="#" class="text-slate-400 hover:text-white transition-colors"><Twitter :size="20"/></a>
            </div>
          </div>

          <div class="md:col-span-2 md:col-start-6">
            <h3 class="font-semibold text-white mb-4 tracking-wide">Shop</h3>
            <ul class="space-y-3">
              <li><Link href="/products" class="text-slate-400 hover:text-indigo-400 transition-colors text-sm">All Products</Link></li>
              <li><Link href="#" class="text-slate-400 hover:text-indigo-400 transition-colors text-sm">Featured</Link></li>
              <li><Link href="/products" class="text-slate-400 hover:text-indigo-400 transition-colors text-sm">New Arrivals</Link></li>
            </ul>
          </div>

          <div class="md:col-span-2">
            <h3 class="font-semibold text-white mb-4 tracking-wide">Company</h3>
            <ul class="space-y-3">
              <li><Link href="/about" class="text-slate-400 hover:text-indigo-400 transition-colors text-sm">Our Story</Link></li>
              <li><Link href="/contact" class="text-slate-400 hover:text-indigo-400 transition-colors text-sm">Contact</Link></li>
            </ul>
          </div>

          <div class="md:col-span-3">
            <h3 class="font-semibold text-white mb-4 tracking-wide">Stay Updated</h3>
            <p class="text-slate-400 text-sm mb-4">Subscribe to get special offers and updates.</p>
            <div class="flex gap-2">
              <input type="email" placeholder="Enter your email" 
                class="bg-slate-800 border-none rounded-lg px-4 py-2 w-full text-sm text-white placeholder-slate-500 focus:ring-2 focus:ring-indigo-500">
              <button class="bg-indigo-600 hover:bg-indigo-500 text-white px-4 py-2 rounded-lg text-sm font-medium transition-colors">
                Join
              </button>
            </div>
          </div>

        </div>

        <div class="border-t border-slate-800 pt-8 flex flex-col md:flex-row justify-between items-center gap-4 text-sm text-slate-500">
          <p>&copy; 2025 Novus Inc. All rights reserved.</p>
          <div class="flex gap-6">
            <a href="#" class="hover:text-slate-300 transition">Privacy</a>
            <a href="#" class="hover:text-slate-300 transition">Terms</a>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>