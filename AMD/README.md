# AMD overclocking patches for undervolting

I've pretty much automated the entire process and made it simple to reapply the patch after HiveOS upgrades overwrite the changes to the amd-oc script.

All you really have to do is step #1, but steps 2-4 are just to verify everything did what it was supposed to.

I hope this helps everyone save money on the electric bill like I did.

If you are so inclined to donate to a poor miner's cause, I would graciously accept anything!

```
Ethereum: 0x7472a4812200fc320793a946f027d559e63b164d
Ethereum Classic: 0xc5b3e79fb542c6c8b2b8b71406a8e275b9b783b7
```

```
Bitcoin: 1LvnfMGfz8xTaZgi25DiRFaJoFvpAPncT5
Bitcoin Cash: 1Ec3CPq3WPsWT7fQaDGgTYkVPNtMZ3CVaA
```

```
Litecoin: LSZBbS7EsKnjXQ1FKxYuAmR5quzEazXfm1
```

```
Monero: 45kv3V7hAA48JH9eZjKM1HLub8wFnkJ4ugqKNPsnmKzbE6t9tYuRqgb3mGwXJDLMePACJNrnsWx4uGaLxJM8adN2LC1Sqap.d7a674172a634431ad96750cff0c45100f3e7bdc31134e928e7ec42fc971c050
```

```
EOS: 0x7472a4812200fc320793a946f027d559e63b164d
```

```
Electroneum: etnk3yDpybAEBqz3nq63qmev4thRi9eFH64CVKzZc2w3A7vehpZkGvd97uSWxtmtAwjTnfKEp9Rup3md7nZyu9Q49VzZQKhxWN
```

```
Sia Coin: 2976b8836ab38c51acbbd9f96f02674a62761251053ef9e5b9f9c1feaed5ea0022728ea4f7a3
```



## Initial patch command
```
1. curl -Ls https://goo.gl/pJEzAQ | bash
```

```
root@hiveos:~# curl -Ls https://goo.gl/pJEzAQ | bash
Starting AMD OC patch process ...

Hmm...  Looks like a new-style context diff to me...
The text leading up to this was:
--------------------------
|*** amd-oc	2018-05-30 22:13:23.444157036 -0400
|--- amd-oc.kuzuri	2018-05-30 22:13:12.528341266 -0400
--------------------------
patching file amd-oc
Using Plan A...
Hunk #1 succeeded at 165.
Hunk #2 succeeded at 187.
Hunk #3 succeeded at 204.
done

AMD OC patching complete.

Attempting to add an alias: amd-oc-patch
	Alias 'amd-oc-patch' added.
	You can use that command to patch amd-oc after HiveOS upgrades.
```


## Verify the amd-oc-patch alias was created
```
2. cat .bash_aliases
```

```
root@hiveos:~# cat .bash_aliases
alias sud='sudo -s'
alias t='tail -n 100 -f'
alias mc='mc --nomouse'
alias s='systemctl'
alias j='journalctl'
alias sr='screen -r'
alias sx='screen -x'
alias amd-oc-patch="curl -Ls https://goo.gl/pJEzAQ | bash"
```


## Reload the aliases (or log out and back in)
```
3.  . .bash_aliases
```

```
root@hiveos:~# . .bash_aliases
```


## Verify amd-oc-patch is there
```
4. alias
```

```
root@hiveos:~# alias
alias alert='notify-send --urgency=low -i "$([ $? = 0 ] && echo terminal || echo error)" "$(history|tail -n1|sed -e '\''s/^\s*[0-9]\+\s*//;s/[;&|]\s*alert$//'\'')"'
alias amd-oc-patch='curl -Ls https://goo.gl/pJEzAQ | bash'
alias egrep='egrep --color=auto'
alias fgrep='fgrep --color=auto'
alias grep='grep --color=auto'
alias j='journalctl'
alias l='ls -CF'
alias la='ls -A'
alias ll='ls -alF'
alias ls='ls --color=auto'
alias mc='mc --nomouse'
alias s='systemctl'
alias sr='screen -r'
alias sud='sudo -s'
alias sx='screen -x'
alias t='tail -n 100 -f'
```

## This is what happens if you try and patch an already patched amd-oc
### Just hit ENTER twice if you do this!
```
root@hiveos:~# amd-oc-patch
Starting AMD OC patch process ...

Hmm...  Looks like a new-style context diff to me...
The text leading up to this was:
--------------------------
|*** amd-oc	2018-05-30 22:13:23.444157036 -0400
|--- amd-oc.kuzuri	2018-05-30 22:13:12.528341266 -0400
--------------------------
patching file amd-oc
Using Plan A...
Reversed (or previously applied) patch detected!  Assume -R? [n]
Apply anyway? [n]
Skipping patch.
Hunk #1 ignored at 165.
Hunk #2 ignored at 187.
Hunk #3 ignored at 204.
3 out of 3 hunks ignored -- saving rejects to file amd-oc.rej
done

AMD OC patching complete.

Attempting to add an alias: amd-oc-patch
	Alias 'amd-oc-patch' exists.
```

## After every HiveOS upgrade run 'amd-oc-patch' again
```
root@hiveos:~# amd-oc-patch
```

# THE END OF THE INTERNETS
