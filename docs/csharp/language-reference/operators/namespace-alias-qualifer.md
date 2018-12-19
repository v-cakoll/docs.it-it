---
title: ':: (operatore) - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 2e456be075f3487676228244e0119ff46ed9a538
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243478"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="4d679-102">:: Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4d679-102">:: Operator (C# Reference)</span></span>
<span data-ttu-id="4d679-103">Il qualificatore di alias dello spazio dei nomi (`::`) viene usato per cercare gli identificatori.</span><span class="sxs-lookup"><span data-stu-id="4d679-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="4d679-104">Viene sempre posizionato tra due identificatori, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4d679-104">It is always positioned between two identifiers, as in this example:</span></span>  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  

<span data-ttu-id="4d679-105">L'operatore `::` può anche essere usato con una *direttiva using alias*:</span><span class="sxs-lookup"><span data-stu-id="4d679-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="4d679-106">Note</span><span class="sxs-lookup"><span data-stu-id="4d679-106">Remarks</span></span>  
 <span data-ttu-id="4d679-107">Il qualificatore di alias dello spazio dei nomi può essere `global`.</span><span class="sxs-lookup"><span data-stu-id="4d679-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="4d679-108">In questo modo viene richiamata una ricerca nello spazio dei nomi globale anziché in uno spazio dei nomi con alias.</span><span class="sxs-lookup"><span data-stu-id="4d679-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="4d679-109">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="4d679-109">For More Information</span></span>  
 <span data-ttu-id="4d679-110">Per un esempio di utilizzo dell'operatore `::`, vedere la seguente sezione:</span><span class="sxs-lookup"><span data-stu-id="4d679-110">For an example of how to use the `::` operator, see the following section:</span></span>  
  
-   [<span data-ttu-id="4d679-111">Procedura: Usare l'alias dello spazio dei nomi globale</span><span class="sxs-lookup"><span data-stu-id="4d679-111">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="4d679-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="4d679-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4d679-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d679-113">See Also</span></span>

- [<span data-ttu-id="4d679-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="4d679-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="4d679-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4d679-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="4d679-116">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="4d679-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="4d679-117">Parole chiave per gli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="4d679-117">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="4d679-118">. (operatore)</span><span class="sxs-lookup"><span data-stu-id="4d679-118">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
- [<span data-ttu-id="4d679-119">alias extern</span><span class="sxs-lookup"><span data-stu-id="4d679-119">extern alias</span></span>](../../../csharp/language-reference/keywords/extern-alias.md)
