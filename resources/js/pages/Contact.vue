<script setup>
import AppLayout from '@/layouts/AppLayout.vue';
import { MapPin, Phone, Mail, Clock, Send } from 'lucide-vue-next';
import { ref } from 'vue';

const formData = ref({
  name: '',
  email: '',
  subject: '',
  message: ''
});

const submitted = ref(false);
const isSubmitting = ref(false);

const handleSubmit = () => {
  isSubmitting.value = true;
  
  setTimeout(() => {
    console.log('Form submitted:', formData.value);
    submitted.value = true;
    isSubmitting.value = false;
    
    setTimeout(() => {
      submitted.value = false;
      formData.value = { name: '', email: '', subject: '', message: '' };
    }, 4000);
  }, 1000);
};
</script>

<template>
  <AppLayout>
    <div class="min-h-screen bg-gray-950 py-16 px-4">
      <div class="max-w-7xl mx-auto">
        
        <!-- Header -->
        <div class="text-center mb-16">
          <h1 class="text-5xl md:text-6xl font-bold mb-4 text-white">
            Contact Us
          </h1>
          <p class="text-gray-400 text-xl max-w-2xl mx-auto">
           Have questions? We have answers. Reach out to our team today.
          </p>
        </div>

        <div class="grid lg:grid-cols-2 gap-8">

          <!-- Contact Form -->
          <div class="bg-gray-900 border border-gray-800 rounded-3xl p-8">
            <h2 class="text-3xl font-bold mb-8 text-white">Send us a Message</h2>
            
            <!-- Success Message -->
            <div 
              v-if="submitted" 
              class="bg-emerald-500/10 border border-emerald-500/30 text-emerald-400 px-6 py-4 rounded-xl mb-6 flex items-center gap-3"
            >
              <div class="w-6 h-6 bg-emerald-500 rounded-full flex items-center justify-center">
                <svg class="w-4 h-4 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
                </svg>
              </div>
              <span class="font-semibold">Thank you! Your message has been sent successfully.</span>
            </div>

            <div class="space-y-6">
              <div>
                <label class="block text-white font-semibold mb-3">Name</label>
                <input
                  v-model="formData.name"
                  type="text"
                  placeholder="Your name"
                  class="w-full px-4 py-4 bg-gray-800 border border-gray-700 rounded-xl focus:ring-2 focus:ring-indigo-500 focus:border-transparent text-white placeholder-gray-500 transition-all"
                  required
                />
              </div>
              
              <!-- Email Input -->
              <div>
                <label class="block text-white font-semibold mb-3">Email</label>
                <input
                  v-model="formData.email"
                  type="email"
                  placeholder="juan@example.com"
                  class="w-full px-4 py-4 bg-gray-800 border border-gray-700 rounded-xl focus:ring-2 focus:ring-indigo-500 focus:border-transparent text-white placeholder-gray-500 transition-all"
                  required
                />
              </div>
              
              <!-- Subject Input -->
              <div>
                <label class="block text-white font-semibold mb-3">Subject</label>
                <input
                  v-model="formData.subject"
                  type="text"
                  placeholder="How can we help you?"
                  class="w-full px-4 py-4 bg-gray-800 border border-gray-700 rounded-xl focus:ring-2 focus:ring-indigo-500 focus:border-transparent text-white placeholder-gray-500 transition-all"
                  required
                />
              </div>
              
              <!-- Message Textarea -->
              <div>
                <label class="block text-white font-semibold mb-3">Message</label>
                <textarea
                  v-model="formData.message"
                  rows="6"
                  placeholder="Tell us more about your inquiry..."
                  class="w-full px-4 py-4 bg-gray-800 border border-gray-700 rounded-xl focus:ring-2 focus:ring-indigo-500 focus:border-transparent resize-none text-white placeholder-gray-500 transition-all"
                  required
                ></textarea>
              </div>
              
              <!-- Submit Button -->
              <button
                @click="handleSubmit"
                :disabled="isSubmitting"
                class="w-full bg-indigo-600 text-white py-4 rounded-xl font-semibold hover:bg-indigo-700 transition-all flex items-center justify-center gap-3 shadow-lg shadow-indigo-500/30 hover:shadow-indigo-500/50 disabled:opacity-50 disabled:cursor-not-allowed"
              >
                <span v-if="!isSubmitting">Send Message</span>
                <span v-else>Sending...</span>
                <Send :size="20" v-if="!isSubmitting" />
              </button>
            </div>
          </div>

          <div class="space-y-6">

            <div class="bg-gray-900 border border-gray-800 rounded-3xl p-8">
              <h2 class="text-3xl font-bold mb-8 text-white">Get in Touch</h2>
              
              <div class="space-y-6">

                <div class="flex items-start gap-4 group">
                  <div class="bg-indigo-500/10 p-4 rounded-xl group-hover:bg-indigo-500/20 transition-colors">
                    <MapPin class="text-indigo-400" :size="28" />
                  </div>
                  <div class="flex-1">
                    <h3 class="font-bold text-lg mb-2 text-white">Address</h3>
                    <p class="text-gray-400 leading-relaxed">
                      321 Commerce Street<br />
                      San Pedro City, Laguna
                    </p>
                  </div>
                </div>
                

                <div class="flex items-start gap-4 group">
                  <div class="bg-emerald-500/10 p-4 rounded-xl group-hover:bg-emerald-500/20 transition-colors">
                    <Phone class="text-emerald-400" :size="28" />
                  </div>
                  <div class="flex-1">
                    <h3 class="font-bold text-lg mb-2 text-white">Phone</h3>
                    <p class="text-gray-400 leading-relaxed">
                      (+63) 9987654321<br />
                      Mon-Fri, 9AM-8PM
                    </p>
                  </div>
                </div>
                
                <!-- Email -->
                <div class="flex items-start gap-4 group">
                  <div class="bg-purple-500/10 p-4 rounded-xl group-hover:bg-purple-500/20 transition-colors">
                    <Mail class="text-purple-400" :size="28" />
                  </div>
                  <div class="flex-1">
                    <h3 class="font-bold text-lg mb-2 text-white">Email</h3>
                    <p class="text-gray-400 leading-relaxed">
                      support@novus.com<br />
                      sales@novus.com
                    </p>
                  </div>
                </div>
              </div>
            </div>

            <!-- Business Hours -->
            <div class="bg-gradient-to-br from-indigo-600 to-purple-600 rounded-3xl p-8 relative overflow-hidden">
              <div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjAiIGhlaWdodD0iNjAiIHZpZXdCb3g9IjAgMCA2MCA2MCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZyBmaWxsPSJub25lIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiPjxnIGZpbGw9IiNmZmYiIGZpbGwtb3BhY2l0eT0iMC4xIj48cGF0aCBkPSJNMzYgMzRjMC0yLjIxLTEuNzktNC00LTRzLTQgMS43OS00IDQgMS43OSA0IDQgNCA0LTEuNzkgNC00em0wLTEwYzAtMi4yMS0xLjc5LTQtNC00cy00IDEuNzktNCA0IDEuNzkgNCA0IDQgNC0xLjc5IDQtNHptLTEwIDBjMC0yLjIxLTEuNzktNC00LTRzLTQgMS43OS00IDQgMS43OSA0IDQgNCA0LTEuNzkgNC00eiIvPjwvZz48L2c+PC9zdmc+')] opacity-10"></div>
              
              <div class="relative z-10">
                <div class="flex items-center gap-3 mb-6">
                  <Clock class="text-white" :size="28" />
                  <h3 class="text-2xl font-bold text-white">Business Hours</h3>
                </div>
                
                <div class="space-y-4">
                  <div class="flex justify-between items-center py-3 border-b border-white/20">
                    <span class="text-white font-medium">Monday - Friday</span>
                    <span class="font-bold text-white">9:00 AM - 8:00 PM</span>
                  </div>
                  <div class="flex justify-between items-center py-3 border-b border-white/20">
                    <span class="text-white font-medium">Saturday</span>
                    <span class="font-bold text-white">10:00 AM - 7:00 PM</span>
                  </div>
                  <div class="flex justify-between items-center py-3">
                    <span class="text-white font-medium">Sunday</span>
                    <span class="font-bold text-white">Closed</span>
                  </div>
                </div>
              </div>
            </div>

          </div>
        </div>
      </div>
    </div>
  </AppLayout>
</template>