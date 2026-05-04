# AISYNC-DEMO-MVP — Functional Scope

## 1. Product statement

AISYNC-DEMO-MVP is a traceable single-user AISync cell where one user can create multiple internal teams, work inside a team workspace, save checkpoints, review basic traceability, consult basic documentation, and resume work from previous states.

The MVP must demonstrate the core AISync loop:

Create → Work → Save → Trace → Consult → Resume

## 2. MVP formula

AISYNC-DEMO-MVP = single-user cell + internal multi-teams + workspace per team + checkpointing + basic Audit Log + basic Documentation Mode + structure prepared for future Organizational Elasticity.

## 3. What stays in the MVP

### Account / Cell
- One Account.
- One User.
- One sovereign single-user cell.
- No real multi-user collaboration.
- No real inter-cell collaboration.

### Projects
- At least one active project.
- Project contains internal teams.
- All saved objects must be associated with `projectId`.

### Multi-teams
The user must be able to:
- create multiple teams;
- rename/edit teams;
- select a team;
- open a workspace for each team;
- see teams in a simplified Map / Tree;
- save checkpoints associated with the active team;
- see team origin in Audit Log and Documentation Mode.

### Workspace per team
Each team must have its own workspace with:
- Manager or Senior Manager panel;
- Worker 1 panel;
- Worker 2 panel;
- message history;
- input;
- Save Version;
- basic secondary actions where already stable.

### Save Version / Checkpoint
`Save Version` remains the visible UI label.

Functionally, it creates a checkpoint.

Each checkpoint must include, at minimum:
- checkpointId;
- projectId;
- teamId;
- workspaceId;
- panelId or agentId;
- timestamp;
- version;
- snapshotContent;
- summary;
- status;
- provenance.

### Audit Log basic
Audit Log must show basic operational events, including:
- team.created;
- team.updated;
- checkpoint.created;
- workspace.resumed.

Audit Log must allow:
- opening event detail;
- identifying team origin;
- resuming work from a checkpoint when available.

### Documentation Mode basic
Documentation Mode must include a minimal Repository View showing:
- checkpoints;
- saved selections, if available;
- derived documents, if available;
- team origin;
- date;
- version;
- status;
- basic metadata;
- detail view.

## 4. What is excluded from the MVP

The MVP must not include active implementation of:

- real Connect Teams;
- real External Team Links;
- real multi-user collaboration;
- complex permissions;
- enterprise settings;
- advanced compliance layer;
- legal hold;
- retention rules;
- mature Knowledge Map;
- mature Investigate View;
- advanced Audit View;
- deep inter-cell governance;
- production auth;
- production tenancy enforcement.

## 5. Organizational Elasticity

Organizational Elasticity is strategically important and must remain prepared, but it is not required as an active MVP function unless budget allows.

The MVP must prepare the data model for future promotion flows.

Future target:

Worker → Promote Agent → Senior Manager → derived subteam

Required reserved fields:

### Team
- parentTeamId
- createdFromAgentId
- hierarchyLevel
- isElasticNode

### Agent / Panel
- canBePromoted
- promotedToTeamId
- promotedFromAgentId
- parentAgentId
- hierarchyLevel

Reserved future events:
- agent.promoted
- elastic_team.created
- elastic_team.attached

The UI may show a disabled or hidden Promote Agent option, but it must not expose a broken feature.

## 6. MVP implementation order

1. Create clean repo baseline.
2. Freeze functional scope.
3. Simplify shell/navigation.
4. Implement or preserve internal multi-teams.
5. Simplify Teams Map / Tree.
6. Ensure workspace per team.
7. Ensure Save Version / Checkpoint.
8. Ensure basic Audit Log.
9. Ensure basic Documentation Mode.
10. Prepare Organizational Elasticity structure.
11. Clean visual hierarchy and copy.
12. Run final QA.

## 7. Mandatory QA flow

Before closing the MVP, the following flow must pass:

1. Create or open a project.
2. Create Team A.
3. Create Team B.
4. Open Team A Workspace.
5. Write in Manager panel.
6. Save Version.
7. Confirm checkpoint appears in Audit Log.
8. Open checkpoint detail.
9. Resume Work.
10. Confirm return to correct team workspace.
11. Open Documentation Mode.
12. Confirm checkpoint appears with team origin.
13. Open Team B.
14. Confirm Team B context is separate.
15. Confirm no out-of-scope broken feature is visible.

## 8. Control principle

Do not amputate structure.
Simplify visible operation.

The MVP must save structurally correct data from day one, even if it exposes fewer advanced views.