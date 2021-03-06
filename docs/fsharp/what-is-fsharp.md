---
title: '什么是 F #'
description: '了解有关 F # 编程语言的含义和新增 F # 编程。 了解丰富的数据类型、 函数和它们如何组合在一起。'
ms.date: 08/03/2018
ms.openlocfilehash: 193747f380c61a387ed79ecca6abbcd90ee74376
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863291"
---
# <a name="what-is-f"></a>什么是 F # #

F # 是函数式编程语言，轻松地编写正确、 可维护代码。

F # 编程主要包括定义类型和函数的类型推断和自动通用化。 这样，你只需重点关注的问题域和操作其数据，而不是编程的详细信息。

```fsharp
open System // Gets access to functionality in System namespace.

// Defines a function that takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

[<EntryPoint>]
let main args =
    // Defines a list of names
    let names = [ "Don"; "Julia"; "Xi" ]

    // Prints a greeting for each name!
    names
    |> List.map getGreeting
    |> List.iter (fun greeting -> printfn "%s" greeting)

    0
```

F # 具有许多功能，包括：

* 轻量语法
* 默认情况下不可变
* 类型推理和自动泛化
* 第一类函数
* 功能强大的数据类型
* 模式匹配
* 异步编程

中介绍了一套完整的功能[F # 语言参考](language-reference/index.md)。

## <a name="rich-data-types"></a>丰富的数据类型

数据类型，如[记录](language-reference/records.md)并[可区分联合](language-reference/discriminated-unions.md)可以表示复杂的数据和域。

```fsharp
// Group data with Records
type SuccessfulWithdrawal = {
    Amount: decimal
    Balance: decimal
}

type FailedWithdrawal = {
    Amount: decimal
    Balance: decimal
    IsOverdraft: bool
}

// Use discriminated unions to represent data of 1 or more forms
type WithdrawalResult =
    | Success of SuccessfulWithdrawal
    | InsufficientFunds of FailedWithdrawal
    | CardExpired of System.DateTime
    | UndisclosedFailure
```

F # 记录和可辨识的联合为非 null、 不可变的和默认情况下，使它们非常易于使用的比较。

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a>已强制实施的正确性，有的功能和模式匹配

F # 函数是轻松地声明和在实践中功能强大。 再加上[模式匹配](language-reference/pattern-matching.md)，它们允许您定义由编译器强制执行其正确性的行为。

```fsharp
// Returns a WithdrawalResult
let withdrawMoney amount = // Implementation elided

let handleWithdrawal amount =
    let w = withdrawMoney amount

    // The F# compiler enforces accounting for each case!
    match w with
    | Success s -> printfn "Successfully withdrew %f" s.Amount
    | InsufficientFunds f -> printfn "Failed: balance is %f" f.Balance
    | CardExpired d -> printfn "Failed: card expired on %O" d
    | UndisclosedFailure -> printfn "Failed: unknown :("
```

F # 函数也是第一类，这意味着它们可作为参数传递，从其他函数返回的。

## <a name="functions-to-define-operations-on-objects"></a>函数来定义对对象的操作

F # 提供对象，都需要进行混合数据和功能的有用的数据类型的完整的支持。 F # 函数用于操作对象。

```fsharp
type Set<[<EqualityConditionOn>] ‘T when ‘T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

[<RequireQualifiedAccess>]
module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

而不是编写代码是面向对象，在 F # 中，您将经常编写代码将对象与另一个数据类型的函数来操作。 等功能[泛型接口](language-reference/interfaces.md)，[对象表达式](language-reference/object-expressions.md)，和明智地使用[成员](language-reference/members/index.md)在较大的 F # 程序中很常见。

## <a name="next-steps"></a>后续步骤

若要了解有关 F # 功能的一大组的详细信息，请查看[F # 简介](tour.md)。