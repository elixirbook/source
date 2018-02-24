Assuming you already installed Erlang and Elixir, you can run Interactive Elixir Shell (iex) inside your terminal/command line.

!!! info "Opening command line / terminal (skip if you already know)"
    On Mac, open terminal by pressing `⌘` + `space` and then typing `terminal` to find it. On windows click on the start button and the type `cmd` to open command prompt. On Ubuntu press `ctrl` + `alt` + `t` to open terminal.

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

    

The last 6 expressions need explanation. In Elixir a function is enclosed in a module, and when we call that function we have to prepend it with the module name, e.g., in expression # 9, `Float` is the name of module and `floor` is the name of function.

Sometimes we have a module name, then sub-module name and then the function name, like in expression # 10 and # 11, `Calendar` is the name of module, `IOS` is the name of sub-module and `leap_year?` is the name of function. 

Anonymous functions are an exception to this rule, like in expression # 12 and 13 we define and call an anonymous function respectively. In that case we call the function by putting name of the function, then dot and then the arguments.

Function `length` used in expression #9, have a module named `Kernel`, but we don't need to prepend name of the module. This kind of functions are inlined by the Elixir compiler into the :erlang module and are called `BIFs` (built-in internal functions). `Kernel` module have many `BIFs`.