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
ms.openlocfilehash: 5bd43bb60736bbcaf8034cc2b369c34f977319ac
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633914"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="02620-102">Operatore :: (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="02620-102">:: operator (C# Reference)</span></span>

<span data-ttu-id="02620-103">Il qualificatore di alias dello spazio dei nomi (`::`) viene usato per cercare gli identificatori.</span><span class="sxs-lookup"><span data-stu-id="02620-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="02620-104">Viene sempre posizionato tra due identificatori, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="02620-104">It is always positioned between two identifiers, as in this example:</span></span>

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

<span data-ttu-id="02620-105">L'operatore `::` può anche essere usato con una *direttiva using alias*:</span><span class="sxs-lookup"><span data-stu-id="02620-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="02620-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="02620-106">Remarks</span></span>

<span data-ttu-id="02620-107">Il qualificatore di alias dello spazio dei nomi può essere `global`.</span><span class="sxs-lookup"><span data-stu-id="02620-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="02620-108">In questo modo viene richiamata una ricerca nello spazio dei nomi globale anziché in uno spazio dei nomi con alias.</span><span class="sxs-lookup"><span data-stu-id="02620-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="02620-109">Per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="02620-109">For more information</span></span>

<span data-ttu-id="02620-110">Per un esempio di utilizzo dell'operatore `::`, vedere la seguente sezione:</span><span class="sxs-lookup"><span data-stu-id="02620-110">For an example of how to use the `::` operator, see the following section:</span></span>

- [<span data-ttu-id="02620-111">Procedura: Usare l'alias dello spazio dei nomi globale</span><span class="sxs-lookup"><span data-stu-id="02620-111">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="02620-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="02620-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="02620-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02620-113">See also</span></span>

- [<span data-ttu-id="02620-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="02620-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="02620-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="02620-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="02620-116">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="02620-116">C# operators</span></span>](index.md)
- [<span data-ttu-id="02620-117">Parole chiave per gli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="02620-117">Namespace Keywords</span></span>](../keywords/namespace-keywords.md)
- [<span data-ttu-id="02620-118">Operatore .</span><span class="sxs-lookup"><span data-stu-id="02620-118">. operator</span></span>](member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="02620-119">alias extern</span><span class="sxs-lookup"><span data-stu-id="02620-119">extern alias</span></span>](../keywords/extern-alias.md)
