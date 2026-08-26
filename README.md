# Baby Keyboard

A colorful, interactive keyboard playground made for young children.

Press almost any key, click or tap the screen, and the page responds with sounds, letters, numbers, emojis, particles, colors, and surprise animations.

The entire application runs from a **single HTML file** with no backend, build process, account, or external dependency required.

## Features

### Interactive Keyboard

The playground reacts to letters, numbers, symbols, function keys, modifiers, and common keyboard controls.

Examples:

* **A-Z** display large colorful letters with matching emoji effects
* **0-9** display numbers with animated shapes
* **Space** launches a large confetti celebration
* **Enter** triggers a rainbow effect
* **Arrow Keys** send animated objects in different directions
* **Backspace** creates a disappearing "poof" effect
* **Shift / Ctrl / Alt / Tab / Caps Lock** trigger their own visual and sound effects
* **F1-F12** create star effects
* Symbols and other printable keys also react

## Touch and Mouse Support

Baby Keyboard is not limited to a physical keyboard.

Children can also:

* Click anywhere on the screen
* Tap on touchscreen devices
* Move a mouse or pointer around the playground
* Trigger colorful particles and sounds

The application uses Pointer Events so mouse, touch, and pen input can share the same interaction system.

## Built-In Sounds

All sounds are created directly in the browser using the **Web Audio API**.

There are no external MP3 or audio files.

Sound effects include:

* Xylophone-style notes
* Chimes
* Bubble pops
* Boing effects
* Sparkles
* Drum taps
* Short melodies
* Chords

The audio system also limits the number of simultaneous sounds to prevent excessive overlapping audio.

## Visual Effects

The playground includes a canvas-based particle system with effects such as:

* Confetti
* Stars
* Balloons
* Bubbles
* Hearts
* Animals
* Flowers
* Music notes
* Sparkles
* Animated letters
* Animated numbers
* Screen glow effects
* Rainbow sweeps
* Shooting stars

## Surprise Events

After a random number of interactions, Baby Keyboard can trigger larger surprise events.

These include:

* Rainbow Time
* Balloon Party
* Star Shower
* Bubble Party
* Happy Monster
* Music Party

This keeps the experience less repetitive and gives children something unexpected to discover.

## Combo Celebrations

Fast consecutive key presses build a combo.

Special messages appear at different milestones:

```text
5 inputs  -> WOW!
10 inputs -> SUPER!
20 inputs -> AMAZING!
```

The largest combo also launches a bigger celebration with confetti, rainbow effects, and music.

## Friendly Monster

One of the surprise events introduces a small animated purple monster that appears, waves, makes sounds, and disappears again.

The character is built completely with HTML and CSS.

## Parent Controls

A discreet settings button is available in the bottom-right corner.

To prevent accidental access, the gear button must be **held for approximately two seconds** before the parent panel opens.

Available controls include:

* Sound on/off
* Volume adjustment
* Animation intensity

  * Low
  * Normal
  * High
* Enter/exit fullscreen
* Reset playground
* Exit playground

## Animation Intensity

Parents can control how many particles are generated.

| Mode   | Particle Limit | Effect Level |
| ------ | -------------: | ------------ |
| Low    |            110 | Reduced      |
| Normal |            210 | Standard     |
| High   |            330 | Increased    |

This can also help when running the playground on lower-powered devices.

## Fullscreen Mode

Pressing **Start Playing** automatically attempts to enter fullscreen mode.

Fullscreen can also be controlled from the Parent Controls panel.

Browser security policies may require the user to approve fullscreen access.

## Reduced Motion Support

Baby Keyboard checks the operating system/browser setting:

```css
prefers-reduced-motion: reduce
```

When enabled, several animations are slowed down, simplified, or disabled to provide a less intense experience.

## Idle Mode

If there is no interaction for roughly 12 seconds, the playground enters an idle state.

During idle mode:

* Background objects move more gently
* Occasional shooting stars may appear
* No loud automatic interaction is required

