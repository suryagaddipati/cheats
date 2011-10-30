Cheats
=======

Because you want to refer to your shortcuts not something from internet.


I wanted to see my cheatsheets as a unix man page in the terminal. Ronn
( https://github.com/rtomayko/ronn) allows you to write man pages in
Markdown format.


## ZSH configuation for my 'cheat' command and autocomplete 

 ```bash
  compctl -K _cheats cheat

  _cheats(){
     reply=( `ls ~/code/cheats/*.ronn| xargs -n1 basename |  sed s/.ronn//` )
  }

  cheat(){
    if [[ $1 != *"open"* ]] ; then
      ronn -m ~/code/cheats/$1.ronn
    else
      vi ~/code/cheats/$2.ronn
    fi
  }
```
