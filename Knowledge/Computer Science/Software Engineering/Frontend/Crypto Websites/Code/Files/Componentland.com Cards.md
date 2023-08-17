# Componentland.com Cards
## Product Card
The Product Card component is an easy way to display content like product descriptions. This Product card component will display featured image, product name, price, quantity, add to cart and Add to Cart button.

```html
<link href="https://fonts.googleapis.com/css2?family=Source+Sans+Pro:ital,wght@0,300;0,400;1,600&display=swap" rel="stylesheet" />
<style>
  * { 
  font-family: 'Source Sans Pro';
  }
</style>

<div class="group my-10 flex w-full max-w-xs flex-col overflow-hidden bg-white">
  <a class="relative flex h-80 w-72 overflow-hidden" href="#">
    <img class="absolute top-0 right-0 h-full w-full object-cover" src="https://images.unsplash.com/photo-1578996953841-b187dbe4bc8a?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mzl8fGJsYXplcnxlbnwwfHwwfHw%3D&auto=format&fit=crop&w=500&q=60" alt="product image" />
    <div class="absolute bottom-0 mb-4 flex w-full justify-center space-x-4">
      <div class="h-3 w-3 rounded-full border-2 border-white bg-white"></div>
      <div class="h-3 w-3 rounded-full border-2 border-white bg-transparent"></div>
      <div class="h-3 w-3 rounded-full border-2 border-white bg-transparent"></div>
    </div>
    <div class="absolute -right-16 bottom-0 mr-2 mb-4 space-y-2 transition-all duration-300 group-hover:right-0">
      <button class="flex h-10 w-10 items-center justify-center bg-gray-900 text-white transition hover:bg-gray-700">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
          <path fill-rule="evenodd" d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z" clip-rule="evenodd" />
        </svg>
      </button>
      <button class="flex h-10 w-10 items-center justify-center bg-gray-900 text-white transition hover:bg-gray-700">
        <svg xmlns="http://www.w3.org/2000/svg" class="mr-2 h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
          <path d="M3 1a1 1 0 000 2h1.22l.305 1.222a.997.997 0 00.01.042l1.358 5.43-.893.892C3.74 11.846 4.632 14 6.414 14H15a1 1 0 000-2H6.414l1-1H14a1 1 0 00.894-.553l3-6A1 1 0 0017 3H6.28l-.31-1.243A1 1 0 005 1H3zM16 16.5a1.5 1.5 0 11-3 0 1.5 1.5 0 013 0zM6.5 18a1.5 1.5 0 100-3 1.5 1.5 0 000 3z" />
        </svg>
      </button>
    </div>
  </a>
  <div class="mt-4 pb-5">
    <a href="#">
      <h5 class="text-center tracking-tight text-gray-500">Piped Linen Blend Blazer</h5>
    </a>
    <div class="mb-5 flex justify-center">
      <p>
        <span class="text-sm font-bold text-gray-900">$179</span>
        <span class="text-sm text-gray-400 line-through">$499</span>
      </p>
    </div>
  </div>
</div>
```
## Stacked Card (Hover for more)
```html
<div class="p-20">
  <div class="group relative mb-4 w-96 h-54 rounded-md border bg-blue-600 text-white py-10 px-8 shadow-lg transition-all duration-200 ease-in-out">
    <h3 class="text-xs uppercase">INTRODUCTION</h3> 
    <p class="mt-2 font-sans text-3xl font-bold">Hover Me!</p>
    <p class="mt-4">Even the clinic, the restaurant is in the cartoon. My massauris amet lorem fusce. It's aimed at the kids as always.</p>
    <div class="absolute top-0 left-0 flex h-full w-full items-center justify-center rounded-md bg-blue-600 px-10 opacity-0 transition group-hover:opacity-100">
      <a href="#" class="text-5xl font-bold">Thanks!</a>
    </div> 
  </div>
</div>
```
## CTA Card
The CTA Card component can be used to display call to action buttons on a web page.
```html
<div class="m-10 mx-4 max-w-screen-lg overflow-hidden rounded-xl border shadow-lg md:pl-8">
  <div class="flex flex-col overflow-hidden bg-white sm:flex-row md:h-80">
    <div class="flex w-full flex-col p-4 sm:w-1/2 sm:p-8 lg:w-3/5">
      <h2 class="text-xl font-bold text-gray-900 md:text-2xl lg:text-4xl">Winter Collection</h2>
      <p class="mt-2 text-lg">By Luis Vuitton</p>
      <p class="mt-4 mb-8 max-w-md text-gray-500">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aliquam iusto, cumque dolores sit odio ex.</p>
      <a href="#" class="group mt-auto flex w-44 cursor-pointer select-none items-center justify-center rounded-md bg-black px-6 py-2 text-white transition">
        <span class="group flex w-full items-center justify-center rounded py-1 text-center font-bold"> Shop now </span>
        <svg class="flex-0 group-hover:w-6 ml-4 h-6 w-0 transition-all" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
          <path stroke-linecap="round" stroke-linejoin="round" d="M14 5l7 7m0 0l-7 7m7-7H3" />
        </svg>
      </a>
    </div>

    <div class="order-first ml-auto h-48 w-full bg-gray-700 sm:order-none sm:h-auto sm:w-1/2 lg:w-2/5">
      <img class="h-full w-full object-cover" src="https://images.unsplash.com/photo-1599751449128-eb7249c3d6b1?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1169&q=80" loading="lazy" />
    </div>
  </div>
</div>
```
## Pricing Card
The Pricing Card component is used to display the pricing information. This component has a shadow, an "outlined button" that says "Request a free demo" as well as other information about the plan.

