---
weight: 20
title: "Some Musings on Production"
description: "Make economics make cents!"
date: "2024-11-26T20:47:36Z"
lastmod: "2025-04-03T20:47:36Z"
draft: false
toc: true
author: "Nedea"
---

There has been some talk about stats again. You can never really get away from it can you? I have been dwelling on this subject for a minute now and I think I have a fairly solid idea for how to handle production, income, trade, and all the bells and whistles that comes with. Firstly, I want to cover Production Classes.

Also, I AM trying to make a map here guys, I know the stat stuff is interesting, but map comes first! All of this is on the Wish List after all.

---

## Production Classes

Each industry has three classes of goods it produces, Bulk, Consumer, & Luxury. Each class automatically occupies a certain % of that specific industries productive power (I'll get  around to codifying terms and definitions at a later date). To begin, when a nation registers with the Economic System, all their stats will be crunched and they will get an overview of how productive each class is in each industry. These classes are just defaults and represent the totality of products within that industry. 

* Bulk goods require 30% of Production
* Consumer goods require 60% of Production
* Luxury goods require 10% of Production.

Athretvari made a good point earlier about a desire to commit certain %'s to custom products that can flow through the system. Initially, I thought this would require insane overhead on my part. But after a serious brain blast, I realized I can just 'tag' these custom products with a Production Class. What does this look like? Well firstly, let's define all the possible tags...

### Arms Manufacturing
ARMABUL
ARMACON
ARMALUX

### Automobile Manufacturing
AUTOMABUL
AUTOMACON
AUTOMALUX

### Basket Weaving
BASWEBUL
BASWECON
BASWELUX

### Beverage Sales
BEVESABUL
BEVESACON
BEVESALUX

### Book Publishing
BOOPUBUL
BOOPUCON
BOOPULUX

### Cheese Exports
CHEEXPBUL
CHEEXPCON
CHEEXLUX

### Furniture Restoration
FURRESBUL
FURRECON
FURRELUX

### Gambling
GAMBUL
GAMCON
GAMLUX

### Information Technology
INFOTBUL
INFOTCON
INFOTLUX

### Insurance
INSUBUL
INSUCON
INSULUX

### Mining
MINBUL
MINCON
MINLUX

### Pizza Delivery
PIZZBUL
PIZZCON
PIZZLUX

### Retail
RETAILBUL
RETAILCON
RETAILLUX

### Timber Wood Chipping
TIMBERBUL
TIMBERCON
TIMBERLUX

### Trout Fishing
TROFIBUL
TROFICON
TROFILUX

Not so bad right? That's only 75 distinct tags. At the beginning, that's all your nation will produce, a certain amount of those products. Let's use Trout Fishing as an example. At this time, we will also introduce our test nation, Drekar.

Drekar has a TROFI (Trout Fishing Industry) of ⍋1,000. Using our predefined %'s, this would mean Drekar produces ⍋300 of TROFIBUL, ⍋600 of TROFICON, and ⍋100 of TROFILUX. These default products will enter the system, be consumed, exported, or stockpiled (Thanks Athretvari)

Now, Drekar is a special guy, and he wants to add abit more color to his production. He decides he wants to register a specific product into the system. Let's go with High Viscosity Whale Oil. He first determines what class this product is. Let's go with Bulk. He then assigns a % of his Bulk Production to HVWO. He chooses 50%. He then let's me know these details and I make the necessary adjustments to his Production Rules (I'll touch on these a little later).

His TROFI now looks like:

⍋150 HVWO
⍋150 TROFIBUL
⍋600 TROFICON
⍋100 TROFILUX

HVWO is still considered a bulk product from the point of view in the system and confers no further benefit other than flavor. It will be measured and consumed the same way as any other product by industry/consumers/exports/etc that requires TROFIBUL. On your Balance Sheet, they will however, show as a seperate entry. Now, when he makes his trades, he can advertise that he has High Viscosity Whale Oil up for sale and he can make his own export agreements with that.

It should also be noted that when registering a product, you will have the option to make it Proprietary or Global. Proprietary Products are specific to your nation and cannot be registered by any other, and I'll try to keep an eye out for copy cats. Global Products can be registered by any other nation if they wish. This helps us build a roster of available products that can be traded around without a bunch of similar products being registered, ie, Self-Sealing Stembolts VS Auto-Combining Stembolts. 

Now, before it is even asked, at this time I would prefer to not adjust your default %'s for your three classes. 30, 60, 10 seems like a good spread and I don't see any reason to adjust this. Maybe if I find an NS stat or two that could feasibly affect these numbers, we can explore that. But in the meantime, let's just stick to this ratio.

---

## The Production Chain

Now that we understand just what our industries are producing, let's take a peek at how they are consumed and moved around.

Your nation has 6 possible Demand Centers, each with different priorities. They are:

1. Industry | Priority 1
    * Hey, your industries gotta eat too! Expect a lot of pressure on Primary Indsutries; Mining, Trout Fishing, Insurance. 
    * Your Indsutry has no account balance, and receives all good for free*.
