# carpogram

## Introduction, definitions, and general notes.

Carpogram is an enumeration of elements that can be used to represent text in an information system such as a computer. This is what's generally known as a "character set" — although, unlike a mathematical set, the order is quite important. That order is what we use to encode the elements in a computer! The encoding of Carpogram into bytes is detailed in [encoding.md](encoding.md).

TODO: explain here or elsewhere its ideas about text.

As I'm writing this document it is in UTF-8, not Carpogram. It is also in markdown, a markup format that produces rich text.

## motivation

The main motivation behind carpogram is being frustrated that computers have made such enormous progress and yet are still unable to represent text. Instead, historical accident confuses information technology infrastructure and forces us into ridiculous contortions. Carpogram fixes this, finally allowing you to type text into a computer and have it actually be right.

## disclaimer and call to action
I am still working on carpogram. You can't even slightly use it right now, but you might find some of the ideas described in this document interesting (although most people don't find this topic very interesting in general, and it will be no more interesting than that!). As such, there isn't even a version number for carpogram yet, and I make random incompatible changes to it all the time. (When there is a version number, it will probably just go 1, 2, 3, etc, and be backwards compatible forever.)

If you are interested in implementing carpogram, let me know. Your experiences implementing a prototype could provide invaluable feedback.

## random notes

if I'm being brutally honest, and not just making a joke that it's lambda (Λ), A without a crossbar should probably be a VS. actually, maybe I just leave that to fonts. Maybe also so for the type of “ that has the heavy part on the bottom vs the top. Possibly even the same with the "wrong way" apostrophe ‘ that people use from time to time as a mistake.

Unicode is bad in that only publish the charts so even determining what a character even is supposed to be, actually, just from a picture, some properties, and a little bit of text, is sometimes pretty hard. I hope carpogram will fix this.

At the same time, carpogram is probably going to be less like "expert research projects" and more like "standard you pay money to get your codepoints into"; purely out of necessity, we must rely on private actors to figure out some of the details for us. And, hopefully, this incentivizes people correctly to put good and useful characters in there. Also, those people will know what those characters are, and can explain them.

I'm not really sure what, if any, "properties" the characters will have. I've always been dubious of those because a punctuation character can sometimes be a letter or vice-versa. On the other hand, I see why they provide those: programmatic manipulation of text is the whole point of encoding text, after all.

I am not sure if carpogram should support soft-hyphens or what. I guess it couldn't hurt. It seems like soft-hyphenation and right-to-level text will have to be controlled explicitly in order to avoid unfortunate accidents of the sort that are fairly common. This will allow us to have just one system, albeit a little inconvenient one. If we already have the rubi characters, eg, then I think this is also fairly natural.

Need to rigorously treat the levels of arbitrary-length strings of: bits, codepoints, and characters (maybe more things). At some point. Probably after I figure out self-synchronizing codes. From each layer of n elements we create a new set of m elements, for any n and m. Isn't that something?

