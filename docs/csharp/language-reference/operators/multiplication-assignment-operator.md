---
title: Operatore *= - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 2038f3b55d46f3503496275b3d25b17663b8c1db
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333434"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a396b-102">Operatore \*= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a396b-102">\*= Operator (C# Reference)</span></span>

<span data-ttu-id="a396b-103">Operatore di assegnazione di moltiplicazione binario.</span><span class="sxs-lookup"><span data-stu-id="a396b-103">The binary multiplication assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="a396b-104">Note</span><span class="sxs-lookup"><span data-stu-id="a396b-104">Remarks</span></span>

<span data-ttu-id="a396b-105">Un'espressione che usa l'operatore di assegnazione `*=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="a396b-105">An expression using the `*=` assignment operator, such as</span></span>

```csharp
x *= y
```

<span data-ttu-id="a396b-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="a396b-106">is equivalent to</span></span>

```csharp
x = x * y
```

<span data-ttu-id="a396b-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="a396b-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="a396b-108">Per i tipi numerici l'[operatore \*](multiplication-operator.md) è predefinito per l'esecuzione di moltiplicazioni.</span><span class="sxs-lookup"><span data-stu-id="a396b-108">The [\* operator](multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>

<span data-ttu-id="a396b-109">L'operatore `*=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore \*](multiplication-operator.md) (vedere [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="a396b-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [\* operator](multiplication-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="a396b-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="a396b-110">Example</span></span>

[!code-csharp[csRefOperators#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#13)]

## <a name="see-also"></a><span data-ttu-id="a396b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a396b-111">See also</span></span>

- [<span data-ttu-id="a396b-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a396b-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a396b-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a396b-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a396b-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="a396b-114">C# Operators</span></span>](index.md)
