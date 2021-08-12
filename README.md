# SoundWave

[![lint](https://github.com/EvasiveXkiller/SoundWave-dev/actions/workflows/lint.yml/badge.svg)](https://github.com/EvasiveXkiller/SoundWave-dev/actions/workflows/lint.yml)
[![spellcheck](https://github.com/EvasiveXkiller/SoundWave-dev/actions/workflows/spellcheck.yml/badge.svg)](https://github.com/EvasiveXkiller/SoundWave-dev/actions/workflows/spellcheck.yml)
> A music bot focused on efficiency

## Announcements

SoundWave has successfully transitioned to Discord V9 API, there might be bugs so please do report if there is any.

If the music stops playing there is a `fix` command that will attempt to fix it. Please see below for more info

For more info, join the [Discord Server](https://discord.gg/d62ZWkVUet)

### Soundwave 4.0.0
- Migrated to Discord V9 API
- Much more stable queue processing mechanism

View more at [changelog](#changelog)

## Commands

All commands need to be prefixed with `=` or the prefix of the server

- [play](#play)
- [playdirect](#playdirect)
- [pause](#pause)
- [resume](#resume)
- [queue](#queue)
- [join](#join)
- [leave](#leave)
- [autoplay](#autoplay)
- [search](#search)
- [skip](#skip)
- [jump](#jump)
- [stop](#stop)
- [shuffle](#shuffle)
- [repeat](#repeat)
- [repeattrack](#repeattrack)
- [repeatqueue](#repeatqueue)
- [player](#player)
- [volume](#volume)
- [seek](#seek)
- [remove](#remove)
- [prune](#prune)
- [ping](#ping)
- [move](#move)
- [moverange](#moverange)
- [invite](#invite)
- [lyrics](#lyrics)
- [effects](#effects)
- [fix](#fix)
- [prefix(NEW!)](#prefix)

<hr>

### play

`=play [link / attached file / query]`

`aliases: p, play`

Command that is used to play a new song on SoundWave

### playdirect

`=playdirect [link]`

`aliases: playdirect, pd, pdirect, direct`

Attempts to directly play a link, throws an error if link cannot be resolved.

### pause

`aliases: pause, holdup`

Pauses the player

### resume

`aliases: resume, continue`

Resumes the player

### queue

`aliases: q, queue, list`

Display the queue for the current server

### join

`aliases: join, j, connect`

Instructs SoundWave to join the channel

### leave

`aliases: leave, dc, goaway`

Instructs SoundWave to leave the channel

### autoplay

`aliases: autoplay, ap`

Turns on autoplay mode. If the last song is not a searchable song, it will fail to turn on.

### search

`=search [query text]`

`aliases: search, se`

Searches the term given and provides an interface to play the song.

### skip

`aliases: skip, next, sk`

Skips the current song and plays the next song.

### jump

`aliases: jump`

Jumps to the specified track and removes all the previous entries

### stop

`aliases: stop, halt`

Stops the player and deletes the queue

### shuffle

`aliases: shuffle, randomize`

Shuffles the queue if there is enough songs

### repeat

`aliases: repeat, loop`

Toggles through all the different loop modes.

### repeattrack

`aliases: repeattrack, repeatt, replay, repeatsong, repeatthis, loopt, lt, looptrack, loopsong, lc`

Repeats the current track only

### repeatqueue

`aliases: repeatqueue, repeatq, repeatplaylist, loopp, lp, lq, loopq, loopqueue, loppplaylist`

Repeats the entire queue

### player

`aliases: player, pl, np`

Shows and interface that can control the player

### volume

`=volume [integer]`

`aliases: volume, v, level`

Changes the volume of SoundWave

### seek

`=seek [timecode]`

`aliases: seek, goto`

Seeks to the position of the song, timecode accepts `seconds` and `MM:SS` formats

### remove

`=remove [index, index2?...]`

`aliases: remove, delete, r`

Examples:
`=remove 2`
`=remove 5 7 8 9`

Removes the song from the queue. Can take multiple songs

### prune

`=prune [integer]`

`aliases: prune`

Deletes the last `nth` messages that are sent by SoundWave

### ping

`aliases: ping, pi, latency`

Shows the latency between the bot and Discord's API

### move

`=move [old_position] [new_position]`

`aliases: move, mv`

Moves a single track to the specified position

### moverange

`=moverange [old_start_range]-[old_end_range] [new_start_range]`

`aliases: moverange, movesongs`

Move a set of tracks to the specified new position

### invite

`aliases: invite`

A link that you can invite SoundWave to another server

### lyrics

`=lyrics [?querytext]`

`aliases: lyrics, lyric`

Searches for lyrics on the provided text, if none is provided then SoundWave will attempt to search from the current
playing song

### fix

`=fix`

`aliases: fix`

Restarts the current instance of the player, to solve issues that are related to player not starting.

### prefix

`=prefix [prefix]`

Changes the bot's prefix to another symbol. If you somehow lost control of the bot, Remove the bot from the server then
re-adding will reset the bot's prefix to its initial state, which is `=`

### Effects

`=effects [effectname]`

`aliases: effects, effects, e`

Add effects to the current playing song.

Side note: Using effects on live songs might cause out of sync issues.

Currently supported effects:

```
tremolo
bassboost
subboost
8d
vaporwave
nightcore
echo
reverb
flanger
chorus
```

# Changelog

### Soundwave v3.4
- Slash Commands are now implemented!
- New command `=jump` Check below for info
- Prefix can now be changed! Use `=prefix` to change. More below
- Soundwave now streams up to 320kbps, if the source origin can handle it.

Stuff that is fixed
- moverange command throwing error
- Race condition when searching is semi fixed

#### SoundWave 3.3 Updates

- Autoplay feature (command list for more details)
- Effects are implemented now! (Check the command list for more details)
- Added new command `fix`
- Major optimizations on server code
- Any issues please let the developer know.

### Links
[Discord Server](https://discord.gg/d62ZWkVUet)

SoundWave Website: [here](https://evasivexkiller.wixsite.com/website/soundwave)




