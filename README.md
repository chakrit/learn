# learn

`learn` is an adaptive technical-tutoring skill for AI coding agents. It turns a
topic, question, or recent problem into a short learning loop:

1. Pick the next useful concept.
2. Explain one small idea with a practical example.
3. Ask the learner to retrieve, predict, or apply it.
4. Adapt the next step to the learner’s response.

It is designed for building understanding over time, not for one-off factual answers
or implementing code on the learner’s behalf.

## Install with [ACE](https://ace-rs.dev)

Install the skill into your ACE school:

```sh
ace import chakrit/learn --skill learn
```

From a local checkout, use the repository path instead:

```sh
ace import /path/to/learn --skill learn
```

Check that ACE can see it:

```sh
ace skills
```

Start an ACE session in the project where you want to use the skill. Invoke it with
`/learn` (or `$learn`), optionally followed by a topic:

```text
/learn database indexing
```

## Direct use

The complete, harness-neutral skill definition is [`skills/learn/SKILL.md`](skills/learn/SKILL.md).
Tools that support the common `SKILL.md` format can load that file directly.
