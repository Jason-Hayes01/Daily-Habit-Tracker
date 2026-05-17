# Daily-Habit-Tracker
A fully functional, game-like daily habit tracker was built from scratch on top of the existing TanStack Start scaffold. The application lets users track habits, maintain streaks, and compete with friends — all with a polished dark-purple UI that makes every check-in feel rewarding.

Core Habit Tracking
Users create habits with a custom icon and color, then tap a check-in button each day. The button bounces with a brief confetti animation when tapped, and a toast notification confirms the action. A seven-day mini heatmap under each habit shows at a glance which days were completed, and a streak badge with a pulsing fire icon displays the current consecutive-day run.

Game Mechanics
A level system spanning ten tiers (Seedling → Godlike) rewards consistent use. Total lifetime check-ins accumulate XP, advancing the user's level, which is shown in the header alongside an animated progress bar. Today's overall completion percentage is displayed as a colored progress bar at the top — it turns green when all habits for the day are done.

Friends & Leaderboard
Users pick a unique username at signup. Anyone can add a friend by typing their @username, making the friendship mutual automatically. The Leaderboard tab ranks the user and all their friends by total check-ins in the last 30 days, with gold/silver/bronze medals for the top three.

Onboarding
First-time visitors see a welcome screen that lets them choose an avatar emoji, set a display name, and pick a username. Their identity is stored in localStorage (a UUID), so no password or sign-in is required on return visits.

Data Persistence
All data is stored in a managed Netlify Postgres database via Drizzle ORM. Four tables power the app: users, habits, check_ins, and friendships. Database migrations are generated with drizzle-kit generate and live in netlify/database/migrations/ for automatic apply on deploy.

UI Design
The entire interface uses a deep space dark theme with violet/indigo gradients, glassmorphism cards, and CSS animations (bounce, confetti burst, fire pulse, slide-up, toast transitions). The layout is single-column and mobile-first, capped at a readable 512 px on desktop.

Files added or changed
db/schema.ts — Drizzle ORM schema for all four tables
db/index.ts — Netlify Database Drizzle client
drizzle.config.ts — Drizzle Kit config pointing migrations to the correct Netlify path
netlify/database/migrations/ — auto-generated SQL migration
src/server/habits.functions.ts — all server functions (users, habits, check-ins, friendships, leaderboard)
src/routes/index.tsx — complete habit tracker UI (replaces the placeholder dashboard)
src/routes/__root.tsx — updated page title to "StreakQuest"
src/styles.css — dark theme variables, glassmorphism utilities, and all animation keyframes
README.md — project overview and local dev instructions
AGENTS.md — architecture guide for future AI agents
