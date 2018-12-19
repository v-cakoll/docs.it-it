---
title: Operatore %= - Riferimenti per C#
ms.custom: seodec18
ms.date: 09/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: d0732f9578b64c894ecc1d3bb15cee11a8d5b6a3
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245561"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="af45b-102">Operatore %= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="af45b-102">%= Operator (C# Reference)</span></span>

<span data-ttu-id="af45b-103">Operatore di assegnazione di resto.</span><span class="sxs-lookup"><span data-stu-id="af45b-103">The remainder assignment operator.</span></span>

<span data-ttu-id="af45b-104">Un'espressione che usa l'operatore `%=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="af45b-104">An expression using the `%=` operator, such as</span></span>  

```csharp
x %= y
```  

<span data-ttu-id="af45b-105">equivale a</span><span class="sxs-lookup"><span data-stu-id="af45b-105">is equivalent to</span></span>  

```csharp
x = x % y
```  

<span data-ttu-id="af45b-106">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="af45b-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="af45b-107">L'[operatore di resto](remainder-operator.md) `%` calcola il resto dopo la divisione dei due operandi.</span><span class="sxs-lookup"><span data-stu-id="af45b-107">The [remainder operator](remainder-operator.md) `%` computes the remainder after division of its operands.</span></span> <span data-ttu-id="af45b-108">È supportato da tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="af45b-108">It's supported by all numeric types.</span></span>

<span data-ttu-id="af45b-109">Se un tipo definito dall'utente [esegue l'overload](../keywords/operator.md) dell'[operatore di resto](remainder-operator.md) `%`, l'operatore di assegnazione di resto `%=` viene sottoposto a overload in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="af45b-109">If a user-defined type [overloads](../keywords/operator.md) the [remainder operator](remainder-operator.md) `%`, the remainder assignment operator `%=` is implicitly overloaded.</span></span>
  
<span data-ttu-id="af45b-110">Nell'esempio seguente viene illustrato l'uso dell'operatore `%=`:</span><span class="sxs-lookup"><span data-stu-id="af45b-110">The following example demonstrates the usage of the `%=` operator:</span></span>

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a><span data-ttu-id="af45b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af45b-111">See also</span></span>

- [<span data-ttu-id="af45b-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="af45b-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="af45b-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="af45b-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="af45b-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="af45b-114">C# Operators</span></span>](index.md)
