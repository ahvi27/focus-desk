# Orbit Focus Desk

A responsive study dashboard that helps you organize tasks and focus on
one thing at a time.

Built with HTML, CSS, and JavaScript in a single file.

## Features

- 25-minute focus timer
- 5-minute break timer
- Start, pause, resume, and reset controls
- Add, complete, and delete tasks
- Task completion progress bar
- Browser storage for tasks and theme preference
- Light and dark themes
- Responsive mobile and desktop layouts
- Labeled controls and visible keyboard focus
- No dependencies, accounts, or API keys

## Getting Started

1. Download or clone this repository.
2. Open `index.html` in a modern browser.
3. Add your tasks and start a focus session.

For consistent browser storage behavior, serve the folder locally:

```bash
python3 -m http.server 8000
```

Then visit:

http://localhost:8000

## Project Structure

```text
orbit-focus-desk/
├── index.html
└── README.md
```

## How to Use

1. Add a task using the input field.
2. Select Focus or Break.
3. Start the timer.
4. Pause or reset whenever needed.
5. Check off completed tasks to update your progress.
6. Use the theme button to switch appearances.

## Data Storage

Tasks and your theme preference are stored in your browser using
`localStorage`.

Data is specific to your browser and website address. It does not sync
between devices. Clearing site data removes saved tasks.

If browser storage is unavailable, you can still use tasks during the
current page session.

## Timer Behavior

The timer uses a target timestamp to reduce drift when the tab is
temporarily inactive. The display updates when the browser runs the
page again.

Timer sessions are not saved after a page reload. There are no sound
alerts or system notifications.

## Technologies

- Semantic HTML
- CSS Grid and Flexbox
- CSS custom properties
- Vanilla JavaScript
- Browser localStorage API

## Customization

Edit the CSS variables in `:root` to change the dark theme and
`body.light` to change the light theme.

Edit the `durations` object in the JavaScript to change timer lengths.
Values are measured in seconds.

```javascript
const durations = {
  focus: 25 * 60,
  break: 5 * 60
};
```

## Deploy with GitHub Pages

1. Upload `index.html` and `README.md` to your repository.
2. Open the repository's Settings → Pages.
3. Choose deployment from a branch.
4. Select your main branch and the root folder.
5. Save and use the URL GitHub provides.

## Future Ideas

- Custom timer durations
- Task categories
- Task export and import
- Focus session history
- Optional completion sounds
