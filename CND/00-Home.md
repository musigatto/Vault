---
type: home
module: "00"
tags: [concept]
topic: "CND Vault Home"
exam_weight: high
status: done
unresolved: []
---
# CND — Certified Network Defender

> [!info] Mission
> EC-Council CND study vault — generated strictly from the 20 module PDFs. Content: schematic, nothing invented.

## Module progress
```base
filters:
  and:
    - 'type == "moc"'
    - file.inFolder("10-MOCs")
views:
  - type: table
    name: Modules
    order:
      - module
```
> [!note] Pending modules show `draft`; a module counts as done when MOC + notes + canvas exist.

## Exam bank
- [[Question-Bank]] — 100 single-best-answer (source of truth)
- [[Mock-Exam-100]] — shuffled, no answers
- [[Answer-Key]] — one-line justifications, module + topic cited

## Needs review
```base
filters:
  and:
    - file.inFolder("20-Notes")
    - 'file.ext == "md"'
    - 'status == "needs-review"'
views:
  - type: list
    name: Needs review
    order:
      - module
      - file.name
```

## Unresolved collection
```base
filters:
  and:
    - file.inFolder("20-Notes")
    - 'file.ext == "md"'
    - '!unresolved.isEmpty()'
views:
  - type: list
    name: Unresolved
    order:
      - module
      - file.name
```

## Tag taxonomy
`concept · process · threat · tool · protocol · command · crypto · port · policy · bestpractice · exam` + `mod/NN`

## Canvases
```base
filters:
  and:
    - file.inFolder("40-Canvas")
    - 'file.ext == "canvas"'
views:
  - type: list
    name: Canvases
    order:
      - file.name
```