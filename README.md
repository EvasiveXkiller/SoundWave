<div align="center">
  <br />
  <p>
    <a href="https://evasivexkiller.wixsite.com/website/soundwave"><img src="https://raw.githubusercontent.com/EvasiveXkiller/SoundWave/main/static/logo.svg" alt="Soundwave" width="800"/></a>
  </p>
  <br />
  <p>
    <a href="https://discord.gg/d62ZWkVUet"><img src="https://img.shields.io/discord/860347110163873842?color=5865F2&label=Discord%20Server&logo=Discord&logoColor=white" alt="Discord server" /></a>
    <a href="https://discord.com/api/oauth2/authorize?client_id=815565837200261131&permissions=2184309840&scope=bot%20applications.commands"><img src="https://img.shields.io/badge/Invite%20Soundwave-Discord-blue" alt="invite soundwave"></a>
    <a href="https://evasivexkiller.wixsite.com/website/donate"><img src="https://img.shields.io/badge/donate-website-F96854.svg" alt="donate" /></a>
  </p>
</div>

## Announcements

[Discord Server](https://discord.gg/d62ZWkVUet)

### SoundWave v5.1

- Added new flags, check out help [play](#play) for more info.
- Fixed `remove` command removing the current song in certain scenarios.
- Added more effects, check out [effects](#effects) of more info.

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
- [prefix](#prefix)

<hr>

### play

`=play [link / attached file / query] [...args?]`

`aliases: p, play`

The main command to play a song on Soundwave, _optional_ arguments can be added

#### Arguments:

Supported arguments:

|  Flags       | Short Flags | Accepted Values               | Description                                                  |
| ------------ | ----------- | ----------------------------- | ------------------------------------------------------------ |
| `--song`     | `-s`        | -                             | Tries to get the music version of the song specified         |
| `--override` | `-o`        | -                             | Overrides the default setting for the detected input, useful when song doesn't exist on the selected search mechanism. |
| `--volume`   | `-v`        | `Number`                      | Sets the volume of the song specified, accepts any seconds or standard time code |
| `--repeat`   | `-r`        | `track` OR `queue`            | Sets the repeat mode of the player when the song is played. |
| `--effect`   | `-e`        | Any valid [effects](#effects) | Sets the effect of the player when reached, accepts any valid effects. If used with a playlist link, only the first song will be applied |
| `--startAt`  | -           | Any valid timecodes           | Begin the song at a certain time. If used with a playlist link, only the first song will be applied |

Examples:

Default prefix is `=`, replace with your server's prefix if applicable

- Searches "Alcohol Free" using default mechanism

```
=play Alcohol Free
```

- Searches "Alcohol Free" and getting the song version of it

```
=play Alcohol Free --song
```

- Parses the Spotify link, and overrides the default search engine behavior as there is no music equivalent to it.

```
=play https://open.spotify.com/track/0BvJvYTy65XrWaVILKVenk?si=a9e6426f285a410c --override
```

This example:

- Plays Alcohol free, while getting the song version of it
- Applies `8d` effects,
- Repeat the current track,
- Begins the song at 1 minute and 35 seconds,
- Sets the track volume at 130%.

```
=play Alcohol Free --song --effect 8d --repeat track --startAt 1:35 --volume 130
```

Things to note:

- The position of arguments is not important. They will be extracted regardless of which comes first.
- Songs with `-` might interfere with the extractor. To avoid this problem remove all `-` from the song name,
- Spotify links will default to search for the music version. This might yield different results depending on the track
  validity on different platforms. To ensure it gets the right track, use the `--overide` flag.
- Arguments are persisted throughout the queue. This allows for simple logic programming of the bot by
  utilizing [`move`](#move)

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

`aliases: volume, v, level, soundwave`

Changes the volume of SoundWave. Volume range 0-200 can be accepted for best experience, however, volume beyond 200 can potentially cause serious physical human parts damage 

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

`aliases: lyrics, lyric, lyr`

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
earrape 
shoppingmall
outsideclub
lofi
```

# Changelog

### SoundWave 5.0.0

- Spotify playlists now loads all songs
- `jump` now maintains queue if `repeatqueue` is true
- `jump` history now selects the correct song

### SoundWave 4.2.0

- `play` command can take arguments now. Check below for syntax errors.
- `search` now identifies the correct user that requested the song

Things that are fixed

- Permission checks are now all modern (hopefully)

### Soundwave v4.1.8

- Unified Engine has been upgraded to v6
- `fix` command has been depreciated
- Max searchable songs inside a playlist has been increased to 1.5k
- Permission checks has been updated

### Soundwave 4.0.0

- Migrated to Discord V9 API
- Much more stable queue processing mechanism

### Soundwave v3.4

- Slash Commands are now implemented!
- New command `=jump` Check below for info
- Prefix can now be changed! Use `=prefix` to change. More below
- Soundwave now streams up to 320kbps, if the source origin can handle it.

Stuff that is fixed

- moverange command throwing error
- Race condition when searching is semi fixed

#### SoundWave 3.3

- Autoplay feature (command list for more details)
- Effects are implemented now! (Check the command list for more details)
- Added new command `fix`
- Major optimizations on server code
- Any issues please let the developer know.

### Links

[Discord Server](https://discord.gg/d62ZWkVUet)

SoundWave Website: [here](https://evasivexkiller.wixsite.com/website/soundwave)

[Top.gg](https://top.gg/bot/815565837200261131)

<div>
<a href="https://discordbotlist.com/bots/815565837200261131"><img src="https://discordbotlist.com/api/v1/bots/815565837200261131/widget" alt="discord list space"></a>
</div>
