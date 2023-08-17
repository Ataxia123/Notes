Nov 16, 2020

Tailwind ·14 min read

![17 Tailwind CSS Card Examples](https://ordinarycoders.com/_next/image?url=https%3A%2F%2Fd2gdtie5ivbdow.cloudfront.net%2Fmedia%2Fimages%2Ftailwindcss_card_cover_image.png&w=3840&q=75)

**What is Tailwind CSS?**

Tailwind CSS is the utility-first CSS framework for those looking to rapidly build custom designs. 

Rather than predesigned components, Tailwind CSS comes with basic utility classes meant for customization. 

**Tailwind Installation**

The documentation highly recommends downloading the framework via npm or yarn to gain full access to component customization.

If you are using Django, follow the [Django +Tailwind Integration guide](https://ordinarycoders.com/blog/article/django-tailwind). If you are using React, follow the [React + Tailwind guide](https://ordinarycoders.com/blog/article/reactjs-tailwindcss). 

Otherwise, visit the [documentation](https://tailwindcss.com/docs/installation#install-tailwind-via-npm) for more integration guides. 

If you prefer using a CDN:

_How to use Tailwind CDN_

```
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <!-- Tailwind CSS -->
    <link href="https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" rel="stylesheet">


    <title>Tailwind CSS CDN</title>
  </head>
  <body>

    <h1>Tailwind CSS Framework</h1>


  </body>
</html>
```

There is only one CDN for Tailwind -- a minified stylesheet added to the `<head>` element. 

**More on TailwindCSS**

![Tailwind Documentation](https://ordinarycoders.com/_next/image?url=https%3A%2F%2Fd2gdtie5ivbdow.cloudfront.net%2Fmedia%2Fuser%2Fimages%2Ftailwind.png&w=3840&q=75)

This article only covers Tailwind card examples.

If you are interested in learning more about the utility classes and making your own components, visit [Top 3 CSS Frameworks for Front-End Development](https://ordinarycoders.com/blog/article/top-3-css-frameworks). 

___

**Tailwind Card Examples from the Documentation**

Now on to Tailwind CSS Cards.

Technically speaking, there are no pre-designed Tailwind card components but the documentation has two card examples.

**Tailwind CSS Card Example #1**

_Tailwind CSS Card  #1 HTML template_

```
<!doctype html>
<html lang="en">
<head>
  <!-- Required meta tags -->
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <!-- Tailwind CSS -->
  <link href="https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" rel="stylesheet">


  <title>Tailwind CSS CDN</title>
</head>
<body>

  <div class="p-10">  
    <!--Card 1-->
    <div class="max-w-sm rounded overflow-hidden shadow-lg">
      <img class="w-full" src="/mountain.jpg" alt="Mountain">
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2">Mountain</div>
        <p class="text-gray-700 text-base">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, Nonea! Maiores et perferendis eaque, exercitationem praesentium nihil.
        </p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#photography</span>
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#travel</span>
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#winter</span>
      </div>
    </div>
  </div>

</body>
</html>
```

The first card is a vertically stacked card with an image placed at the top. 

![Tailwind CSS vertically stacked card example](https://ordinarycoders.com/_next/image?url=https%3A%2F%2Fd2gdtie5ivbdow.cloudfront.net%2Fmedia%2Fuser%2Fimages%2Ftailwind_card_example_1.png&w=1080&q=75)

**Tailwind CSS Card Example #1 in a Row**

_Tailwind CSS Card Row #1 HTML template_

```
<!doctype html>
<html lang="en">
<head>
  <!-- Required meta tags -->
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <!-- Tailwind CSS -->
  <link href="https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" rel="stylesheet">


  <title>Tailwind CSS CDN</title>
</head>
<body>


  <div class="p-10 grid grid-cols-1 sm:grid-cols-1 md:grid-cols-3 lg:grid-cols-3 xl:grid-cols-3 gap-5">
    <!--Card 1-->
    <div class="rounded overflow-hidden shadow-lg">
      <img class="w-full" src="/mountain.jpg" alt="Mountain">
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2">Mountain</div>
        <p class="text-gray-700 text-base">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, Nonea! Maiores et perferendis eaque, exercitationem praesentium nihil.
        </p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#photography</span>
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#travel</span>
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#winter</span>
      </div>
    </div>
    <!--Card 2-->
    <div class="rounded overflow-hidden shadow-lg">
      <img class="w-full" src="/river.jpg" alt="River">
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2">River</div>
        <p class="text-gray-700 text-base">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, Nonea! Maiores et perferendis eaque, exercitationem praesentium nihil.
        </p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#photography</span>
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#travel</span>
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#summer</span>
      </div>
    </div>

    <!--Card 3-->
    <div class="rounded overflow-hidden shadow-lg">
      <img class="w-full" src="/forest.jpg" alt="Forest">
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2">Forest</div>
        <p class="text-gray-700 text-base">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, Nonea! Maiores et perferendis eaque, exercitationem praesentium nihil.
        </p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#photography</span>
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#travel</span>
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#fall</span>
      </div>
    </div>
  </div>
</div>

</body>
</html>
```

To create a card row, nest all cards within a grid that specifies the number of columns in each viewpoint.

![TailwindCSS stacked cards in a row](https://ordinarycoders.com/_next/image?url=https%3A%2F%2Fd2gdtie5ivbdow.cloudfront.net%2Fmedia%2Fuser%2Fimages%2Ftailwind_card_example_row_1.png&w=3840&q=75)

**Tailwind CSS Card Example #2**

_Tailwind CSS Card  #2 HTML template_

```
<!doctype html>
<html lang="en">
<head>
  <!-- Required meta tags -->
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <!-- Tailwind CSS -->
  <link href="https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" rel="stylesheet">


  <title>Tailwind CSS CDN</title>
</head>
<body>


  <div class="p-10">
    <!--Card 1-->
    <div class=" w-full lg:max-w-full lg:flex">
      <div class="h-48 lg:h-auto lg:w-48 flex-none bg-cover rounded-t lg:rounded-t-none lg:rounded-l text-center overflow-hidden" style="background-image: url('/mountain.jpg')" title="Mountain">
      </div>
      <div class="border-r border-b border-l border-gray-400 lg:border-l-0 lg:border-t lg:border-gray-400 bg-white rounded-b lg:rounded-b-none lg:rounded-r p-4 flex flex-col justify-between leading-normal">
        <div class="mb-8">
          <p class="text-sm text-gray-600 flex items-center">
            <svg class="fill-current text-gray-500 w-3 h-3 mr-2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
              <path d="M4 8V6a6 6 0 1 1 12 0v2h1a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2v-8c0-1.1.9-2 2-2h1zm5 6.73V17h2v-2.27a2 2 0 1 0-2 0zM7 6v2h6V6a3 3 0 0 0-6 0z" />
            </svg>
            Members only
          </p>
          <div class="text-gray-900 font-bold text-xl mb-2">Best Mountain Trails 2020</div>
          <p class="text-gray-700 text-base">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, Nonea! Maiores et perferendis eaque, exercitationem praesentium nihil.</p>
        </div>
        <div class="flex items-center">
          <img class="w-10 h-10 rounded-full mr-4" src="/ben.png" alt="Avatar of Writer">
          <div class="text-sm">
            <p class="text-gray-900 leading-none">John Smith</p>
            <p class="text-gray-600">Aug 18</p>
          </div>
        </div>
      </div>
    </div>
  </div>

</body>
</html>
```

The second card example is a horizontal card with the image placed on the left. In smaller viewpoints, the card becomes vertically stacked. 

![TailwindCSS horizontal card example](https://ordinarycoders.com/_next/image?url=https%3A%2F%2Fd2gdtie5ivbdow.cloudfront.net%2Fmedia%2Fuser%2Fimages%2Ftailwind_card_example_2.png&w=2048&q=75)

**Tailwind CSS Card Example #2 in a Row**

_Tailwind CSS Card  Row #2 HTML template_

```
<!doctype html>
<html lang="en">
<head>
  <!-- Required meta tags -->
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <!-- Tailwind CSS -->
  <link href="https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" rel="stylesheet">


  <title>Tailwind CSS CDN</title>
</head>
<body>


  <div class="p-10 grid grid-cols-1 sm:grid-cols-1 md:grid-cols-1 lg:grid-cols-1 xl:grid-cols-3 gap-5">
    <!--Card 1-->
    <div class=" w-full lg:max-w-full lg:flex">
      <div class="h-48 lg:h-auto lg:w-48 flex-none bg-cover rounded-t lg:rounded-t-none lg:rounded-l text-center overflow-hidden" style="background-image: url('/mountain.jpg')" title="Mountain">
      </div>
      <div class="border-r border-b border-l border-gray-400 lg:border-l-0 lg:border-t lg:border-gray-400 bg-white rounded-b lg:rounded-b-none lg:rounded-r p-4 flex flex-col justify-between leading-normal">
        <div class="mb-8">
          <p class="text-sm text-gray-600 flex items-center">
            <svg class="fill-current text-gray-500 w-3 h-3 mr-2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
              <path d="M4 8V6a6 6 0 1 1 12 0v2h1a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2v-8c0-1.1.9-2 2-2h1zm5 6.73V17h2v-2.27a2 2 0 1 0-2 0zM7 6v2h6V6a3 3 0 0 0-6 0z" />
            </svg>
            Members only
          </p>
          <div class="text-gray-900 font-bold text-xl mb-2">Best Mountain Trails 2020</div>
          <p class="text-gray-700 text-base">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, Nonea! Maiores et perferendis eaque, exercitationem praesentium nihil.</p>
        </div>
        <div class="flex items-center">
          <img class="w-10 h-10 rounded-full mr-4" src="/ben.png" alt="Avatar of Writer">
          <div class="text-sm">
            <p class="text-gray-900 leading-none">John Smith</p>
            <p class="text-gray-600">Aug 18</p>
          </div>
        </div>
      </div>
    </div>
    <!--Card 2-->
    <div class="w-full lg:max-w-full lg:flex">
      <div class="h-48 lg:h-auto lg:w-48 flex-none bg-cover rounded-t lg:rounded-t-none lg:rounded-l text-center overflow-hidden" style="background-image: url('/river.jpg')" title="River">
      </div>
      <div class="border-r border-b border-l border-gray-400 lg:border-l-0 lg:border-t lg:border-gray-400 bg-white rounded-b lg:rounded-b-none lg:rounded-r p-4 flex flex-col justify-between leading-normal">
        <div class="mb-8">
         
          <div class="text-gray-900 font-bold text-xl mb-2">15 Rivers In Norway</div>
          <p class="text-gray-700 text-base">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, Nonea! Maiores et perferendis eaque, exercitationem praesentium nihil.</p>
        </div>
        <div class="flex items-center">
          <img class="w-10 h-10 rounded-full mr-4" src="/karen.png" alt="Avatar of Writer">
          <div class="text-sm">
            <p class="text-gray-900 leading-none">Karen Johnson</p>
            <p class="text-gray-600">Aug 10</p>
          </div>
        </div>
      </div>
    </div>
    <!--Card 3-->
    <div class="w-full lg:max-w-full lg:flex">
      <div class="h-48 lg:h-auto lg:w-48 flex-none bg-cover rounded-t lg:rounded-t-none lg:rounded-l text-center overflow-hidden" style="background-image: url('/forest.jpg')" title="Forest">
      </div>
      <div class="border-r border-b border-l border-gray-400 lg:border-l-0 lg:border-t lg:border-gray-400 bg-white rounded-b lg:rounded-b-none lg:rounded-r p-4 flex flex-col justify-between leading-normal">
        <div class="mb-8">
          <p class="text-sm text-gray-600 flex items-center">
            <svg class="fill-current text-gray-500 w-3 h-3 mr-2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
              <path d="M4 8V6a6 6 0 1 1 12 0v2h1a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2v-8c0-1.1.9-2 2-2h1zm5 6.73V17h2v-2.27a2 2 0 1 0-2 0zM7 6v2h6V6a3 3 0 0 0-6 0z" />
            </svg>
            Members only
          </p>
          <div class="text-gray-900 font-bold text-xl mb-2">5 National Forests across the U.S.</div>
          <p class="text-gray-700 text-base">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, Nonea! Maiores et perferendis eaque, exercitationem praesentium nihil.</p>
        </div>
        <div class="flex items-center">
          <img class="w-10 h-10 rounded-full mr-4" src="/rafael.png" alt="Avatar of Writer">
          <div class="text-sm">
            <p class="text-gray-900 leading-none">Rafael Martin</p>
            <p class="text-gray-600">Aug 9</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

</body>
</html>
```

To create a card row, nest all cards within a grid that specifies the number of columns in each viewpoint.

![Tailwind CSS horizontal cards in a row](https://ordinarycoders.com/_next/image?url=https%3A%2F%2Fd2gdtie5ivbdow.cloudfront.net%2Fmedia%2Fuser%2Fimages%2Ftailwind_card_example_row_2.png&w=3840&q=75)

___

**15 Tailwind Card Examples**

With the two documentation card examples out of the way, let's go over some CodePen TailwindCSS card examples for inspiration. 

The links are provided below to each pen.

**Tailwind - Cards**

_By [Andi Grether](https://codepen.io/handplant)_

Cards are used to display vacation rental prices in this example.

Description, price, distance, contact, and reviews are displayed in this stacked Tailwind CSS card template. 

Upon card hover, the image scales up by 1.05, and a slightly darker shadow displays around the card. Rounded corners and responsive flex wrapping are already added to each card. 

![Tailwind card template](https://ordinarycoders.com/_next/image?url=https%3A%2F%2Fd2gdtie5ivbdow.cloudfront.net%2Fmedia%2Fuser%2Fimages%2Fandi_tailwind_cards.png&w=3840&q=75)

**Calcite Tailwind Cards**

_By [Erich Rainville](https://codepen.io/TheBlueDog)_

The next pen is one Tailwind CSS card that is stacked with an image on top and description text below. 

Circular badges are added to the bottom and a large shadow is placed around the corners of the card. 

![Tailwind Card Example](https://ordinarycoders.com/_next/image?url=https%3A%2F%2Fd2gdtie5ivbdow.cloudfront.net%2Fmedia%2Fuser%2Fimages%2Ferich_tailwind_cards.png&w=1200&q=75)

**Tailwind Cards - Left-Right**

_By [leolo](https://codepen.io/diomed)_

Horizontal cards can display the image on the left or right side of the card. This pen demonstrates how to use both when linking to articles. 

In smaller viewpoints, the cards are stacked in one column, while in larger viewpoints it maintains two columns. Add an `<a>` element around each card or to "Read more" to link to blog articles or pages. 

![Tailwind CSS card example](https://ordinarycoders.com/_next/image?url=https%3A%2F%2Fd2gdtie5ivbdow.cloudfront.net%2Fmedia%2Fuser%2Fimages%2Fleolo_tailwind_cards.png&w=2048&q=75)

**Tailwind (Cards)**

_By [Jesse Schneider](https://codepen.io/mechawrench)_

This CodePen user demonstrates how to create a Tailwind card without an image along with a stacked and a horizontal card with images. 

Each is responsive and uses Tailwind's default colors. There is no custom CSS and all of the images are from Unsplash.

![Tailwind CSS card examples](https://ordinarycoders.com/_next/image?url=https%3A%2F%2Fd2gdtie5ivbdow.cloudfront.net%2Fmedia%2Fuser%2Fimages%2Fjesse_tailwind_cards.png&w=3840&q=75)

**Tailwind (Cards)**

_By [Artexxx](https://codepen.io/artexxx)_

Tailwind horizontal cards work well for blogs, as they can act as links to articles. This CodePen user displays horizontal cards in one column as "Recent Articles".

The title, description, author, and publication date are all displayed on the right side of the card while the image remains on the left. 

However, in smaller viewpoints, the cards collapse into stacked cards. 

![Tailwind Horizontal cards](https://ordinarycoders.com/_next/image?url=https%3A%2F%2Fd2gdtie5ivbdow.cloudfront.net%2Fmedia%2Fuser%2Fimages%2Fart_tailwind_cards.png&w=3840&q=75)

**Tailwind Cards**

_By [User123](https://codepen.io/user_123)_

This TailwindCSS card template displays three stacked cards in a row. Each card has a title, description, and a download button at the bottom of the card. 

These cards are not mobile compatible as they do not collapse into one column in smaller viewpoints.

Refer to the documentation examples above to make them responsive. 

![Tailwind CSS cards template example](https://ordinarycoders.com/_next/image?url=https%3A%2F%2Fd2gdtie5ivbdow.cloudfront.net%2Fmedia%2Fuser%2Fimages%2Fuser_tailwind_cards.png&w=3840&q=75)

**Tailwind Cards**

_By [Jay Newey](https://codepen.io/jaynewey)_

This Tailwind CSS card template example comes with a navbar and a card cloning JS function. 

On hover, the card raises along the Y-axis and the card border is replaced with a shadow. It is a clean, simple CSS card hover effect that makes a nice visual impact. 

![Tailwind CSS card hover template](https://ordinarycoders.com/_next/image?url=https%3A%2F%2Fd2gdtie5ivbdow.cloudfront.net%2Fmedia%2Fuser%2Fimages%2Fjay_tailwind_cards.png&w=3840&q=75)

**TailwindCSS Cards**

_By [Sanjay Sanjel](https://codepen.io/sanjaysanjel)_

The pen is one Tailwind card centered on the page. Although stacked, this card has the description overlapping the card image using a negative margin. 

The template is based on a vacation rental card that includes the number of rooms, bathrooms, weekly price, and rating. 

Shadows are placed on both the image and the description card to provide a contrast between the two. 

![Tailwind CSS card template](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

**Tailwind card**

_By [Djordje](https://codepen.io/dzoni404)_

Similar to the previous Tailwind card template, this card has a description text overlapping the image.

Both the image and the text are within the same horizontal card, however, the text box has a white background overlayed on the bottom of the image. 

This effect is done purely through TailwindCSS utility classes, with the card stacked in smaller viewpoints. 

![Tailwind CSS card template](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

**Tailwind Card Design**

_By [matt-tonks](https://codepen.io/matt-tonks)_

Designed as a hotel booking, this Tailwind CSS template displays a horizontal card with hotel name, location, and cost all presented to the user. 

A "Book Now" link anchors the bottom of the card while the price is the main focal point. 

![Tailwind CSS card template](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

**Tailwind Card**

_By [Nirajan Basnet](https://codepen.io/nirazanbasnet)_

This Tailwind card is horizontal with a plus sign button located in the upper right-hand corner of the card. An e-commerce site or social media platform would be a good place to implement this card design.

The card is currently not mobile compatible, but easily can be with the addition of some height utility cases to the image.

See the horizontal card example at the top of the page for the code. 

![Tailwind CSS card](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

**Tailwind-card**

_By [Tommy Pratama](https://codepen.io/tommypratama)_

Designed for an educational site, this card displays a course completion progress bar, the current course lesson, and a button linked to the current lesson page. 

It is a basic card but does a good job of displaying relevant information to the user and can easily be adapted to display products or links to services. 

![Tailwind CSS card template](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

**Tailwind Card**

_By [Tony Nguyen](https://codepen.io/tnguyen201)_

The last Tailwind card example provided is for what seems to be a commenting or support interface. It may also be an employee review card.

Status, name of instructor, date, and comment are all presented in a Tailwind card with no image. 

The card is responsive but the padding may need adjustment. 

![Tailwind CSS card](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)