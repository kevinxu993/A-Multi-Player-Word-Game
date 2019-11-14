# A Multi-Player Word Game

A word guessing game implemented in C using socket and select.

## Getting Started

### Prerequisites

* GCC
* Shell (Bash is recommended)

### Download source code and compile
The following instructions are presented using Bash in macOS:
```
# Change to HOME directory
$ cd ~

# Clone this repo and 'cd' into it
$ git clone https://github.com/kevinxu993/A-Multi-Player-Word-Game.git
$ cd A-Multi-Player-Word-Game/

# Let's compile.
$ make
gcc -DPORT=59041 -Wall -g -std=gnu99  -c wordsrv.c
gcc -DPORT=59041 -Wall -g -std=gnu99  -c socket.c
gcc -DPORT=59041 -Wall -g -std=gnu99  -c gameplay.c
gcc -DPORT=59041 -Wall -g -std=gnu99  -o wordsrv wordsrv.o socket.o gameplay.o
```

## Usage
### Server
```
Usage: wordsrv <dictionary filename>
```
### Client
if you are using macOS; then
```
$ nc -c localhost 59041
```
else
```
$ nc -C localhost 59041
```
fi

## Examples
### Server
```
$ ./wordsrv dictionary.txt 
Looking for word at index 55784
A new client is connecting
Waiting for a new connection...
New connection accepted from 127.0.0.1:62315
Connection from 0.0.0.0
Adding client 0.0.0.0
client fd=5 left game without entering a name
Removing client 5 0.0.0.0
A new client is connecting
Waiting for a new connection...
New connection accepted from 127.0.0.1:62321
Connection from 0.0.0.0
Adding client 0.0.0.0
client fd=5 left game without entering a name
Removing client 5 0.0.0.0
A new client is connecting
Waiting for a new connection...
New connection accepted from 127.0.0.1:62324
Connection from 0.0.0.0
Adding client 0.0.0.0
client fd=5 left game without entering a name
Removing client 5 0.0.0.0
A new client is connecting
Waiting for a new connection...
New connection accepted from 127.0.0.1:62326
Connection from 0.0.0.0
Adding client 0.0.0.0
Kevin has just joined
It's Kevin's turn.
It's Kevin's turn.
Letter b is not in the word
It's Kevin's turn.
Letter c is not in the word
It's Kevin's turn.
Letter d is not in the word
No guesses left. Game over.
Looking for word at index 67553
New game.
It's Kevin's turn.
It's Kevin's turn.
Removing client 5 0.0.0.0
^C
```

### Client
```
$ nc -c localhost 59041
Welcome to our word game. What is your name? Kevin    
Kevin has just joined
***************
Word to guess: --------
Guesses remaining: 4
Letters guessed: 

***************
Your guess?
a
Kevin guesses: a
***************
Word to guess: --a-----
Guesses remaining: 3
Letters guessed: 
a 
***************
Your guess?
b
b is not in the word
Kevin guesses: b
***************
Word to guess: --a-----
Guesses remaining: 2
Letters guessed: 
a b 
***************
Your guess?
c
c is not in the word
Kevin guesses: c
***************
Word to guess: --a-----
Guesses remaining: 1
Letters guessed: 
a b c 
***************
Your guess?
d
d is not in the word
Kevin guesses: d
***************
Word to guess: --a-----
Guesses remaining: 0
Letters guessed: 
a b c d 
***************
No guesses left. Game over.

Let's start a new game
***************
Word to guess: --------
Guesses remaining: 4
Letters guessed: 

***************
Your guess?
qw
Invalid guess. Your guess?
q
Kevin guesses: q
***************
Word to guess: --q-----
Guesses remaining: 3
Letters guessed: 
q 
***************
Your guess?
^C
```

## Author(s)

| Name                    | GitHub                                     | Email
| ----------------------- | ------------------------------------------ | -------------------------
| Xinzheng (Kevin) Xu     | [kevinxu993](https://github.com/kevinxu993)| xuxinzheng24@gmail.com

## Thoughts and future improvements

* Since this is a rather simple beginner's project, no further improvements will be made.

## Contributing to this project

1. Fork it [![GitHub forks](https://img.shields.io/github/forks/kevinxu993/A-Multi-Player-Word-Game.svg?style=social&label=Fork&maxAge=2592000&)](https://github.com/kevinxu993/A-Multi-Player-Word-Game/fork)
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to your feature branch (`git push origin my-new-feature`)
5. Create a new Pull Request

Details are described [here](https://git-scm.com/book/en/v2/GitHub-Contributing-to-a-Project).

## Bug Reporting [![GitHub issues](https://img.shields.io/github/issues/kevinxu993/A-Multi-Player-Word-Game.svg?)](https://github.com/kevinxu993/A-Multi-Player-Word-Game/issues/)

Please click `issue` button above↑ to report any issues related to this project  
OR you can shoot an email to <xuxinzheng24@gmail.com>

## License
This project is released under GNU General Public License v3.0 - see [LICENSE](LICENSE) file for more details.
