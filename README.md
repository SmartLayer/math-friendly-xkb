# Math-Friendly XKB

Welcome to the `math-friendly-xkb` repository. This project offers a customized version of the "English (intl., with AltGr dead keys)" keyboard layout for Linux users. The layout is optimized for typing mathematical symbols and expressions without compromising the original layout's capabilities[^microsoft]. It's designed as a diff file against the `/usr/share/X11/xkb/symbols/us` file that comes with Ubuntu, replacing the "English (intl., with AltGr dead keys)" layout directly. The repository is updated with every Ubuntu LTS release.

You can find the latest diff file as ubuntu-22.04.diff (for Ubuntu 22.04).

[^microsoft]: The "English (intl., with AltGr dead keys)" layout, originally developed by Microsoft, enables typing in virtually any Latin-based script. It is specifically optimized for Spanish and French, designed to minimize the use of dead keys. Only a few words, such as "bilingüe" (bilingual in Spanish), require the use of dead keys. 

## Features

This is a seven-level keyboard, meaning that each key on the keyboard can produce up to seven symbols.

These symbols are organized into 4 columns. The first column of symbols is generated by either directly pressing the key or using the Shift modifier. The second column is accessed by holding the AltGr key, or AltGr in combination with Shift. The third column is produced by holding the Super key (commonly the Windows key on most keyboards) or using Super in conjunction with Shift. The last column is produced by holding the Super Key in conjuction wiht AltGr key. These are superscript A-Z symbols. There is no key defined for the 8th level, that is Super, AltGr and Shift combined.

````
///
// ┌────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┲━━━━━━━━┓
// │ ~~ │ !⁄⁽ │ @²⁾ │ #³³ │ $฿⁴ │ %¸⁵ │ ^¼⁶ │ 7½⁷ │ 8¾⁸ │ 9˘⁹ │ |°⁰ │ _ ̣ª │ =÷⁺ ┃Back    ┃
// │ `` │ 1¡₁ │ 2˝₂ │ 3¯₃ │ 4€₄ │ 5°₅ │ 6^₆ │ 7 ̛₇ │ 8˛₈ │ 9‘₉ │ 0’₀ │ -¥º │ +×₌ ┃space⌫  ┃
// ┢━━━━┷━━┱──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┺━━┳━━━━━┫
// ┃Tab    ┃ QÄ𝑄 │ WÅ𝑊 │ EÉ𝐸 │ RË𝑅 │ TÞ𝑇 │ YÜ𝑌 │ UÚ𝑈 │ IÍ𝐼 │ OÓ𝑂 │ PÓ𝑂 │ [“⁽ │ ]”⁾ ┃ |‡№ ┃
// ┃ ↹     ┃ qä𝑞𐞥│ wå𝑤ʷ│ eé𝑒ᵉ│ rë𝑟ʳ│ tτ𝑡ᵗ│ yü𝑦ʸ│ uú𝑢ᵘ│ ií𝑖ⁱ│ oó𝑜ᵒ│ pö𝑜ᵖ│ («₍ │ )»₎ ┃ \†‖ ┃
// ┣━━━━━━━┻━━┱──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┬──┴──┲━━┻━━━━━┫
// ┃Caps      ┃ AÁ𝐴 │ S§𝑆 │ DÐ𝐷 │ FƑ𝐹 │ GG𝐺 │ HH𝐻 │ JÏ𝐽 │ KŒ𝐾 │ LØ𝐿 │ :꞉  │ "¨  ┃ ⏎      ┃
// ┃Lock  ⇬   ┃ aá𝑎ᵃ│ sß𝑠ˢ│ dð𝑑ᵈ│ fƒ𝑓ᶠ│ gg𝑔ᵍ│ hhℎʰ│ jï𝑗ʲ│ kœ𝑘ᵏ│ lø𝑙ˡ│ ;¶  │ '´  ┃ Enter  ┃
// ┣━━━━━━━━━━┻━┱───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┲━━━┻━━━━━━━━┫
// ┃Shift       ┃ ZÆ𝑍 │ XΞ𝑋 │ C¢𝐶 │ Vɑ𝑉 │ BΒ𝐵 │ NÑ𝑁 │ Mµ𝑀 │ <Ç  │ >ˇ… │ ? ̉╱ ┃Shift       ┃
// ┃ ⇧          ┃ zæ𝑧ᶻ│ xξ𝑥ˣ│ c©𝑐ᶜ│ vα𝑣ᵛ│ bβ𝑏ᵇ│ nñ𝑛ⁿ│ mµ𝑚ᵐ│ ,ç  │ .˙· │ /¿⧸ ┃ ⇧          ┃
// ┣━━━━━━━┳━━━━┻━━┳━━┷━━━━┱┴─────┴─────┴─────┴─────┴─────┴────┲┷━━━━┳┷━━━━┳┻━━━━━┳━━━━━━┫
// ┃Ctrl   ┃ Super ┃Alt    ┃ ␣ Space            Nobreakspace ⍽ ┃AltGr┃ Fn  ┃ Ctxt ┃ Ctrl ┃
// ┃       ┃       ┃       ┃ ␣ Space            Nobreakspace ⍽ ┃     ┃     ┃ Menu ┃      ┃
// ┗━━━━━━━┻━━━━━━━┻━━━━━━━┹───────────────────────────────────┺━━━━━┻━━━━━┻━━━━━━┻━━━━━━┛

