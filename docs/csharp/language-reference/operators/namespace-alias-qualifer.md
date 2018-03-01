---
title: 'Operatore :: (Riferimenti per C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6b4f1683e1250ed745e15ced88203ca942c75ff8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="7ca6c-102">Operatore :: (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7ca6c-102">:: Operator (C# Reference)</span></span>
<span data-ttu-id="7ca6c-103">Il qualificatore di alias dello spazio dei nomi (`::`) viene usato per cercare gli identificatori.</span><span class="sxs-lookup"><span data-stu-id="7ca6c-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="7ca6c-104">Viene sempre posizionato tra due identificatori, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="7ca6c-104">It is always positioned between two identifiers, as in this example:</span></span>  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="7ca6c-105">Note</span><span class="sxs-lookup"><span data-stu-id="7ca6c-105">Remarks</span></span>  
 <span data-ttu-id="7ca6c-106">Il qualificatore di alias dello spazio dei nomi può essere `global`.</span><span class="sxs-lookup"><span data-stu-id="7ca6c-106">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="7ca6c-107">In questo modo viene richiamata una ricerca nello spazio dei nomi globale anziché in uno spazio dei nomi con alias.</span><span class="sxs-lookup"><span data-stu-id="7ca6c-107">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="7ca6c-108">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="7ca6c-108">For More Information</span></span>  
 <span data-ttu-id="7ca6c-109">Per un esempio di utilizzo dell'operatore `::`, vedere la seguente sezione:</span><span class="sxs-lookup"><span data-stu-id="7ca6c-109">For an example of how to use the `::` operator, see the following section:</span></span>  
  
-   [<span data-ttu-id="7ca6c-110">Procedura: Usare l'alias dello spazio dei nomi globale</span><span class="sxs-lookup"><span data-stu-id="7ca6c-110">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="7ca6c-111">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7ca6c-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7ca6c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ca6c-112">See Also</span></span>  
 [<span data-ttu-id="7ca6c-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="7ca6c-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7ca6c-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7ca6c-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7ca6c-115">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="7ca6c-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="7ca6c-116">Parole chiave per gli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="7ca6c-116">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="7ca6c-117">. (operatore)</span><span class="sxs-lookup"><span data-stu-id="7ca6c-117">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
 [<span data-ttu-id="7ca6c-118">alias extern</span><span class="sxs-lookup"><span data-stu-id="7ca6c-118">extern alias</span></span>](../../../csharp/language-reference/keywords/extern-alias.md)
