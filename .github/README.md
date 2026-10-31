# AzerothCore Playerbots core — portable integration

This fork supplies the WoW 3.3.5a (build 12340) core for
[AzerothCore Playerbots Portable](https://github.com/Syntax555/mod-playerbots-portable).
It combines the Playerbots core APIs with earned-era spell, experience,
riding and PvP rules used by the assembly's matching modules.

## Install or build

For normal use, download the Windows server and matching EraTalents client pack
from the assembly's [Latest release](https://github.com/Syntax555/mod-playerbots-portable/releases/latest),
then follow its [quick start](https://github.com/Syntax555/mod-playerbots-portable#quick-start).

For source builds, use the assembly's
[build guide](https://github.com/Syntax555/mod-playerbots-portable/blob/main/docs/building.md).
Its [versions.lock.json](https://github.com/Syntax555/mod-playerbots-portable/blob/main/versions.lock.json)
selects the exact core commit and all matching module commits. This fork's
`master` branch is the development branch; use the locked revisions to
reproduce an assembly. Mixing this core with other module revisions is not a
verified configuration.

## Behavior and scope

Content access follows each character's earned Individual Progression era,
independently of level, account or party leader. Historical talents require the
matching EraTalents server module and client files. Humans, active SelfBots and
controlled altbots retain their normal character rights and manual talents.
The assembly configures these integrations in `configs/worldserver.conf` and
`configs/modules/`; cloning the core alone does not apply those settings.

Native personal-bank handlers update delivery-quest counters before removing
deposits and credit only the transferred amount when withdrawals merge stacks.
Banker access and ordinary item/storage checks remain authoritative.

The engine and client remain Wrath-based. Selected historical rules do not make
this an exact Vanilla or original TBC simulation. Source fixtures cover specific
contracts; they do not establish complete gameplay, raid, class or population
coverage. See the [supported scope](https://github.com/Syntax555/mod-playerbots-portable/blob/main/docs/configuration.md#supported-scope)
and [validation work](https://github.com/Syntax555/mod-playerbots-portable/blob/main/docs/todo.md).

## Development and provenance

Read [AGENTS.md](../AGENTS.md), the assembly's
[contributing guide](https://github.com/Syntax555/mod-playerbots-portable/blob/main/CONTRIBUTING.md)
and [core integration reference](https://github.com/Syntax555/mod-playerbots-portable/blob/main/docs/module-versions.md#server-modules).
Make validated changes on `master`, then update the assembly pin. Preserve
earned-play gates, characters, databases, configuration and pinned history.

This core follows
[Grimfeather/azerothcore-wotlk at `38db9bb1b588`](https://github.com/Grimfeather/azerothcore-wotlk/commit/38db9bb1b588a2562ebcb052af1175a9429e32e6),
which adds the core changes of Grimfeather's Individual Progression to the
Playerbots core
[mod-playerbots/azerothcore-wotlk at `93333d6a9eb0`](https://github.com/mod-playerbots/azerothcore-wotlk/commit/93333d6a9eb00fdf0179adde30da3c17618207d6).
Its [original README](https://github.com/mod-playerbots/azerothcore-wotlk/blob/93333d6a9eb00fdf0179adde30da3c17618207d6/.github/README.md)
and [AzerothCore wiki](https://www.azerothcore.org/wiki/) provide general engine
and API documentation; the assembly guides define this fork's installation.

Credits remain with AzerothCore, the Playerbots core contributors, Grimfeather,
SunwellCore, TrinityCore, MaNGOS and the [authors](../AUTHORS). Keep the
[GPL-2.0 license](../LICENSE), individual GPL/AGPL source notices and dependency
licenses with their files.
