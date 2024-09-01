# Keyboard Kits

- [Keyboard Kits](#keyboard-kits)
  - [Firmware Support](#firmware-support)
    - [Claims for QMK/VIA support with Wireless](#claims-for-qmkvia-support-with-wireless)
  - [Switch orientation](#switch-orientation)
  - [Hotswap support](#hotswap-support)
  - [Mounts](#mounts)
  - [Boards We Have Feelings About](#boards-we-have-feelings-about)
    - [Any Optical Board](#any-optical-board)
    - [Some Skyloong Optical Kit (SK6\*/GK6\*, SK87, etc.)](#some-skyloong-optical-kit-sk6gk6-sk87-etc)
    - [Some Skyloong Mechanical Kit (GK6\*X, GK87, etc)](#some-skyloong-mechanical-kit-gk6x-gk87-etc)
    - [TM680 (Wired)](#tm680-wired)
      - [LK67](#lk67)
    - [Royal Kludge Boards](#royal-kludge-boards)
    - [Tofu60 case](#tofu60-case)
    - [DZ6\* (DZ60, DZ65) PCBs](#dz6-dz60-dz65-pcbs)
  - [PCB/Case compatability](#pcbcase-compatability)

## Firmware Support

Being able to reprogram your keyboard with your preferred key layout or fun features is one of the significant benefits of having a fancier keyboard. If programming custom key layouts or macros is something you're interested in, then this is something you may want to note.

- Worst: No software - what you see is what you get!
- Kinda Bad: China software
  - No idea if you’ve installed a rootkit or not. (You probably haven’t, but still).
  - Poorly documented, only occasionally translated to English, and sometimes impenetrable.
- Not Ideal: Proprietary Software that you need to keep installed.
  - Often not easy to understand or use, confusing, and bloatware.
- Acceptable: Non-mainlined QMK support
  - Some PCBs will advertise that they run QMK/VIA, but they haven’t had their firmware merged to [their Git](https://github.com/qmk/qmk_firmware/tree/master/keyboards) yet; these only will ship some .hex/.bin file to be flashed with QMK Toolbox/equivalent command line tool.
  - Likewise, if the layout JSON hasn’t been merged to the-via yet, then you will need to take the .json layout file that the vendor provides, and side-load that into VIA Configurator. It’s one more step, it’s not the worst thing in the world..
- Best: Out-of-the-box QMK + VIA/VIAL support
  - You can compile it! You can adjust your keymaps and flash! You can enable features not included in the shipped firmware or binary! Wow!

### Claims for QMK/VIA support with Wireless

For the known future, there are no wireless chips that provide a firmware support stack whose licenses are compatible with QMK, which is licensed under GPL. For this reason, the QMK maintainers refuse to merge support for boards that run QMK on one MCU and offload wireless connections to a separate chip. The downstream effect of this is that
* the source code for your keyboard's firmware is probably not going to be easily findable
  * this means you won't be able to get any reasonable support for updates or firmware modification outside of what VIA provides
* the keyboard layout JSON will not be merged into VIA
  * (with the exception of Keychrons because their users are... well... you know...)
* which means you'll be forced to side-load the layout JSON into VIA, which means you have to find the JSON on your own. If that file's in a private discord server, or a website that will go down in a couple of years after the vendor moves on, you may be SOL.
* the battery life of these boards is awful in comparison to something that is only powered by a single chip, like an NRF, and thus requires a massive battery to power them for longer than a single digit number of hours.

## Switch orientation

Look, most of these cheaper kits you’ll find on Amazon, AliExpress, or BangGood are going to have north-facing switches, which will slightly limit the set of keycaps you can use on your keyboard. (For more information, message !northfacing within the help channel in mechkeys)
Budget keyboard kits that are easily available having south facing switches are more of an exception to the rule than the rule itself, but you can still find them with a bit of looking around.

## Hotswap support

issey83 provides a very good video about how hotswap sockets hold up over repeated swaps [here](https://www.youtube.com/watch?v=HFJmuj31Ayg).

- Kailh hotswap is reasonably good hotswap that can arrive in a prebuilt, and it supports most-all Cherry MX clone switches.
- Quality of TTC hotswap is solid and pins remain tight.
- Gateron hotswap provides similar compatibility (most to all Cherry MX clone type switches) as the above two.
  I'm not sure if it's a population bias thing or not, but the leaves on these seem to get weaker faster than
  Kailh. Fix them by jamming in tweezers if you can.
- CIY hotswap is known to have fairly weak contact leaves, to the point where a CIY hotswap socket can hardly retain a switch by the pins like the above hotswap sockets can.
- Outemu rivet hotswap is installed onto PCB’s cheaply and easily, but compatibility is much more limited than with Kailh/Gateron/TTC/CIY style sockets. This sort of hotswap is found only on prebuilts.
  - Compatability for other Outemu switches and KTT (includes Akko CS) is known.
  - Huano stuff like Feker Pandas have mixed reports on support.
  - Outemu has a new hotswap socket comaprable to the Kailh style of offering, but I have yet to see any boards with them soldered on.

## Mounts

Milo has provided a wisely worded guide to understanding the different keyboard mount styles (the way in which
the plate and pcb is fixed to the case) affect typing feel and sound
[here](https://docs.google.com/document/d/1G-UZOmY3ZdEM288UN3sB-tz9oRRZOTPfjtdnokDO1Nw/edit), but if you are too
lazy to read that, I have a much cruder run-down below.

| Mount | Review |
| - | - |
| Top | Feels even, sounds clean, and has a bit more give than stiffer mounts like sandwich/integrated/tray. |
| Bottom | Much like top, only may sound a little like bones. |
| Gasket | Not always as soft/flexy-wexy as you think, but generally has the most give of all. Popular, people-pleaser, too many keyboard sellers cancel out any flex by pairing with a foam lasagna. |
| Tray | Usually found in the cheapest of boards. No give, and sound can be very uneven. |
| Sandwich | Even and stiff, but can feel like typing into a wall. Not the worst thing in the world. |
| Integrated | Cheap to make. Tends to sound hollow and pingy in most implementation. Consider force breaking. |

Jamming foam into your keyboard stiffens the feel, and so on.

## Boards We Have Feelings About

### Any Optical Board

Most of these are not great. Optical boards only work with optical switches. Even if yours are hotswap, you cannot use mechanical switch bottoms, your options for tactile leaves are zero-to-limited, and actuation distance will be weird if you stem swap; you’re shooting yourself in the foot if you want to upgrade your switches. The sensors for optical keys sometimes just don’t work or break, and don’t always take to lube great (don’t lube your stem poles, please). And most importantly, optical switches won’t make you play games better. A laser does not improve latency. Your performance as a gamer will not improve.

### Some Skyloong Optical Kit (SK6*/GK6*, SK87, etc.)

Even if they say that they are hotswap, you cannot put mechanical keyboard (Cherry MX/Cherry MX Clone) switches into these; these boards take only (generally Gateron) optical switches.
A mechanical switch keyboard PCB does not take optical switches.
An optical switch keyboard PCB does not take mechanical switches.

### Some Skyloong Mechanical Kit (GK6*X, GK87, etc)

USB port likes to lift off a little too easily. Software sucks to use, not documented very well, is not reprogrammable without it actively running, mediocre build quality. Beyond that, if you pick up one of these, you'll live.

### TM680 (Wired)

Don’t. I’m telling you now, don’t. I know you love the knob. The QC on the PCB is known to be significantly poor, and so your PCB may have individual keys’ RGB die, individual switches die, or the PCB may stop working outright.

#### LK67

The case may be the same, but the PCB may be designed by someone more competent this time. Hard to say. Purchase cautiously.

### Royal Kludge Boards

RK61 PCB is somewhat wonky. Software doesn’t find it all the time. A handful of users have come into the help channel in the past to figure out why their PCB doesn’t work (switch doesn’t work, won’t connect to software, computer fails to detect keyboard), more than DZ60 users who just need to be reminded to reset the EEPROM on their board.

RK61 and RK68 PCB have RGB LEDs mounted on the surface only accept SMD-compatible switches - this means that if your switch bottom housing doesn’t have a cutout for a PCB-mount LED, it will not sit flush - this means no JWK switches, only Gateron KS-9’s, only Cherry MX RGB switches, etc.
RKG68, RK84,and presumably RK100 do not suffer from this issue with RGB LED’s that are flush with the PCB instead. Words of warning to uneven QC.

### Tofu60 case

Mediocre sound with stiff and somewhat inconsistent feel (from the tray mount), but it’s close to the cheapest aluminum case you can get. If you have access to Aliexpress, PSD60 provides identical GH60 tray mount points for cheaper. If you are based within the US, consider a Baka60 from Paramountkeeb.

### DZ6* (DZ60, DZ65) PCBs

Some people say these boards break easily. Honestly, I think most of the time they just need their EEPROM reset.

## PCB/Case compatability

TODO: Fill this out
