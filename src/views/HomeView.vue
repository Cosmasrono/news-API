<template>
  <div class=" text-white ">
    <h1 class=" text-2xl text-yellow-500 items-center justify-center flex p-3"> GET THE WORLD NEWS </h1>
    <h2 class=" text-xl text-yellow-500 items-center justify-center flex">Latest News Headlines</h2>
  <div class=" flex items-center justify-center ">
    <ul v-if="articles.length" class=" bg-slate-600 items-center justify-center p-4 m-5">
      <li v-for="article in articles" :key="article">
        <a :href="article.url" target="_blank">{{ article.title }}</a>
      </li>
    </ul>
  </div>

<footer class="p-4 bg-slate-700 rounded-lg shadow md:px-6 md:py-8 ">
  <div class="sm:flex sm:items-center sm:justify-between">
      <!-- <a href="https://flowbite.com/" class="flex items-center mb-4 sm:mb-0">
          <img src="https://flowbite.com/docs/images/logo.svg" class="h-8 mr-3" alt="Flowbite Logo" />
          <span class="self-center text-2xl font-semibold whitespace-nowrap dark:text-white">Flowbite</span>
      </a> -->
      <ul class="flex flex-wrap items-center mb-6 text-sm text-white sm:mb-0 dark:text-gray-400">
          <li>
              <a href="#" class="mr-4 hover:underline md:mr-6 ">About</a>
          </li>
          <li>
              <a href="#" class="mr-4 hover:underline md:mr-6">Privacy Policy</a>
          </li>
          <li>
              <a href="#" class="mr-4 hover:underline md:mr-6 ">Licensing</a>
          </li>
          <li>
              <a href="#" class="hover:underline">Contact</a>
          </li>
      </ul>
  </div>
   <hr class="my-6 border-gray-200 sm:mx-auto dark:border-gray-700 lg:my-8" />
  <span class="block text-sm text-white sm:text-center dark:text-gray-400">@cossi Wing001@23. All Rights Reserved.
  </span>
</footer>

  </div>
</template>

<script>
import axios, { isCancel } from 'axios';

export default {
  data() {
    return {
      articles: [],
    };
  },
  mounted() {
    const API_KEY = '474e46efb1fb4bd4ad1abe6ce15321ad';
    const API_ENDPOINT = `https://newsapi.org/v2/top-headlines?country=us&apiKey=${API_KEY}`;
    axios.get(API_ENDPOINT)
      .then(response => {
        this.articles = response.data.articles;
      })
      .catch(error => {
        console.error(error);
      });
  },
};
</script>
