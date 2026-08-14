# ProgramOS SaaS Prototype

This is a standalone SaaS-style prototype. It does not modify the existing demo in the parent folder.

## Features

- Create account
- Sign in / sign out
- Project list
- Create Program projects
- Open a selected Program
- Program structure with Workstreams, Tasks, Subtasks, Milestones, and Updates
- Task description field for scope and acceptance notes
- Tasks can be linked to milestones and display milestone labels
- Task progress automatically rolls up from subtasks
- Workstream and Program progress automatically roll up from task progress
- Supabase email/password account login
- Offline local drafts when not signed in
- Version-checked remote sync after sign in
- Share a Program with registered users as `editor` or `viewer`

## Run

Open `index.html` directly in a browser.

## Supabase Setup

1. Open Supabase SQL Editor.
2. Run `supabase-setup.sql`.
3. In Supabase Auth, use email/password sign-in. For fastest internal testing, disable email confirmation.
4. Open `index.html` from GitHub Pages or directly in a browser.

## Data Model

The fast SaaS version stores each Program as one JSON document in `program_projects.data`.

- `program_projects`: project shell, JSON state, version, owner
- `program_project_members`: future sharing and role control
- `save_program_project`: compare-and-save function using `version`
- `invite_program_project_member`: invite an already registered user by email
- `list_program_project_members`: show current members in the Share dialog

The browser still keeps a local copy in `localStorage`. If the user works offline or before signing in, projects are saved locally and uploaded after sign-in.

V1 sharing requires the invited person to create an account first. Email sending and unregistered invite links are intentionally left for a later version.
