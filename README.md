# none: A placeholder command to use in scripts
A use case:
```
if [[ $DEBUGPKGS = "" ]]; then
		elif yay -Rns $(yay -Qq | grep -- -debug) --noconfirm &> /dev/null ; then
			notify-send $(echo -e "Removed these packages with a '-debug' suffix:\n$DEBUGPKGS")
		else
        	notify-send "Failed to remove packages with a '-debug' suffix. Try again later!"
    	fi
```
Results in:
```
/usr/bin/rmdebug: line 6: syntax error near unexpected token `elif'
/usr/bin/rmdebug: line 6: `		elif yay -Rns $(yay -Qq | grep -- -debug) --noconfirm &> /dev/null ; then'
```

But with none:
```
		if [[ $DEBUGPKGS = "" ]]; then
			none
		elif yay -Rns $(yay -Qq | grep -- -debug) --noconfirm &> /dev/null ; then
			notify-send $(echo -e "Removed these packages with a '-debug' suffix:\n$DEBUGPKGS")
		else
        	notify-send "Failed to remove packages with a '-debug' suffix. Try again later!"
    	fi
```

No error! ( It might also be that I made a bad script and I have a skill issue but that doesn't matter )
