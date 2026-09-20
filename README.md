# Our Solar System

A single-page app about the solar system, made for a 6-year-old who is just
starting to read. Everything lives in `index.html`: no build step, no server,
no network, no images. Double-click the file and it runs.

## How to open it

Double-click `index.html`, or drag it onto a browser window. It works offline
and runs the same from a phone, a tablet or a laptop. To put it on a tablet,
copy the one file across, or host it anywhere that serves static files.

The app opens on a "Tap to start" screen. That tap is not decoration: browsers
refuse to start audio or the reading voice until a real finger asks for it, so
the first tap is what switches the sound on. You should hear a short welcome
line straight away, which also tells you the sound is working.

### If there is no sound on an iPhone or iPad

Three things silence it, in the order they usually bite:

1. **The silent switch.** iOS mutes web audio *and* the reading voice when the
   side switch is set to silent. Flick it off and turn the volume up. The app
   asks iOS to play through the switch where the system allows it, but the
   switch still wins on older versions.
2. **Previewing the file instead of opening it.** Tapping the file inside
   another app, such as a file preview, a mail attachment or a chat window,
   runs it in a restricted viewer that blocks audio. Open it in Safari itself:
   share the file to Safari, or host it and visit the address.
3. **Skipping the start tap.** If the start screen was dismissed without a real
   tap, sound stays locked. Reload the page and tap the button.

## The four screens

**Explore** shows the Sun with the planets orbiting around it, plus the asteroid
belt and Pluto out at the edge. Tapping anywhere near a planet opens its card:
the name in big letters, a pronunciation hint, three short facts, one "wow"
fact, its moons, its size and how hot or cold it is. Every fact is a button, so
he can sound out the sentence and then tap to hear it read back. "Read to me"
reads the whole card. Arrow buttons walk through all ten bodies in order.

**Line Up** puts the planets side by side at their true relative sizes and
scrolls sideways. Earth is a marble next to a Jupiter that runs off the screen,
and the Sun does not fit at all. The word under each planet is its place in
"My Very Excellent Mother Just Served Us Nachos."

**Find It!** says and shows "Find Mars!" and he taps it on the map. Eight
rounds. A right answer gets a chime and confetti; a wrong one wiggles and says
try again, and the answer starts glowing after two misses. Stars at the end
count how many he got on the first try. The "Aa" button hides the planet names
when you want it to be about the planets rather than the words.

**In Order** asks him to tap the planets in order out from the Sun. Wrong
answers just wiggle, so there is nothing to undo.

## Things that were built in on purpose

- **Reading first.** Every name and sentence can be spoken aloud, using the
  browser's own speech voice. The speaker button is the check, not a hint.
- **Forgiving taps.** Mercury is a few pixels wide on a phone, so a tap picks
  the nearest planet rather than needing a direct hit.
- **Big controls.** The bottom bar and all buttons are sized for small fingers.
- **Sound off.** One toggle in the corner silences speech and effects.
- **Sound that survives iOS.** The audio engine is unlocked inside the first
  tap, the page asks for a playback audio session so the ringer switch does not
  mute it, the context is resumed after the app returns from the background,
  and speech is never cancelled and restarted in the same instant, which is a
  combination iOS renders as silence.
- **Pause.** The orbits can be stopped. They also start stopped for anyone whose
  device asks for reduced motion.
- **Keyboard and screen readers.** Planets are focusable buttons with labels;
  arrow keys move between cards and Escape closes them.
- **No dependencies.** The planets are drawn with inline SVG gradients, the
  sound effects are generated in code, and the file is about 50 KB.

## About the facts

The wording is deliberately short and plain, and a few figures are rounded to
keep them sayable. Sizes and order are accurate. Moon counts change as new
moons are found, so Jupiter and Saturn are written as "95 or more" and "over
100" rather than exact numbers. Pluto is included and labeled a dwarf planet
throughout, including in the Line Up, where it sits apart from the eight
planets in the mnemonic.

Orbit spacing on the Explore screen is compressed so the whole system fits on a
screen. The order of the planets is right, but the gaps between them are not to
scale. Sizes in the Line Up screen are to scale.

## Editing it

All the text a grown-up might want to change is in one place: the `BODIES`
array near the top of the script, where each planet holds its name,
pronunciation, facts, wow fact, moons and size. Change a sentence there and it
updates the card, the speech and the games together.
