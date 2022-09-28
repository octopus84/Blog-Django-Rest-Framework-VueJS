<template>
  <div class="bg-white">
    <div class="mx-auto max-w-2xl py-16 px-4 sm:py-24 sm:px-6 lg:max-w-7xl lg:px-8">
      <h2 class="text-2xl font-bold tracking-tight text-gray-900">PostDetail del Blog</h2>
      <div
        class="min-h-80 aspect-w-1 aspect-h-1 w-full overflow-hidden rounded-md bg-gray-200 group-hover:opacity-75 lg:aspect-none lg:h-80">
      </div>
      <div class="mt-4 flex justify-between">
        <div>
          <h3>
            {{ $route.params.slug }}
          </h3>
        </div>
        <p class="mt-5 text-sm text-gray-500">{{ $route.params.content }}</p>
      </div>
    </div>
  </div>
</template>