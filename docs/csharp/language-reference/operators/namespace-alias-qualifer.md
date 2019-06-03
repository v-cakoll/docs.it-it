---
title: 'Operatore :: - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 0b456ed3ce9965ef389d8ce40167afa4ac33da18
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422531"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a13e8-102">Operatore :: (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a13e8-102">:: operator (C# Reference)</span></span>

<span data-ttu-id="a13e8-103">Il qualificatore di alias dello spazio dei nomi (`::`) viene usato per cercare gli identificatori.</span><span class="sxs-lookup"><span data-stu-id="a13e8-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="a13e8-104">Viene sempre posizionato tra due identificatori, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a13e8-104">It is always positioned between two identifiers, as in this example:</span></span>

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

<span data-ttu-id="a13e8-105">L'operatore `::` può anche essere usato con una *direttiva using alias*:</span><span class="sxs-lookup"><span data-stu-id="a13e8-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="a13e8-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a13e8-106">Remarks</span></span>

<span data-ttu-id="a13e8-107">Il qualificatore di alias dello spazio dei nomi può essere `global`.</span><span class="sxs-lookup"><span data-stu-id="a13e8-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="a13e8-108">In questo modo viene richiamata una ricerca nello spazio dei nomi globale anziché in uno spazio dei nomi con alias.</span><span class="sxs-lookup"><span data-stu-id="a13e8-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="a13e8-109">Per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="a13e8-109">For more information</span></span>

<span data-ttu-id="a13e8-110">Per un esempio di utilizzo dell'operatore `::`, vedere la seguente sezione:</span><span class="sxs-lookup"><span data-stu-id="a13e8-110">For an example of how to use the `::` operator, see the following section:</span></span>

- [<span data-ttu-id="a13e8-111">Procedura: Usare l'alias dello spazio dei nomi globale</span><span class="sxs-lookup"><span data-stu-id="a13e8-111">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="a13e8-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a13e8-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a13e8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a13e8-113">See also</span></span>

- [<span data-ttu-id="a13e8-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a13e8-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a13e8-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a13e8-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a13e8-116">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="a13e8-116">C# operators</span></span>](index.md)
- [<span data-ttu-id="a13e8-117">Operatore .</span><span class="sxs-lookup"><span data-stu-id="a13e8-117">. operator</span></span>](member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="a13e8-118">alias extern</span><span class="sxs-lookup"><span data-stu-id="a13e8-118">extern alias</span></span>](../keywords/extern-alias.md)
