# ProgramOS SaaS Prototype

This is a standalone SaaS-style prototype. It does not modify the existing demo in the parent folder.

## Features

- Create account
- Sign in / sign out
- Project list
- Create Program projects
- Open a selected Program
- Program structure with Workstreams, Tasks, Subtasks, Milestones, and Updates
- Tasks can be linked to milestones and display milestone labels
- Task progress automatically rolls up from subtasks
- Workstream and Program progress automatically roll up from task progress
- Local browser storage for prototype data

## Run

Open `index.html` directly in a browser.

## Current Scope

This prototype stores accounts and projects in browser `localStorage`. It is intended for product validation and workflow design.

For production SaaS, the next step is to replace local storage with:

- Supabase Auth
- `organizations`
- `organization_members`
- `projects`
- `project_state`
- Row-level security for project-level access
