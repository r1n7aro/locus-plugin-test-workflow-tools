# Unity Workflow Tools

Unity Workflow Tools is a test fixture for validating richer plugin detail descriptions in Locus. It models a lightweight Unity editor workflow helper package with checklists, automation notes, and visual preview content.

![Workflow preview](docs/workflow-preview.svg)

## Intended Workflow

The plugin represents a small set of commands that would help a Unity developer repeat project maintenance tasks with less context switching. The Hub detail view should make the scope clear before installation.

## Capabilities Used For Testing

| Capability | Test Purpose |
| --- | --- |
| Checklist rendering | Verifies list spacing in the modal |
| Relative SVG preview | Verifies Markdown image URL rewriting |
| External icon | The card icon still comes from `icon.svg` |
| Code block | Confirms compact code styling in plugin details |
| Link handling | Opens external links through the existing Markdown renderer behavior |

## Sample Checklist

- Confirm the active scene is saved
- Rebuild generated editor metadata
- Validate required Unity packages
- Open the project-specific task panel
- Record the last successful workflow step

```yaml
workflow:
  name: editor-maintenance
  steps:
    - save-active-scene
    - refresh-generated-assets
    - validate-packages
    - open-task-panel
```

## Registry Fixture Notes

This README is loaded through the registry entry's `descriptionSource` field. The installable plugin package is published as a GitHub release asset. The repository keeps source-level fixture files, README content, and icon assets without committing binary archives. The Hub can show detailed documentation without putting documentation files inside the registry repository.

The same repository also exposes `icon.svg`, which is used by the registry card as an external icon URL.