+++
author = "Tunç Bahçecioğlu"
title = "Why I still hate Object oriented programming"
date = "2023-06-24"
description = "Why I still hate Object oriented programming"
tags = [
    "programming",
    "oop",
]
categories = [
    "programming",
]
series = ["programming"]
aliases = ["oop-hate-2"]
+++

I still hate object oriented programming...
<!--more-->

In a previous post I wrote about how OOP was actually a domain design system and leads to complicated and inter-connected code. I also established that I hated OOP because it gives you the tools to create evil and at the end leads to violence.

And I still hate object oriented programming but at this point I want to pause hating OOP and be a little bit more constructive. I'd like to talk about an alternative. By no means this is the single alternative nor the best one, and probably there are many like it but this one is mine.

## **G**room your data and algorithms.

Your data and algorithms need grooming. And you cannot groom them together, they need to be separated.

```cpp
struct MyInput;

struct MyOutput;

auto MyAlgorithm(const MyInput &input) -> MyOutput;
```

Don't put your input data, output data and your algorithms into the same structure they deserve individual attention.

## **E**liminate properties.

Properties are tiny bits of algorithms and algorithms should not be combined with data.
Use POD structures for your inputs and outputs.
Plain old data is your friend.

```cpp
struct Point
{
  double x;
  double y;
  double z;

  // No need for getX, setX functions.
}
```

## **O**perations are transformations.

Every operation is actually a transformation between the input to the output. So write your algorithms in terms of transformations, especially pure ones.

```cpp
struct Data1;
struct Data2;
struct Data3;

auto Transform1(const Data1 &input) -> Data2;
auto Transform2(const Data2 &input) -> Data3;

```

## **S**uit your transformations to your needs.

Transformations can be customized using customizations points. The simplest customization point is just a function. If you want more you can use overload sets in C++ or something similar to interfaces, every programming language has some version of them like traits in Rust.

```cpp
template <auto InputData, auto OutputData, auto MyCustomizer>
auto Transform(const InputData &input, MyCustomizer fun) -> OutputData
{
    if (fun(input)) {} // customization
}
```

Design patterns are indirections, indirections can be implemented using customization points and with enough indirections you can implement anything.

## **I**nabilities are not exceptions.

Your transformation might not be able to handle all inputs. But don't use exceptions for these cases. Instead use Optional or Expected. Make sure that the caller knows something might go wrong.
Exceptions are for fatal flaws only.

```cpp
auto Transform1(const Data1 &input) -> std::optional<Data2>;
{
    if (input.value <= 0) return std::nullopt;

    // ...
}
```

## **Merge** your algorithms into pipelines.

Mingle your algorithms to form pipelines.
Don't use implicit conditions like events to connect them, do it explicitly.

Explicit pathways are easy to understand and easy to change.

```cpp
auto executePipeline(const Input &input) -> void;
{
    auto data1 = transform1(input);
    auto data2 = transform2(data1);
    auto data3 = transform3(data2);
    auto data4 = transform4(data3);
    send(data4);
}
```

We can bind the four transformations together using events attached to data, like when data1 is changed call transform1. However a pipeline will be more explicit. And explicit is better than implicit.

## The G.E.O.S.I.M. method.

* **G**room your data and algorithms.
* **E**liminate properties.
* **O**perations are transformations.
* **S**uit your transformations to your needs.
* **I**nabilities are not exceptions.
* **M**erge your algorithms in pipelines.

Don't choose violence (OOP), choose G.E.O.S.I.M.
