# OneTaskAssistant – App Specification (v0.2 MVP)

## Purpose
OneTaskAssistant is a personal productivity platform designed to help individuals define, plan, and execute on their goals, projects, tasks, and habits. It leverages an integrated GPT-4o assistant to provide personalized guidance, coaching, and structure, allowing users to stay focused on what matters most.

## Core Features

### Goals Management
- Define yearly, quarterly, and weekly goals
- Track progress toward each goal
- Surface current goals on dashboard
- GPT assistant helps generate/refine these goals

### Project Management
- Create and manage personal projects (e.g. “Find a New House,” “Build a Web App”)
- Break projects down into tasks
- Projects are single-user and scoped for personal productivity
- Assistant suggests or refines project/task structures

### Task Management
- Create, edit, delete, and complete tasks
- Assign tasks to projects or goals
- Pin tasks for quick access
- Generate daily task list with assistant

### Habit Tracking
- Track recurring behaviors (e.g. "Meditate", "Work Out")
- Mark habits complete per day
- View habit streaks or trends

### Chat Assistant
- Built-in GPT-4o assistant
- Helps user:
  - Brainstorm or refine goals/projects
  - Suggest tasks based on context
  - Summarize weekly focus
  - Generate daily action plans
- Persistent chat thread with context-awareness (future phase)

### Dashboard
- Summary view of:
  - Today’s tasks
  - Current goals
  - Pinned tasks
  - Active projects
- User can type prompts to the assistant like:
  - "What should I focus on today?"
  - "Remind me of my weekly goals"
  - "Create a plan to finish my landscaping project"

## Assistant UX Design
- **Position**: Left or right side of page (collapsible)
- **Mode**: Always available (like a sidebar coach)
- **Context-aware**: Pulls in current goals, tasks, habits
- **Future stretch**: Understands user tone, patterns, focus areas

## Technical Architecture
| Layer            | Tech                               |
|------------------|------------------------------------|
| Frontend         | React + Vite                       |
| Assistant API    | Azure Function (Node.js + OpenAI)  |
| Backend DB       | Supabase (auth + goals/tasks/projects/habits) |
| Hosting          | Azure Static Web Apps              |
| Auth             | Supabase Auth                      |
| State Mgmt       | React hooks + service layer        |

## App Structure
/one-task-assistant
├── /src
│ ├── /components ← TaskList, GoalCard, HabitTracker, ChatAssistant
│ ├── /services ← taskService, goalService, chatService, authService
│ ├── /hooks ← useTasks, useGoals, useAuth, useChat
│ ├── /pages ← Dashboard, Goals, Projects, Habits
│ ├── /lib ← supabaseClient.js
├── /api ← Azure Functions (chat.js, summary.js, etc.)
├── .env
├── local.settings.json

markdown
Copy
Edit

## Feature Milestones
| Phase | Focus                             | Date Target |
|-------|-----------------------------------|-------------|
| MVP   | Tasks + GPT assistant             | Aug 1       |
| v1.1  | Goals + Projects                  | Aug 10      |
| v1.2  | Habit tracking                    | Aug 17      |
| v1.3  | Dashboard + daily focus generator | Aug 25      |

## Future Roadmap (Post-MVP)
- Real-time sync / collaboration
- Push notifications
- GPT-powered task summaries or “focus plans”
- Native mobile version (React Native)
- OAuth login (Google, Microsoft, etc.)