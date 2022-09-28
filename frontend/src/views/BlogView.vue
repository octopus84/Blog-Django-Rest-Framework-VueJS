<template>
  <div class="bg-white">
    <div class="mx-auto max-w-2xl py-16 px-4 sm:py-24 sm:px-6 lg:max-w-7xl lg:px-8">
      <h2 class="text-2xl font-bold tracking-tight text-gray-900">Post del Blog</h2>
      <div class="mt-6 grid grid-cols-3 gap-y-10 gap-x-6 sm:grid-cols-2 lg:grid-cols-4 xl:gap-x-8">

        <div v-for="post in APIData" :key="post.id" class="group relative">
          <div
            class="min-h-80 aspect-w-1 aspect-h-1 w-full overflow-hidden rounded-md bg-gray-200 group-hover:opacity-75 lg:aspect-none lg:h-80">
            <!-- <img :src="post.thumbnail" class="h-full w-full object-cover object-center lg:h-full lg:w-full" /> -->
          </div>
          <div class="mt-4 flex justify-between">
            <div>
              <h3 class="text-sm text-gray-700">
              <router-link :to="{ name: 'BlogPost', params: { slug: post.slug, id: post.id, title: post.title, content: post.content, excerpt: post.excerpt, published: post.published, author: post.author }}">  
                {{ post.title }}
              </router-link> 
            </h3>

              <p class="mt-1 text-sm text-gray-500">{{ post.content }}</p>
            </div>
            <p class="text-sm font-medium text-gray-900">{{ post.published }}</p>
            <div>
              <p class="text-sm font-medium text-gray-900">{{ post.author }}</p>
            </div>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
import { getAPI } from '../axios-api'

export default {
  name: 'Blog',
  data() {
    return {
      APIData: []
    }
  },
  created() {
    getAPI.get('/blog/posts/',)
      .then(response => {
        console.log('Post API has recieved data')
        this.APIData = response.data
      })
      .catch(err => {
        console.log(err)
      })
  }
}
</script>