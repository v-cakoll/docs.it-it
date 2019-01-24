---
title: Operatore |= - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: f4f7806c8679af400a371decd0c367929b3fb81d
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333265"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="5cc6f-102">Operatore |= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5cc6f-102">|= operator (C# Reference)</span></span>

<span data-ttu-id="5cc6f-103">Operatore di assegnazione OR.</span><span class="sxs-lookup"><span data-stu-id="5cc6f-103">The OR assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="5cc6f-104">Note</span><span class="sxs-lookup"><span data-stu-id="5cc6f-104">Remarks</span></span>

<span data-ttu-id="5cc6f-105">Un'espressione che usa l'operatore di assegnazione `|=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="5cc6f-105">An expression using the `|=` assignment operator, such as</span></span>

```csharp
x |= y
```

<span data-ttu-id="5cc6f-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="5cc6f-106">is equivalent to</span></span>

```csharp
x = x | y
```

<span data-ttu-id="5cc6f-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="5cc6f-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="5cc6f-108">L'[operatore &#124;](or-operator.md) esegue un'operazione con OR logico bit per bit su operandi integrali e un'operazione con OR logico sugli operandi bool.</span><span class="sxs-lookup"><span data-stu-id="5cc6f-108">The [&#124; operator](or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>

<span data-ttu-id="5cc6f-109">L'operatore `|=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore &#124;](or-operator.md) (vedere [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="5cc6f-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](or-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="5cc6f-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="5cc6f-110">Example</span></span>

[!code-csharp[csRefOperators#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#10)]

## <a name="see-also"></a><span data-ttu-id="5cc6f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cc6f-111">See also</span></span>

- [<span data-ttu-id="5cc6f-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="5cc6f-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5cc6f-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5cc6f-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5cc6f-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="5cc6f-114">C# operators</span></span>](index.md)