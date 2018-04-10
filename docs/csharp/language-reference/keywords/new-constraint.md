---
title: Vincolo new (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8557e056a664fd470b1f185b619d81235c8fcba7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="01230-102">Vincolo new (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="01230-102">new Constraint (C# Reference)</span></span>
<span data-ttu-id="01230-103">Il vincolo `new` specifica che qualsiasi argomento di tipo in una dichiarazione di classe generica deve avere un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="01230-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="01230-104">Per usare il vincolo new, il tipo non può essere astratto.</span><span class="sxs-lookup"><span data-stu-id="01230-104">To use the new constraint, the type cannot be abstract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01230-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="01230-105">Example</span></span>  
 <span data-ttu-id="01230-106">Applicare il vincolo `new` a un parametro del tipo quando la classe generica crea nuove istanze del tipo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="01230-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="01230-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="01230-107">Example</span></span>  
 <span data-ttu-id="01230-108">Quando il vincolo `new()` viene usato con altri vincoli, è necessario specificarlo per ultimo:</span><span class="sxs-lookup"><span data-stu-id="01230-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 <span data-ttu-id="01230-109">Per altre informazioni, vedere [Vincoli sui parametri di tipo](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="01230-109">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="01230-110">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="01230-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="01230-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01230-111">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="01230-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="01230-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="01230-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="01230-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="01230-114">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="01230-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="01230-115">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="01230-115">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="01230-116">Generics</span><span class="sxs-lookup"><span data-stu-id="01230-116">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
