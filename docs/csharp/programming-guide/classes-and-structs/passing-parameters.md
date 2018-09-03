---
title: Passaggio di parametri (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: a1ccfff8081d101eee46360009653b0591dfb3ff
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43404126"
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="d481b-102">Passaggio di parametri (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d481b-102">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="d481b-103">In C# è possibile passare gli argomenti ai parametri per valore o per riferimento.</span><span class="sxs-lookup"><span data-stu-id="d481b-103">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="d481b-104">Il passaggio per riferimento consente a membri di funzioni, metodi, proprietà, indicizzatori, operatori e costruttori di modificare il valore dei parametri e rendere permanenti le modifiche nell'ambiente chiamante.</span><span class="sxs-lookup"><span data-stu-id="d481b-104">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="d481b-105">Per passare un parametro per riferimento con l'intenzione di modificare il valore, usare la parola chiave `ref` o `out`.</span><span class="sxs-lookup"><span data-stu-id="d481b-105">To pass a parameter by reference with the intent of changing the value, use the `ref`, or `out` keyword.</span></span> <span data-ttu-id="d481b-106">Per passare per riferimento con l'intenzione di evitare la copia, ma non la modifica del valore, usare il modificatore `in`.</span><span class="sxs-lookup"><span data-stu-id="d481b-106">To pass by reference with the intent of avoiding copying but not changing the value, use the `in` modifier.</span></span> <span data-ttu-id="d481b-107">Per semplicità, negli esempi riportati in questo argomento verrà utilizzata soltanto la parola chiave `ref`.</span><span class="sxs-lookup"><span data-stu-id="d481b-107">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="d481b-108">Per altre informazioni sulla differenza tra `in`, `ref` e `out`, vedere [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) e [Passaggio di matrici mediante ref e out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="d481b-108">For more information about the difference between `in`, `ref`, and `out`, see [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), and [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="d481b-109">L'esempio seguente illustra la differenza fra parametri di valore e di riferimento.</span><span class="sxs-lookup"><span data-stu-id="d481b-109">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 <span data-ttu-id="d481b-110">Per altre informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="d481b-110">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="d481b-111">Passaggio di parametri di tipo di valore</span><span class="sxs-lookup"><span data-stu-id="d481b-111">Passing Value-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [<span data-ttu-id="d481b-112">Passaggio di parametri di tipo di riferimento</span><span class="sxs-lookup"><span data-stu-id="d481b-112">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="d481b-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d481b-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d481b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d481b-114">See Also</span></span>  
 [<span data-ttu-id="d481b-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d481b-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d481b-116">Metodi</span><span class="sxs-lookup"><span data-stu-id="d481b-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)
