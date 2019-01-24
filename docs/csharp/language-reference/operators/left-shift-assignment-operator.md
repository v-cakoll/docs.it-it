---
title: Operatore &lt;&lt;= - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: 4513c4b78dea3e8102c72a43249b4a44ffa2421d
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333252"
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="42dbe-102">Operatore &lt;&lt;= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="42dbe-102">&lt;&lt;= operator (C# Reference)</span></span>

<span data-ttu-id="42dbe-103">Operatore di assegnazione di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="42dbe-103">The left-shift assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="42dbe-104">Note</span><span class="sxs-lookup"><span data-stu-id="42dbe-104">Remarks</span></span>

<span data-ttu-id="42dbe-105">Un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="42dbe-105">An expression of the form</span></span>

```csharp
x <<= y
```

<span data-ttu-id="42dbe-106">viene valutata come</span><span class="sxs-lookup"><span data-stu-id="42dbe-106">is evaluated as</span></span>

```csharp
x = x << y
```

<span data-ttu-id="42dbe-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="42dbe-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="42dbe-108">L'[operatore <<](left-shift-operator.md) sposta `x` verso sinistra del numero di bit specificato da `y`.</span><span class="sxs-lookup"><span data-stu-id="42dbe-108">The [<< operator](left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>

<span data-ttu-id="42dbe-109">L'operatore `<<=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore <<](left-shift-operator.md) (vedere [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="42dbe-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](left-shift-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="42dbe-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="42dbe-110">Example</span></span>

[!code-csharp[csRefOperators#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#12)]

## <a name="see-also"></a><span data-ttu-id="42dbe-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42dbe-111">See also</span></span>

- [<span data-ttu-id="42dbe-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="42dbe-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="42dbe-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="42dbe-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="42dbe-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="42dbe-114">C# Operators</span></span>](index.md)
