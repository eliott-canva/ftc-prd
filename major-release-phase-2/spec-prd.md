# User Stories and Requirements

| User Story | MoSCoW | Requirements |
|---|---|---|
| **Major Release Management** | | |
| Major Release List View | Must | Displays all Major Releases in a card view. Each card/row shows: Major Release name, Major Release ID, Event date, Release Manager(s), image, and launch count. Clicking a Major Release navigates to the Major Release detail page. |
| Edit Major Release | Must | User must populate the following fields upon creation: Name, Major Release ID, Release Manager, Slack channel, Event date, SFX start date, CFX start date, Code complete date, Additional information, Launch Checklist Help URL (optional). User can edit all fields except Launch ID. Note: Launch Type editor removed at Major Release level. |
| Major Release Change Log | Must | Audit log captures: Major Release updates (field level changes), Launch updates (added, removed), Train updates (created, updated), Shared policy (created, updated, removed). Entries include timestamp, actor, event. Accessible to everyone with access to the Major Release. |
| **Shared Policy Management** | | |
| Bulk Update Notifications Improvement | Must | When a Bulk Update is submitted by Release Squad member, the system sends a Slack notification to every Experiment Owner. When a Bulk Update is published by an Experiment Owner, the system sends a Slack notification to the Release Squad member who submitted the bulk update. |
| Shared Policy Change Log | Must | Chronological log of changes e.g. policy added, policy removed, policy modified — with reason, timestamp and actor. Visible under the change log. |
| **Launch Management** | | |
| Launch List View | Must | Table list displays: Launch name, Experiment ID, Owner (TRO), Evaluation (dependency on Experiment team). |
| Create Launch | Must | Launch input fields broken into 4 sections: General (name, marketing name, launch type, feature, description, release plan notes), Timeline (code complete date, SFX/CFX start dates, launch timing), Experiment (link existing experiment, confirm variant role mapping), Team (TRO required, Train Conductor required, additional roles optional). Anyone can create a Launch. |
| Launch Status | Must | System-inferred status values: Draft (default), Needs Attention, In SFX, In CFX, Rolled out. No notifications triggered on status change. |
| Edit Launch | Must | All field changes captured in change log only — no notifications triggered. |
| Launch Detail View | Must | Launch info panel: full launch details (including team), change log, decisions scoped to this Launch. Main page content: Experiments, Assigned trains (read-only view with CTA to reassign). |
| Remove Experiment From Launch | Must | Experiment has a Remove CTA on the Launch Detail View. Confirmation step required before removal. A reason must be provided, recorded in launch change log. Removing Experiment is disabled once a Launch is assigned to a Train. |
| Delete Launch | Must | Delete CTA under launch details. Confirmation step required, noting that the Launch and its log history will be removed. Deletion is recorded in the Major Release change log. |
| Launch Change Log | Must | Chronological log of composition changes e.g. launch joined/left, variant reassigned — with reason, timestamp and actor. Visible under the change log. |
| **Train Management** | | |
| Train Composition View | Must | Trains appear under Release train page of a Major Release. For each train: Train name, Colour identifier, Assigned launches, Current rollout percentage, Variant, Evaluation, Link to CFX config and report. |
| Auto-sync Flag Changes from SFX to CFX | Must | When a feature owner or TRO updates flags in their SFX, those changes are automatically reflected in the combined feature experiment in Pilot. |
| Train Change Log | Must | Chronological log of composition changes e.g. launch joined/left, variant reassigned — with reason, timestamp and actor. Visible under the change log. |
