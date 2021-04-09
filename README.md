# ejemedosirearga
manju hergen-i ejeme dosire arga, RIME based
Juwan-Juwe Uju-based Input System

# Input Method:
Manchu word should be segmented into syllables (uju):
- "a uju" is of the form Ca, should use Ca- to input.
- "at, an, ak, ai uju" has a non-final form and a final form. On a final form, one should append a "*".
- "t/d" + vowel has an initial form and a non-initial form. On an initial form, one should prepend a "*".
- Ali Kali is described separately.

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

![ali kali](https://github.com/tyotakuki/ejemedosirearga/blob/main/Screen%20Shot%202021-04-09%20at%202.43.15%20AM.png)

# Exceptional Cases from the Twelve Uju

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

### Unicode Genetive "i"
U+202F U+1873
U+200D U+1873

{"ᡨ᠋ᠠ", "ᡨᡝ᠋", "ᡨ᠋ᡳ", "ᡨ᠋ᠣ", "ᡨᡠ᠋", "ᡨ᠋ᡡ", "ᡩᠠ", "ᡩ᠋ᡝ᠋", "ᡩᡳ", "ᡩᠣ", \
"ᡩ᠋ᡠ᠋", "ᡨᡡ"}
