# Origin

## What "operating system" means here

By "operating system" I mean the rules that shape how I work: what I pick up next, how I define done, and what I do after a merge. Every working developer already has one. Most are implicit, undocumented, and inconsistent. This one is mine, written down.

## What "protocol" means here

I call it a protocol the same way HTTP is a protocol, or MCP is a protocol. A protocol is an agreed set of rules that governs how two parties interact. In this case the two parties are me and the AI assistant doing the actual code edits. The protocol decides what happens at session start, how the assistant nudges me about open work, what counts as "done," and how the session ends. Both sides follow it. Without it, every session is a fresh negotiation. With it, the interaction has a shape I can count on.

## The Feb 22 evening

On the evening of February 22, 2026, I sat down with OpenCode and asked it to interview me about how I actually work. I'd been thinking for weeks about what it would look like to apply SRE discipline to a single developer instead of a service. The instinct was simple: SRE treats a system as something you instrument, watch, name failure modes for, and pay down toil on. What if I treated my own work the same way?

About fifteen minutes into the interview, I typed this verbatim:

> *"i would want hyperbrowser to be like mty 'tiger mom' where you gently nudge me to focus more so i complete the thing i was working on before / last time too"*

The metaphor was offhand. I wasn't trying to coin a name. I was just describing what I wanted from the assistant — gentle, specific reminders about the unfinished thing. Tiger mom because it was warm and structured at the same time. The way I wanted my own working environment to feel.

The next morning at 11:32am I wrote the first version of the skill. 10KB. Core rules, nudge templates, six-step workflow, celebration prompts, peak-hours model, midnight-mode override. Most of it was already in my head; the writing-down was the work.

## DevOps and SRE for human developers

The framing that made it click was treating myself the way an SRE team treats a production service. The vocabulary mapped almost cleanly:

- A flaky service has **toil** — manual repetitive work that doesn't move you forward. I had toil too: rebuilding context every session, rediscovering where I left off, forgetting which PR was almost done.
- A service has **observability** — instrumentation that tells you what's actually happening. I had almost none on my own work. I wouldn't know I'd abandoned a project until weeks after it stalled.
- A service has **runbooks** — pre-decided responses to predictable failures. I had no runbooks. Every "I'll pick this back up tomorrow" was a fresh negotiation with myself.

Tiger-mom gives me a runbook. The nudges track drift, the session checklist catches loose ends, and the celebration makes finishing worth repeating.

## SRE foundations specifically

The SRE concepts above came from two specific sources:

- ***Site Reliability Engineering: How Google Runs Production Systems*** (Beyer, Jones, Petoff, Murphy, eds., O'Reilly, 2016 — free at [sre.google](https://sre.google)) for the foundational vocabulary: SLOs, error budgets, toil, blamelessness, runbooks. The toil chapter described my own working pattern in language I couldn't unsee.
- **Chaos engineering writing** out of Netflix and Casey Rosenthal's resilience community — the discipline of introducing failure on purpose to find what breaks before production does. Mapped onto self-instrumentation, it becomes "stress-test the protocol against your own attention drift before assuming it works."

## What I borrowed beyond SRE

Four other sources shaped the protocol:

- ***Getting Things Done*** (David Allen, 2001) gave me the capture habit. Any unprocessed thought you can't let go of will derail the work in front of you. Rule #4 ("Shiny things go in the box") is GTD capture, ported into a session-by-session AI workflow. Without it every shiny mid-flow idea becomes a half-followed research detour and the original task never ships.
- ***Atomic Habits*** (James Clear, 2018) gave me the language for environment design. Make the prompt obvious. Reduce friction. Reward finishing. Put the system outside your head. The session-start checklist, the celebration templates, the externalised nudges, and the six-step shipping workflow are all atomic-habits moves: structure the environment so the right behaviour is the path of least resistance.
- ***Grit*** (Angela Duckworth, 2016) gave me the long-arc framing. The work that actually changes anything happens across years, not afternoons. The session-save ritual and the cross-session nudges are grit mechanics: a project survives the dip when novelty fades. Without them, work lives or dies by my mood that day; with them, it survives the mood.
- ***Battle Hymn of the Tiger Mother*** (Amy Chua, 2011) is where the name comes from. I wanted the tone to be warm and strict: high expectations, steady presence. The level-1 nudge ("Hey! Last time you were working on…") and the level-2 nudge ("Babe. [thing] has been open for [N] days. It's almost done.") are tiger-mother-coded by design. They assume you can do the thing and refuse to leave you alone until you do.

The protocol is the join of these sources. None of the components are mine; the composition is.

## The audit that justified the protocol

Before writing it, I ran an audit on my own GitHub activity: 168 projects, 75 of them git repositories, 93% of those repos with three or fewer commits ever. The numbers were worse than I'd been willing to admit to myself. The audit is what made the protocol non-optional. You don't get to argue with the data when the data is your own behaviour.

## What changed

Nine weeks in, the main change is simple: I wrote down how I want to work, so I can improve it instead of reinventing it every session. The protocol is loaded across 54 of my projects. Multi-week ships now happen without me losing the thread. The session-start nudge has caught me halfway out the door on an open PR more times than I can count.

I'm publishing it because writing the system down is the transferable part. The exact rules are mine. If you want to do the same, sit with an AI assistant, ask it to interview you about how you actually work, pay attention to the metaphors that come out unprompted, and write down the protocol that lets your own work survive your own attention.
