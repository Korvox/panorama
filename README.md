Project Panorama

An easy to use all in one platform for content distribution and consumption. The means of interaction are derived from
reddit and less from youtube, deviantart, soundcloud, etc - submissions have uniform formatting with embedded content and
diverse means to fund creators. Use vote weighted algorithm to determine popularity rather than views, with a powerful enough
metadata based search indexer and tag system to track other metrics for comprehensive searches.

To avoid the copyright fiascos involving traditional media, and to dodge legal murkiness, the only content allowed in the
tracker must be licensed under a freedom respecting creative commons media license or GPL compliant code license. This means
users can upload others works, but trying to claim others open works as their owns are as much a violation as uploading
nonfree material. The line is distinct - either the work was always free information and is properly atributed, or the uploader
is also the copyright holder and can thus relicense it to site standards. Anything else is rejected. Hopefully we can implement
a user flagging feature that is straightforward. The real problem on this front is DMCA spam - through if this project got
large enough to afford the attention of major trolls that try to abuse taketown notices, we would also have the capability to
migrate the servers and site to a country without a broken legal system.

Code is always open source, of course. There is no real risk of anyone taking the idea if we get big enough to attract
attention and steal our userbase - there is a strong network effect in this type of ecosystem that while you can steal it
with better tech, as long as what we release is AGPL nobody can take what we start and modify it without also releasing their
changes that we can then merge back ourselves. Early bird advantage is the winner here, and openness just guarantees that
nobody can take that throne.

The technical details:

Two servers: bottle based webserver hosting page content, nodejs server hosting webtorrent tracker.
* Potentially third server for user local content hosting. Though using a third party CDN would make more sense.

Design via bootstrap, try to avoid jquery (should not be front end intensive). Whole thing uses webtorrents to
distribute content.
* We need some way to guarantee backlog availability of low seeding material. Preferrably, client side would have an
  option to just enable seeding on dangerously low files. If successful / big enough, we could incentivize it with some 
  small bitcoin payout for bandwidth served, or better yet, let users pay the hosts.

Persona / openid logins, no local user accounts and resultant data stores etc.

Use third party bitcoin clients (coinbase, blockchain.io, bitpay). 
* Potentially use Amazon / Google payments and Paypal at some point if necessary.

* We can use native libraries server side to connect the webtorrent node server to the udp torrent network, if useful.
* A lot of room for expansion, but the base concept works to minimize the overhead site side to a minimum:
  1. The only things we host are a bottle webserver and tracker. We do not keep copies of torrents or don't cache media
     no matter how small.
  2. We avoid interacting with market tyrants like Google and Amazon as long as possible, by using peer to peer and 
     cryptocurrencies to avoid fiat payment schemas until we are at scale enough to afford the opportunity costs.
  3. We can start with a minimal content set - in this case, video, because it is the most ripe for disruption - but I do
     eventually want to move this idea into the realms of written, audio-only, code, and other digital creative passions to
     enable the funding of all kinds of creative works.

So how does the payment system work? The launch model should be bitcoin based - using external wallet services or traceable
blockchain payments from your own local wallets, implement straightforward ways to let users fund creators however they want.
This means:
* Payment options on the users page to subscribe for a monthly amount, pay per released content, and pay in a traditional one
  time way.