The playground immediately wakes when the child interacts again.

## Technology

Baby Keyboard is intentionally simple.

It uses only:

* HTML5
* CSS3
* Vanilla JavaScript
* Canvas API
* Web Audio API
* Web Animations API
* Pointer Events
* Fullscreen API

There are:

* No frameworks
* No npm packages
* No build tools
* No external JavaScript libraries
* No backend
* No database
* No account system

## Project Structure

The complete project can be stored as:

```text
baby-keyboard/
│
├── index.html
└── README.md
```

All application HTML, CSS, JavaScript, audio generation, animations, and interaction logic are contained inside `index.html`.

## Running Locally

### Option 1: Open Directly

Clone or download the repository and open:

```text
index.html
```

in a modern browser.

### Option 2: Run a Local Server

If Python is installed:

```bash
python -m http.server 8000
```

Then visit:

```text
http://localhost:8000
```

### Clone from GitHub

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

Then open `index.html`.

## Deploying with GitHub Pages

Because Baby Keyboard is a completely static application, it can be hosted directly with GitHub Pages.

1. Push `index.html` to your GitHub repository.
2. Open the repository on GitHub.
3. Go to **Settings**.
4. Open **Pages**.
5. Under **Build and deployment**, select **Deploy from a branch**.
6. Select your main branch.
7. Select `/ (root)`.
8. Save.

GitHub will provide a public URL for the playground.

## Browser Support

A modern browser is recommended.

Examples:

* Google Chrome
* Microsoft Edge
* Mozilla Firefox
* Safari

For the complete experience, the browser should support:

* Web Audio API
* Canvas
* Web Animations API
* Pointer Events
* Fullscreen API

## Privacy

Baby Keyboard runs entirely inside the browser.

The current application does not require:

* User accounts
* Personal information
* Cookies
* Analytics
* Server communication
* Cloud storage

No keyboard interaction needs to be sent to a remote server for the playground to work.

## Performance

The particle system uses a reusable particle pool instead of continuously creating new particle objects.

The application also:

* Limits simultaneous sound voices
* Limits maximum particles
* Ignores excessive keyboard auto-repeat
* Throttles pointer movement effects
* Uses `requestAnimationFrame`
* Uses Web Animations for frequent animations
* Limits rendering device pixel ratio

These measures help keep the playground responsive during rapid keyboard input.

## Customization

Most of the application can be customized directly inside `index.html`.

### Change Colors

Edit the CSS variables near the top:

```css
:root {
  --sky1: #8ec5ff;
  --sky2: #c9a8ff;
  --sky3: #ffd6e8;
  --purple: #7c5cf0;
  --pink: #ff6b9d;
}
```

### Change Letter Effects

Letter-specific emoji and colors are configured in:

```javascript
const LETTER_DATA = {
  A: { emoji: '⭐', color: '#FFD166' },
  B: { emoji: '🫧', color: '#60A5FA' },
  // ...
};
```

### Change Sound Notes

The musical scale is configured with:

```javascript
const PENTATONIC = [
  261.63,
  293.66,
  329.63,
  392.00,
  440.00,
  523.25,
  587.33,
  659.25
];
```

### Change Surprise Frequency

Surprise events are controlled by the interaction counter and random threshold.

This can be adjusted in the JavaScript application state.

## Purpose

Baby Keyboard is designed as a simple cause-and-effect playground where children can press keys freely without needing to understand typing, menus, or traditional game controls.

The focus is on immediate feedback:

**Press → Sound → Color → Animation → Fun**

## Contributing

Contributions and improvements are welcome.

Possible future additions include:

* More visual themes
* More characters
* Additional sound sets
* Animal mode
* Alphabet learning mode
* Number learning mode
* Parent-selectable themes
* Custom sound packs
* Progressive Web App support
* Offline installation
* Additional accessibility settings

## License

This project is licensed under the MIT License.

See the [LICENSE](LICENSE) file for details.