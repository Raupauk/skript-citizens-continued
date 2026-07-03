# skript-citizens-continued

A continued fork of [nylhus/skript-citizens](https://github.com/nylhus/skript-citizens), updated to work with modern Skript and Paper versions. The original addon has been unmaintained since 2023 and stopped working after Skript's registration API overhaul in 2.10+/2.15.

## Requirements

- **Skript** 2.15.0 or newer
- **Paper** 1.21.1 or newer (Spigot alone is no longer supported by Skript)
- **Citizens** 2.0.x
- **Java** 21 or newer

## What changed from the original

- Updated the Skript dependency from `2.7.0-beta3` to `2.15.4`
- Replaced the removed `EventValues.registerEventValue(Class, Class, Getter, int)` call with the still-supported `Converter`-based overload
- Migrated from the deprecated `ch.njol.skript.registrations.Converters` to `org.skriptlang.skript.lang.converter.Converters`
- Switched the build from Spigot API to Paper API
- Bumped Java compatibility to 21
- Updated the Citizens dependency version

**No syntax changes** — all existing scripts written for the original skript-citizens should work without modification.

## Installation

1. Make sure [Skript](https://github.com/SkriptLang/Skript) (2.15+) and [Citizens](https://www.spigotmc.org/resources/citizens.13811/) are installed on your server.
2. Download the latest `.jar` from the [Releases](../../releases) page.
3. Drop it into your `plugins/` folder.
4. Restart your server.

## Building from source

```bash
git clone https://github.com/Raupauk/skript-citizens-continued.git
cd skript-citizens-continued
./gradlew clean build
```

The compiled jar will be in `build/libs/`.

## Syntax examples

```
# Spawning
spawn a zombie citizen named "Guard" at player's location

# Retrieving
set {_npc} to citizen from id 0
set {_npc} to citizen from entity event-entity

# Events
on npc click:
    broadcast "%event-npc% was clicked by %player%!"

on npc spawn:
    broadcast "An NPC spawned at %event-location%"

# Conditions
if event-entity is a citizen:
    broadcast "That's an NPC!"

# Despawning
despawn last spawned npc
```

For the full list of expressions, effects, conditions and events, check the Skript documentation generated from this addon (`/skript gen-docs` on your server) or browse the source under `src/main/java/ca/nylhus/skriptcitizens/elements/`.

## Credits

- Original addon by [nylhus](https://github.com/nylhus)
- Maintenance/compatibility updates by [Raupauk](https://github.com/Raupauk)

## License

GPLv3, same as the original project. See [LICENSE](LICENSE).
