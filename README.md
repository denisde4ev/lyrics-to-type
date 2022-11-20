# lyrics-to-type
Some lyrics that I type on the terminal.

## WARRANTY:
I did not wrote those song lyrics / text. Please look at `SOURCE:` at song-\* and text-\* files.<br>
With the exeption for files that have `SOURCE: SELF MADE` or `SOURCE: ME`.<br>
<br>
Some songs such as "song-My_Neck,_My_Back_(Lick_It)" may contain uncensored words.<br>


## How I use this:
`$ bash song-fsf; song-fsf | tt;`<br>
or when I just want something random: `$ song=$(song_shuf); bash "${song}"; "${song}" | tt`<br>
`tt` is my fork [denisde4ev/tt-nobgcolor](https://github.com/denisde4ev/tt-nobgcolor) of [lemnos/tt](https://github.com/lemnos/tt) that just disables background color. <br>
[my tt is aliased to `time tt-split -showwpm -noskip -oneshot`](https://github.com/denisde4ev/shrc/blob/df3a0e2f93def01789da6956372eeb8b88922d1c/a#L90), [tt-split](https://github.com/denisde4ev/bin/blob/master/tt-split) splits input by '\n\n' before piping it to `tt` and by default passes -raw option<br>
`$ bash "${song}"` for *most* of the song files will open(*xdg-open*) source to listen YouTube/Sopotify/Deezer/etc. that I have saved as song source. (Semetimes source to listen is remix/nightcore)<br>


## Structure of files:

note: files are mess of old versions of this stucture (bat/tail) (xdg-open '...' / echo not for shells) (SOURCE: ?)

### 1. song-\*
For example song-impossible
```
$ head song-impossible
#!/usr/bin/bat -r5:
exec printf %s\\n 'original: https://deezer.page.link/uyk81ugQZEAe6vnT8' 'nightcore version: https://deezer.page.link/Eq67FE6FTwNx4xLJ6' | fzf | grep -o https.* | xargs -r -d \\n xdg-open;exit
SOURCE: AZLirics
############################################################
I remember years ago
Someone told me I should take
Caution when it comes to love
I did, I did
And you were strong, and I was not
My illusion, my mistake
```

##### song-\* shebang:
header: `bat -r5:` prints/opens in pager everithing from 5-th line and after.<br>
I rearly use it in pager, I just pipe it to `tt` `$ song-impossible | tt`.<br>
For this purpose shebang `#!/bin/tail -n+6` would also work just fine. (some files still have it like this)<br>


#### song-\* open song url:
`xdg-open` is used when called by `bash song-impossible`<br>
for some songs .in ths case song-impossible is "Nightcore Impossible (Rock Version)" in Deezer<br>

BTW ` | fzf | grep | xargs xdg-open` first time used for this file song-impossible.<br>
Others have: `exec xdg-open 'https://...`<br>
or the older one: `exit 1 # NOT FOR SHELLS`.<br>

### 2. song_gen
Used to generate new *song-\** file<br>
I rearly call it when I want to generate new song,<br>
I just use my [command_not_fund_handle -> "song-* does not exist, do you want to create it now? [Y/n]"](https://github.com/denisde4ev/shrc/blob/b7cdfd873620816c95203297927a89b2febda8cf//__sourceable/command_not_found_handle#L128)<br>

### 3. song_shuf
Just print random song-* to stdout<br>

### 4. song
A random parts of lyrics I found.<br>
I use it as `alias song=_song` https://github.com/denisde4ev/shrc/blob/master/_loadable/_song.sh (I sorry for the quality of the script with those non-POSIX --null options, it works well enough for me)<br>

### 5. text-\*
same as song-\*

### 6. song_fzf
choose song from fzf and print it to stdout


## my tt alias+wrapper *mess* tracked:
alias tt='time tt-split -showwpm -noskip -oneshot' from here https://github.com/denisde4ev/shrc/blob/df3a0e2f93def01789da6956372eeb8b88922d1c/a#L90 <br>
tt-split is https://github.com/denisde4ev/bin/blob/master/tt-split



## todo: what about those files:
_/<br>
.-todo-LetraX<br>
tt-shuf-song<br>

## todo:
song_gen-new