2. Government | Priority 1
    * For some of you, this might be one of your biggest Demand Centers. Depending on your government expendeture, your government will buy all sorts of different products from your Industry.
    * Your national budget will be used to pay for these goods.
3. Consumers | Priority 1
    * Depending on various stats, your Consumers will apply different Demand Pressures on different products. 
    * Using various demographic information, income stats, etc, we will pay your industries with your disposable income.
    * For those of you who tax every last penny from your citizens, that will be covered in a seperate changeblog.
4. Business Subsidization | Priority 1
    * This is the 'Industry' part of your pie chart. Using that money, your government will purchase additional goods from your Industry and add it to the National Stockpile.
5. Stockpiling | Priority 2
    * If for whatever reason you want to stockpile additional goods, that is chosen here. All P1 Demand Centers cannot be manually adjusted. You adjust those with the issues you answer. 
    * You will have more granular control over Stockpiling. Either by selecting a % of the surplus, or a raw ⍋ amount.
6. Exports | Priority 3
    * Finally, if there is anything left over, this surplus will exported to the world at large. 
    * The system will first check if you have a trade agreement for any specific class of product, or custom product, and sell it to your counter party.
    * Any remaining goods will be sold to the Commodities Broker at a price below cost.

### But what about deficits?

Deficits can happen in two areas. You may encounter either monetary deficits or industrial deficits. 

#### Industrial Deficits

Industrial Deficits happen when your local industry is unable to fulfill all P1 Demand Centers. When this occurs, you will be forced to import the shortfall from the global economy. The system will first check for any trade agreements you have for the product in question and if so, you will buy the goods from your counter party. Any goods that do not have a trade agreement in place will be purchased from the Commodities Broker at a price above cost. You may also allow your deficits to draw from any stockpiled goods you have before buying the goods abroad.

#### Monetary Deficits

Monetary Deficits happen when your government cannot afford to pay for any of its obligations or imports. When this happens, you will still receive the goods and ultimately fund your government, but you will be in the hole. If this goes on, it will have compounding effects on your economy. We cover the effects and solutions of to this later on.

---

## Accounting 

Accounting is near and dear to my heart. It's like witchcraft with numbers. We invented it to make our lives easier. Did it actually though? Well, that's not what we are exploring here.

Anyway...

As a nation, you will have two accounts. Your Sovereign Account, and your Trade Account. After some amount of numerical sorcery, you will receive deposits into your Sovereign account. This money is yours to do with however you see fit. Lend it, spend it, save it. You will receive money into this account no matter how poorly your nation is running.

Your Trade Account is a little different. When the dust settles after your trades are calculated, and net income will be deposited and net expenses will be withdrawn. If there is a positive balance remaining, you may tax it at whatever % rate you prefer. These taxes will be deposited into your Sovereign Account.

### But I still have questions about deficits!

Okay okay! Fine, lets cover that. Let's first cover solutions to deficits before we go over all the bad things that can happen. Note, bad things happen based on your choices (Safe, Risky, Dangerous). :P

If you run a deficit in your Government Expenses, you can:
* Use money from your Sovereign Account to cover. Safe
* Take a loan from a friend. Safe - Dangerous
* Take a loan from the Commodities Broker. Risky - Dangerous
* Mint new currency. Safe - Dangerous
* Default. Dangerous

#### Use the Sovereign Account

Maybe you don't run the best budget in the world, but you are an active trader on the Stock Market or Commodity Market. If you have enough funds here to cover your deficit, you suffer no drawbacks.

#### Take a loan from a friend

Okay, so maybe you're not a great trader either, but at least you have a friend who can lend you some money. Depending on the interest they charge, and their proclivities, this can be anywhere from safe to dangerous.

#### Take a loan from the Commodities Broker

Huh, so you can't trade, and you have no friends, or maybe they are also broke. Okay, well the Commodities Broker is here to rescue you! Sure, he charges a much higher interest rate than a friend would, but you'll be able to pay it back right?

#### Mint new currency

This is where all you Keynesians can have your time in the sun. You can authorize any amount of currency to be minted and then deposited into your Sovereign Account, which from there you can cover your balance. Please note however, this will have downstream effects. Like making all the goods from your industry more expensive, inflation right? So this is pretty much kicking the can down the road, but on the bright side, Inflation will burn off by a certain % every cycle, so long as you don't keep doing this.

#### Default

There is absolutely no reason why you should ever choose this option. But if you do, you will recieve an interest free bailout from the Commodities Broker (Or a friend is they have the dough to cover it). If this happens, well, I have no idea what happens. I suppose choosing this will require a bit of negotiation and Role-Playing but first thing that comes to mind is commiting a % of your national production to your creditors for a period of time.

It should also be noted that if your deficit reaches a certain % of GDP, you will automatically default. You really should have fixed this sooner. Though I will make provisions for nations taking a vacation so you don't come back to a totally collapsed nation.

## Conclusion

So there is a ton of information on what's kicking around my noggin for the economic system. I can see a lot of interesting RP opportunities arising from this. Members of the IMF debating on what the Commodities Broker's Interest Rate should be. Price fixing, currency wars, tarrifs, embargos. There is a lot we can explore here and I can't wait to hear your opinions on all these.