```html
<link href="https://fonts.googleapis.com/css2?family=Source+Sans+Pro:ital,wght@0,300;0,400;1,600&display=swap" rel="stylesheet" />
<style>
  * {
  font-family: 'Source Sans Pro';
  }
</style> 

<div class="m-10 w-80 rounded-lg border-2 border-gray-100 py-8 px-6 shadow-lg shadow-gray-200">
  <p class="text-lg font-bold">Essential</p>
  <p class="text-sm font-semibold text-gray-500">Covers all your basic needs</p>
  <p class="mt-3 text-4xl font-bold">$65</p>
  <p class="text-sm font-semibold text-gray-500">Per Agent per month</p>
  <button class="mt-4 w-full rounded-lg border-2 border-black px-10 py-2 text-sm font-semibold hover:bg-black hover:text-white">Request a free demo</button>
  <ul class="mt-4 space-y-2 font-semibold">
    <li class="flex items-center space-x-4"><span class="h-2 w-2 rounded-full bg-black"></span><span>250 calls per month</span></li>
    <li class="flex items-center space-x-4"><span class="h-2 w-2 rounded-full bg-black"></span><span>4 mediums</span></li>
    <li class="flex items-center space-x-4"><span class="h-2 w-2 rounded-full bg-black"></span><span>10 users</span></li>
  </ul>
  <hr class="my-4" />
  <ul class="space-y-2 font-semibold">
    <li class="flex items-center space-x-2 text-rose-600">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-500" fill="none" viewBox="0 0 20 20" stroke="currentColor" stroke-width="2">
        <path fill-rule="evenodd" d="M10 5a1 1 0 011 1v3h3a1 1 0 110 2h-3v3a1 1 0 11-2 0v-3H6a1 1 0 110-2h3V6a1 1 0 011-1z" clip-rule="evenodd" />
      </svg>
      <span>Everything from basic</span>
    </li>
    <li class="flex items-center space-x-2">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-500" fill="none" viewBox="0 0 20 20" stroke="currentColor" stroke-width="2">
        <path fill-rule="evenodd" d="M10 5a1 1 0 011 1v3h3a1 1 0 110 2h-3v3a1 1 0 11-2 0v-3H6a1 1 0 110-2h3V6a1 1 0 011-1z" clip-rule="evenodd" />
      </svg>
      <span>24/7 Support</span>
    </li>
    <li class="flex items-center space-x-2">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-500" fill="none" viewBox="0 0 20 20" stroke="currentColor" stroke-width="2">
        <path fill-rule="evenodd" d="M10 5a1 1 0 011 1v3h3a1 1 0 110 2h-3v3a1 1 0 11-2 0v-3H6a1 1 0 110-2h3V6a1 1 0 011-1z" clip-rule="evenodd" />
      </svg>
      <span>10 users</span>
    </li>
  </ul>
</div>
```
## Pricing - 3 Plans
The Pricing component displays pricing information in a visually pleasing manner.
```html
<div class="container mx-auto py-20">
  <div class="grid px-4 lg:grid-cols-4">
    <div class="mt-10 mr-14 lg:col-span-1">
      <h1 class="text-7xl">Primex</h1>
      <h2 class="mt-4 text-xl">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Molestias dignissimos nemo sint accusantium iure sed quasi error nisi.</h2>
    </div>
    <div class="lg:col-span-3">
      <div class="my-4 border-2 py-5">
        <p class="text-center font-medium">Are you a student? <span class="whitespace-nowrap text-blue-600">Get student discounts</span></p>
      </div>
      <div class="flex flex-col gap-4 md:flex-row md:justify-between">
        <div class="flex flex-col border px-4 py-8 md:w-60 lg:w-72">
          <p class="whitespace-nowrap text-3xl font-medium">Primex VI</p>
          <p class="text-3xl font-medium">Basic</p>
          <p class="text-sm font-medium">Essentials at a great price</p>
          <div class="mt-20">
            <p class="text-2xl font-medium">EUR 79</p>
            <button class="mt-2 whitespace-nowrap bg-blue-700 px-8 py-2 font-medium text-white transition-all hover:pr-10">Start Trial</button>
          </div>
        </div>
        <div class="flex flex-col bg-blue-600 px-4 py-8 text-white md:w-60 lg:w-72">
          <p class="whitespace-nowrap text-3xl font-medium">Primex VII</p>
          <p class="text-3xl font-medium">Power</p>
          <p class="text-sm font-medium">More power to you</p>
          <div class="mt-20">
            <p class="text-2xl font-medium">EUR 79</p>
            <button class="mt-2 whitespace-nowrap bg-white px-8 py-2 font-medium text-gray-900 transition-all hover:pr-10">Start Trial</button>
          </div>
        </div>
        <div class="flex flex-col bg-blue-900 px-4 py-8 text-white md:w-60 lg:w-72">
          <p class="whitespace-nowrap text-3xl font-medium">Primex VIII</p>
          <p class="text-3xl font-medium">Extreme</p>
          <p class="text-sm font-medium">Get the best in the market</p>
          <div class="mt-20">
            <p class="text-2xl font-medium">EUR 79</p>
            <button class="mt-2 whitespace-nowrap bg-white px-8 py-2 font-medium text-gray-900 transition-all hover:pr-10">Start Trial</button>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class=""></div>
</div>
```
## Pricing Card
The Pricing Card component can be used to display pricing information. This example has a red background for the card. This color will work well in some scenarios depending on color theory.

