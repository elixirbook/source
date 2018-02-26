Assuming you already installed Erlang and Elixir, you can run Interactive Elixir Shell (iex) inside your terminal/command line.

## Interactive Elixir
Open command line / terminal, type `iex` and press enter. It will output the Erlang and Elixir versions and the prompot will change to `iex(1)>`. The number will change every time you execute a new command.

IEx is a [repl (Read-Eval-Print Loop)](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop), it will take a single input, evaluate it and return the result. We can tell it to return some [string](https://techterms.com/definition/string), we can add, subtract, divide and multiply two or more than two numbers and get the result back. We can run elixir's built-in functions inside iex, or we can even write our own functions and modules inside iex, we can also run functions written in some file from iex. A single command we enter iex is called an expression.

Let's open iex and enter the following expressions.

    :::elixir
    iex(1)> 1 + 2
    3
    iex(2)> 5 - 3
    2
    iex(3)> 2 + 2 == 4
    true
    iex(4)> 3 * 3 == 10
    false
    iex(5)> 3 + 5 != 20
    true
    iex(6)> 8 > 3
    true
    iex(7)> 2 + 2 > 3
    true
    iex(8)> length([1, 2, 3, 4])
    4
    iex(9)> Float.floor(15.3373, 2)
    15.33
    iex(10)> Calendar.ISO.leap_year?(2018)
    false
    iex(11)> Calendar.ISO.leap_year?(2020)
    true
    iex(12)> add = fn(a, b) -> a + b end
    #Function<12.99386804/2 in :erl_eval.expr/5>
    iex(13) add.(1, 2)
    3

The last six expressions are functions. All functions in Elixir except the anonymous functions are contained by some Module. While calling these functions we have to prepend it with the module (and sub-module) name. 

In expression #9, `Float` is the module and `floor` is the function. In expressions #10 and #11, `Calendar` is the module, `IOS` is the `sub-module` and `leap_year?` is the function.

In expression #8 `length` is part of the module `Kernel` but not prepended by it's name, as it's a built-in function. In the last two expressions we define and then call an anonymous function.

!!!info "" 
    More details on Functions in the _Functions chapter_
