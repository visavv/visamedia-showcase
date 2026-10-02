# VISAMEDIA

### From hours of livestream footage to editable selections in DaVinci Resolve.

VISAMEDIA is a personal desktop companion for finding conversations, reactions and highlight candidates in long livestreams. It combines a keyboard-driven terminal interface, configurable AI analysis and an editing workflow that keeps clips linked to their original source footage.

**Public project showcase · Active development · Application source code is private**

![VISAMEDIA channel browser with saved Twitch channels](assets/channel-profiles.png)

## The problem

A useful moment in a livestream can be a thirty-second reaction or a complete ten-minute discussion. Finding it manually means searching through hours of footage, keeping track of timestamps and rebuilding the same editing setup for each stream.

VISAMEDIA lets the editor describe the kind of video they want, browse recent streams, reuse a channel's preferences and turn candidate moments into markers or editable timeline selections.

## The workflow

1. **Choose footage.** Browse Twitch, Kick or YouTube channel history, select multiple VODs, paste URLs or reference local video files.
2. **Describe the edit.** Combine long-form and Shorts presets, write a narrative brief, and adjust duration, exclusions and quality thresholds.
3. **Analyze and review.** Use a selected AI provider, optionally compare two selectors and inspect a verdict with supporting transcript evidence.
4. **Open in Resolve.** Export marker EDLs or assemble selected source ranges back-to-back, with markers and access to the original media handles.
5. **Refine without starting over.** Try another prompt or model against the saved transcript and compare independent result versions.

```mermaid
flowchart LR
    A[Channel VODs or local files] --> B[Captions or local transcription]
    B --> C[Brief, presets and model analysis]
    C --> D[Editorial review]
    D --> E[Marker EDLs and reports]
    D --> F[Resolve selects timelines]
    F --> G[Reviewed face emphasis effects]
```

## Selected capabilities

| Area | What it enables |
| --- | --- |
| VOD browsing | Saved channels, paginated history, title filters and group selection with Space |
| Reusable profiles | Channel-specific briefs, content styles, filters, model choices and clip-guide notes |
| Narrative discovery | Complete conversations, evolving opinions across source streams, standalone reactions and Shorts candidates |
| Model flexibility | Codex/ChatGPT subscription integration, a Claude Code subscription adapter, and local Ollama analysis |
| Editorial review | Two independent candidate sets followed by a verdict; uncertain interpretations remain visible for review |
| Experiment versions | Reuse transcripts and existing media, compare selections and save successful prompts as presets |
| Resolve handoff | Original-media selections, mapped markers, separate Videos/Shorts timelines and optional project opening |
| Thumbnail candidates | Sampled face-location and expression analysis, local image-quality screening and manual approval |
| Editable effects | Reviewed face zoom suggestions, local motion tracking, Fusion keyframes and separate Effects timeline versions |
| Format-specific layouts | Independent Videos and Shorts native layout snapshots and channel preferences |

![VISAMEDIA Twitch VOD browser](assets/vod-browser.png)

*Development screenshots from the working application. Labels and navigation continue to evolve. Channel names and stream titles are examples of browsing public metadata; they do not imply affiliation.*

Technology: **Python, prompt_toolkit, Rich, yt-dlp, FFmpeg/FFprobe, faster-whisper, Ollama, OpenCV, Pillow, and the DaVinci Resolve scripting/Fusion APIs.**

See the [development case study](CASE_STUDY.md) for design decisions, validation and current limits.

## Current status

This is a working personal tool under active development