{ Intercal interlude. I use the squig bracket here because markdown was designed by people who don't really understand text, so it's completely impossible for me to use block quotes correctly otherwise while still grouping everything together right.

It would be sort of funny to encode the ascii double-quote into carpogram to support Intercal and call it “rabbit-ears”, but this would be ruinous. Anyway, we no more support Intercal than we support APL, nor other feverish dreams of various computing systems.

Intercal allegedly also has a rabbit character (period with straight double quote above it) named rabbit, a V with a line through it named bookworm, and a blotch named blotch, which apparently do not exist in unicode, according to https://www.muppetlabs.com/~breadbox/intercal-man/tonsila.html. These are mysterious to me, except for the comment in http://catb.org/~esr/intercal/ick.htm#Grouping-Rules

> One final comment about sparks and rabbit-ears; if the next character in the program is a spot, as often happens because onespot variables are common choices for operands, a spark and the following spot can be combined into a wow (!). Unfortunately, the rabbit-ear/spot combination has no one-character equivalent in any of the character sets that C-INTERCAL accepts as input (UTF-8, Latin-1, and ASCII-7) as none of these contain the rabbit character, although the Hollerith input format that CLC-INTERCAL can use does."

(?!)

And this paragraph from "Tonsil B: Notes On The Atari Implementation" https://3e8.org/pub/intercal.pdf#page=21

> The Atari implementation of INTERCAL differs from the original Princeton version primarily in the use of
ASCII rather than EBCDIC. Since there is no “change” sign (c/) in ASCII, we have substituted the “big
money” ($) as the mingle operator. We feel that this correctly represents the increasing cost of software in
relation to hardware. (Consider that in 1970 one could get RUNOFF for free, to run on a $20K machine,
whereas today a not quite as powerful formatter costs $99 and runs on a $75 machine.) We also feel that there
should be no defensible contention that INTERCAL has any sense. Also, since overpunches are difficult to
read on the average VDT, the exclusive-or operator may be written ?. This correctly expresses the average
person’s reaction on first encountering exclusive-or, especially on a PDP-11. Note that in both of these
cases, the over-punched symbol may also be used if one is masochistic, or concerned with portability to the
Princeton compiler. The correct over-punch for “change” is “c〈backspace〉/” and the correct over-punch
for V- is ”V〈backspace〉-”. These codes will be properly printed if you have a proper printer, and the
corresponding EBCDIC code will be produced by the /IBM option on the LIST command.

see also, this explanation of what "Atari syntax" is: http://catb.org/~esr/intercal/ick.htm#Princeton-and-Atari-Syntax. If the rabbit character is also an overpunch, it's odd that they don't mention it. (I think maybe blotch is a million things overpunched, or at least brackets and asterisk and maybe #, as a joke?).

But maybe it's some kind of ebcidc character (I'm not 100% sure what an overpunch is or if it counts as a "character), given this paragraph from the same source https://3e8.org/pub/intercal.pdf#page=7 :

> Combining a rabbit-ears with a spot to form a rabbit (".) is not permitted, although the programmer is
free to use it should he find an EBCDIC reader which will properly translate a 12-3-7-8 punch

(where this actually is a straight quote mark directly over the period, in the pdf)

Or perhaps that's a joke about how that character doesn't exist in ebcdic.

Allegedly there were a huge number of ebcdic codepages, which is weird. To quote https://en.wikipedia.org/wiki/EBCDIC

> There are hundreds of EBCDIC code pages based on the original EBCDIC character encoding; there are a variety of EBCDIC code pages intended for use in different parts of the world, including code pages for non-Latin scripts such as Chinese, Japanese (e.g., EBCDIC 930, JEF, and KEIS), Korean, and Greek (EBCDIC 875). There is also a huge number of variations with the letters swapped around for no discernible reason.[citation needed]

Which I think is amusing.

https://en.wikipedia.org/wiki/Code_page#EBCDIC-based_code_pages does indeed list a large number of code pages.

} End of intercal interlude

Note various ways an automatic conversion from Unicode to carpogram is not possible:
* No straight quote. If you have a " in a Unicode document, this must be converted to the appropriate “ or ” character based on context (or, perhaps, maybe even some other symbol, based on the intent of the author, like a double prime or gershayim).
* The straight ' character in ascii and the right single quote mark are often used ambiguously (or even incorrectly) and must be converted to the correct carpogram character (if you simply convert all ' to apostrophes and ’ to closing single quotes, you will get the wrong result). On that note, many systems butcher user input and turn leading apostrophes into opening single quotes; this should also be corrected Based on context — unless you are trying to make fun of that person.
* The diariesis and the umlaut are not the same character in carpogram, Even though they typically are in Unicode and cannot be distinguished there except with tricks that nobody uses that aren't even standard.
* The period in abbreviations must be converted to an abbreviation point instead of a period.
* The ascii asterisk is probably equivalent to a superscript asterisk in carpogram, same for the dagger used for footnotes and the double dagger etc; but you should verify this is what was intended if feasible. A carpogram asterisk is probably equivalent to a unicode ✱ heavy asterisk.
* There is no hyphen-minus in carpogram. You must use the appropriate character instead, which is probably a hyphen or a minus but also could be several other types of dashes or similar looking characters if we're being real. This is probably the most striking example of carpogram’s allegiance to real text over electronic text, because the hyphen-minus is so common.
* In general, a lack of extended characters, for which I suppose some gaiji system must needs be used or something. The only reason I do not have these is that I lack the resources to. Ideally I would encode all of human language, but not even the Unicode consortium has done that and they have many people working on it.
  * I guess a serious attempt at encoding all of text would also include all of the weird digital mistake punctuation marks like straight double quote. So, eventually, this project would turn me into a superset of Unicode. Womp-womp.

