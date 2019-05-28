[(Back to puzzle)](./)<br/>
[(Back to main page)](./..)

# Cardano Puzzler #1 - Solution

![image](https://user-images.githubusercontent.com/5585355/56515020-8a59d980-653f-11e9-82eb-0ff2ae915c9c.png)

## Step 1 - Romans

The first hint was that target is a Yoroi wallet, being famously 15 mnemonic words over 12 words in Daedalus. So the first question is how to get 15 of something from these numbers.

Converting these 3 separate numbers to Roman numberals gives sequence:
```
DCXLIV CLXVI XXIV
```

Which gives 15 characters altogether.

## Step 2 - Exclude "obvious" words

Next question is how to get 15 valid words from these 15 characters. First instinct might be to try and find a word starting with the same corresponding letter, but soon enough it might be noticed there are no valid words starting with `X`.

Solution does not require searching thru the BIP39 list of available words, because whether a word is valid or not can be checked in the wallet restoration itself, but you can check the words in the list for convinience: [https://github.com/bitcoin/bips/blob/master/bip-0039/english.txt](https://github.com/bitcoin/bips/blob/master/bip-0039/english.txt)

So since there are no words starting with `X` - "words starting with same letters" theory can be abandoned altogether, and some other pattern supposed to be found. And the idea was that in search for a logical enough word represented by Roman numeral character `X` - people would find that `ten` is a valid mnemonic word.

Following this theory we can start looking for similar available words for other characters and come up with this:

|#| Character     | Word              |
|-|---------------|-------------------|
|1| D | ? |
|2| C | hundred |
|3| X | ten |
|4| L | ? |
|5| I | one |
|6| V | ? |
|7| C | hundred |
|8| L | ? |
|9| X | ten |
|10| V | ? |
|11| I | one |
|12| X | ten |
|13| X | ten |
|14| I | one |
|15| V | ? |

This already gives us most of the phrase, so at least a worthy theory to pursue. But then it lives us with three unresolved characters:
```
D L V
```

## Step 3 - Looking for something obvious

Starting from here - it's where I am not that happy with this puzzle, and why I decided to close it after all. Up to here every step seems to me to be pretty logical (or logical enough, at least) and is kinda suggesting that it might be a best bet just by the leap of progress it gives you, like so conviniently turning 3 numbers into 15 characters, or so conviniently excluding 9 out of 15 words. Starting from here it turnes into the real puzzler, where you need to figure things one-by-one, but at the same time it does not provide the same feeling of a leap you get from figuring out previous steps.

So the task remains the same - we need to find one word for each corresponding character. And there's basically no ground for us to base the guesses on, apart from the previous steps. So it seems like at least the words gotta have some obviousness, logic, or theme consistency with the previous two steps, because up to now it wass all about roman numerals and the numbers they represent.

So we can try and go from last to first:

### V

`V` seemd to me as the most obvious and easy one. If we don't have "five" as a valid word for this character - what is the second most obvious **valid** guess?

#### V = Victory

"Victory" is a valid word for a mnemonic phrase, and the third hint "V for Vendetta" was a clue about this, along with being a clue for first two steps at the same time:
1. "V" and there are five people sitting in chairs
2. "V for Vendetta" suggesting character corresponds to words
3. And finally "V for Vendetta" sounding like "V for Victory" from WW2 ([https://en.wikipedia.org/wiki/V_sign#Second_World_War:_V_for_Victory_campaign](https://en.wikipedia.org/wiki/V_sign#Second_World_War:_V_for_Victory_campaign))

Always seemd to me like "V" is so closely linked with "Victory" that it's almost like giving a character away just for free:

<img src="https://user-images.githubusercontent.com/5585355/58418783-6e42de00-8091-11e9-8bc4-54ed15531a2b.png" width="200"/>

### L

`L` is harder, because it seems like there's no word that would be jumping forward in associations just as easily as "Victory". But we gotta look out for some logic, e.g. what is an obvious word association that can be found in the world when character `L` is used. "Looser" could be a good option, but is not a valid mnemonic word, and does seem to "american". In Roman numeerals `L` stands for 50. Could there be any way how we could tie `L` with 50 in any other way?

#### L = Large

![L for Large](https://user-images.githubusercontent.com/5585355/58419362-12795480-8093-11e9-9fa3-9d41ef98cd69.png)

It might be a surprise for people from UK and US, but `L` **does** mean "50" in some context in some parts of the world )

## Step 4 - D for Different

`D` is the hardest one, which is suggested by "D for Different" hint. And since `different` is not a valid mnemonic word people for some reason started suggesting that this hint means `D` should correspond to valid word `differ`, which, let's be honest' would be way too easy )

It seems there's no valid word that would be a good easy logical associiation for `D`. Something that would be associated with `D` and where `D` would be used as a replacement in the world, apart from some americanized lewd options, but they are not valid mnemonic words )

If we look for all available words for `D` in the list it also seems like there are no optons that would feel quite like words for `L` and `V`. "Decade" could be a good option, but it stands for 10, and in Romans `D` means 500, so quite a difference.

So there was an additional hint saying: "What historically happened to some alphabet letters you now can do to words", and this hint only starts making sense after you have spent a ton of time trying to think what `D` could stend for and when you start wondering why `D` stand for 500 in Romans at all.

That's why I always suggested you might need some googling at the end of solviing this. Because if you start really wondering what `D` could stand for and why `D` is 500 at all, and if you google it for a while, there's a chance you could find this: [https://www.livescience.com/32052-roman-numerals.html](https://www.livescience.com/32052-roman-numerals.html) (or other similar source) that says:

> M = 1,000 — Originally, the Greek letter phi — Φ — represented this value.

> D = 500 — The symbol for this number was originally IƆ — half of CIƆ.

So basically what they did is they took 'Φ' (a "thousand") and cut away the first half of it to represent a "half of a thousand", and the remaining part looked like 'D'.

So what can WE do with this information? If we need to work with words instead of letters and numbers... we can take the word "thousand", and cut away the first half of it... and let the remaining part to represent `D for 500` )

#### D = Sand

## Solution

So the final solution is the mnemonic phrase:
```
sand hundred ten large one victory hundred large ten victory one ten ten one victory
```

You can check this mnemonic phrase quickly in [https://www.adalite.io](https://www.adalite.io)

## Conclusion

So this whole solution was a very interesting sequence to come up with, and might be very interesting to read thru. But very quickly became obvious that it's not that easy to work thru, at least because what might look like logical enough steps and conclusions just by themselves, are absolutely not obvious on how to chain them together, and the order of the solution is logical only for the two first steps. So the actual puzzle itself, basically, was: "figure out how to connect these three characters with some words", and this sub-puzzle by iitself does not make me happy as a creator. Hence the solution to close it. Maybe one day after some practice I will be able to come up with a puzzler of the similar (intended) depth, but a properly solvable one, and will happily do it. Meanhile I will try to keep producing new interesting puzzles and refine my understanding of how different methods and tricks work in puzzles of different styles and contexts.

Gitter user `@underctrl` was the first one to propose valid solution for first two steps after the closing were announced, and no **better** further solution was proposed after that until the closing itself, so they get the prize:

![image](https://user-images.githubusercontent.com/5585355/58421130-e6ac9d80-8097-11e9-97bf-425ee732dec9.png)

At the moment they are asked to provide an address to receive the prize. For now prize was transferred to a temporary wallet, just to close the puzzler. When prize will be transferred to the winner - I will update this page.

### Update

By agreement with `@underctrl` - they [received](https://seiza.com/blockchain/address/Ae2tdPwUPEYzTvuJjpJBiU35nBhHeetEiQ1WYZSG4Ght71TiHETiPWii7H1) only half of the initial reward, and the rest was divided to increase prizes for puzzles [#2](../0002_0-based) and [#3](../0003_Hand_in_hand)

![image](https://user-images.githubusercontent.com/5585355/58501825-eee70480-818d-11e9-8252-084f5d4ecb56.png)