* Users have a multitude of ways to award contributors - to start, we can simply enable custom emotes in comments, custom titles,
  early release (in that the pages are not publicly announced - they are still visible, and the content is still open, just
  they can delay general availability so that those who are funding it or just paying attention are rewarded. Add in custom
  tiers the users can make at their whims, and they are set. Long term, cooperation with physical and virtual goods retailers
  and vendors could be very lucrative. Imagine site wide partnerships with paraphernalia vendors and printing companies to 
  provide easy to use brand stores.
* Per video, users can donate once, subscribe to the user, etc. The priority changes since we want to provide great UX - a 
  user viewing content more likely wants to just thank the author for *that* content. Always provide options, though.
* Using cryptocurrencies means there is no lower bound on donation amounts. It also means that if necessary we can inject 
  ourselves in our payment forms as an intermediary if third party payment companies are insufficient to avoid fraud at any
  time. One way to help protect users would be to require that content creators maintain at least 10% of each months earnings
  in an on site escrow - that way if they defraud anyone there is at least some restitution and you can blacklist their account
  and put them in the red the remainder so they cannot ask for funding again until they are well in the green in their local
  wallet again. Though, this *is* only a long term thing - it can scale easily from something as simple as third party payments
  between account associated addresses to local wallets and escrow as need be.
* Funding comes from whatever portion of transactions we need to shave off the top. We can also of course seek funding through our
  own platform - to start, we won't be in the payments themselves anyway so long as its a proof of implementation and payments
  would always be through their respective platforms. If we deem it necessary to soak up some of the revenue moving through the
  system to continue growing / funding, then we would be at the point where taking a percentage would be enough to run a legitimate
  business anyway. This is all about convenience, after all - users could share their addresses and dodge us entirely if they want,
  but using our tools should be enough of a value gain they appreciate them and do not mind whatever cut we take.

So that is user payments, I want to just postulate on all the ways this idea makes money in a traditional business sense - since
nobody really pays attention to this anymore in San Fran Wonderland.

1. Funding through our own platform. This is dogfooding - if this idea is good enough to be worth it, the long run we should be 
   able to get the vast majority of our revenues through user contributions (especially for things they want in the service) with 
   all other revenue sources as temporary or transitive means to keep things afloat until scale. But this is day one revenue assuming 
   we have a day one customer interested in seeing us succeed. Call this our own localized patreon for the project from launch day.
2. Percentage of transactions. In the same way a lot of modern crowdfunding services work, a la Twitch, Kickstarter, Patreon, 
   etc. We just route transactions through our own accounts as escrow, and take a percentage of sales and act as a payment processor. 
   There is a lot of overhead to implement this, so of course to do so we would need enough revenue in our funding model to 
   justify it. I easily imagine this becoming mandatory at scale if we attract a consumer audience, because they would be much less 
   likely to directly contribute to us, just due to general ignorance on how the tech works.
3. Paid promotions. Users can pay for ranking in the either "ad" spots, or just on the userless login page. Or they could buy 
   spots on some service approved channel a la how Twitch has its own Twitch channel they show promotional deals on. This is 
   between users and us, so it avoids some of the nasty problems with more traditional advertising models. We could also have 
   one on one deals with other companies interested in doing this, though.
4. Classic ads. This is a weapon of last resort, but I imagine some users might want this as a feature. There are two classes 
   of third party ads as they would relate to this project - static ad and video ads. The first is just stick images in pages 
   like most of the Internet does to pay the server bills. Boring, old, and very inefficient revenue. Especially on a content 
   site, where our primary revenue is people using *our* platform, the only real ad deals we could get without promoting competition 
   would be physical goods vendors. Promoting any proprietary information this way only detracts from our goals, though like I said, 
   users could use this as a revenue source without any broader consequence on the entire site. Since we are the tracker and arbiter 
   of content, we could let users embed video ads at seed time or let third party advertisers preroll in the html, but really that 
   just sounds disgusting for a platform meant to enable content creation and dissemination. But hey, it is an option, gotta keep all 
   your cards at hand.
   
Concerns:
* The whole webtorrents platform is based on a hack. That Chrome and Firefox do not respect subdomain restrictions on data allotments
  (at this point, probably intentionally) enabling sites to manage any amount of data in localstorage. I cannot imagine them fixing 
  this -enough services are now dependent on this functionality and there is a real need for persistent unlimited client side storage 
  that is not space restricted like that. Regardless, our site would be a massive hack of subdomain allocators for torrent blocks.
* Content. For this to succeed you cannot just build it and let "them" come - the value add requires there be both content for users
  to consumer and users for creators to get paid by. And this is the difference between the pet project and the business venture - to
  move to the latter, we would need to both get some original content made, attract amateur creators to give us a chance, and get users
  visiting us to get the ball rolling, all at once. It is not a "only one chance" kind of deal, but any day it is not growing with a
  strong userbase and creative base then we are gaining no ground. The biggest benefit is that it would be easy for content creators to
  just import their works elsewhere to us - it would be in our interests to make tools that enable them to do that automatically. Then
  they could point their own fans to us to fund them, and over time by using us as a payment service the creators could end up just
  using us exclusively and keeping their users here as content consumers. This is the entire gamble, however.
  
TODO: Start this shit. Gotta get a few days of no-work to just crank out a skeleton of the whole ordeal.
