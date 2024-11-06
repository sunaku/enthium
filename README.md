# Enthium - Engrammer meets Hands Down Promethium

This adaptation of the [Engrammer] and [Hands Down Promethium] keyboard layouts
improves on the latter's performance in keyboard layout analyzers (see below)
by mirroring it horizontally to restore familiarity with [Arno's Engram 2.0]
layout (CIEA on left hand's home row; PF is swapped with WV to be like Engram)
and the [Dvorak] layout (HTNS on right hand's home row), and by optimizing the
placement of punctuation for programming in the spirit of the Engrammer layout.

[Hands Down Promethium]: https://reddit.com/r/KeyboardLayouts/comments/1g66ivi
[Arno's Engram 2.0]:     https://engram.dev
[Engrammer]:             https://github.com/sunaku/engrammer
[Dvorak]:                https://www.dvzine.org

## Layout

      b y o u / x l d w v
    q c i e a , k h t n s z
      ' - = . ; j m g p f
                r

## Rationale

* Q and Z are split apart onto different hands for balance and symmetry.

* Apostrophe is away (on a different finger entirely) from YOU and I so
  it can be typed without same-finger bigrams such as `you'd` and `I'd`.

* Slash is near 1 for affinity between their shifted symbols `?` and `!`.

* Cluster minus and equals for intuitive zoom in/out shortcuts with Ctrl.

* Cluster comma and semicolon for prev/next jumping in Vim for f/F/t/T.

* Although period and comma are backwards in the sense of their shifted
  symbols `>` and `<`, their arrangement reduces lateral stretch bigrams
  and also clusters `>` with minus and equals for `->` and `=>` arrows.

### Deviation: PF and WV

PF is swapped with WV in order to address the following inconveniences:

* WN is a stair-step ascension same-finger bigram that I wished I could rake down instead
* DW (2u skip) is not as convenient for Vim as it was in Engram (which puts them adjacent)
* FG (2u skip) is not as convenient for shell background jobs (`bg`, `fg`) as it was in Engram
* SW (half scissor) feels a little bit weaker curling inward than reaching up (as in Engram)
* FF (e.g. "stu*ff*") is a little bit of a chore for the pinky finger to tap twice in the upper row

I really didn't want to deviate from the canonical Hands Down Promethium layout
(this "Enthium" derivative was just supposed to be a simple horizontal mirror,
plus some rearranged punctuation marks) so I reluctantly went to the keyboard
layout analyzer playgrounds to see how bad it would be to swap PF with WV... and
to my complete surprise, this change hardly affected the layout's performance:

* Oxey's analyzer showed no changes at all in the stats!
* KeySolve analyzer showed an increase in FSB from 0.14% to 0.37% but the other
  stats improved: FSS reduced from 0.82% to 0.48%, HSB reduced from 6.05% to
  5.64%, and HSS reduced from 5.97% to 5.50%; everything else was identical.
* Cyanophage analyzer's Total Word Effort increased from 730.9 to 735.9 but all
  other stats remained the same!

I'm _so glad_ this experiment worked out because it makes the layout a lot more
comfortable for me in practice and it would also further reduce the barrier to
entry for others seeking to switch over to Enthium from the Engrammer layout. :)

## Performance

### [Cyanophage analyzer](https://cyanophage.github.io/playground.html)

![Screenshot](analyzer/cyanophage.png)

Playground link:
> https://cyanophage.github.io/playground.html?layout=vwdlx%2Fuoyb%5Csnthk%2Caeicqfpgmj%3B.%3D-%27zr&mode=ergo&lan=english

Overall stats:
* Total Word Effort: 735.9
* Effort:            398.47

Finger usage:
* Same Finger Bigrams: 0.55%
* Skip Bigrams (2u):   0.30%
* Lat Stretch Bigrams: 0.20%
* Pinky/Ring Scissors: 0.49%

Trigram stats:
* alt:             37.47%
* bigram roll in:  28.99%
* bigram roll out: 14.71%
* other:           9.07%
* alt sfs:         5.08%
* redirect:        1.94%
* roll in:         1.36%
* weak redirect:   1.24%
* roll out:        0.13%

### [KeySolve analyzer](https://clemenpine.github.io/keysolve-web/)

![Screenshot](analyzer/keysolve1.png)
![Screenshot](analyzer/keysolve2.png)
![Screenshot](analyzer/keysolve3.png)

Overall stats:

    BIGRAMS     SFB: 0.83%      LSB: 0.41%      HSB: 5.62%      FSB: 0.37%
    SKIPGRAMS   SFS: 6.56%      LSS: 0.85%      HSS: 5.47%      FSS: 0.48%
    TRIGRAMS    ALT: 40.37%     ROL: 41.16%     ONE: 2.70%      RED: 1.90%

Finger usage:

    LEFT        LI: 13.77%      LM: 20.17%      LR: 8.84%       LP: 4.40%
    RIGHT       RI: 13.12%      RM: 14.59%      RR: 10.60%      RP: 8.95%
    TOTAL               LH: 47.18%                      RH: 52.82%

Custom source for copy/paste:

    b y o u / x l d w v
    c i e a , k h t n s
    ' - = . ; j m g p f
    r q z

### [Oxey's analyzer](https://oxey.dev/playground/index.html)

![Screenshot](analyzer/oxey.png)

Overall stats:
* Sfb:              0.829%
* Dsfb:             6.529%
* Lsb:              0.319%
* Inrolls:          29.137%
* Outrolls:         14.679%
* Total Rolls:      43.816%
* Onehands:         2.206%
* Alternates:       34.215%
* Alternates (sfs): 8.044%
* Total Alternates: 42.259%
* Redirects:        2.107%
* BadRedirects:     1.243%
* Total Redirects:  3.350%
* Other:            8.369%
* Invalid:          0.001%

Finger usage:

    finger 0:   5.02%   finger 9:       9.56%
    finger 1:   9.25%   finger 8:       10.65%
    finger 2:   19.30%  finger 7:       14.56%
    finger 3:   13.11%  finger 6:       12.33%

    Left hand:   46.68% Right hand:     47.10%
    Left center: 1.211% Right center:   1.189%

    Home keys usage: 56.37%

Sfb% per finger:

    finger 0:   0.021%  finger 9:       0.028%
    finger 1:   0.071%  finger 8:       0.100%
    finger 2:   0.122%  finger 7:       0.051%
    finger 3:   0.322%  finger 6:       0.114%

## Installation

### Linux setup

Install:

    cd linux/
    sudo make install
    echo Now restart your graphical session.

Activate:

    setxkbmap -layout us    -variant enthium         # one layout; no switch
    setxkbmap -layout us,us -variant enthium,basic   # dual layout switching

Repair (e.g. whenever a system-wide XKB package upgrade reverts installation):

    cd linux/
    sudo make reinstall
    echo Now restart your graphical session.

Uninstall:

    cd linux/
    sudo make uninstall
    echo Now restart your graphical session.

## License

Released under the same terms as [Arno's Engram 2.0] keyboard layout's sources:

> MIT License
>
> Copyright 2022 Ricard Figueroa <https://github.com/rfiga>  
> Copyright 2021 Suraj Kurapati <https://github.com/sunaku>  
> Copyright 2021 Arno Klein <https://github.com/binarybottle>  
>
> Permission is hereby granted, free of charge, to any person obtaining a copy
> of this software and associated documentation files (the "Software"), to deal
> in the Software without restriction, including without limitation the rights
> to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
> copies of the Software, and to permit persons to whom the Software is
> furnished to do so, subject to the following conditions:
>
> The above copyright notice and this permission notice shall be included in
> all copies or substantial portions of the Software.
>
> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
> IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
> FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
> AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
> LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
> OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
> SOFTWARE.

---------------------------------------------------------------------------
[Spare A Life]: https://sunaku.github.io/vegan-for-life.html
> Like my work? 👍 Please [spare a life] today as thanks! 🐄🐖🐑🐔🐣🐟✨🙊✌  
> Why? For 💕 ethics, the 🌎 environment, and 💪 health; see link above. 🙇
