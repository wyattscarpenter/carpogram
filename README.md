# carpogram
a text encoding

## random notes

possibly include the left comma and straight comma? perhaps also the Chinese list comma (diagonal comma? backslash comma?). Could also include the right colon but idk the normal space+colon kind of does that alright already though.

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

ASCII punctuation (most of it).

normal punctuation (including interobang and perconitination point).

combining italicizer, obliqueizer, reverse obliqueizer, rotator(?), boldizer (DUPLOYAN THICK LETTER SELECTOR?), superscriptizer (this one can stack, to make 2^2^2), subscriptizer (same), strikethough (also stacks, to get, like, ¥ (bad example, but if you imagine a double-crossed out letter)), underline (distinct from underscore) (stacks), overline (distinct from overscore/macron(?)) (stacks), sans-serif, monospace, blackletter (including the variation selector for the style of black letter fraktur versus round hand I think), small caps izer. big smalls izer? (probably not). double-struckizer / blackboard bold. Cursivizer? slab serif izer? Swashizer?

text is assumed to be written in Roman (non-italic, non-bold, etc) in a traditional serif font. There is no way to explicitly request this because 1 these are combining marks not variation selectors 2 are you crazy this is just what text is; pick a different font if yours doesn't work right.

It's clear that some of these can compose (bold+italic, for example), but for some of them it is not so clear (italic+italic). So, guidence should probably be given about this.

Turnedizer (upsidedownizer). Possibly conflicts with / just is egyptian rotational controls?

Regional-indicator-izer? hmm. Keycap-izer? Hmm. Could also merge these ideas in with drop-caps, although that might be foolish.

oh yeah, also, There are only lower case base letters and then there's a combining capitalizor. I guess this doesn't stack.

Probably no drop-caps or illuminated letters.

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

Should I map var selector 256 to 0? Seems like a crazy idea, but more attractive if you consider that VS1 is often used for a common variant form of the glyph, leaving the most common variant with no explicit specifier (unless I want to lay down the law here and say "NO. YOU'RE NEVER ALLOWED TO USE THAT VARIANT IN YOUR FONT UNLESS IT'S SPECIFICALLY REQUESTED"). Also that to match unicode currently the 0x00 byte would map to VS1 and the 0xFF byte to VS256, which is a bit annoying. Anyway I guess I'm not really "mapping" so much as "declaring a new variation selector VS0.

interlinear annotation characters

egyptian heiroglyph format controls

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
Like all realistic text-encodings (such as unicode, in contrast to ASCII, which encodes a fantasy text encoding where people use a small subset of text), care must be taken when processing carpogram. In particular, despite being a "single-byte" encoding, many of the bytes are modifiers, which must be considered to determine the semantic meaning of the text. This is often largely dependent on the context in which you are writting an application. If writing a program to add numbers, zero and slashed zero should be accounted the same. If writing a program to display text, they should be accounted differently. If writing a program to search through text, they should be accounted the same unless strict matching is enabled (but this itself is a UX (user experience) choice.

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
