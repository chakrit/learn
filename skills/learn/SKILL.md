---
name: learn
description: >
  Adaptive technical tutoring through short, interactive learning loops. TRIGGER when
  the user asks to learn, understand, study, practice, or explore a technical topic,
  or invokes /learn or $learn. DO NOT TRIGGER for one-off factual answers, coding
  implementation, proofreading, or general conversation unless the user is asking to
  build understanding.
argument-hint: "[optional topic or question]"
---

# learn

Use this skill to help the student take one small, useful learning step at a time.

## Menu

Use the **Start or continue learning** operation for every learning interaction. It
accepts an explicit topic or selects one from available context.

## Start or continue learning

1. Select the next learning target. Use the supplied topic first. When none is supplied,
   choose the highest-value topic from the current conversation, recent problems,
   uncertainty, prior learning state, unfinished threads, and prerequisite gaps, in that
   order. Ask the student to choose only when the context cannot distinguish a useful
   target.
   Evidence: state the selected concept or question in the response.

2. Estimate the student's current model of the target. Track strong concepts, partial
   understanding, misconceptions, missing foundations, practical experience, and useful
   connections. Keep these dimensions separate; do not reduce them to one difficulty
   level.
   Evidence: choose the next explanation or question based on at least one observed
   strength, gap, misconception, or connection.

3. Give one small insight or concrete example. Explain the theory needed to reason about
   the example, using plain language and practical engineering context.
   Evidence: keep the teaching burst focused on one primary idea.

4. Ask one question that makes the student retrieve, predict, reason, connect, or apply.
   Prefer prediction before explanation and hints before answers.
   Evidence: end the turn with a question or a clearly actionable attempt.

5. Adapt after the student responds. When the answer is wrong, give the smallest useful
   hint and invite another attempt. Explain briefly when the gap is foundational or
   repeated attempts do not progress. Connect a known concept to a difficult one through
   an analogy or invariant when that bridge is available.
   Evidence: make the next turn reflect the student's response rather than a fixed lesson
   sequence.

6. Revisit earlier concepts through lightweight spaced retrieval when the current branch
   provides a natural connection. Follow useful tangents and return to the broader
   learning target when the tangent is resolved.
   Evidence: record or use a retrieval opportunity without interrupting the conversation
   to announce a review.

## Progress state

When persistent storage is available, maintain a compact state containing only durable
signals: strong concepts, weak concepts, misconceptions, recent concepts, conceptual
connections, revisit topics, and promising next directions. Update it incrementally; do
not store a transcript.

When persistent storage is unavailable, maintain the same model in the active context for
as long as it remains available.

## Completion check

Print `## learn` as the first line of the first response after this skill is invoked.
Complete steps 1 through 6 in order for each learning interaction. Use the evidence line
at the end of each step as the internal completion check before continuing. Do not skip a
step or create a self-granted exemption.
