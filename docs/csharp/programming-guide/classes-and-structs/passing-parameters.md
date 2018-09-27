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
ms.openlocfilehash: a9538ee9f5f49554e9fe1822367404ab1d1e858d
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44194852"
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="82c98-102">Passaggio di parametri (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="82c98-102">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="82c98-103">In C# è possibile passare gli argomenti ai parametri per valore o per riferimento.</span><span class="sxs-lookup"><span data-stu-id="82c98-103">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="82c98-104">Il passaggio per riferimento consente a membri di funzioni, metodi, proprietà, indicizzatori, operatori e costruttori di modificare il valore dei parametri e rendere permanenti le modifiche nell'ambiente chiamante.</span><span class="sxs-lookup"><span data-stu-id="82c98-104">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="82c98-105">Per passare un parametro per riferimento con l'intenzione di modificare il valore, usare la parola chiave `ref` o `out`.</span><span class="sxs-lookup"><span data-stu-id="82c98-105">To pass a parameter by reference with the intent of changing the value, use the `ref`, or `out` keyword.</span></span> <span data-ttu-id="82c98-106">Per passare per riferimento con l'intenzione di evitare la copia, ma non la modifica del valore, usare il modificatore `in`.</span><span class="sxs-lookup"><span data-stu-id="82c98-106">To pass by reference with the intent of avoiding copying but not changing the value, use the `in` modifier.</span></span> <span data-ttu-id="82c98-107">Per semplicità, negli esempi riportati in questo argomento verrà utilizzata soltanto la parola chiave `ref`.</span><span class="sxs-lookup"><span data-stu-id="82c98-107">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="82c98-108">Per altre informazioni sulla differenza tra `in`, `ref` e `out`, vedere [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) e [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="82c98-108">For more information about the difference between `in`, `ref`, and `out`, see [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md), and [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md).</span></span>  
  
 <span data-ttu-id="82c98-109">L'esempio seguente illustra la differenza fra parametri di valore e di riferimento.</span><span class="sxs-lookup"><span data-stu-id="82c98-109">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 <span data-ttu-id="82c98-110">Per altre informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="82c98-110">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="82c98-111">Passaggio di parametri di tipo di valore</span><span class="sxs-lookup"><span data-stu-id="82c98-111">Passing Value-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [<span data-ttu-id="82c98-112">Passaggio di parametri di tipo di riferimento</span><span class="sxs-lookup"><span data-stu-id="82c98-112">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="82c98-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="82c98-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="82c98-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82c98-114">See Also</span></span>

- [<span data-ttu-id="82c98-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="82c98-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="82c98-116">Metodi</span><span class="sxs-lookup"><span data-stu-id="82c98-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)
