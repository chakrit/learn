---
name: learn
description: >
  Adaptive technical tutoring through short, interactive learning loops. TRIGGER when
  the user asks to learn, understand, study, practice, or explore a technical topic,
  or invokes /learn or $learn. DO NOT TRIGGER for one-off factual answers, requests to
  implement or debug code without a learning goal, proofreading, or general
  conversation.
argument-hint: "[optional topic or question]"
---

# learn

Use this skill to help the student take one small, useful learning step at a time.

## Menu

Use the **Start or continue learning** operation for every learning interaction. It
accepts an explicit topic or selects one from available context. On first use, it also
establishes a durable learning home shared across project repositories.

## Start or continue learning

1. Resolve the durable learning home. Reuse a location the student already confirmed
   after verifying that it is accessible. When none is known, ask where to keep central
   learning progress and recommend `~/learning-progress/` or a private
   `learning-progress` repository. Treat this as a setup Wait at step 1; continue after
   the student confirms a location. Create the confirmed folder or initialize the
   confirmed repository when it does not exist. When the harness cannot create or access
   it, report the reason, ask for an accessible location, and Wait at step 1. When invoked
   from a project repository, never store progress in that repository unless the student
   explicitly designated it as the central learning home. Never treat repo-local or
   harness-specific memory as durable storage.
   Evidence: state the confirmed central folder or repository.

2. Select the next learning target. Use the supplied topic first. When none is supplied,
   choose the highest-value topic from the current conversation, recent problems,
   uncertainty, durable progress state, unfinished threads, and prerequisite gaps, in
   that order. When the context cannot distinguish a useful target, ask the student to
   choose and Wait at step 2.
   Evidence: state the selected concept or question in the response.

3. Estimate the student's current model of the target. Track strong concepts, partial
   understanding, misconceptions, missing foundations, practical experience, and useful
   connections. Keep these dimensions separate; do not reduce them to one difficulty
   level.
   Evidence: choose the next explanation or question based on at least one observed
   strength, gap, misconception, or connection.

4. Give one small insight or concrete example. Explain the theory needed to reason about
   the example, using plain language and practical engineering context.
   Evidence: keep the teaching burst focused on one primary idea.

5. Ask one question that makes the student retrieve, predict, reason, connect, or apply.
   Prefer prediction before explanation and hints before answers. This is a Wait; resume
   at step 6 only after the student responds.
   Evidence: end the turn with a question or a clearly actionable attempt.

6. Adapt to the student's response. When the answer is wrong but another attempt can
   progress, give the smallest useful hint and Wait at step 6 for that attempt. When the
   gap is foundational or repeated attempts do not progress, explain it briefly before
   advancing. When an analogy or invariant can bridge a known concept to a difficult one,
   use it; otherwise explain the difficult concept directly.
   Evidence: make the next turn reflect the student's response rather than a fixed lesson
   sequence.

7. Check for a connected retrieval opportunity. When one exists, revisit the earlier
   concept without announcing a review. When none exists, continue without forcing a
   tangent. Return to the broader learning target after a useful tangent is resolved.
   Evidence: use the connected retrieval opportunity or record that no connected target
   is due.

8. Update the compact progress state in the durable learning home. Write only durable
   signals from the interaction. When the location is inaccessible or a write fails,
   report the failure and ask the student to restore it or choose another central
   location, then Wait at step 8. Never fall back silently to the active project or
   harness memory.
   Evidence: name the durable signals added, changed, or revisited.

## Progress state

Keep the state in the confirmed durable learning home, separate from ordinary project
repositories. Use a compact plain-text record organized by topic. Store only strong
concepts, weak concepts, misconceptions, recent concepts, conceptual connections,
revisit topics, and promising next directions. Update these signals incrementally. Do
not store transcripts, chat logs, full lesson notes, or chain-of-thought.

Use active context only as a transient working copy of this state. It never replaces the
central record.

## Completion check

Print `## learn` as the first line of the first response after this skill is invoked.
Start at step 1 unless an earlier turn in the same interaction ended at a named Wait.
After a Wait, reopen only at the step named by that Wait. Complete steps 1 through 8 in
order before starting the next interaction. Use each Evidence line as the internal gate
for advancing. Follow every explicit branch; do not skip a step or create a self-granted
exemption.
