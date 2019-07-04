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
ms.openlocfilehash: c494e8dbb18f44ce5520b21800a21d3feb03da59
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025068"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a97c0-102">Operatore :: (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a97c0-102">:: operator (C# reference)</span></span>

<span data-ttu-id="a97c0-103">Il qualificatore di alias dello spazio dei nomi (`::`) viene usato per cercare gli identificatori.</span><span class="sxs-lookup"><span data-stu-id="a97c0-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="a97c0-104">Viene sempre posizionato tra due identificatori, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a97c0-104">It is always positioned between two identifiers, as in this example:</span></span>

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

<span data-ttu-id="a97c0-105">L'operatore `::` può anche essere usato con una *direttiva using alias*:</span><span class="sxs-lookup"><span data-stu-id="a97c0-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="a97c0-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a97c0-106">Remarks</span></span>

<span data-ttu-id="a97c0-107">Il qualificatore di alias dello spazio dei nomi può essere `global`.</span><span class="sxs-lookup"><span data-stu-id="a97c0-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="a97c0-108">In questo modo viene richiamata una ricerca nello spazio dei nomi globale anziché in uno spazio dei nomi con alias.</span><span class="sxs-lookup"><span data-stu-id="a97c0-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="a97c0-109">Per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="a97c0-109">For more information</span></span>

<span data-ttu-id="a97c0-110">Per un esempio di utilizzo dell'operatore `::`, vedere la seguente sezione:</span><span class="sxs-lookup"><span data-stu-id="a97c0-110">For an example of how to use the `::` operator, see the following section:</span></span>

- [<span data-ttu-id="a97c0-111">Procedura: Usare l'alias dello spazio dei nomi globale</span><span class="sxs-lookup"><span data-stu-id="a97c0-111">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="a97c0-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a97c0-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a97c0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a97c0-113">See also</span></span>

- [<span data-ttu-id="a97c0-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a97c0-114">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a97c0-115">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="a97c0-115">C# operators</span></span>](index.md)
- [<span data-ttu-id="a97c0-116">Operatore .</span><span class="sxs-lookup"><span data-stu-id="a97c0-116">. operator</span></span>](member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="a97c0-117">alias extern</span><span class="sxs-lookup"><span data-stu-id="a97c0-117">extern alias</span></span>](../keywords/extern-alias.md)
