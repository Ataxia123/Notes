# Navbar
## Navbar Not Width Constrained(?)
This example includes support for a mobile dropdown menu.
```html
<header class="text-slate-700 container relative mx-auto flex flex-col overflow-hidden px-4 py-4 lg:flex-row lg:items-center">
  <a href="#" class="flex items-center whitespace-nowrap text-2xl font-black">
    <span class="mr-2 w-8">
      <img src="/images/JOJj79gp_Djhwdp_ZOKLL.png" alt="" />
    </span>
    spline
  </a>
  <input type="checkbox" class="peer hidden" id="navbar-open" />
  <label class="absolute top-5 right-5 cursor-pointer lg:hidden" for="navbar-open">
    <svg class="h-7 w-7" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M4 6h16M4 12h16M4 18h16"></path>
    </svg>
  </label>
  <nav aria-label="Header Navigation" class="peer-checked:pt-8 peer-checked:max-h-60 flex max-h-0 w-full flex-col items-center overflow-hidden transition-all lg:ml-24 lg:max-h-full lg:flex-row">
    <ul class="flex w-full flex-col items-center space-y-2 lg:flex-row lg:justify-center lg:space-y-0">
      <li class="lg:mr-12"><a class="rounded text-gray-700 transition focus:outline-none focus:ring-1 focus:ring-blue-700 focus:ring-offset-2" href="#">Components</a></li>
      <li class="lg:mr-12"><a class="rounded text-gray-700 transition focus:outline-none focus:ring-1 focus:ring-blue-700 focus:ring-offset-2" href="#">Pricing</a></li>
      <li class="lg:mr-12"><a class="rounded text-gray-700 transition focus:outline-none focus:ring-1 focus:ring-blue-700 focus:ring-offset-2" href="#">Contact</a></li>
      <li class="lg:mr-12"><a class="rounded text-gray-700 transition focus:outline-none focus:ring-1 focus:ring-blue-700 focus:ring-offset-2" href="#">FAQ</a></li>
    </ul>
    <hr class="mt-4 w-full lg:hidden" />
    <div class="my-4 flex items-center space-x-6 space-y-2 lg:my-0 lg:ml-auto lg:space-x-8 lg:space-y-0">
      <a href="#" title="" class="whitespace-nowrap rounded font-medium transition-all duration-200 focus:outline-none focus:ring-1 focus:ring-blue-700 focus:ring-offset-2 hover:text-opacity-50"> Log in </a>
      <a href="#" title="" class="whitespace-nowrap rounded-xl bg-blue-700 px-5 py-3 font-medium text-white transition-all duration-200 focus:outline-none focus:ring-2 focus:ring-blue-700 focus:ring-offset-2 hover:bg-blue-600">Get free trial</a>
    </div>
  </nav>
</header>
```
## Amazon-Esque Navbar (White)
This example includes support for a mobile dropdown menu.
```html
<link href="https://fonts.googleapis.com/css2?family=Source+Sans+Pro:ital,wght@0,300;0,400;1,600&display=swap" rel="stylesheet" />
<style>
  * {
  font-family: 'Source Sans Pro';
  }
</style>

<header class="mb-2 shadow">
  <div class="relative flex max-w-screen-xl flex-col overflow-hidden px-4 py-4 sm:mx-auto sm:flex-row">
    <img class="h-8 w-8" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAH0AAAB9CAMAAAC4XpwXAAAAnFBMVEX///8AAAD/mQD/lwD/lADHx8f/jwD/kgC0tLTc3Nzg4OC3t7eSkpIdHR0VFRX5+fmbm5vOzs7t7e1tbW3/+fP/iwBzc3OHh4fAwMCrq6ssLCxNTU2kpKRBQUGAgIA5OTkNDQ0kJCT/7+H/p0n/oTtXV1dhYWH/6db/voD/q1T/3sL/wo3/tGv/uXn/2bj/mSL/yJj/0Kj/sF//ni8fK2bFAAAGL0lEQVRoge2a22KiMBCGi4lEUIsgnttaBUUBRfD9320Tz0AGIYTdm/2vWo35yGQymUz4+BCSZXa/JsPFsq8oyud8M+x1pppYT1WldcfzTyWv/uLLNJpF64PFL4d81/eP3hy7uy0g37SZNsPuzN+zmZYN8Nsl2ZfxS7a/MSzPZurKhGsVBn5VTx68W5VN9SML/iUAlzb6gRBcUToy4FNBuKJICL66MFzZ1IYbC3G6UjvsiE76Rcua8Bp2Z2rXo1cMcVmNmxr6cjgzdV03B5uiLbcWfQL1umg/EwkdbFVz0UGdZgKJBtK/asCB+L6ysg0tiF4n2v9we+zn4HT3B+gLcbjR5/Zo8toCOdeveJ7Jtyd/FZnA4MXpHW5/fDe2gPyDM0sl1eN1twIaA3FJPMPjWnMANOZ7KN9JymnAObNAoRvYjupEet2czibb5ar/iKbfUNOZfPpdhm52O4Px4ncI+jDfRetv8eUExMX/9Mb1b+cdSLxl+HyhLK3dmU2A3LcpuqWZXboIVyteGaVBuqW3e9vFsiifa4huaL3hsgy2AXp3XAEsl25WRsujT78F2JLophhbCt0oOC80TtdWwvD69FqH6Lp0catLoHMT279Ff2P239X3z6AzNU0TeMpa9OKCVW/6TNeB7KIOHTybUk3SBwUgu6hDhwtWvewRST4dtPs8f5iTTjegyvSCk9VLpwPHE+Wbd6SQTTeAnYVXu5B/koIKAvx7B9l0IJkAzpFAEV+UbgDpG1AEkxzrIMMDtRCgeiBKh+5DgObAPInSgULMkN/a2MilA6EGuOyxVvzmohdzQHczfmuoVAs0fycLOJ4B3UF5wESMrgPHNIAO7YaC9wOQKfn1Omh5KkuxYiVE5/s8fMgSux8AK/68xgU3KGITD807N9YBi51pLmR6yOd5C77wjhoq7BZrBfT2mcstii/tfoUGD174Z2dSf/NqwFaEDl8Epm+k3p8xRaJtwZ3/61SWOWMKXBGAAYRqPr1OvjUrVbjipqHFgnKbq/rfw/F2XoqtCC16kSIRoM/qti8yfVVVTzKgfF5EAtEeOJ4ISOgyuEpJlE6uBoUIsSJ9tZnXPnTu3vApegkPJOk89RmDN1eC+QVTadvf7uTzV9GbGm87QolyVo+MJxt/BLPKO77U6J8+nUmJBBPqJ/79u5TL11iSyjQkvOj1rl44Sc/s0/P6UsrjWkHapoxzIfxea+rLesFXA5bePFc4Y7qGiaXEV3uN2TgT9ufbHjQ4baH0c++62J4f78JknxyCo79+fOyFfqkHsPT2bDIeDoc/k0HH1IuCiGFlvrX90EWEYESFMSHR3rt9ExI1XOc6kKn1LlIRar0I4ci+fuePWogEDcIPKqZodNWdr94HHKutFiblzC+gs0pUdaRGZ2e/dyKVoDT9Y0foo5GkIfMfdrHv2TdDUw9wLnj8pIWY/Y8Cm/97yYrYPJxfWCFhz0Oi49+gh4y+T31ywSPV8aDfSKYfUh/t1FbDfPseY1xKJxkrn8htKZKkCf46iPDo+iebdzXrYjG+LUaMQtn89SGiK+1K95jhnVwT/xELsNzl54eEjQzvLv8dqZHxifOE0SMUoVEiKfzYMQ2zlyG51w+Y0424azshz1Cs4lP99X/cj24TSpxbbyPad8Jv/Zj8y1aAQ7/GA9jeZbavIuF9W6EDJJBfee5z+GwBuDtP6AEo2iX40ZG6u39xQC0MDJ397EBeN0OEVWdXdQnYcXhWU1Z8eJlNnwgV9edj3HoVoi5wiMsuAvsYuCOS2s5J9MRRjycch39VoKZygasJ1H3sFz/C2o8TkiEz931NHhKE92AHN3n7HP/ihShyD3S/9Nb20xlse+15x1N4jjDGuV9Rz3m1s0dQVMKP4jPO4S+zQLMy2oPr0lyByXHcc8RSNozyz8viZnrZHgguNYV2gLj820OkBDbD2YwxcUr7TzCC+SVUd7+k4yfgwN6gsVp/r7JPDsf/3rMJ2knZp2w/qWgAujacWF6KuI5dzloC0VEgOz3w4mwA45ERGZ1PDWVmx8BR6WGA8wxs1RGV7INmc2Lbiw+Ji+hDsPiC2YGQHlRI5IS7WGwvrP4I6zU9DZ8CplNMj8Ovcfe/yukPrgFu76d1KUsAAAAASUVORK5CYII=" alt="" />
    <input type="checkbox" class="peer hidden" id="navbar-open" />
    <label class="absolute right-4 top-5 cursor-pointer sm:hidden" for="navbar-open">
      <span class="sr-only">Toggle menu</span>
      <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
        <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16" />
      </svg>
    </label>
    <nav aria-labelledby="header-navigation" class="peer-checked:mt-8 peer-checked:max-h-32 flex max-h-0 w-full flex-col items-center justify-between overflow-hidden transition-all sm:ml-24 sm:max-h-full sm:flex-row sm:items-start">
      <h2 class="sr-only" id="header-navigation">Header navigation</h2>
      <ul class="flex flex-col items-center sm:flex-row">
        <li class="font-bold sm:mr-12">Orders</li>
        <li class="text-gray-800 sm:mr-12">Teams</li>
        <li class="text-gray-800 sm:mr-12">Customers</li>
      </ul>
      <ul class="mt-4 flex sm:mt-0">
        <li class="ml-6 flex h-8 w-8 cursor-pointer items-center justify-center rounded-xl border text-gray-600 hover:text-black hover:shadow">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M5.121 17.804A13.937 13.937 0 0112 16c2.5 0 4.847.655 6.879 1.804M15 10a3 3 0 11-6 0 3 3 0 016 0zm6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
          </svg>
        </li>
        <li class="ml-6 flex h-8 w-8 cursor-pointer items-center justify-center rounded-xl border text-gray-600 hover:text-black hover:shadow">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M18.364 5.636l-3.536 3.536m0 5.656l3.536 3.536M9.172 9.172L5.636 5.636m3.536 9.192l-3.536 3.536M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-5 0a4 4 0 11-8 0 4 4 0 018 0z" />
          </svg>
        </li>
        <li class="ml-6 flex h-8 w-8 cursor-pointer items-center justify-center rounded-xl border text-gray-600 hover:text-black hover:shadow">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z" />
            <path stroke-linecap="round" stroke-linejoin="round" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
          </svg>
        </li>
      </ul>
    </nav>
  </div>
</header>
```
## Simple Dark Navbar (Blue accent)
This example does not include support for a mobile dropdown menu.
```html
<div id="navigation" class="mb-40 w-full bg-gray-800">
  <ul id="desktop-nav" class="hidden md:flex">
    <li class="relative">
      <a id="current" href="#" class="block bg-blue-600 px-6 py-4 text-sm font-semibold text-white hover:bg-blue-600 hover:text-white">Home</a>
    </li>

    <li class="relative">
      <a href="#" class="block px-6 py-4 text-sm font-semibold text-white hover:bg-blue-600 hover:text-white">Features</a>
    </li>

    <li class="relative">
      <a href="#" class="block px-6 py-4 text-sm font-semibold text-white hover:bg-blue-600 hover:text-white">Shortcodes</a>
    </li>

    <li class="relative">
      <a href="#" class="block px-6 py-4 text-sm font-semibold text-white hover:bg-blue-600 hover:text-white">Portfolio</a>
      <ul class="absolute left-0 hidden hover:opacity-100">
        <li class="relative">
          <a href="#" class="block w-40 border-gray-800 px-4 py-2 font-sans text-xs text-gray-500 hover:bg-blue-600 hover:text-white">2 Columns</a>
        </li>
        <li class="relative">
          <a href="#" class="block w-40 border-gray-800 px-4 py-2 font-sans text-xs text-gray-500 hover:bg-blue-600 hover:text-white">3 Columns</a>
        </li>
        <li class="relative">
          <a href="#" class="block w-40 border-gray-800 px-4 py-2 font-sans text-xs text-gray-500 hover:bg-blue-600 hover:text-white">4 Columns</a>
        </li>
        <li class="relative">
          <a href="#" class="block w-40 px-4 py-2 font-sans text-xs text-gray-500 hover:bg-blue-600 hover:text-white">Single Project</a>
        </li>
      </ul>
    </li>

    <li class="relative">
      <a href="#" class="block w-40 px-6 py-4 text-sm font-semibold text-white hover:bg-blue-600 hover:text-white">Shop</a>
      <!--
    Dropdown menu, show/hide based on menu state.

    Entering: "transition ease-out duration-100"
      From: "transform opacity-0 scale-95"
      To: "transform opacity-100 scale-100"
    Leaving: "transition ease-in duration-75"
      From: "transform opacity-100 scale-100"
      To: "transform opacity-0 scale-95"
  -->
      <ul class="absolute left-0 w-40 bg-gray-800 hover:opacity-100">
        <li class="relative">
          <a href="#" class="block border-gray-800 px-4 py-2 font-sans text-xs text-gray-500 hover:bg-blue-600 hover:text-white">Shop</a>
        </li>
        <li class="relative">
          <a href="#" class="block px-4 py-2 font-sans text-xs text-gray-500 hover:bg-blue-600 hover:text-white">Product Page</a>
        </li>
      </ul>
    </li>

    <li class="relative">
      <a href="#" class="block px-6 py-4 text-sm font-semibold text-white hover:bg-blue-600 hover:text-white">Blog</a>
    </li>
    <li class="relative">
      <a href="#" class="block px-6 py-4 text-sm font-semibold text-white hover:bg-blue-600 hover:text-white">Contact</a>
    </li>
  </ul>

  <ul id="mobile-nav" class="flex flex-col md:hidden">
    <li class="relative">
      <a id="current" href="#" class="block bg-blue-600 px-6 py-4 text-sm font-semibold text-white hover:bg-blue-600 hover:text-white">Home</a>
    </li>

    <li class="relative">
      <a href="#" class="block px-6 py-4 text-sm font-semibold text-white hover:bg-blue-600 hover:text-white">Features</a>
    </li>

    <li class="relative">
      <a href="#" class="block px-6 py-4 text-sm font-semibold text-white hover:bg-blue-600 hover:text-white">Shortcodes</a>
    </li>

    <li class="relative">
      <a href="#" class="block px-6 py-4 text-sm font-semibold text-white hover:bg-blue-600 hover:text-white">Portfolio</a>
      <ul class="absolute left-0 hidden hover:opacity-100">
        <li class="">
          <a href="#" class="block w-40 border-gray-800 px-4 py-2 font-sans text-xs text-gray-500 hover:bg-blue-600 hover:text-white">2 Columns</a>
        </li>
        <li class="">
          <a href="#" class="block w-40 border-gray-800 px-4 py-2 font-sans text-xs text-gray-500 hover:bg-blue-600 hover:text-white">3 Columns</a>
        </li>
        <li class="">
          <a href="#" class="block w-40 border-gray-800 px-4 py-2 font-sans text-xs text-gray-500 hover:bg-blue-600 hover:text-white">4 Columns</a>
        </li>
        <li class="">
          <a href="#" class="block w-40 px-4 py-2 font-sans text-xs text-gray-500 hover:bg-blue-600 hover:text-white">Single Project</a>
        </li>
      </ul>
    </li>

    <li class="relative">
      <a href="#" class="block px-6 py-4 text-sm font-semibold text-white hover:bg-blue-600 hover:text-white">Shop</a>
      <!--
    Dropdown menu, show/hide based on menu state.

    Entering: "transition ease-out duration-100"
      From: "transform opacity-0 scale-95"
      To: "transform opacity-100 scale-100"
    Leaving: "transition ease-in duration-75"
      From: "transform opacity-100 scale-100"
      To: "transform opacity-0 scale-95"
  -->
      <ul class="ml-5 flex flex-col bg-gray-800 hover:opacity-100">
        <li class="relative">
          <a href="#" class="block w-40 border-gray-800 px-4 py-2 font-sans text-xs text-gray-500 hover:bg-blue-600 hover:text-white">Shop</a>
        </li>
        <li class="relative">
          <a href="#" class="block w-40 px-4 py-2 font-sans text-xs text-gray-500 hover:bg-blue-600 hover:text-white">Product Page</a>
        </li>
      </ul>
    </li>

    <li class="relative">
      <a href="#" class="block px-6 py-4 text-sm font-semibold text-white hover:bg-blue-600 hover:text-white">Blog</a>
    </li>
    <li class="relative">
      <a href="#" class="block px-6 py-4 text-sm font-semibold text-white hover:bg-blue-600 hover:text-white">Contact</a>
    </li>
  </ul>
</div>
```