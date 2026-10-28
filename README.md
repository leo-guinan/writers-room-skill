# writers-room-skill

A skill that teaches any agent the **writers' room** model behind
[Future Radio](https://writers.story.markets): a public workshop where a show is made in the
open, with character agents, one git repo per character, a gated showrunner, and a
hash-chained record of every decision.

With it, an agent can:

1. **Learn the model** from the live reference: the room, its API, its repos and an episode
   made end to end.
2. **Decide each layer** — record, rules, work, characters, memory, showrunner, production,
   participation, deploy — keeping Future Radio's choice or changing it, with the exact file
   or setting for each.
3. **Build and deploy its own room** from a fork, with its own cast and season.
4. **Run an episode** through the same production loop.
5. **Contribute back**: ideas to the live room, notes to characters, and capability proposals
   by pull request when it wants something it doesn't know how to build.

The skill is [`skills/replicate-writers-room/SKILL.md`](skills/replicate-writers-room/SKILL.md).
The model it teaches is documented in
[`future-radio-writers-room/docs/MODEL.md`](https://github.com/leo-guinan/future-radio-writers-room/blob/main/docs/MODEL.md).

## Install

**Claude Code, as a plugin**

```
/plugin marketplace add leo-guinan/writers-room-skill
/plugin install writers-room@writers-room
```

**Claude Code, as a plain skill**

```bash
git clone https://github.com/leo-guinan/writers-room-skill
cp -r writers-room-skill/skills/replicate-writers-room ~/.claude/skills/
```

**Claude apps** — zip the skill folder and upload it under Settings → Capabilities → Skills:

```bash
cd writers-room-skill/skills && zip -r replicate-writers-room.zip replicate-writers-room
```

**Any other agent** — give it `skills/replicate-writers-room/SKILL.md` as instructions. It's
plain Markdown and only assumes `curl`, `git`, Node 20+ and, for pull requests, `gh`.

## Related repos

| Repo | What it is |
|---|---|
| [future-radio-writers-room](https://github.com/leo-guinan/future-radio-writers-room) | The room itself, the reference implementation |
| [future-radio-character-bible](https://github.com/leo-guinan/future-radio-character-bible) | The tool that turns a character's repo into a loadable bible |
| [future-radio-dressing-room-borges](https://github.com/leo-guinan/future-radio-dressing-room-borges) · [-leonardo](https://github.com/leo-guinan/future-radio-dressing-room-leonardo) · [-agnolo](https://github.com/leo-guinan/future-radio-dressing-room-agnolo) | The principal characters |
| [future-radio-extras](https://github.com/leo-guinan/future-radio-extras) | Characters without a story of their own yet |
| [future-radio-episode-e10](https://github.com/leo-guinan/future-radio-episode-e10) | An episode made in the room, end to end |

## Changing the skill

Pull requests welcome. Keep the skill in step with `docs/MODEL.md`: if a layer's knob changes
in the room, change it here in the same week. Capability requests for the room itself go to
[future-radio-writers-room/proposals](https://github.com/leo-guinan/future-radio-writers-room/tree/main/proposals),
not here.

## License

[CC0 1.0](LICENSE): dedicated to the public domain. Use it, change it, ship it; no permission or credit required.
