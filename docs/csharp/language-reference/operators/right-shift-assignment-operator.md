---
title: '>>Operatore = - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 8cc341c14ee1b90fde2abb369c187e57b4ce5c00
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278980"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="57fc3-102">Operatore >>= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="57fc3-102">>>= operator (C# Reference)</span></span>

<span data-ttu-id="57fc3-103">Operatore di assegnazione di spostamento a destra.</span><span class="sxs-lookup"><span data-stu-id="57fc3-103">The right-shift assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="57fc3-104">Note</span><span class="sxs-lookup"><span data-stu-id="57fc3-104">Remarks</span></span>

<span data-ttu-id="57fc3-105">Un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="57fc3-105">An expression of the form</span></span>

```csharp
x >>= y
```

<span data-ttu-id="57fc3-106">viene valutata come</span><span class="sxs-lookup"><span data-stu-id="57fc3-106">is evaluated as</span></span>

```csharp
x = x >> y
```

<span data-ttu-id="57fc3-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="57fc3-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="57fc3-108">L'[operatore >>](right-shift-operator.md) sposta `x` verso destra di una quantità specificata da `y`.</span><span class="sxs-lookup"><span data-stu-id="57fc3-108">The [>> operator](right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>

<span data-ttu-id="57fc3-109">L'operatore >>= non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore >>](right-shift-operator.md) (vedere [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="57fc3-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](right-shift-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="57fc3-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="57fc3-110">Example</span></span>

[!code-csharp[csRefOperators#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#11)]

## <a name="see-also"></a><span data-ttu-id="57fc3-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57fc3-111">See also</span></span>

- [<span data-ttu-id="57fc3-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="57fc3-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="57fc3-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="57fc3-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="57fc3-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="57fc3-114">C# operators</span></span>](index.md)