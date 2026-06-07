# Unity Workflow Tools

Unity Workflow Tools is a test fixture for validating localized plugin detail descriptions in Locus. It models a lightweight Unity editor maintenance workflow with checklists, automation notes, and preview content.

![Workflow preview](docs/workflow-preview.svg)

## Intended Workflow

- Save the active scene and scan package metadata
- Check plugin manifest and compatibility fields
- Run repeated editor helper commands
- Record the result for later inspection

## Capabilities Used For Testing

| Capability | Test Purpose |
| --- | --- |
| Checklist rendering | Verifies English list spacing |
| Relative SVG preview | Verifies Markdown image URL rewriting |
| External icon | The list icon still comes from `icon.svg` |
| Code block | Confirms compact code styling in plugin details |

~~~ts
export async function runWorkflow() {
  await saveScene();
  await validatePackages();
  return recordResult("ok");
}
~~~

This repository only hosts the test plugin source and documentation. The plugin package is downloaded from a release or repository archive.
