# DACC Fuel Calculator

Standalone static ACC fuel calculator based on the DACC Race Engineer fuel workflow.

## Deploy with GitHub Pages
1. Create a new GitHub repository (for example `dacc-fuel-calc`).
2. Upload `index.html` to the root of the repository.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select `main` and `/ (root)`, then Save.
6. Share the resulting GitHub Pages link with drivers.

No backend, login or database is required. Each driver's last-used values are stored only in that browser via localStorage.

## Calculation
- Time mode expected laps = `ceil((remaining time - pit loss) / average lap time)`
- Lap mode expected laps = entered laps
- Minimum fuel = `expected laps × fuel/lap`
- Recommended fuel = `(expected laps + safety margin laps) × fuel/lap`
- Fuel to add = `max(0, recommended fuel - current fuel)`
- Displayed fuel loads round upward to 0.1 L.
