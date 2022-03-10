<template>
  <div class="flex w-full ml-3 mb-3 mt-3">
		<label for="toggleTheme" class="flex items-center cursor-pointer">
			<div class="relative">
				<input 
          type="checkbox" 
          id="toggleTheme" 
          class="sr-only" 
          @change="check($event)" 
          :checked="theme=='dark' ? true : false"
        >
				<div class="block bg-gray-600 w-14 h-8 rounded-full"></div>
				<div class="dot absolute left-1 top-1 bg-white w-6 h-6 rounded-full transition"></div>
			</div>
			<div class="ml-3 text-gray-700 font-medium">
				Dark mode 
			</div>
  		</label>
	</div>

  <Post />
</template>

<script>
import Post from './components/Post.vue'

export default {
  name: 'App',
  data: function() {
    return {
      theme: ''
    }
  },
  components: {
    Post
  },
  methods: {
    check() {
      if (this.theme !== 'dark') {
        this.theme = 'dark'
        document.documentElement.classList.add('dark')
        localStorage.theme = 'dark'
      } else {
        this.theme = ''
        document.documentElement.classList.remove('dark')
        localStorage.theme = ''
      }
    }
  },
  mounted() {
    if (localStorage.theme === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
      this.theme = 'dark'
      document.documentElement.classList.add('dark')
    } else {
      this.theme = ''
      document.documentElement.classList.remove('dark')
    }
  },
}
</script>

<style scoped>
input:checked ~ .dot {
  transform: translateX(100%);
  background-color: #48bb78;
}
</style>
