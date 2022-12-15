# :snake: monty

This is the monty Bytecode Interpreter done as part of our ALX-Holberton Project. This interpreter was built in the C language.

Our interpreter can be run as either a stack (LIFO) or queue (FIFO). Mode can be switched mid-script. The interpreter can handle a variety of Monty opcodes, including printing, mathematical operations, and more - all handled opcodes are listed below.


## :warning: Prerequisites
* [Ubuntu 14.04 LTS](http://releases.ubuntu.com/14.04/) - Operating system reqd.
* [GCC 4.8.4](https://gcc.gnu.org/gcc-4.8/) - Compiler used
* Must have `git` installed.
* Must have repository cloned.

Update first
```
sudo apt-get update
```

Install GIt
```
$ sudo apt-get install git
```

Clone the repository into a new directory:
```
$ git clone https://github.com/BennettDixon/monty.git
```

Compile the c files:
```
gcc -Wall -Werror -Wextra -pedantic *.c -o monty
```

Run the interpreter on a file:
```
./monty file.m
```


## :wrench: Monty Opcodes

* **push**
  * Usage: `push <int>`
  * Pushes an element to the stack.
  * The parameter `<int>` must be an integer.

* **pall**
  * Prints all values in the stack/queue, starting from the top.

* **pint**
  * Prints the top value of the stack/queue.

* **pop**
  * Removes the top element of the stack/queue.

* **swap**
  * Swaps the top two elements of the stack/queue.

* **nop**
  * Does not do anything.

* **add**
  * Adds the top two elements of the stack/queue.
  * The result is stored in the second element from the top and the top element is popped.

* **sub**
  * Subtracts the top element of the stack/queue from the second element from the top.
  * The result is stored in the second element from the top and the top element is removed.

* **mul**
  * Multiplies the top two elements of the stack/queue.
  * The result is stored in the second element from the top and the top element is removed.

* **div**
  * Divides the second element from the top of the stack/queue by the top element.
  * The result is stored in the second element from the top and the top element is removed.

* **mod**
  * Computes the modulus of the second element from the top of the stack/queue divided by the top element.
  * The result is stored in the second element from the top and the top element is removed.

* **pchar**
  * Prints the character value of the top element of the stack/queue.
  * The integer at the top is treated as an ASCII value.

* **pstr**
  * Prints the string contained in the stack/queue.
  * Prints characters element by element until the stack/queue is empty, a value is `0`, or an error occurs.

* **rotl**
  * Rotates the top element of the stack/queue to the bottom.

* **rotr**
  * Rotates the bottom element of the stack/queue to the top.

* **stack**
  * Switches a queue to stack mode.

* **queue**
  * Switches a stack to queue mode.

## :clipboard: Examples

Note, Monty Interpreter runs in the default mode of STACK mode. Meaning it uses a stack. To switch to queue mode, see examples below.

Push values onto the stack and print them all, or the top of the stack/front of queue.

```
$ cat push_pall_pint.m
push 1
push 2
push 3
pall
pint
$ ./monty push_pall_pint.m
3
2
1
3
```

Using mathmatical operations to add, multiply, divide, etc. Takes the second from the top and performs the operation on the top: `second_from_top / top`, `second_from_top - top`, `etc`. Then assigns that to the `second_from_top` and pops the top element off the stack.

```
$ cat math.m
push 3
push 2
push 1
pall
mul
pall
$ ./monty math.m
1
2
3
1
6
```

Entering queue mode to perform all operations in FIFO (queue) mode instead of default LIFO (stack) mode. Note: does not change current stack, sets front of queue to top of stack.

```
$ cat queue.m
queue
push 1
push 2
push 3
pall
stack
push 4
push 5
push 6
pall
$ ./monty queue.m
1
2
3
6
5
4
1
2
3
```

## :books: Coding Style Tests

Strictly followed `Betty` style guide. To install

```
$ git clone https://github.com/holbertonschool/Betty.git

$ cd into Betty then install by ```./install.sh```
```
## :blue_book: Authors

* **Berhane Zerabruk Desta** - [@berhanez](https://github.com/berhanez)

* **Anteneh Mulusew** - [@muluante](https://github.com/muluante)


## :mega: Acknowledgments

* ALX + Holberton School for giving us these challenges to grow and providing us with guidance in this program.
* Stack Overflow (help on various memory errors (not leaks))
<p align="center">
  <img src="http://www.holbertonschool.com/holberton-logo.png">
</p>
