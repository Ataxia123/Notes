## Unibot.app Telegram Sniper
> The Fastest Telegram Trading Bot. Experience seamless and lightning-fast trading on the go with our free-to-use Telegram bot. Start Trading Explore Features.

Since webpage was built using TailwindCSS. I believe there are some styles that are not from TailwindCSS but are probably custom.

### First Glance
As soon as the page loads, you see there's an animation in the background. It is a loop of lights passing through slits of a grid. It looks very futuristic. You can tell that the brands color is purple as everything at first-glance is either purple or monochromatic.

In the header, on the left, is the logo. It is a unicorn silhouette with "UNIBOT" written next to it. The menu items are aligned to the right and it includes two large buttons on the far right:
- Start trading
- Buy $UNIBOT

Other menu items include:
- Tutorials
- Rewards
- Twitter
- Telegram

#### Navbar Code
```html
<div id="main-navbar" class="sticky flex justify-center w-full top-0 h-[65px] z-50 transparent">
	<div class="flex justify-between items-center w-full max-w-[1400px]">
		<div id="main-navbar-logo" class="max-w-[175px] md:max-w-[200px] p-4"><img src="static/media/logo.png" alt="Unibot Logo"></div>
		<div id="main-navbar-interactions" class="hidden lg:flex justify-center items-center pe-3"><a href="https://www.youtube.com/playlist?list=PLW2nrgz37AeihOPYSDUIFqd4Z6tRvTz74" class="font-bold">Tutorials</a><a href="https://unibot.app/dashboard" target="_blank" rel="noopener noreferrer" class="font-bold">Rewards</a><a href="https://twitter.com/TeamUnibot" class="font-bold">Twitter</a><a href="https://t.me/unibotportal" class="font-bold">Telegram</a><a href="https://t.me/unibotsniper_bot" target="_blank" rel="noopener noreferrer" class="button-anchor font-medium">Start Trading</a><a href="https://app.uniswap.org/#/swap?inputCurrency=ETH&amp;outputCurrency=0xf819d9Cb1c2A819Fd991781A822dE3ca8607c3C9&amp;chain=mainnet" target="_blank" rel="noopener noreferrer" class="button-anchor purple-gradient font-medium">Buy $UNIBOT</a></div><button id="main-navbar-mobile-menu-button" class="lg:hidden w-[40px] h-[40px] me-4">
			<div class="main-navbar-mobile-menu-button-bar bar-1"></div>
			<div class="main-navbar-mobile-menu-button-bar bar-2"></div>
			<div class="main-navbar-mobile-menu-button-bar bar-3"></div>
		</button>
		<div id="main-navbar-mobile-interactions" class="absolute w-full overflow-hidden h-0 inset-0 bg-black mt-[65px] top-0">
			<div class="flex flex-col items-start w-full h-fit p-6"><a href="https://www.youtube.com/playlist?list=PLW2nrgz37AeihOPYSDUIFqd4Z6tRvTz74" class="font-bold text-anchor my-2">Tutorials</a><a href="https://unibot.app/dashboard" target="_blank" rel="noopener noreferrer" class="font-bold text-anchor my-2">Rewards</a><a href="https://twitter.com/TeamUnibot" class="font-bold text-anchor my-2">Twitter</a><a href="https://t.me/unibotportal" class="font-bold text-anchor my-2">Telegram</a><a href="https://t.me/unibotsniper_bot" target="_blank" rel="noopener noreferrer" class="button-anchor font-medium w-full my-2">Start Trading</a><a href="https://app.uniswap.org/#/swap?inputCurrency=ETH&amp;outputCurrency=0xf819d9Cb1c2A819Fd991781A822dE3ca8607c3C9&amp;chain=mainnet" target="_blank" rel="noopener noreferrer" class="button-anchor purple-gradient font-medium w-full my-2">Buy $UNIBOT</a></div>
		</div>
	</div>
</div>
```

The Hero is also visible at first glance. Is is vertically laid out with the typical, Title, Description, Buttons layout. The Title is white and large. The line spacing is appropriate. The description is a subtler color, almost tinted blue and is much smaller than the title. The buttons are below that and there's one for "Start Trading" (second button so far for this) and another for "Explore Features" which simply scrolls you down to the next section of the page.

