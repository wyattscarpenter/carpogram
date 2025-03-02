# carpogram
a text encoding

# random notes

a basic goal of this plain text encoding is to make it really nice for real actual English — computing has come a long way since using a computer meant you had to compromise and have one symbol as a hyphen-minus. you can have nice things.
  (incidentally, this also connects to the idea that all of this text is by default proportionally laid out and serif implicitly)

one of my unusual opinions that will be represented here is that the apostrophe character will be encoded differently from, and visually distinct to, the single quotes ‘ and ’. There also is no "straight single quotes". (And perhaps the double quote should simply be made of single quotes... hmm...)

Include a character like ) (but smaller?) to be used in smiley faces like :) without messing up nesting parens its found within

iso basic Latin

possibly æ and œ? unclear to me. possibly also single-storey a? or var selector for that? Possibly also var selector for single- and double- storey g.

ASCII punctuation

normal punctuation (including interobang and perconitination point)

combining italicizer, obliqueizer, reverse obliqueizer, rotator(?) boldizer, superscriptizer (this one can stack, to make 2^2^2), subscriptizer (same), strikethough (also stacks, to get, like, ¥ (bad example, but if you imagine a double-crossed out letter)), underline (distinct from underscore) (stacks), overline (distinct from overscore/macron(?)) (stacks), sans-serif, monospace, blackletter (including the variation selector for the style of black letter fractor versus round hand I think), small caps izer. big smalls izer? (probably not). double-struckizer / blackboard bold? 

oh yeah, also, There are only lower case base letters and then there's a combining capitalizor. I guess this doesn't stack.

combining combinizer for o^(that) = ô. (oh yes this is also specifically combining over, because you could also put things under etc. There is also a combine-under mark.)

maybe ø is just o/(combining combinizer)

possibly a combining variation selectionizer, which is used with a hex digit?

possibly a combining tagizer?

I have also joked about adding the chess characters, possibly with a black square and then using the combining combinizer on that to color them. and maybe the integral symbol.

I would add the android blob emojis if I could, but that seems out-of-scope.

space, nonbreaking space, breaking nonspace, and nonbreaking nonspace. (These are all already unicode concepts, but this is what I will call them.)

particular picture of a dog (cartoon) (question dog)

0xFF is formfeed?

one type of new line, possibly called LF, possibly NL. 

var selector for 0, 0 with slash, 0 with dot, 0 explicitly with nothing in the middle. 0 with reverse slash?

var selector for z with stroke (does this make a problem given that ƶ is a distinct unicode character?)? 7 with stroke?

var selector for double-bar & single-bar dollar sign?

interlinear annotation characters

egyptian heiroglyph format controls

the sound a bell makes

fraction bar character, that does the fraction slash stuff. Note that % is its own character, and cannot be made through 0⁄0 or ⁰/₀ or any such trickery. (ideally, your font reflects this by slightly ornamenting the % sign.)

May encode a fraction slash and also a fraction bar. It would be possible to get non-digit characters to render in these, but would need more funny control characters to do so...

∧ ∨ symbols. To get the xor symbols and whatever you just have to use the combiners. ¬ symbol.

Distinct umalut and diaerisis. (Note that in the conversion back to unicode, the canonical way to keep these distinct, so far, is the questionable hack https://unicode.org/faq/char_combmark.html#18 (but I don't think there will be a ton of converting carpogram back to unicode, honestly, given that carpogram is highly distinct in its concepts and much more wide-reaching)).

dele, krull, irony exclamation point. 

minus, hyphen, en dash, em dash, two-em dash, three-em dash, double hyphen (or perhaps n-hyphens should be achieved with --(over-combiner)

I would like to include emoji but it's hard to say how I could do that without breaking the bounds (which I am already stretching) of a "single-byte encoding".
