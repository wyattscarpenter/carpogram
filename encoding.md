# Encoding of Carpogram into bits and bytes

TODO: um, finish all of this, I guess. Can't really use this on a computer until I do so.

## Executive Summary

The encoding of Carpogram is (TODO: figure out the encoding of Carpogram)

## Detailed Analysis

The eventual goal of 


### Fixed-Format

### Just Steal 8

> The main character of Javascript is Dracula (Javascript is the only programming language to have a main character ) 
— snarp

(the section title here is a joking reference to "just send 8", an old protocol & movement)

One of UTF-8's most striking flaws, to me, is the fact that there are multiple ways to encode a codepoint in UTF-8, necessitating the "overlong encodings" rule to 

This rule is not so bad (we follow a number of rules all the time), but it indicates a significant amount of wasted space, or "air" in the encoding. We're wasting encoding space on invalid representations of codepoints?!

Backwards compat, which we feel free to drop

self-synch (I don't think the text is, since compositing characters can silently disappear, just the bytes) (well, I think it's a different property, and it is self-synching there)

error correction?

substring seaching?

### Our own encoding?

infinity code points

VLQ / crockford's kim (https://www.crockford.com/kim.html)

sorting property of UTF-8

or... a 10xxxxxx 01xxxxxx 11xxxxxx type code, if need be?

self-synchronizing

## Stuff about Dracula

Carpogram is an enumeration of textual codepoints (discrete pieces of information in a computer system that are used to represent text). Carpogram can be used in three different realizations: Dracula, Frankenstein, and Wolfman. Again let me stress that all of these are incompatible with regular Unicode and ASCII, despite the similarities I'm about to discuss.
Dracula: the simplest and oldest carpogram encoding. one byte (one octet) is one codepoint. there are 256 codepoints.
Frankenstein: utf-8 but the first 256 codepoints of Unicode are replaced with the first 256 codepoints of Carpogram. This also means there are more canonical equivalences, including for surprising things such as variation selectors, and a precise map of them could be developed for Unicode-processing programs to use to adapt to Frankenstein. The first 256 codepoints of Unicode are mostly wasted on control characters anyway, so having carpogram there instead (almost a straight upgrade) is a huge boon. The main benefit of Frankenstein is being able to encode other languages, like Chinese, which are involved enough that the carpogram autocrat (me) would never independently figure out a good way to accommodate them (due to lack of expertise, spare time, etc).
Wolfman: the codepoint-encoding scheme of utf-8, but the codepoints encoded are carpogram. this is the only encoding that can accommodate a hypothetical future where a future version of carpogram adds more codepoints.
(unnamed potential encoding): there might be something better than UTF-8, given that we can abandon its constraints, and given that it has a known problem of overlong encodings being possible. The solution should still be self-synchronizing, but I'm not sure how easy that is or easy to mess up it might be, and I haven't thought about this problem for very long.

I'm thinking I will revise the above provisional encodings to, instead: Xenophon which is 1-byte; and Dracula that is utf-8 with u+0–u+ff modified. If I develop a taste for quixotic quests, I can allocate more code points, and possibly eventually develop another encoding along the same lines. Possibly getting rid of deprecated Unicode codepoints in the process.

Xenophon is named after the ancient greek Xenophon, author of the Anabasis, a story about a guy coincidentally also named Xenophon.

Note that in Xenophon there is no right-to-left text (should I add this?) so you don't have to worry about that. In dracula 

This does suggest that maybe the file extensions should be .dracula_carpogram, etc. maybe with a hyphen. and also for the mime types. Actually, come to think of it, the right system allows for nested semantics, so whatever.vlq.carpogram.json.someconfig should be the ideal type of configuration. If you get my drift. Which, in turn, kind of removes the pressure on picking the perfect one immediately.
