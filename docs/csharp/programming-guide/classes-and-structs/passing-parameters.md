---
title: Passaggio di parametri (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4b8c0c7f7b8c3820edbafbe90fb961c12da8fc84
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="b7557-102">Passaggio di parametri (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="b7557-102">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="b7557-103">In C# è possibile passare gli argomenti ai parametri per valore o per riferimento.</span><span class="sxs-lookup"><span data-stu-id="b7557-103">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="b7557-104">Il passaggio per riferimento consente a membri di funzioni, metodi, proprietà, indicizzatori, operatori e costruttori di modificare il valore dei parametri e rendere permanenti le modifiche nell'ambiente chiamante.</span><span class="sxs-lookup"><span data-stu-id="b7557-104">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="b7557-105">Per passare un parametro per riferimento, usare la parola chiave `ref` o `out`.</span><span class="sxs-lookup"><span data-stu-id="b7557-105">To pass a parameter by reference, use the `ref` or `out` keyword.</span></span> <span data-ttu-id="b7557-106">Per semplicità, negli esempi riportati in questo argomento verrà utilizzata soltanto la parola chiave `ref`.</span><span class="sxs-lookup"><span data-stu-id="b7557-106">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="b7557-107">Per altre informazioni sulla differenza tra `ref` e `out`, vedere [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md) e [Passaggio di matrici mediante ref e out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="b7557-107">For more information about the difference between `ref` and `out`, see [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md), and [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="b7557-108">L'esempio seguente illustra la differenza fra parametri di valore e di riferimento.</span><span class="sxs-lookup"><span data-stu-id="b7557-108">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 <span data-ttu-id="b7557-109">[!code-cs[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b7557-109">[!code-cs[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="b7557-110">Per altre informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="b7557-110">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="b7557-111">Passaggio di parametri di tipo di valore</span><span class="sxs-lookup"><span data-stu-id="b7557-111">Passing Value-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [<span data-ttu-id="b7557-112">Passaggio di parametri di tipo di riferimento</span><span class="sxs-lookup"><span data-stu-id="b7557-112">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="b7557-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b7557-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b7557-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7557-114">See Also</span></span>  
 <span data-ttu-id="b7557-115">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b7557-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b7557-116">Metodi</span><span class="sxs-lookup"><span data-stu-id="b7557-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

