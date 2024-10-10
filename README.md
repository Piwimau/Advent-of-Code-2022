# 🎄 Advent of Code 2022 🎄

This repository contains my solutions for [Advent of Code 2022](https://adventofcode.com/2022),
my second year of participation.

## What is Advent of Code?

[Advent of Code](https://adventofcode.com/) is a series of small programming puzzles created by
[Eric Wastl](http://was.tl/). Every day from December 1st to 25th, a puzzle is released alongside an
engaging fictional Christmas story. Each puzzle consists of two parts, the second of which usually
contains some interesting twist or changing requirements and is only unlocked after completing the
first one. The objective is to solve all parts and collect fifty stars ⭐ until December 25th to
save Christmas.

Many users compete on the [global leaderboard](https://adventofcode.com/2022/leaderboard) by
solving the puzzles in an unbelievably fast way in order to get some extra points. Personally,
I see Advent of Code as a fun exercise to do during the Advent season while waiting for Christmas.
I often use it to learn a new programming language (like I did in 2021 with `C#`) or some advanced
programming concepts. I can only encourage you to participate as well - of course in a way that you
find fun. Just get started and learn more about Advent of Code
[here](https://adventofcode.com/2022/about).

## About this project

The solutions for Advent of Code 2022 were originally developed using `.NET 7` and `C# 11` at the
time. Since then I have taken some time to update them to more recent versions (`.NET 8` and
`C# 12`), which allowed me to take advantage of new language features and modern data structures
that either did not exist yet or I did not know about (as I was still learning the whole ecosystem).
These include expression bodies (`=>`), collection expressions (`[...]`), target-typed `new()`,
`Span<T>` and `ReadOnlySpan<T>`, types of the `System.Collections.Immutable` or
`System.Collections.Frozen` namespaces and much more.

For this project and in general when developing software, I strive to produce readable and well
documented source code. However, I also enjoy benchmarking and optimizing my code, which is why I
sometimes implement a less idiomatic, yet more efficient solution at the expense of readability.
In those situations, I try to document my design choices with analogies, possible alternative
solutions and sometimes little sketches to better illustrate the way a piece of code works.

The general structure of this project is as follows:

```
Day 1 - Calorie Counting/
    Resources/
        .gitkeep
    Source/
        Benchmark.cs
        CalorieCounting.cs
    Day 1 - Calorie Counting.csproj
Day 2 - Rock Paper Scissors/
    Resources/
        .gitkeep
    Source/
        Benchmark.cs
        RockPaperScissors.cs
    Day 2 - Rock Paper Scissors.csproj
...
Day 25 - Full of Hot Air/
    ...
.gitignore
Advent of Code 2022.sln
LICENSE
README.md
```

On the top level, the [solution file](Advent+of+Code+2022.sln) contains 25 standalone projects
for the days of the Advent calendar, organized into separate directories. Each one provides a
corresponding `.csproj` file that can be opened in Visual Studio. In addition, there are the usual
`Source` and `Resources` directories, the latter of which contains the puzzle description and my
personal input for that day. However, [as requested](https://adventofcode.com/2022/about) by the
creator of Advent of Code, these are only present in my own private copy of the repository and
therefore not publicly available.

> If you're posting a code repository somewhere, please don't include parts of Advent of Code like
  the puzzle text or your inputs.

As a consequence, you will have to provide your own inputs for the days, as described in more detail
in the following section.

## Dependencies and usage

If you want to try one of my solutions, follow these steps below:

0. Make sure you have `.NET 8` or a later version installed on your machine.

1. Clone the repository (or download the source code) to a directory of your choice.

   ```shell
   git clone https://github.com/Piwimau/Advent-of-Code-2022 "./Advent of Code 2022"
   cd "./Advent of Code 2022"
   ```

2. Put your input for the day in a file called `input.txt` and copy it to the appropriate resources
   directory. You can get all inputs from the [official website](https://adventofcode.com/2022) if
   you have not downloaded them already.

   ```shell
   cp input.txt "./Day 1 - Calorie Counting"
   ```

3. Nagivate into the appropriate day's directory.

   ```shell
   cd "./Day 1 - Calorie Counting"
   ```

4. Finally, run the code in release mode to take advantage of all optimizations and achieve the best
   performance.

   ```shell
   dotnet run -c Release
   ```

   Optionally, specify an additional flag `--benchmark` to benchmark the relevant day on your
   machine. Note that in this mode no output for the results of the solved puzzle is produced.

   ```shell
   dotnet run -c Release --benchmark
   ```

If you have Visual Studio installed on your machine, you may also just open the provided
[solution file](Advent+of+Code+2022.sln) and proceed from there.

## Benchmarks

Finally, here are some (non-scientific) benchmarks I created using the fantastic
[BenchmarkDotNet](https://github.com/dotnet/BenchmarkDotNet) package and my main machine (Intel Core
i9-13900HX, 32GB DDR5-5600 RAM) running Windows 11 24H2. All benchmarks include the time spent for
reading the input from disk, as well as printing the puzzle results (although the output is written
to `TextWriter.Null` when benchmarking, which is effectively a no-op and rather fast).

| Day                             | Min      | Max      | Mean     | Median   | Standard Deviation |
|---------------------------------|----------|----------|----------|----------|--------------------|
| Day 1 - Calorie Counting        | 0.074 ms | 0.078 ms | 0.076 ms | 0.076 ms | 0.001 ms           |
| Day 2 - Rock Paper Scissors     | 0.256 ms | 0.268 ms | 0.262 ms | 0.261 ms | 0.003 ms           |
| Day 3 - Rucksack Reorganization | 0.351 ms | 0.373 ms | 0.359 ms | 0.357 ms | 0.007 ms           |
| Day 4 - Camp Cleanup            | 0.149 ms | 0.155 ms | 0.151 ms | 0.150 ms | 0.002 ms           |
| Day 5 - Supply Stacks           | 0.189 ms | 0.202 ms | 0.198 ms | 0.197 ms | 0.003 ms           |
| Day 6 - Tuning Trouble          | 0.032 ms | 0.033 ms | 0.032 ms | 0.032 ms | 0.000 ms           |
| Day 7 - No Space Left On Device | 0.218 ms | 0.225 ms | 0.221 ms | 0.221 ms | 0.002 ms           |
| Day 8 - Treetop Tree House      | 0.549 ms | 0.567 ms | 0.556 ms | 0.558 ms | 0.005 ms           |
| Day 9 - Rope Bridge             | 0.985 ms | 1.024 ms | 1.000 ms | 0.998 ms | 0.011 ms           |
| Day 10 - Cathode-Ray Tube       | 0.024 ms | 0.024 ms | 0.024 ms | 0.024 ms | 0.000 ms           |

## License

This project is licensed under the [MIT License](LICENSE). Feel free to experiment with the code,
adapt it to your own preferences, and share it with others.