````

The `math-friendly-xkb` introduces several enhancements beyond the original "English (intl., with AltGr dead keys)" layout it was based on:

- **Currencies**. The 'currency' symbol has been replaced with the Euro Sign (€). Use `<alt> + <4>` to type this symbol.  The Bitcoin symbol (₿) can be typed using `<alt> + <shift> + <4>`.
- **Greek Letters**: The layout includes α and ξ, two frequently used Greek letters in mathematics. Future updates may include additional Greek letters based on usage frequency.
- **Italic Letters**: A `<super>` key level has been added for every letter in the English alphabet, producing an Italic variant in Unicode often used in mathematical expressions, such as 𝑛.
- **Subscript Digits**: A `<super>` key level has been added for every digit, producing a subscript digit. This feature may be removed in the future due to infrequent use.
- **Superscript Numbers and Operators**: A `<shift> + <super>` level has been added for superscript numbers and arithmetic operators. For example, `<shift> + <super> + <4>` gives you ⁴. This feature is also less used than anticipated.
- **Superscript Letters**: A `<shift> + <super>` level has been added for every letter in the English alphabet except q, which lacks a superscript codepoint in Unicode.
- **A Lot of Slashes**: Division slash (∕) and fraction slash (⁄) symbols have been added.
- **Note Symbols**: The first four traditional order of [note symbols](https://en.wikipedia.org/wiki/Note_(typography)) in English have been added. The traditional order of these symbols in English is [*](https://en.wikipedia.org/wiki/Asterisk), [†](https://en.wikipedia.org/wiki/Dagger_(typography)), [‡](https://en.wikipedia.org/wiki/Double_dagger_(typography)), [§](https://en.wikipedia.org/wiki/Section_sign), [‖](https://en.wikipedia.org/wiki/Vertical_Bar), [¶](https://en.wikipedia.org/wiki/Pilcrow). The first exists on standard keyboards, the section sign § and the pilcrow sign ¶ existed in "English (intl., with AltGr dead keys)", this project piles the rest 3 symbols on the backslash key.
- **Numero symbol and cardinal signs**: These are frequently used in Europe.

## Additional Configuration for Small Keyboards

### 1. Swap ESC key and the tile key with `swap_esc_tlde.diff` ###

For keyboards with a limited number of keys (63 keys), where the upper-left key is often assigned to ESC instead of tilde, you may prefer to have the tilde key for its use in vim and command line operations. To change the ESC key to a tilde, add the following to the section "English (intl., with AltGr dead keys)":

```bash
key <ESC> { [    grave, asciitilde,  dead_grave,   dead_tilde, Escape ] };
```

This layout is designed to enhance the typing experience for users frequently working with mathematical symbols and expressions. Your feedback and suggestions for improvement are always welcome.

### 2. Use the CAPS key as ISO_Level5_Shift with `swap_caps_level5_shift.diff`

In this project, we remapped LWIN key (Left Windows) to ISO_Level5_Shift. If your keyboard lacks a WIN key,  you can repurpose the CAPS key to serve as `ISO_Level5_Shift` using a feature called tap-hold pattern, which means a key function differently when it is tapped then when it is held in combination of another key. You can do so through 2 simple steps, 

1. **Remap the CAPS Key**: Add the following to `/usr/share/X11/xkb/symbols/us`:
   ```
   // Map CAPS to ISO_Level5_Shift and let someone else play Caps_Lock
   key <CAPS> { [ ISO_Level5_Shift ] };
   key <RWIN> { [ Caps_Lock ] };
   ```

2. **Restore Caps_Lock Function**: Execute the command:
   
   ```
   xcape -e 'ISO_Level5_Shift=Caps_Lock' -t 100
   ```
   in your session manager to revert the `Caps_Lock` function to the CAPS key. You might want to play with the timeout value to find the best number for you.
   

**Special Case: Retaining `SUPER_L` Function**
If you have a Windows key and wish to keep its `SUPER_L` function, remove or comment out the `include "level5(lwin_switch_lock)"` line from the keyboard layout configuration. This line repurposes the Windows key's function.

**Can this be done with a programmable keyboard?**
Instead of mapping LWIN as ISO_Level5_Shift, you might consider program a keyboard to use a special key to do it.

In the file `/usr/share/X11/xkb/keycodes/evdev` on many Linux distributions, you'll find the following mapping:

```   
<LVL5> =   203;
```

This means that keycode 203 corresponds to the LVL5 key in X11. Due to an established offset of +8 between X11 keycodes and Linux driver keycodes (historically set at this value), the actual keycode transmitted by the Linux driver for the LVL5 key would be 195 (`203 - 8`). 

However, I haven't personally tested this approach since I'm not familiar with keyboard firmware programming frameworks like QMK/VIA, and I suspect if it would work, since key 195 is not defined in `linux/include/uapi/linux/input-event-codes.h` at all. It appears no existing keyboard has LVL5 keys, or even if it does the Linux kernel may not recognize an event when it is pressed as USB HID keycode 195 is undefined.

If your keyboard firmware supports a tap-and-hold feature natively, you could program the CAPSLOCK key such that when held, it sends the Linux driver keycode 195. With luck, this may be interpreted by X11 as holding down the LVL5 key. 

## Known Issues

While the `math-friendly-xkb` layout aims to enhance the typing experience, there are a few known issues and areas for potential improvement:

- **Superscript Minus**: Currently, there is no superscript minus symbol, because muscular and feminine cardinal is where you would expect superscript minus. This is rarely an issue as superscripts are often used for elliptic curve math, which primarily involves addition.
- **Trademark and Registered Symbols**: There are currently no mappings for the 'trademark' or 'registered' symbols. One potential solution is to use `alt+shift+'1'` for the trademark symbol and `alt+shift+'2'` for the registered symbol, as there are two ways to produce superscript brackets.
- **Degree Sign**: There are 2 ways to produce the degree sign (°). Alt+shift+0 typed twice is sufficient for this symbol, so the one on number key 5 is not really needed. This is inherited from "English (intl., with AltGr dead keys)" layout.
- **Unused Alt Key Combinations**: The combinations `alt+g`, `alt+shift+g`, `alt+h`, `alt+shift+h`, and `alt+m` and `alt+shift+m` currently do not produce any special symbols.

These issues are minor and do not significantly impact the overall functionality of the layout. However, they will be considered for future updates and improvements.

## It's a feature, not a bug

- Superscript O **ᵒ**, and superscript A **ᵃ** can be used for muscular and feminine cardinal **º** and **ª**, so having all of them on a keyboard layout is appears overdsigned. However, often cardinal numbers have underscores in certain fonts, they are visually not replaceable for each other. People who speaks Spanish or Portuguese can tell.
- Usually capital N followed by muscular cardinal º, when typed together like this Nº, suffices as a substitute of Numero sign №. We kept both anyway because the Numero Sign is special.
- The Latin Alpha (ɑ) and Copyright (©) symbols have not seen much real life uses. Pity.
- The combination `super+shift+'q'` produces nothing, because there is no Unicode code point for superscript q, it just doesn't exist. Also, nothing happens with `super` plus period or comma.

## Helpful hint

To get the Unicode point of a character, use this command:
````
echo -n "𐞥" | iconv -f utf8 -t UTF-32 | hexdump -e '/2 "U+%04X\n"'
U+FEFF
U+0000
U+07A5
U+0001
````
This shows that 𐞥 is U107A5.
