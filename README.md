# Orbit Focus Desk

A responsive productivity dashboard for study sessions, personal tasks,
and steady progress.

Built with HTML, CSS, and vanilla JavaScript in one self-contained file.

## Features

### Focus Timer

- Default 25-minute focus sessions
- Default 5-minute breaks
- Custom durations from 1 to 180 minutes
- Separate saved durations for focus and break modes
- Start, pause, resume, and reset controls
- Remaining time displayed in the browser tab while running
- Saved all-time completed focus-session counter

### Task Management

- Add tasks with normal or high priority
- Mark tasks complete
- Delete individual tasks
- Search tasks by text
- Filter by active, completed, or high-priority tasks
- Clear completed tasks after confirmation
- View completion progress and task statistics

### Backups

- Export tasks as a JSON file
- Import a previously exported task backup
- Validate imported task data
- Confirm before replacing existing tasks

### Interface

- Light and dark themes
- Responsive layouts for mobile and desktop
- Localized date display
- Labeled inputs and visible keyboard focus
- Browser storage for tasks, settings, and session counts
- Automatic migration of valid tasks from the original Orbit version

## Project Structure

```text
orbit-focus-desk/
├── index.html
└── README.md
```

## Run Locally

Download this repository and open `index.html` in a modern browser.

For consistent browser storage behavior, serve the project locally:

```bash
python3 -m http.server 8000
```

Open:

http://localhost:8000

No installation or build process is required.

## Usage

1. Add a task and select its priority.
2. Choose Focus or Break.
3. Optionally change the session length and select Apply.
4. Start the timer.
5. Check off tasks as you finish them.
6. Use search and filters to find tasks.
7. Export your tasks periodically to keep a backup.

Applying a new duration, switching timer modes, or selecting Reset
discards the current timer's progress.

## Focus Session Counter

The session counter increases when a focus timer reaches zero.

Break timers and manually reset sessions do not increase the counter.

The counter is cumulative across visits in the same browser and website
address. It is not a daily statistic.

## Task Import and Export

Select Export tasks to download `orbit-tasks.json`.

Select Import tasks and choose an Orbit backup to restore tasks.

Import replaces the current task list after confirmation. Export your
existing tasks first if you want to keep them.

Import limits:

- Maximum file size: 2 MB
- Maximum number of tasks: 5,000
- Maximum task text length: 160 characters

Backups contain tasks only. They do not include theme settings, timer
durations, or focus-session counts.

## Data Storage

Orbit stores its dashboard data in your browser using this localStorage
key:

```text
orbit.dashboard.v2
```

Saved data includes:

- Tasks and priorities
- Completion states
- Theme preference
- Focus and break durations
- Completed focus-session count

Data does not sync between browsers or devices.

Clearing site data removes saved dashboard data. If storage is unavailable
or full, the interface continues to work for the current page session,
and you can export tasks manually.

## Timer Limitations

The timer uses a target timestamp to reduce drift during background-tab
throttling. When the browser resumes running the page, the displayed
time updates.

Active timers do not survive page reloads or closing the tab.

The timer has no sound alerts or system notifications. Changing the
device clock can affect the remaining time.

## Technologies

- HTML5
- CSS Grid
- CSS Flexbox
- CSS custom properties
- Vanilla JavaScript
- localStorage
- File API
- Blob API

No external libraries, fonts, or API services are required.

## Customization

Change the CSS variables in `:root` to customize the dark theme.

Change the variables in `body.light` to customize the light theme.

The initial timer durations are defined in seconds:

```javascript
durations: {
  focus: 1500,
  break: 300
}
```

Previously saved durations take precedence over these defaults.

## Deploy with GitHub Pages

1. Create a repository named `orbit-focus-desk`.
2. Upload `index.html` and `README.md`.
3. Open Settings → Pages.
4. Select deployment from a branch.
5. Select your main branch and the root folder.
6. Save and open the website URL GitHub provides.

## Future Improvements

- Editable task titles
- Task due dates
- Weekly focus statistics
- Optional timer completion sounds
- Full dashboard backups
