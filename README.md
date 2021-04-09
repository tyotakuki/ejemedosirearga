# Purpose of This Project
The purpose of this project is to design a syllable-based input system for the Manju Hergen. The Manju Hergen syllables are traditionally called "uju", and is organized into 12 groups: a, ai, ar, an, ang, ak, as/aš, at, ao/au, al, am. These twelve syllable groups are usually how a traditional Manchu dictionary is organized.

Due to certain errors in the usual rendering of the Unicode standard, for example in OS X built-in font Noto Sans Mongolian, a pre-processed table of Manchu syllables with correctly inflected characters would solve some problems in character transformation.

I will use the Twelve Uju table made by Wanggiyan Sure available at [https://zhuanlan.zhihu.com/p/128547926](https://zhuanlan.zhihu.com/p/128547926). 

# Summary of Problems
The most intricate problem of the Unicode system and Unicode Manchu fonts is in the letters "t/d" and "k". The Noto Sans Mongolian rendering and the Unicode standard itself have created a huge problem for processing. The initial , medial and ending forms of these two letters do not correspond in the Unicode standard.

## Problem of the Unicode Standard
The biggest problem of the Unicode standard lies in the processing of "t/d" and "k". The initial form and medial form of "t/d" are essentially two different characters, and will be represented by "\*t/ \*d" and "t/d", respectively. Similarly, the medial and final form of "k" are two different characters, and will be denoted by "k" and "k\*", respectively.

### Medial and Final form of "k"
- Medial form of "k"
	- Masculine form as in most of the "ak, ok, uk, ik" and "tek" is U+1874 U+180B
	- Feminine form as in most of the "ek, vk" and "kuk, guk, huk, k'ak, g'ak, h'ak" is U+1874 U+180C
- Final form of "k\*"
	- Masculine form as in most of the "ak, ok, uk, ik" and "tek" is U+1874
	- Feminine form as in most of the "ek, vk" and "kuk, guk, huk, k'ak, g'ak, h'ak" is U+1874 U+180B

### Initial and Medial form of "t/d"
- Non-initial "t"
	- Non-initial masculine "ta, ti, to, tv" takes U+1832
	- Non-initial feminine "te, tu" takes U+1868, with "e" + U+180B, "u"+ U+180B to remove the dot for feminine vowels.
- Non-initial "d"
	- Non-initial masculine "da, de, do" takes U+1869 U+180B
	- Non-initial "dv" takes U+1868
	- Non-initial feminine "de, du" takes U+1869, with "e" + U+180B, "u"+ U+180B to remove the dot for feminine vowels.
- Initial "*t"
	- Initial masculine "*ta, *ti, *to, *tv" takes U+1868 U+180B (can also be U+1832)
	- Initial feminine "*te, *tu" takes U+1868, with "e" + U+180B, "u"+ U+180B to remove the dot for feminine vowels.
- Initial "*d"
	- Initial masculine "*da, *de, *do" takes U+1869
	- Initial "*dv" takes U+1868
	- Initial "*de, *du" takes U+1869 U+180B, with "e" + U+180B, "u"+ U+180B to remove the dot.

### an, at, ai-Uju
For convenience, "an, at, ai"-uju are treated separately in their non-final and final forms. The final forms are represented by "an*, at*, ai*" in our input system.

- The letter "i" as a syllable ending is U+1873 U+180C except in "iui, iung, iong" (affixed by U+180D in these cases).
- A final syllable ending "i*" takes U+1873.
- An "n" medial is ALWAYS the U+1828 U+180B.
- Final "n*" final usually takes U+1828, but should be allowed U+1828 U+180C as another choice like in the Chinese syllable "han" (to distinguish it from the Manchu word for "king, khan"). The same should also be allowed in "en*" which should display a dot on the left to distinguish it from "a".
- A "t" in the middle is ALWAYS U+1832 U+180C
- Final "t*" is simply U+1868.

### Other Special Cases
- "k'v, h'v" has the same shape with "kv, hv", but choose to not process it here.
- "fa, fe" uses the "f" initial, "wa, we" uses the "w" initial, and "fi, fo, fu, fv" uses the "f" initial with U+180B of a similar shape as "w".
- "iui, iung, iong" to transcribe Chinese do not have dots and do not show any repeating "i"'s.
- The "au/ao"-uju is a problem: in such a uju, the ending "o" is actually an "u" when pronunced, but do not display a dot on the right. However, for the purpose of completeness, we will require the user to type all "-u" endings as "-o", and will leave the choice of typing the "-u" ending with a dot to the user.

# The Input Standard

## Syllable Initials
The native syllable initials include the following letters:
> None, n, k/g/h, p/b, s/x, t/d, *t/*d (word-initial), l/m, c/j/y/r, f/w

They should be typed as-is in the input system.

The Chinese initials
> k'/g'/h', dz/ts', ž

should be typed as
> K/G/H, Z/C, R

in our input system.

## Vowels and Endings (Uju)
The six vowels are typed as "a, e, i, o, u, v" as in most transcription system.
The endings include:
> -(none), i, i*(final), r, n, n*(final), ng, k, k*(final), s, x, t, t*(final), b, u, o, l, m

"None" means the syllable is open, and the vowel should be followed with a dash "-"/

Other special characters include:
- Genitive "i" : iii
- k',g',h': K, G, H
- ts': C
- dz: Z
- ž: R
- c': Q
- j': J
- +y: Y
- Quotation marks: LQ, RQ
- FVS: FVS1, FVS2, FVS3
- ZWJ: ZWJ, ZWNJ.

## The Galik Alphabet for Sanskrit
![ali kali](https://github.com/tyotakuki/ejemedosirearga/blob/main/Screen%20Shot%202021-04-09%20at%202.43.15%20AM.png)


## Appendix: A Description of the Special Cases in the Wanggiyan Sure Table

### 1. a-uju
- "dv" does not have dot, and uses the female form "d".
- "k'v, h'v" has the same shape with "kv, hv".
- "fa, fe" uses the "f" initial, "wa, we" uses the "w" initial.
- "fi, fo, fu, fv" uses the "w" initial.

### 2. ai-uju
- "iui" should be considered as one ligature and should not have any dot.
- "dvi" does not have dot, and uses the female form "d".
- The medial form of "i" in "Vi" shows two sticks, but the final form does NOT.

### 3. ar-uju
- It is forbidden for "r" to appear in the initial form, thus one have to replace by "Vr" according to vowel harmony.
- "dvr" does not have dot, and uses the female form "d".
- "c'", "z'" and "r'" are defective, and can only be combined with "-ar, -er, -ur" in the Uju table.

### 4. an-uju
- "en" needs to show a dot on the left, and the "-n" in the final form swings to the right.
- A few words: "sain", "dain", "duin" and "ainci" are good examples to demonstrate the problem of "-in" after vowels.
- "dvn" does not have dot, and uses the female form "d".

### 5. ang-uju
- "-iung" should be considered as one ligature and should not have any dot.
- "dvng" does not have dot, and uses the female form "d".

### 6. ak-uju
- "-ak, -ok, -uk, -ik" take the male "-k" in general, however the "kuk, guk, huk, k'ak, g'ak, h'ak" take the female "-k".
- "-ek, -vk" take the female "-k" in general, however "tek" takes the male "-k".
- "dvk" does not have dot, and uses the female form "d".
- "c', z'" are defective, can only take "-ak, -ek, -ok, -uk".

### 7. as/ax-uju
- "dvs" does not have dot, and uses the female form "d".
- "c', z'" are defective, can only take "-as, -es, -os, -us" and "-ax, -ex, -ox, -ux".

### 8. at-uju
- "dvt" does not have dot, and uses the female form "d".
- "c', z'" are defective, can only take "-at, -et, -ot, -ut".
- a special rule: "-td-" should be pronounced as "-dd-".

### 9. ab-uju
- "dvb" does not have dot, and uses the female form "b".
- "c', z'" are defective, can only take "-ab, -eb, -ob, -ub".

### 10. au-uju
- "u" after any vowel has no dot. "Vu" and "Vo" have the same pronunciation and the same appearance.
- "dvu" does not have dot, and uses the female form "b".

### 11. al-uju
- "dvl" does not have dot, and uses the female form "b".
- "c', z'" are defective, can only take "-al, -el, -ol, -ul".

### 12. am-uju
- "dvm" does not have dot, and uses the female form "b".
- "c', z'" are defective, can only take "-am, -em, -om, -um".

### Syllable Seperator
- The syllable seperator should be used for any combinations of vowels except in "-Vu-, -Vo-, -Vi-, -iui-"
- "dv" and "tv" has the same appearance.




