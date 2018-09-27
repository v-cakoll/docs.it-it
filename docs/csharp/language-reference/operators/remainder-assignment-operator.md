---
title: Operatore %= (Riferimenti per C#)
ms.date: 09/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: c475517666bdadaa457dbb4188808b3a96fcdf0e
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085647"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="cf1df-102">Operatore %= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="cf1df-102">%= Operator (C# Reference)</span></span>

<span data-ttu-id="cf1df-103">Operatore di assegnazione di resto.</span><span class="sxs-lookup"><span data-stu-id="cf1df-103">The remainder assignment operator.</span></span>

<span data-ttu-id="cf1df-104">Un'espressione che usa l'operatore `%=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="cf1df-104">An expression using the `%=` operator, such as</span></span>  

```csharp
x %= y
```  

<span data-ttu-id="cf1df-105">equivale a</span><span class="sxs-lookup"><span data-stu-id="cf1df-105">is equivalent to</span></span>  

```csharp
x = x % y
```  

<span data-ttu-id="cf1df-106">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="cf1df-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="cf1df-107">L'[operatore di resto](remainder-operator.md) `%` è supportato da tutti i tipi numerici e calcola il resto dopo la divisione dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="cf1df-107">The [remainder operator](remainder-operator.md) `%` is supported by all numeric types and computes the remainder after division of its operands.</span></span>

<span data-ttu-id="cf1df-108">Se un tipo definito dall'utente [esegue l'overload](../keywords/operator.md) dell'[operatore di resto](remainder-operator.md) `%`, l'operatore di assegnazione di resto `%=` viene sottoposto a overload in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="cf1df-108">If a user-defined type [overloads](../keywords/operator.md) the [remainder operator](remainder-operator.md) `%`, the remainder assignment operator `%=` is implicitly overloaded.</span></span>
  
<span data-ttu-id="cf1df-109">Nell'esempio seguente viene illustrato l'uso dell'operatore `%=`:</span><span class="sxs-lookup"><span data-stu-id="cf1df-109">The following example demonstrates the usage of the `%=` operator:</span></span>

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a><span data-ttu-id="cf1df-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf1df-110">See also</span></span>

- [<span data-ttu-id="cf1df-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="cf1df-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cf1df-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="cf1df-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cf1df-113">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="cf1df-113">C# Operators</span></span>](index.md)