there is a category of metatextual pseudocharacters that I should discuss, which are (roughly) glyphs that appear in text that do not make sense to include in a text encoded. for example, to minimize ambiguity, the "hyphen" that breaks a word over lines should look distinct from a hyphen used in text, and because plain text is supposed to be reflowable (this is an implication of its other properties), It wouldn't make any sense for us to encode it; that would simply allow you to include it in the text in an incorrect place this creating ambiguity. I'm not sure if the same logic applies to the end of text tombstone, or if you could legitimately use that multiple times if you had multiple articles in the same text document or something, like an entire magazine as one txt — I guess you probably could, so that doesn't apply. many people think you can't encode a horizontal rule in a text encoding, but I think you can; the same logic about linebreak hyphens doesn't apply there. the external-link arrowbox glyph is also like this, as the current Unicode consortium has ruled: they are automatically generated by the software for document display (in hypertext, even), and it would not be helpful (or even really make sense) to be able to manually insert them.

I have recently learned that a carpogram is actually something already. "The carpogram is a simple radiographic technique that allows to visualize all the bones of the hand, wrist (carpus) and distal portion of the forearm (radioulnar)." —https://medicosdoc.com/en/oferta-detalle/carpograma-barranquilla/2374 should i rename this project to something else? idk it's probably fine. I also have a hunch, based on the sources in which this term appears, that this is actually just a Spanish term, carpograma, which is being calqued to carpogram. So it may be something of an idiosyncratic translation quirk and not be a word in wide currency otherwise.

In carpogram, the asterisk and dagger (and double dagger, etc) are not superscript by default; they are just regular symbols. This will strike most people as strangely large because they are used to seeing the superscript versions. You should superscript them to get the versions that indicate footnotes. Actually, TODO, I'm trying to figure out if it's inherent in the concept of an asterisk that it's superscript or at least sized like a superscript symbol. The word does mean "little star", after all. Or is ✱ the true unsuperscripted form of an asterisk...? (Nota bene: asterisk is still, naturally, distinct from the star character ⭐︎ which is also present in many text encodings (and hopefully this one).)

irony mark is the CPNB proposal 2007, a slightly kinked exclamation mark

unlike Unicode, which is as complicated as human language and also a lot of technical tech, carpogram hopes to be only as incredibly complicated as human language.

There are no double-prime, double-quote, double-guillmet, double-equal-sign nor double-em-dash characters in carpogram, etc. Just the single version of all of these, which you can then double up the normal way. So, ′′ ‘‘ ‹‹ == and ——. Much like _ and ⎯ (U+23AF Horizontal Line Extension), — is defined to run together if you use it multiple times, in order to allow for the famous 2-em and 3-m dashes so useful to authors of semi-anonymous letters.

vs for long s? vs for “ that is turned ” vs mirrored ” (so to speak)? vs for ampersand &, 3| and Et?

One tempting, but probably wrong-headed, idea is to make base i always dotless, and if you want the dot, you compose it. (Software will likely do this automatically unless you are turkish.)

It's not clear to me if there should be a page break character, but if so it should probably be canonically equivalent to ascii formfeed (0xC). Although mine would have a different code point.

I'm not sure if the quotation bar is the same as the em dash in carpogram.

I'm not going to add a lot of space characters to carpogram (see also: repeated marks when one can), but I'm also definitely not going to add an em quad, since apparently that was added in by mistake it seems.

