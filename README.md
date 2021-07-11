# SoundWave

> A music bot focused on efficiency

### Soundwave v3.3
- Autoplay feature (command list for more details)
- Effects are implemented now! (Check the command list for more details)
- Added new command `fix`
- Major optimizations on server code
- Any issues please let the developer know.

## Commands

All commands need to be prefixed with `=`

- [play](#play)
- [playdirect](#playdirect)
- [pause](#pause)
- [resume](#resume)
- [queue](#queue)
- [join](#join)
- [leave](#leave)
- [autoplay(NEW!)](#autoplay)
- [search](#search)
- [skip](#skip)
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
- [effects(NEW!)](#effects)
- [fix(NEW!)](#fix)

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

`aliases: q, queue`

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

`=remove [index]`

`aliases: remove, delete, r`

Removes the song from the queue

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

`aliases: invite`

Searches for lyrics on the provided text, if none is provided then SoundWave will attempt to search from the current
playing song

### fix

`=fix`

`aliases: fix`

Restarts the current instance of the player, to solve issues that are related to player not starting.

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

### Links
SoundWave Website: [here](https://evasivexkiller.wixsite.com/website/soundwave)