As you scroll, there's a video that is clearly professionally done. It contains a demonstration of the bot. It has glitching transitions, background music, and all sorts of animations to go along with it. The fact that this video is good, makes it worth adding.

The next section includes some stats wrapped in cards. These cards are horizontally displayed with the center one being the focus. They all contain stats about the product. The code for the cards can be found below:

#### Stats Container
```html
<div id="stats-container" class="flex justify-center items-center w-full mb-24 md:mb-32 md:mt-16 lg:mt-32 rounded-[2.5rem]">
	<div id="stats-container-content" class="flex flex-col lg:flex-row justify-center items-center w-full max-w-[1600px]">
		<div class="stat-box box-1 lg:order-2 flex flex-col justify-center items-center w-full lg:w-1/4 h-fit bg-primary light-border p-5 rounded-3xl mx-3 my-3 py-8" style="translate: none; rotate: none; scale: none; transform: scale(1.2, 1.2); opacity: 1;">
			<h1 class="stat-header text-white">6x Faster</h1>
			<h3 class="stat-description text-slate-300">Than Trading on Uniswap</h3>
		</div>
		<div class="stat-box box-2 lg:order-1 flex flex-col justify-center items-center w-full lg:w-1/3 h-fit bg-primary light-border p-5 rounded-3xl mx-3 my-3 py-8" style="translate: none; rotate: none; scale: none; transform: scale(0.8, 0.8); opacity: 1;">
			<h1 class="stat-header text-white">
				$<span id="statTotalTradingVolume">170,955,643</span>
			</h1>
			<h3 class="stat-description text-slate-300">Total Trading Volume</h3>
		</div>
		<div class="stat-box box-3 lg:order-3 flex flex-col justify-center items-center w-full lg:w-1/3 h-fit bg-primary light-border p-5 rounded-3xl mx-3 my-3 py-8" style="translate: none; rotate: none; scale: none; transform: scale(0.8, 0.8); opacity: 1;">
			<h1 class="stat-header text-white">
				$<span id="statRevShareDistributed">3,229,614</span>
			</h1>
			<h3 class="stat-description text-slate-300">Revenue Share Distributed</h3>
		</div>
	</div>
</div>
```

The next section is important to convey the product offering. It contains the title "Trading Perfected" which lets you know the purpose of the product. It has a description and another button to "Start Trading" (3rd mention,) but after that, it has a section that's divided into 2. On the left side, you can click on an item which will update the animation and the information on the right side. This likely cannot be done with TailwindCSS alone.

The next section is titled "Discover New Tokens" and has a full-width animation of how the alerts look in Telegram. This video is being played in an inline video tag. More info about that can be found on the [[Modern Web Content]] page.

The next section covers other important features of their company. It is vertically laid out and each feature alternates which side it's on. For example, The Revenue Share program is flush with the left, but the Referral Program (next) is pushed to the right. This is likely done with some kind of grid or flex box system. The exact code is pasted below:

#### Two-Part Full Width Section
```html
<div id="rev-share-content" class="flex flex-col lg:flex-row justify-between w-full max-w-[1600px] px-6 md:px-24 xl:px-32">
	<div id="rev-share-content-text" class="flex flex-col order-last lg:order-first items-start w-full lg:w-1/2 lg:my-auto xl:mt-40 lg:pe-12">
		<h1 class="h1 text-grey-gradient mb-2" style="translate: none; rotate: none; scale: none; transform: translate(0px, 0px); opacity: 1;">
			Revenue Share</h1>
		<p class="text-gray-400" style="translate: none; rotate: none; scale: none; transform: translate(0px, 0px); opacity: 1;">
			Rewards are proportional to the amount of tokens held. Holders receive 40% of
			transaction fees and 1% of total $UNIBOT traded volume. Rewards are calculated in
			2-hour intervals and claimable after 24 hours. Transferring more than 200 tokens
			between every 2-hour interval will result in forfeit of your revenue share. Must
			hold 50 $UNIBOT tokens to be eligible.</p><a href="https://unibot.app/dashboard" class="text-anchor mt-4" style="opacity: 1;">Claim Rewards <svg aria-hidden="true" focusable="false" data-prefix="fas" data-icon="arrow-right" role="img" xmlns="http://www.w3.org/2000/svg" width="14px" height="16px" viewBox="0 0 448 512" class="ms-1">
				<path fill="currentColor" d="M438.6 278.6c12.5-12.5 12.5-32.8 0-45.3l-160-160c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3L338.8 224 32 224c-17.7 0-32 14.3-32 32s14.3 32 32 32l306.7 0L233.4 393.4c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0l160-160z">
				</path>
			</svg></a>
	</div>
	<div id="rev-share-content-media" class="relative flex flex-col order-first lg:order-last w-full lg:w-1/2"><video playsinline="" autoplay="" loop="" muted="" class="w-full h-auto object-cover pointer-events-none" style="opacity: 1;">
			<source src="static/media/unibotHomeGrid.webm" type="video/webm">
			<source src="static/media/mobileUnibotEthMorph.mp4" type="video/mp4">
		</video><video playsinline="" autoplay="" loop="" muted="" class="absolute w-3/5 h-auto inset-0 m-auto object-cover pointer-events-none" style="opacity: 1;">
			<source src="static/media/unibotEthMorph.webm" type="video/webm">
		</video></div>
</div>
```