```html
<div class="my-10 max-w-xs rounded-xl bg-pink-100 px-6 py-8 text-pink-800">
  <p class="mb-2 text-2xl font-medium">Enterprise</p>
  <p class="mb-6">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Suscipit earum vitae tempore.</p>
  <div class="mb-6 space-y-2">
    <div class="flex space-x-2 font-medium">
      <span class="text-blue-600"
        ><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="h-6 w-6">
          <path fill-rule="evenodd" d="M2.25 12c0-5.385 4.365-9.75 9.75-9.75s9.75 4.365 9.75 9.75-4.365 9.75-9.75 9.75S2.25 17.385 2.25 12zm13.36-1.814a.75.75 0 10-1.22-.872l-3.236 4.53L9.53 12.22a.75.75 0 00-1.06 1.06l2.25 2.25a.75.75 0 001.14-.094l3.75-5.25z" clip-rule="evenodd"></path>
        </svg>
      </span>
      <span>Better Support</span>
    </div>
    <div class="flex space-x-2 font-medium">
      <span class="text-blue-600"
        ><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="h-6 w-6">
          <path fill-rule="evenodd" d="M2.25 12c0-5.385 4.365-9.75 9.75-9.75s9.75 4.365 9.75 9.75-4.365 9.75-9.75 9.75S2.25 17.385 2.25 12zm13.36-1.814a.75.75 0 10-1.22-.872l-3.236 4.53L9.53 12.22a.75.75 0 00-1.06 1.06l2.25 2.25a.75.75 0 001.14-.094l3.75-5.25z" clip-rule="evenodd"></path>
        </svg>
      </span>
      <span>5 team members</span>
    </div>
    <div class="flex space-x-2 font-medium">
      <span class="text-blue-600"
        ><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="h-6 w-6">
          <path fill-rule="evenodd" d="M2.25 12c0-5.385 4.365-9.75 9.75-9.75s9.75 4.365 9.75 9.75-4.365 9.75-9.75 9.75S2.25 17.385 2.25 12zm13.36-1.814a.75.75 0 10-1.22-.872l-3.236 4.53L9.53 12.22a.75.75 0 00-1.06 1.06l2.25 2.25a.75.75 0 001.14-.094l3.75-5.25z" clip-rule="evenodd"></path>
        </svg>
      </span>
      <span>200 Credits</span>
    </div>
  </div>
  <button class="w-full rounded-xl bg-blue-600 px-4 py-3 text-xl font-medium text-white">Choose Plan</button>
</div>
```
## Feature Card
The Feature Card component is an easy way to display content like blog intros. This Blog article card is displaying featured image, post date, title, summary and author name.
```html
<div class="mx-auto my-10 max-w-xs rounded-xl px-6 py-10 text-gray-600 shadow">
  <div class="mb-4 w-20 rounded-md bg-blue-100 px-2 py-1 text-sm font-medium text-blue-700">Feature</div>
  <p class="mb-2 text-2xl">Never miss your important emails</p>
  <p class="mb-6 text-gray-400">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Eligendi natus quae ex! Aliquam, ipsa.</p>
  <button class="flex items-center space-x-2 rounded-md border-2 border-blue-500 px-4 py-2 font-medium text-blue-600 transition hover:bg-blue-500 hover:text-white">
    <span> Learn more </span>
    <span
      ><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="h-6 w-6">
        <path fill-rule="evenodd" d="M16.72 7.72a.75.75 0 011.06 0l3.75 3.75a.75.75 0 010 1.06l-3.75 3.75a.75.75 0 11-1.06-1.06l2.47-2.47H3a.75.75 0 010-1.5h16.19l-2.47-2.47a.75.75 0 010-1.06z" clip-rule="evenodd" />
      </svg>
    </span>
  </button>
</div>
```
## Author Card
Use this Tailwindcss component to showcase author details on a news site or any multi-author site.
```html
<div class="mx-2 my-10 rounded-xl border bg-white px-4 shadow-md sm:mx-auto sm:max-w-xl sm:px-8">
  <div class="mb-2 flex flex-col gap-y-6 border-b py-8 sm:flex-row sm:items-center sm:justify-between">
    <div class="flex items-center">
      <img class="h-14 w-14 rounded-full object-cover" src="/images/y9s3xOJV6rnQPKIrdPYJy.png" alt="Simon Lewis" />
      <div class="ml-4 w-56">
        <p class="text-slate-800 text-xl font-extrabold">Richard Hendricks</p>
        <p class="text-slate-500">Algorithms Expert</p>
      </div>
    </div>
    <button class="flex items-center justify-center gap-1 rounded-lg border border-emerald-500 px-4 py-2 font-medium text-emerald-500 focus:outline-none focus:ring hover:bg-emerald-100">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="h-4 w-4">
        <path d="M11.645 20.91l-.007-.003-.022-.012a15.247 15.247 0 01-.383-.218 25.18 25.18 0 01-4.244-3.17C4.688 15.36 2.25 12.174 2.25 8.25 2.25 5.322 4.714 3 7.688 3A5.5 5.5 0 0112 5.052 5.5 5.5 0 0116.313 3c2.973 0 5.437 2.322 5.437 5.25 0 3.925-2.438 7.111-4.739 9.256a25.175 25.175 0 01-4.244 3.17 15.247 15.247 0 01-.383.219l-.022.012-.007.004-.003.001a.752.752 0 01-.704 0l-.003-.001z" />
      </svg>

      <span>Sponsor</span>
    </button>
  </div>
  <div class="mb-2 flex justify-between border-b py-8 text-sm sm:text-base">
    <div class="flex flex-col items-center">
      <p class="text-slate-700 mb-1 text-xl font-extrabold">14</p>
      <p class="text-slate-500 text-sm font-medium">Posts</p>
    </div>
    <div class="flex flex-col items-center">
      <p class="text-slate-700 mb-1 text-xl font-extrabold">1124</p>
      <p class="text-slate-500 text-sm font-medium">Followers</p>
    </div>
    <div class="flex flex-col items-center">
      <p class="text-slate-700 mb-1 text-xl font-extrabold">25</p>
      <p class="text-slate-500 text-sm font-medium">Sponsors</p>
    </div>
    <div class="flex flex-col items-center">
      <p class="text-slate-700 mb-1 text-xl font-extrabold">3</p>
      <p class="text-slate-500 text-sm font-medium">Awards</p>
    </div>
  </div>
  <div class="flex justify-between py-8">
    <button class="text-slate-500 hover:bg-slate-100 rounded-lg border-2 px-4 py-2 font-medium focus:outline-none focus:ring">Message</button>
    <button class="rounded-lg border-2 border-transparent bg-blue-600 px-4 py-2 font-medium text-white focus:outline-none focus:ring hover:bg-blue-700">Follow</button>
  </div>
</div>
```
## "Technique 2"
Finance card with money and percentage stat surrounded by a gray rounded box. Modern component.
```html
<h1 class="mt-4 text-center text-2xl leading-normal">Making white cards stand out on a white background <span class="bg-fuchsia-400/40 whitespace-nowrap rounded-md px-2 py-1 text-violet-900"> without using shadow</span></h1>

<div class="bg-slate-100 w-fit m-5 rounded-lg p-2">
  <button class="rounded-lg bg-white px-6 py-2 font-medium text-blue-700">Start your journey</button>
</div>
<div class="bg-slate-100 w-fit m-5 rounded-2xl p-4">
  <div class="rounded-2xl bg-white p-4">
    <div class="flex items-center">
      <span class="relative rounded-xl bg-purple-200 p-4">
        <svg width="40" fill="currentColor" height="40" class="absolute top-1/2 left-1/2 h-4 -translate-x-1/2 -translate-y-1/2 transform text-purple-500" viewBox="0 0 1792 1792" xmlns="http://www.w3.org/2000/svg">
          <path d="M1362 1185q0 153-99.5 263.5t-258.5 136.5v175q0 14-9 23t-23 9h-135q-13 0-22.5-9.5t-9.5-22.5v-175q-66-9-127.5-31t-101.5-44.5-74-48-46.5-37.5-17.5-18q-17-21-2-41l103-135q7-10 23-12 15-2 24 9l2 2q113 99 243 125 37 8 74 8 81 0 142.5-43t61.5-122q0-28-15-53t-33.5-42-58.5-37.5-66-32-80-32.5q-39-16-61.5-25t-61.5-26.5-62.5-31-56.5-35.5-53.5-42.5-43.5-49-35.5-58-21-66.5-8.5-78q0-138 98-242t255-134v-180q0-13 9.5-22.5t22.5-9.5h135q14 0 23 9t9 23v176q57 6 110.5 23t87 33.5 63.5 37.5 39 29 15 14q17 18 5 38l-81 146q-8 15-23 16-14 3-27-7-3-3-14.5-12t-39-26.5-58.5-32-74.5-26-85.5-11.5q-95 0-155 43t-60 111q0 26 8.5 48t29.5 41.5 39.5 33 56 31 60.5 27 70 27.5q53 20 81 31.5t76 35 75.5 42.5 62 50 53 63.5 31.5 76.5 13 94z"></path>
        </svg>
      </span>
      <p class="text-md ml-2 text-black">Finance</p>
    </div>
    <div class="flex flex-col justify-start">
      <p class="my-4 text-left text-4xl font-bold text-gray-700">
        34,500
        <span class="text-sm"> $ </span>
      </p>
      <div class="flex items-center text-sm text-green-500">
        <svg width="20" height="20" fill="currentColor" viewBox="0 0 1792 1792" xmlns="http://www.w3.org/2000/svg">
          <path d="M1408 1216q0 26-19 45t-45 19h-896q-26 0-45-19t-19-45 19-45l448-448q19-19 45-19t45 19l448 448q19 19 19 45z"></path>
        </svg>
        <span> 5.5% </span>
        <span class="ml-2 text-gray-400"> vs last month </span>
      </div>
    </div>
  </div>
</div>
```