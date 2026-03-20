# User Stories and Requirements (test edit in Github directly)

## Major Release Management

**User story#1 - Major Release List View (must-have)**

As a Pilot user, I can view all Major Releases on a landing page so that I can quickly find and navigate to a specific Major Release.

Requirements:
- Displays all Major Releases in a card view
- Each card shows: Major Release name, Major Release ID, Event date, Release Manager(s), image, and launch count
- Clicking a Major Release navigates to the Major Release detail page

**User story#2 - Edit Major Release (must-have)**

As a Release Manager, I can edit a Major Release in Pilot so that there is a central place to manage all Launches and associated experiments for that release.

Requirements:
- User must populate the following fields: Name, Major Release ID, Release Manager, Slack channel, Event date, SFX start date, CFX start date, Code complete date, Additional information, Launch Checklist Help URL (optional)
- User can edit all fields except Launch ID
- Note [19/3]: Launch Type editor removed at Major Release level — users can still pick Launch Type at Launch level

**User story#3 - Major Release Change Log (must-have)**

As a Release Manager, I can see a chronological record of significant events across a Major Release so that I have a reliable audit trail.

Requirements:
- Audit log captures: Major Release updates (field level changes), Launch updates (added, removed), Train updates (created, updated), Shared policy (created, updated, removed)
- Entries include timestamp, actor, and event
- Accessible to everyone with access to the Major Release

---

## Shared Policy Management

**User story#4 - Bulk Update Notifications Improvement (must-have)**

As a Release Manager, when I bulk update linked SFXs, notifications are sent to relevant stakeholders so I know everyone is up to date.

Requirements:
- When a Bulk Update is submitted by a Release Squad member, the system sends a Slack notification to every Experiment Owner
- When a Bulk Update is published by an Experiment Owner, the system sends a Slack notification to the Release Squad member who submitted the bulk update

**User story#5 - Shared Policy Change Log (must-have)**

As a Release Manager, I have a change log of Shared Policy changes so I can audit historical changes.

Requirements:
- Chronological log of changes e.g. policy added, policy removed, policy modified — with reason, timestamp and actor
- Visible under the change log

---

## Launch Management

**User story#6 - Launch List View (must-have)**

As a Pilot user, I can view all Launches under a Major Release so that I can scan all launches.

Requirements:
- Table list displays: Launch name, Experiment ID, Owner (TRO), Evaluation (dependency on Experiment team)

**User story#7 - Create Launch (must-have)**

As a Pilot user, I can create a new Launch within a Major Release in Pilot so that launch scope is captured.

Requirements:
- Launch input fields are broken into 4 sections:
  - General: Launch name (required), Marketing name (optional), Launch type, Feature link to Feature Catalogue (optional), Description (optional, max 240 chars), Release plan notes (optional)
  - Timeline: Code complete date (optional), SFX start date and CFX start date (optional), Launch timing (at event, post event, or pre event)
  - Experiment: Search for and link an existing experiment (optional); on adding, user confirms variant role mapping — Control, Launch (required), Promo (optional)
  - Team: TRO (required), Train Conductor (required), additional roles optional, On-call field (optional)
- Anyone can create a Launch

**User story#8 - Launch Status (must-have)**

As a Pilot user, I can see the system-inferred status of a Launch so that I know where my Launch is in the Major Release process.

Requirements:
- Each Launch has a system-inferred status field
- Available statuses: Draft (default on creation), Needs Attention, In SFX, In CFX, Rolled out
- No notifications triggered on status change

**User story#9 - Edit Launch (must-have)**

As a Pilot user, I can edit a Launch I own so that I can keep launch details up to date.

Requirements:
- All field changes are captured in the change log only — no notifications triggered
- Moved out of scope: Access controls on Launch edits, high stake fields edit notifications

**User story#10 - Launch Detail View (must-have)**

As a Pilot user, I can view the full details of a Launch so that I can see all metadata, experiments, assigned trains, and activity in one place.

Requirements:
- Launch info panel includes: full launch details (including team), change log, decisions scoped to this Launch
- Main page content includes: Experiments, Assigned trains (read-only view of which train/s this Launch is assigned to, with CTA to reassign to a different train)

**User story#11 - Remove Experiment From Launch (must-have)**

As any Launch Stakeholder, I can remove an experiment from a Launch so that the experiment list stays accurate as scope changes.

Requirements:
- Experiment has a Remove CTA on the Launch Detail View
- A confirmation step is required before removal
- A reason must be provided, recorded in the launch change log
- Removing an experiment is disabled once a Launch is assigned to a Train

**User story#12 - Delete Launch (must-have)**

As a Launch Stakeholder, I can delete a Launch so that confirmed-out-of-scope launches are removed from the Major Release.

Requirements:
- Delete CTA available under launch details
- A confirmation step is required before deletion, noting that the Launch and its log history will be removed
- Deletion is recorded in the Major Release change log

**User story#13 - Launch Change Log (must-have)**

As a Launch Stakeholder, I have a change log of Launch changes so that I can audit historical changes.

Requirements:
- Chronological log of composition changes e.g. launch joined/left, variant reassigned — with reason, timestamp and actor
- Visible under the change log

---

## Train Management

**User story#14 - Train Composition View (must-have)**

As a Train Conductor, I can view the current composition of all trains under a Major Release so that I have a real-time overview.

Requirements:
- Trains appear under the Release train page of a Major Release
- For each train: Train name, Colour identifier, Assigned launches, Current rollout percentage (derived from the linked CFX experiment config), Variant, Evaluation, Link to CFX config and report

**User story#15 - Auto-sync Flag Changes from SFX to CFX (must-have)**

As a Train Conductor, flag changes in SFX experiments are automatically synced to the CFX so that I no longer have to manually sync them.

Requirements:
- When a feature owner or TRO updates flags in their SFX, those changes are automatically reflected in the combined feature experiment in Pilot

**User story#16 - Train Change Log (must-have)**

As a Train Conductor, I have a change log of Train changes so I can audit historical changes.

Requirements:
- Chronological log of composition changes e.g. launch joined/left, variant reassigned — with reason, timestamp and actor
- Visible under the change log
