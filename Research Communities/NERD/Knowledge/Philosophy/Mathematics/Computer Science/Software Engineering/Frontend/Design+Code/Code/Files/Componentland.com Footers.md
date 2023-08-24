# Componentland.com Footers
## Newsletter Footer
This footer contains links on the left side of the footer and a newsletter field on the right side to subscribe for updates. it also contains an address above the newsletter but this could be changed or removed. This footer is good for a product that may not be released yet.

```html
<footer class="bg-gray-50">
  <div class="mx-auto grid max-w-screen-xl gap-y-8 gap-x-12 px-4 py-10 md:grid-cols-2 xl:grid-cols-4 xl:px-10">
    <div class="max-w-sm">
      <div class="mb-6 flex h-12 items-center space-x-2">
        <span class="text-2xl font-bold">Bel<span class="text-blue-600">Air</span>.</span>
      </div>
      <div class="text-gray-500">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nobis ad a officia ea expedita!</div>
    </div>
    <div class="">
      <div class="mt-4 mb-2 font-medium xl:mb-4">Address</div>
      <div class="text-gray-500">
        35 Remida Heights, <br />
        45 Street, <br />
        South Caroline, US
      </div>
    </div>
    <div class="">
      <div class="mt-4 mb-2 font-medium xl:mb-4">Links</div>
      <nav aria-label="Footer Navigation" class="text-gray-500">
        <ul class="space-y-3">
          <li><a class="hover:text-blue-600 hover:underline" href="#">Pricing</a></li>
          <li><a class="hover:text-blue-600 hover:underline" href="#">Demo</a></li>
          <li><a class="hover:text-blue-600 hover:underline" href="#">Press</a></li>
          <li><a class="hover:text-blue-600 hover:underline" href="#">Support Hub</a></li>
          <li><a class="hover:text-blue-600 hover:underline" href="#">Contact</a></li>
        </ul>
      </nav>
    </div>
    <div class="">
      <div class="mt-4 mb-2 font-medium xl:mb-4">Subscribe to our Newsletter</div>
      <div class="flex flex-col">
        <div class="mb-4">
          <input type="email" class="focus:outline mb-2 block h-14 w-full rounded-xl bg-gray-200 px-4 sm:w-80 focus:outline-none focus:ring-1 focus:ring-blue-600" placeholder="Enter your email" />
          <button class="block rounded-xl bg-blue-600 px-6 py-3 font-medium text-white">Subscribe</button>
        </div>
      </div>
    </div>
  </div>
  <div class="bg-gray-100">
    <div class="mx-auto flex max-w-screen-xl flex-col gap-y-4 px-4 py-3 text-center text-gray-500 sm:flex-row sm:justify-between sm:text-left">
      <div class="">© 2022 BelAir | All Rights Reserved</div>
      <div class="">
        <a class="" href="#">Privacy Policy</a>
        <span>|</span>
        <a class="" href="#">Terms of Service</a>
      </div>
    </div>
  </div>
</footer>
```

## Two Link Columns
This type of footer contains two columns of links. It also contains the logo and some additional info. It's a good choice for enterprise or traditional companies that may have a lot of links. This example also contains cute text at the bottom for "Made with <3 Remotely," this should only be used in certain scenarios.

```html
<footer class="">
  <div class="mx-auto grid max-w-screen-xl gap-y-8 gap-x-12 px-4 py-10 sm:px-20 md:grid-cols-2 xl:grid-cols-4 xl:px-10">
    <div class="max-w-sm">
      <div class="mb-6 flex h-10 items-center space-x-2">
        <img class="h-full object-contain" src="/images/logo-circle.png" alt="" />
        <span class="text-lg font-medium">Boleno</span>
      </div>
      <div class="text-gray-500">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nobis ad a officia ea expedita!</div>
    </div>
    <div class="">
      <div class="mt-4 mb-2 font-medium xl:mb-4">Guides</div>
      <nav aria-label="Guides Navigation" class="text-gray-500">
        <ul class="space-y-3">
          <li><a class="hover:text-blue-600 hover:underline" href="#">How to make a footer</a></li>
          <li><a class="hover:text-blue-600 hover:underline" href="#">Designing your app</a></li>
          <li><a class="hover:text-blue-600 hover:underline" href="#">Getting help from the community</a></li>
          <li><a class="hover:text-blue-600 hover:underline" href="#">Pricing vs Hourly Rate</a></li>
        </ul>
      </nav>
    </div>
    <div class="">
      <div class="mt-4 mb-2 font-medium xl:mb-4">Links</div>
      <nav aria-label="Footer Navigation" class="text-gray-500">
        <ul class="space-y-3">
          <li><a class="hover:text-blue-600 hover:underline" href="#">Pricing</a></li>
          <li><a class="hover:text-blue-600 hover:underline" href="#">Demo</a></li>
          <li><a class="hover:text-blue-600 hover:underline" href="#">Press</a></li>
          <li><a class="hover:text-blue-600 hover:underline" href="#">Support Hub</a></li>
          <li><a class="hover:text-blue-600 hover:underline" href="#">Contact</a></li>
        </ul>
      </nav>
    </div>
    <div class="">
      <div class="mt-4 mb-2 font-medium xl:mb-4">Support Us on Product Hunt</div>
      <div class="flex flex-col">
        <div class="mb-4">
          <a href="https://www.producthunt.com/products/Apple?utm_source=badge-follow&utm_medium=badge&utm_souce=badge-Apple" target="_blank"><img src="https://api.producthunt.com/widgets/embed-image/v1/follow.svg?post_id=100070&theme=light" alt="Apple - Think&#0032;Different | Product Hunt" style="width: 250px; height: 54px;" width="250" height="54" /></a>
        </div>
      </div>
    </div>
  </div>
  <div class="border-t">
    <div class="mx-auto flex max-w-screen-xl flex-col gap-y-4 px-4 py-3 text-center text-gray-500 sm:px-20 lg:flex-row lg:justify-between lg:text-left xl:px-10">
      <p class="">© 2022 Boleno | All Rights Reserved</p>
      <p class="-order-1 sm:order-none">Made with ❤️ Remotely</p>
      <p class="">
        <a class="" href="#">Privacy Policy</a>
        <span>|</span>
        <a class="" href="#">Terms of Service</a>
      </p>
    </div>
  </div>
</footer>
```
## Simple Vertically Aligned
Simple footer that is vertically aligned with the webpage. There is a logo placed slightly above the footer that is also centered. The logo (img) is optional for this type of footer.

```html
<footer class="relative mt-20 bg-gray-900 px-4 pt-20">
  <div class="absolute -top-10 left-1/2 h-16 w-16 -translate-x-1/2 rounded-xl border-4 border-sky-500 bg-white p-2"><img class="h-full object-contain" src="/images/logo-circle.png" alt="" /></div>
  <nav aria-label="Footer Navigation" class="mx-auto mb-10 flex max-w-lg flex-col gap-10 text-center sm:flex-row sm:text-left">
    <a href="#" class="font-medium text-white">Demo</a>
    <a href="#" class="font-medium text-white">Support</a>
    <a href="#" class="font-medium text-white">Privacy Policy</a>
    <a href="#" class="font-medium text-white">Terms & Conditions</a>
  </nav>
  <p class="py-10 text-center text-gray-300">© 2022 Boleno | All Rights Reserved</p>
</footer>
```