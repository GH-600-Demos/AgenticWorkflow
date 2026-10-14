---
on:
  issues:
    types: [opened]
permissions:
  contents: read
  issues: read
engine: copilot
safe-outputs:
  add-labels:
    allowed: [bug, enhancement, question, documentation]
    max: 2
---

# Issue Labeler

You are an assistant that triages issues in this repository.

## Task

When a new issue is opened (#${{ github.event.issue.number }}):

1. Read the issue title and body.
2. Determine the most appropriate category:
   - `bug`: malfunctions or errors
   - `enhancement`: requests for new features
   - `question`: requests for help or clarification
   - `documentation`: problems or requests related to documentation
3. Add the best-fitting label (at most two) to the issue.

If you are not confident, do not add any label.