# Frontend Webpage Concepts
Building a UI frontend in 2023 requires the perfect mix of tools for your use case. There are so many nowadays that it's easy to get lost if you're on your own. Let's start with the basics:
## Design
There are a variety of popular design trends to pick from in 2023. It's best to stick to one rather than blending them together for visual consistency. The code I generate will always be from one code style and I will not take elements from Neobrutalism and mix it with Glassmorphism for example.
- [[Popular Design Trends]]
### Fonts
The easiest way to get nice fonts onto your webpage is using the available Google Fonts. The code I generate will use Google Fonts exclusively.

## Tailwind
Tailwind is an easy-to-learn library for styling HTML. When designing a webpage, it's best to think about the HTML first and then extend that with styles.

**The code I output will only use Tailwind**. I will avoid generating CSS code when possible, but if unavoidable, I will generate CSS code and specify the file path at the top of the file as a CSS comment.

## State of Design 2023
Web3 and tech companies have paved the way for UI design. Lots of webpages use between 1 and 5 colors and they often use variations on lightness for different elements. Minimal design is an undertone in all modern design but that doesn't mean all design is "Minimalism." What this means in practicality is that designers often opt to elements with intention rather than just because. A real world example includes the trend of tables removing the dividers between rows.

Web3 design trends typically lean towards Neobrutalism and Glassmorphism however there are some truly unique webpages out there that break all of the rules. Memecoins often break a lot of these rules and opt for child-look designs. A cast study referenced in [[Web3]] talks about a memecoin that has elements of Neobrutalism.

## Code Standards
A goal for any webpage to build it so that it's maintainable. This means that in the future, others can build onto it without friction. The code I output will also follow best practices when it comes to code.

A strong recommendation is to install a code formatter and enable "Format on Save" in your favorite editor. This will ensure the code stays formatted in a way that helps you read it. The code I output will always be formatted with 2 spaces for indention.

## Frontend Examples
### Crypto
The following sections explain how to make a crypto one-page website piece-by-piece. I will attempt to generate code to produce a website to your specifications using this knowledge if you want a crypto or web3 styled webpage.

- [[Web3]] - Design case studies

#### Tailwind Component Examples
- [[Navbars]]
- [[Heros]]
- [[Features]]
- [[Testimonials]]
- [[Footer]]

#### Page Layout
Web3/crypto pages are typically laid out in the following order:

- Navbar (sometimes sticky, sometimes with social links)
	- Includes social links, other pages, or section headings linked in the navbar.
- Hero (sometimes with animations or videos or images or social links. Typically has a CTA.)
	- Typically tall and contains key info for the page.
- Feature preview or description
	- Features or further elaboration on the project.
- Main feature #1 (with CTA)
	- The main selling point with a call to action.
- Main feature #2 (optional)
	- Secondary selling point.
- More features (optional)
	- Include remaining features in an easy-to-digest layout. Often this is done in a grid or vertically listed as bullet points / cards.
- Tokenomics
	- Explain tokenomics of the crypto token if the webpage is for a token. I will ask for your tokenomics if I think your project is related to a crypto token for this section.
- Testimonials
	- Contains (often in cards) references to quotes of people appreciating the product.
- Newsletter (optional)
- Footer (social links or contract address typically. Typically includes a copyright notice.)