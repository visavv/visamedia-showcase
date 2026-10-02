# VISAMEDIA: development case study

## Goal

Build a practical companion for a livestream editor: discover worthwhile moments, keep their context, and arrive in DaVinci Resolve with editable selections instead of reviewing an entire raw stream every time.

The work extends an existing clip-finder into a focused VISAMEDIA workflow. Development is iterative and AI-assisted, with the editor's actual browsing and editing needs driving the changes.

## Product decisions

### A small main menu

The earlier application exposed many separate features at once. The companion concentrates on Markers + VOD and Settings, while preserving older tools behind an optional feature library. Frequent actions stay close to the main workflow.

### Profiles instead of repeated setup

A saved channel can carry its own brief, styles, quality filters, provider/model preferences and title/description guidance. Selecting footage leads to a reviewable setup before processing. This supports a recurring creator workflow while allowing changes for a specific stream.

### Conversations and Shorts can coexist

An editor may want a complete discussion and a shorter standalone moment within it. Styles combine as alternatives, with shared focus and exclusions. Duration controls remain explicit. This avoids treating every useful segment as a short burst of excitement.

### Experiments keep the original material

Prompt and model comparisons reuse saved transcripts and source references. Each experiment gets a separate result version so the editor can inspect differences without downloading or transcribing the same footage again.

### Resolve becomes the editing destination

Selected ranges refer to the original Media Pool items. Source frames and assembled timeline positions are recorded separately, allowing markers to follow the shorter selects sequence while preserving access to source handles.

Videos and Shorts have separate timelines and separate saved layout choices. Their different aspect ratios, crops and visual styles should be represented explicitly. Native three-track snapshots preserve the reference layout; automatic retargeting of arbitrary templates remains future work.

## Technical challenges addressed

| Challenge | Approach |
| --- | --- |
| Partial analysis appearing complete | Validate provider output and review results; preserve failure details and stop finalization when required analysis fails |
| Ambiguous jokes, quotes or sarcasm | Check source context, retain proposal sets and verdicts, and expose uncertainty for human review |
| Excess work during comparisons | Cache matching analysis and reuse saved transcripts/media across experiments |
| Source timing versus assembled timing | Store both coordinate systems and verify source In/Out and timeline placement |
| Facecam positions changing | Locate candidate faces per sampled frame; track approved short regions locally instead of assuming a fixed crop |
| Effects that become difficult to undo | Add editable Fusion effects on a dedicated track in a separate timeline version |
| Tracking failure or changed clip geometry | Reject uncertain tracking and require a valid timing/layout map before applying effects |
| Noisy terminal navigation | Refine keyboard behavior, bounded layouts, resize handling and progress presentation |

## Validation

Automated checks cover provider routing and failures, transcript reuse, profile persistence, source selection, marker/selection mapping, effects constraints, tracking failure and independent layout choices.

Local integration trials include synthetic transcript analysis, original-media selection placement in Resolve, and a synthetic moving-pattern effect test. The effect's rendered enlargement and return to normal size were checked, alongside editable animation keys and native layout snapshot export.

These checks establish specific behaviors. They do not establish a measured productivity gain, audience growth, model accuracy score or guaranteed clip quality. Such claims would require a separate evaluation on real editing sessions.

## Remaining work

- Map and validate the actual Videos and Shorts three-layer templates for automatic reuse.
- Evaluate thumbnail selection and motion tracking on representative streams.
- Trial the Claude subscription adapter with an authenticated live session.
- Improve emphasis timing with stronger audiovisual evidence and editor feedback.
- Add a concise end-to-end demo and representative Resolve timeline screenshots to this showcase.

## Portfolio summary

**VISAMEDIA — AI-assisted livestream discovery and editing companion.** A Python terminal application combining multi-source VOD browsing, reusable editorial profiles, versioned transcript analysis, marker EDL export and editable DaVinci Resolve selections. The project emphasizes practical UI iteration, reproducible experiments, explicit failure handling and preservation of source-media editability.