To be honest, I'm not completely convinced ß is its own letter and not just a long-s tailed-z ligature, no matter what the Germans think. Which raises the question again of how to deal with æ and œ and also ꜵ (and ꜹ and ꜷ and Ꜹ and Ꜷ?) and ĳ for that matter. Mayhaps I could use the stick-em-together operator and then a VS? On the other hand, these are proper letters in some languages, and I guess you have to admit that ligatures can eventually spawn new proper letters, or w is also out, for example. On the other other hand if you think about it privileging this as a letter is actually just as biased against everyone who was using it as a ligature, ie to write encyclopædia — unless you want to say the ligatures are a font matter and the correct spelling of this (spelling of this) word in English is encyclopaedia, or alternatively again if you want to claim that English was actually still using the æsch letter all along and it's simply synonymous in value with some other things, rendering the whole dispute moot. Maybe you should just go with "whatever printing presses would do". On the other hand then you have to support ﬁ ligature, and no one wants that.

blockquote bar that looks a bit like | but is for blockquoting a paragraph. (Should I just use | instead? Could be reasonable. Looks a bit bad though, and is not semantically distinct, for whatever that's worth.

due to carpogram's particular conception of plain text features, I was forced to consider what the "emoji" style is supposed to mean. I thought it was intractable, considering that the Unicode materials mention it as being large, colorful, and possibly animated. the latter two I reject as plaintext, and the former i don't really endorse as a description. (It is also paradoxical that they call the opposite of emoji text, given it the whole point of emoji is to be textual characters, but that's neither here nor there.) they also say "whimsical", which is something, but not very specific. However, it occurred to me that the word "cartoon" applies. the emoji characters are illustrated in cartoon. that resolves it.

This is a good reference to pick up the actually useful characters of Unicode 256: https://mrinitialman.com/TestSite/HTMLBook/Chapters/Appendices/Appendices-Characters.html (those characters which are not directly encoded and aren't control characters I'm abandoning should have some story of being encoded, using composition.) (it's also possible that I should adopt some of these control characters).

Variation selectors for certain serbian and masadonian italic letters? https://jankojs.tripod.com/SerbianCyr.htm (I probably won't actually have cyrillic in carpogram anyway.) actually the Wikipedia page on this has a lot of detail. I would ideally want an expert to tell me which ones to put in, though.

I'm not an expert on all this stuff for every language, so I'm sort of relying on comments from others if I stray outside of my bounds.

The unicode variation selection database for CJK is such a weird system. Are you even supposed to be able to implement them? Or is it just for internal company use...?

VS for §, for the stacked s or side-by-side s. VS for dollar sign (both one bar and two bar, and also bar all the way through or not (do var selections compose, or do I have to precompose them?)), VS for cent sign (bar all the way through or not). Also maybe straight and angled for the $/¢ bars.

I'm still doing furigana, don't forget that...

probably you should be able to have arbitrary text attribute combinations, and you should just have a mathematical model of what it does to the characters which can simply be repeatedly applied. Not as hard as you might think. 

possibly a mistake to conflate chinese/han gothic/grass distinction with Latin San serif. But what if I were to refer to this as "unifying" them. Now we're talking.

the symbol codepoints should line up with ASCII mostly and should match the digits on the keyboard (so the byte for ! ends in 1, etc)

There is no "magic number" to indicate a carpogram stream. I'm afraid such methods are generally unreliable and also unfollowed and also inefficient and also unstreamable, so you must simply preserve the metadata of what your file is in some other standard way. This is a problem for a different part of the computer system, not text encoding.

possibly include the left comma and straight comma? perhaps also the Chinese list comma (diagonal comma? backslash comma?). Could also include the right colon but idk the normal space+colon kind of does that alright already though.

I'm pretty sure, at this point, that you'll make a "double quote" in carpogram with two single quote marks. After all, why not? It also occurs to me that people will probably be able to represent ascii "straight" double-quotes using two apostrophes, much like how they can abuse the apostrophe character to make an ascii "straight" single-quote. It is no matter. That's beyond my control.

abbreviation mark similar but not identical to a period. interpunct makes it in, probably not word separator middle dot though. combiner that combines the next two.

cool s ( https://en.wikipedia.org/wiki/Cool_S )

whether or not a text file "should" end with a new line is a convention of files and operating systems. However, in the opinion of this author, it is clear that there is no semantic reason why a file should end with a new line (newline is a separator in this standard), and the reason text files do on Unix (which determined a great number of computing conventions) is to make it easier to manipulate them (you can >> the file without having to check if it happens to end with a new line first). So, you should probably continue doing that unless you are working on an operating system (or within the context of different operating system conventions) that handles things differently.

possibly add the regional indicator izer, and having done that, extend the standard to also encompass the welsh thing? And the use of years for flag emoji? _Do_ I believe in the unicode extended universe? (W/ emoji zwj sequences suggested for general interchange and also maybe not) I lean toward no in general. But this might be an exception. Although I might not believe in this mechanism of encoding, frankly (this is immaterial for compatibility, as unicode already changed the encoding mechanism from the original character-based system from the original — see "what's new in unicode 6" for more.) a more philosophical question: are all characters Unicode encodes ipso facto textual characters? It seems like if people use characters/certain-shapes in text enough (ever?) they do in fact become textual characters ipso facto, so maybe adding to Unicode is enough (or at least enough to create the presumption, much like how the official name for something is presumptively a good name candidate for the Wikipedia page about it, even though the Wikipedia page goes by common usage, because it least somebody is probably using the official name!)

Possibly have an object marker character, which I used to think was a crazy thing to have in unicode, so that people can actually work with carpogram in enriched formats better? (actually I guess the TEI thing fixes this.)

Suggest TEI as an alternative for people who need non-latin chars?
(as a fun fact, TEI documents are XML and they can declare their encoding, so they could(?) be written in carpogram)

the izers have to be prefix or it's impossible to answer "what is the first character" without scanning in the entire text. (This is still impossible for last character, but that's far less common of an operation) (nth character is impossible in O(n) for unicode or any non-fantasy text encoding).

variation selector to make periods square, which I believe is required for Armenian or something

combiners have to be prefix in order to answer such devious questions as "what is the first character". You still can't answer what is the last character without scanning the whole thing, but that's a much less common question

The layout is invariably left-to-right.

Are the masculine and feminine ordinal indicators ◌ª ◌º just superscript a and o, despite being distinct in unicode? I think that's plausible. This also kind of implies that you can make a numero symbol just by using No_(2-place combiner under)(superscriptizer).

Should superscripts be their own characters, or belong to the previous character? Their own characters.

a basic goal of this plain text encoding is to make it really nice for real actual English — computing has come a long way since using a computer meant you had to compromise and have one symbol as a hyphen-minus. you can have nice things.
  (incidentally, this also connects to the idea that all of this text is by default proportionally laid out and serif implicitly).



one of my unusual opinions that will be represented here is that the apostrophe character will be encoded differently from, and visually distinct to, the single quotes ‘ and ’. There also is no "straight single quotes". (And perhaps the double quote should simply be made of single quotes... hmm...) (let's not make it a comma accent mark, though; let's not go crazy (Plus also there are comma diacriticals that should not be confused).

Include a character like ) (but smaller?) to be used in smiley faces like :) without messing up nesting parens its found within.

possibly æ and œ? unclear to me. possibly also single-storey a? or var selector for that? Possibly also var selector for single- and double- storey g.

Not clear if I should include a thorn, etc, either.

ASCII punctuation (most of it) (mostly in ascii order).

normal punctuation (including interobang and perconitination point).

The izers I'm about to name affect what we call "attributes", such as boldedness, italicization; which should not be confused with "properties" like "is a letter" as specified e.g. in the uniccode character property tables. Although in carpogram capitalizedness is treated as an attribute instead of as a property (which unicode treats, in part, using Lu vs Ll properties)

combining italicizer, obliqueizer, reverse obliqueizer, rotator(?), boldizer (DUPLOYAN THICK LETTER SELECTOR?), superscriptizer (this one can stack, to make 2^2^2), subscriptizer (same), strikethough (also stacks, to get, like, ¥ (bad example, but if you imagine a double-crossed out letter)), underline (distinct from underscore) (stacks), overline (distinct from overscore/macron(?)) (stacks), sans-serif, monospace, blackletter (including the variation selector for the style of black letter fraktur versus round hand I think), small caps izer. big smalls izer? (probably not). double-struckizer / blackboard bold. Cursivizer? slab serif izer? Swashizer?

text is assumed to be written in Roman (non-italic, non-bold, etc) in a traditional serif font. There is no way to explicitly request this because 1 these are combining marks not variation selectors 2 are you crazy this is just what text is; pick a different font if yours doesn't work right.

It's clear that some of these can compose (bold+italic, for example), but for some of them it is not so clear (italic+italic). So, guidence should probably be given about this. Actually they should probably all arbitrarily combine.

Turnedizer (upsidedownizer). Possibly conflicts with / just is egyptian rotational controls?

Regional-indicator-izer? hmm. Keycap-izer? Hmm. Could also merge these ideas in with drop-caps, although that might be foolish.

oh yeah, also, There are only lower case base letters and then there's a combining capitalizor. I guess this doesn't stack.

Probably no drop-caps or illuminated letters.

to make a text look like a typewriter or how computer code listings are often printed, it should be monospace and slab serif. Todo: should this actually be its own attribute? after all you can imagine a transformation on times new Roman that is monospace and slab serif but doesn't look like typewriter. To make typewriter you would have to switch fonts. which I suppose is ultimately be job of the rich text layer. or should it be?

Unclear to me yet if underscore = macron below or if underscore = low line. Same for overscore(?) = macron or overscore = overline. Also not clear to me what I will do for macrons or ties over two characters (maybe something like U+FE2D COMBINING CONJOINING MACRON BELOW?). Actually, this is settled by the fact that unicode considers U+005F, the underscore, to be a low line, putting it in congruence with their combining low line diacritic. I guess overline would just be x_(over-combiner)

If feeling greedy: greek letters, possibly cyrillic, possibly allow people to typeset music in carpogram. Tables seem possible, but like too much comeon ha ha that's rich text there.

combining combinizer for o^(that) = ô. (oh yes this is also specifically combining over, because you could also put things under etc. There is also a combine-under mark.) (this is sort of conceptually similar to an ascii "backspace" (tho not a modern keyboard backspace) but I won't call it that because that's just too confusing)

need a lot of hooks and curls and stuff.

maybe ø is just o/(combining combinizer) (combiner overlay?) (there's probably an obscure unicode character I've read about that already claims to do this, unsuccessfully).

possibly a combining variation selectionizer, which is used with a hex digit? Actually it's used with a byte I guess. Maybe more, for forward compatibility.

possibly a combining tagizer? to make tag characters, which can then be used to indicate source language.

I have also joked about adding the chess characters, possibly with a black square and then using the combining combinizer on that to color them. and maybe the integral symbol.

I would add the android blob emojis if I could, but that seems out-of-scope.

space, nonbreaking space, breaking nonspace, and nonbreaking nonspace. (These are all already unicode concepts, but this is what I will call them.) (I do not have

particular picture of a dog (cartoon) (question dog)

0xFF is formfeed?

one type of new line, possibly called LF, possibly NL.

var selector for 0, 0 with slash, 0 with dot, 0 explicitly with nothing in the middle. 0 with reverse slash?

var selector for z with stroke (does this make a problem given that ƶ is a distinct unicode character?)? 7 with stroke?

var selector for double-bar & single-bar dollar sign?

Should I map var selector 256 to 0? Seems like a crazy idea, but more attractive if you consider that VS1 is often used for a common variant form of the glyph, leaving the most common variant with no explicit specifier (unless I want to lay down the law here and say "NO. YOU'RE NEVER ALLOWED TO USE THAT VARIANT IN YOUR FONT UNLESS IT'S SPECIFICALLY REQUESTED"). Also that to match unicode currently the 0x00 byte would map to VS1 and the 0xFF byte to VS256, which is a bit annoying. Anyway I guess I'm not really "mapping" so much as "declaring a new variation selector VS0, and saying that it's like Unicode's variation selector 256".

interlinear annotation characters

egyptian heiroglyph format controls (or use generalized rotation controls instead?)

the sound a bell makes

fraction bar character, that does the fraction slash stuff. Note that % is its own character, and cannot be made through 0⁄0 or ⁰/₀ or any such trickery. (ideally, your font reflects this by slightly ornamenting the % sign.)

May encode a fraction slash and also a fraction bar. It would be possible to get non-digit characters to render in these, but would need more funny control characters to do so...

∧ ∨ symbols. To get the xor symbols and whatever you just have to use the combiners. ¬ symbol.

Distinct umlaut and diaerisis/trema. (Note that in the conversion back to unicode, the canonical way to keep these distinct, so far, is the questionable hack https://unicode.org/faq/char_combmark.html#18 (but I don't think there will be a ton of converting carpogram back to unicode, honestly, given that carpogram is highly distinct in its concepts and much more wide-reaching)). There should also be a ◌̋ (double accute accent), I suppose, unless you just use two accute accents on that thang. Possibly the trema would just be two dots over, anyway. Also possibly, the standalone umlaut, if we have one, could encode ascii " (this is a dumb idea, actually).

dele, krull, irony exclamation point.

minus, hyphen, en dash, em dash, two-em dash, three-em dash, double hyphen (or perhaps n-hyphens should be achieved with --(over-combiner), triple hyphen, quadruple hyphen. I guess one of these (em dash) could be used for strike-through?

I would like to include emoji but it's hard to say how I could do that without breaking the bounds (which I am already stretching) of a "single-byte encoding".

To have tool tips for abbreviations, maybe use the unicode tags. And invent a new tag character for abbrs? Or perhaps just use the interlinear gloss characters, since uhhh how you gonna print a tooltip lol. This isn't hypertext.

Possibly include a novelty [carpogram] character, the word carpogram in a box, that can also be used as a magic number for this type of text.

proper angle brackets, of many types.

Some care has been taken in carpogram to avoid being sadistically incompatible with Unicode, which we acknowledge as a very useful encoding as well. As a random example of this, all variation sequences in carpogram that **could** match a variation sequence in Unicode, do. As another example, combiners in carpogram are postfix, even though they could easily have been prefix (as was, at one point, my intuitive placement for them — on the logic that the computer needs to know those to figure out what to render, so you could do it without backtracking).

Possibly include a tag that is not begin language but rather begin transliteration, and this allows for other scripts in carpogram. This seems bad, however, in that it seems like a multibyte encoding, and indeed a multi-byte encoding smuggled in. So probably won't do this.

## How to work with Carpogram
Like all realistic text-encodings (such as unicode, in contrast to ASCII, which encodes a fantasy text encoding where people use a small subset of text), care must be taken when processing carpogram. In particular, despite being a "single-byte" encoding, many of the bytes are modifiers, which must be considered to determine the semantic meaning of the text. This is often largely dependent on the context in which you are writting an application. If writing a program to add numbers, zero and slashed zero should be accounted the same. If writing a program to display text, they should be accounted differently. If writing a program to search through text, they should be accounted the same unless strict matching is enabled (but this itself is a UX (user experience) choice). See "text equivalence choices".

Internally, carpogram has some interesting rules for combining characters. Carpogram (inspired by unicode in many ways, but what isn't these days?) has a series of codepoints (in carpogram, a codepoint is a byte is an octet (of bits)) which sometimes combine, to create what you might call a "grapheme cluster". (This is what the end-user might think of as a "character". I think we avoid calling them "characters" ourselves in case this would confuse programmers who think every codepoint is a character.)

A variation-selector-izer (denoted here as VSizer or [VS]) after a codepoint turns that codepoint, instead, into a variation selector of its codepoint value (denoted here as VS[whatever]). Thus, the VSizer can be thought of roughly as a right-associative operator. This is unambiguous, in case you were wondering. Example:

0 = 0.
0[VS] = a VS0.
0[VS][VS] = 0 followed by a VS[the numerical value of a VS's codepoint].
0[VS]0[VS] = 0 followed by a VS0. (This makes it a 0 stylized with an explicitly empty middle.)
0[VS][VS][VS] = a VS0 followed by VS[the numerical value of a VS's codepoint].

This final example (as it does not currently mean anything) seems to suggest the possibility of using multiple VSizer to create VSs of greater and greater numerical value, in a base-256 manner. This method of doing things seems unlikely to be useful, but has been left open as a possiblity for the future for forwards compatibility. As a great man once said: why should there be any limit at all?

A similar situation applies to the tagizer (denoted here as [TAG], and what it produces as TAG([whatever]) There is a difference though, because while the VS works on numerical values, the tag characters are supposed to work on character values (grapheme clusters) to mirror https://www.unicode.org/charts/PDF/UE0000.pdf . Therefore, the otherwise-completed character before a tag character is turned into its tag value. Examples:

A = A. Recall that capital A is already a composed character in carpogram (a followed by capitalizer).
A[TAG] = TAG(A)
A[TAG][TAG] = TAG(TAG(A))

This also composes with the VS as you would(?) expect.

A[TAG][VS] = A followed by VS[the numerical value of a tagizers's codepoint]
A[VS][TAG] = TAG(a followed by VS[the numerical value of a capitalizer's codepoint])

The reader will note that most unicode tag characters are thus representable in carpogram, except for the ascii straight-quote tag, which character is not present in carpogram.

TODO: how do I summon the begin/language tag, and the end tag? I have a lot of codepoints to work with, but it's unclear to me what to do...

## How can I publish a book in carpogram

There are two answers to this question. If you just want running text in a book-like style, carpogram is in fact optimised for that. That's, in a way, what it was made for.

If you want heirarchical text relations like sections and headings, and aren't happy with something like writing `1.1.1.1 My section`, then you are out of luck, and must use an actual markup language to do this. So too if you want funny (rich) text formatting like color (todo: could I include a mechanism for rubricated or colored text, possibly using the tag characters?), or hypertext features. You also cannot control stuff like justification, margins, etc, in carpogram. if you would like to do this, may I recommend the software open office writer? perhaps use gutenberg's movable type machine?

## Text equivalence choices

There are a number of ways you can consider carpogram texts "equivalent", based on your purposes. Here are some of the most important ones:

• Full codepoint sequence comparison: all codepoint sequences that are distinct produce distinct texts. Note that this has some counterintuitive results, like how bold italic is now different from italic bold.
  ◦ Techincally your application could also consider what happens if, somehow, you have non-carpogram-codepoints in the input stream, like if each codepoint is encoded in 16-bit records and a record with no corresponding carpogram codepoint is read in. You could choose to ignore or consider those. But that is beyond the scope of this document.
• Full effect comparison: all codepoints are considered, as above, but the order of attribute specifications does not matter. A bold italic k is now considered equivalent to an italic bold k. Similarly, the order of diacritics that do not interfere (ie, both are applied to the base letter, not to each other) does not matter. **This is the recommended mode for most carpogram applications, like presentation and precise matching.**
• As above, but ignoring variation selectors.
• As above, but ignoring attribute modifiers EXCEPT capitalization, which is still respected.
• As above, but ignoring attribute modifiers INCLUDING capitalization, which is now ignored. **This is the recommended mode for when the meaning of the text is important, such as in commanding a computer system, as most people consider eg case and attribute variants of a word to be "the same word".** (Note that you presumably do not want word2 and word² to be the same, if the second one is simply a footnote marker, so separate footnote markers from the words they mark using a narrow space or something probably. Or use a different form of matching.) This form of equality is so useful that it has its own name, "Roman equivalence", and its own symbol (≈ with ʀᴏᴍᴀɴ above); "roman" because that's what text that isn't italic, bold, etc is called, and also because the Roman's Latin alphabet was a unicameral.
• As above, but with diacritical marks also ignored. This is useful for allowing english users to search for foreign terms, etc.


## Does carpogram accommodate the turkish dotless i? (ı)
No. The turkish dotless i requires an additional character, ı, which is not found in carpogram. Even worse, it changes the meaning of what a capital i is from I to İ. The capitalizer in carpogram does not accommodate this; the capitalizer always maps i to I.
So, how might turkish people write missives in carpogram? My recommended solution is that they use a normal i for what they would use the dotless i for; this will capitalize correctly to I. Then, for what they would use a dotted i for, they use i̇, an i with an extra combining dot (it is unlikely, as of 2025, that the preceding sequence of unicode characters has displayed correctly on your system); this will capitalize correctly to İ. When i is given a diacritic, it usually has its native dot (which is sometimes called a tittle) replaced with whatever the new diacritic is; obviously, this cannot be done in the case of the extra-dotted i — instead, the extra dot must be placed above the tittle. (The same goes for j, although I don't know of any call for an extra-dotted j). Care must also be taken to make this technically distinguishable (even if in practice nearly identical) from an i with a colon diacritic. Different spacing of the two should be sufficient.