Next is a section of testimonials. It is laid out in a "Masonry" fashion which means there are 2 columns and each testimonials only takes up the space it needs before the one below it. These testimonials are displayed as gray cards with information about tweets that people have posted. Some contain images, all contain the date, likes, and author.

Lastly is the footer, they only include information about their tax rate and their copyright. On the far left of the footer they've included the Unicorn graphic.

## References

1. **[^](#cite_ref-1 "Jump up")** Liu, Xu; Ramirez, Steve; Pang, Petti T.; Puryear, Corey B.; Govindarajan, Arvind; Deisseroth, Karl; Tonegawa, Susumu (22 March 2012). ["Optogenetic stimulation of a hippocampal engram activates fear memory recall"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3331914). _Nature_. **484** (7394): 381–385. [Bibcode](/wiki/Bibcode_(identifier) "Bibcode (identifier)"):[2012Natur.484..381L](https://ui.adsabs.harvard.edu/abs/2012Natur.484..381L). [doi](/wiki/Doi_(identifier) "Doi (identifier)"):[10.1038/nature11028](https://doi.org/10.1038%2Fnature11028). [PMC](/wiki/PMC_(identifier) "PMC (identifier)") [3331914](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3331914). [PMID](/wiki/PMID_(identifier) "PMID (identifier)") [22441246](https://pubmed.ncbi.nlm.nih.gov/22441246).
2. **[^](#cite_ref-2 "Jump up")** Ryan, T. J.; Roy, D. S.; Pignatelli, M.; Arons, A.; Tonegawa, S. (28 May 2015). ["Engram cells retain memory under retrograde amnesia"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5583719). _Science_. **348** (6238): 1007–1013. [Bibcode](/wiki/Bibcode_(identifier) "Bibcode (identifier)"):[2015Sci...348.1007R](https://ui.adsabs.harvard.edu/abs/2015Sci...348.1007R). [doi](/wiki/Doi_(identifier) "Doi (identifier)"):[10.1126/science.aaa5542](https://doi.org/10.1126%2Fscience.aaa5542). [PMC](/wiki/PMC_(identifier) "PMC (identifier)") [5583719](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5583719). [PMID](/wiki/PMID_(identifier) "PMID (identifier)") [26023136](https://pubmed.ncbi.nlm.nih.gov/26023136).
3. **[^](#cite_ref-Levy_3-0 "Jump up")** Levy, Adam (14 January 2021). ["Memory, the mystery"](https://knowablemagazine.org/article/mind/2021/memory-mystery). _Knowable Magazine_. [doi](/wiki/Doi_(identifier) "Doi (identifier)"):[10.1146/knowable-011421-3](https://doi.org/10.1146%2Fknowable-011421-3). Retrieved 25 March 2022.
4. **[^](#cite_ref-4 "Jump up")** Semon, Richard (1921). ["Chapter II. Engraphic Action of Stimuli on the Individual"](https://archive.org/stream/cu31924100387210#page/n31/mode/2up). _The Mneme_. London: George Allen & Unwin. p. 24; trans by Louis Simon.`{{[cite book](/wiki/Template:Cite_book "Template:Cite book")}}`: CS1 maint: postscript ([link](/wiki/Category:CS1_maint:_postscript "Category:CS1 maint: postscript"))
5. ^ [Jump up to: _**a**_](#cite_ref-:0_5-0) [_**b**_](#cite_ref-:0_5-1) Sa, Josselyn; S, Köhler; Pw, Frankland (September 2015). ["Finding the Engram"](https://pubmed.ncbi.nlm.nih.gov/26289572/). _Nature Reviews. Neuroscience_. **16** (9): 521–534. [doi](/wiki/Doi_(identifier) "Doi (identifier)"):[10.1038/nrn4000](https://doi.org/10.1038%2Fnrn4000). [PMID](/wiki/PMID_(identifier) "PMID (identifier)") [26289572](https://pubmed.ncbi.nlm.nih.gov/26289572). [S2CID](/wiki/S2CID_(identifier) "S2CID (identifier)") [205511443](https://api.semanticscholar.org/CorpusID:205511443). Retrieved 2020-06-02.
6. **[^](#cite_ref-bruce_6-0 "Jump up")** Bruce, Darryl (1 December 2001). "Fifty Years Since Lashley's In Search of the Engram: Refutations and Conjectures". _Journal of the History of the Neurosciences_. **10** (3): 308–318. [doi](/wiki/Doi_(identifier) "Doi (identifier)"):[10.1076/jhin.10.3.308.9086](https://doi.org/10.1076%2Fjhin.10.3.308.9086). [PMID](/wiki/PMID_(identifier) "PMID (identifier)") [11770197](https://pubmed.ncbi.nlm.nih.gov/11770197). [S2CID](/wiki/S2CID_(identifier) "S2CID (identifier)") [27180078](https://api.semanticscholar.org/CorpusID:27180078).
7. **[^](#cite_ref-7 "Jump up")** McCormick, David; Thompson, Richard (20 Jan 1984). "Cerebellum: Essential Involvement in the Classically Conditioned Eyelid Response". _Science_. **222**: 296-299. [doi](/wiki/Doi_(identifier) "Doi (identifier)"):[10.1126/science.6701513](https://doi.org/10.1126%2Fscience.6701513).
8. **[^](#cite_ref-8 "Jump up")** James W. Kalat, Biological Psychology p. 392–393
9. **[^](#cite_ref-Gerrig_and_Zimbardo_2005_9-0 "Jump up")** Gerrig and Zimbardo (2005) _Psychology and Life_ (17th edition: International edition)
10. **[^](#cite_ref-10 "Jump up")** Costandi, Mo (6 April 2012). ["Light brings back bad memories"](https://www.theguardian.com/science/neurophilosophy/2012/apr/06/1). _The Guardian_.
11. **[^](#cite_ref-11 "Jump up")** Stefanelli, Thomas; Bertollini, Cristina; Lüscher, Christian; Muller, Dominique; Mendez, Pablo (March 2016). ["Hippocampal Somatostatin Interneurons Control the Size of Neuronal Memory Ensembles"](https://doi.org/10.1016%2Fj.neuron.2016.01.024). _Neuron_. **89** (5): 1074–1085. [doi](/wiki/Doi_(identifier) "Doi (identifier)"):[10.1016/j.neuron.2016.01.024](https://doi.org/10.1016%2Fj.neuron.2016.01.024). [PMID](/wiki/PMID_(identifier) "PMID (identifier)") [26875623](https://pubmed.ncbi.nlm.nih.gov/26875623).
12. **[^](#cite_ref-12 "Jump up")** Roy, Dheeraj S.; Arons, Autumn; Mitchell, Teryn I.; Pignatelli, Michele; Ryan, Tomás J.; Tonegawa, Susumu (March 2016). ["Memory retrieval by activating engram cells in mouse models of early Alzheimer's disease"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4847731). _Nature_. **531** (7595): 508–512. [Bibcode](/wiki/Bibcode_(identifier) "Bibcode (identifier)"):[2016Natur.531..508R](https://ui.adsabs.harvard.edu/abs/2016Natur.531..508R). [doi](/wiki/Doi_(identifier) "Doi (identifier)"):[10.1038/nature17172](https://doi.org/10.1038%2Fnature17172). [PMC](/wiki/PMC_(identifier) "PMC (identifier)") [4847731](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4847731). [PMID](/wiki/PMID_(identifier) "PMID (identifier)") [26982728](https://pubmed.ncbi.nlm.nih.gov/26982728).