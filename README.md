# wow_item_db_ngrams
A meaningless collection containing ngrams of various lengths, for all the item names in World of Warcraft (Retail and Classic)

# What are n-grams?
"n-grams" are simply n-length strings of characters, where *n* can be any old number. In this particular context, the n-grams are made up of all the n-length strings that make up the item names of World of Warcraft items.

Perhaps better explain with an example.

# Example
Say we want to break up the string `morning` into trigrams (3-grams). To do this, we create an imaginary sliding window that can fit exactly 3 characters inside of it, and we start at the left-most end of the string. We record what we can see in the window, then we slide the window **1 character** to the right. Repeat until the right side of the window shows the right-most character of the string. Note that this does mean all n-grams where `n > 1`  will overlap to neighboring n-grams!

1. [**mor**]ning
2. m[**orn**]ing
3. mo[**rni**]ng
4. mor[**nin**]g
5. morn[**ing**]

This means the string `morning` contains these 5 trigrams:

```
mor
orn
rni
nin
ing
```

You may realize that any string of length `L` contains `L - (n-1)` n-grams, where `n` is the gram length. This means any string of length `L` contains exactly `L - (2)` trigrams, or `L - (1)` bigrams, or `L - (3)` tetragrams, etc.

# Why?

I ended up generating this data while working on an AddOn for World of Warcraft that lets the user perform fuzzy searches among all items purported by the game servers to exist.
