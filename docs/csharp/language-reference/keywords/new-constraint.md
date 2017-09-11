---
title: Vincolo new (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
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
ms.openlocfilehash: 762941794184605f90443ed8f36c88ecfa50aa84
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="117e7-102">Vincolo new (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="117e7-102">new Constraint (C# Reference)</span></span>
<span data-ttu-id="117e7-103">Il vincolo `new` specifica che qualsiasi argomento di tipo in una dichiarazione di classe generica deve avere un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="117e7-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="117e7-104">Per usare il vincolo new, il tipo non può essere astratto.</span><span class="sxs-lookup"><span data-stu-id="117e7-104">To use the new constraint, the type cannot be abstract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="117e7-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="117e7-105">Example</span></span>  
 <span data-ttu-id="117e7-106">Applicare il vincolo `new` a un parametro del tipo quando la classe generica crea nuove istanze del tipo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="117e7-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>  
  
 <span data-ttu-id="117e7-107">[!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="117e7-107">[!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="117e7-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="117e7-108">Example</span></span>  
 <span data-ttu-id="117e7-109">Quando il vincolo `new()` viene usato con altri vincoli, è necessario specificarlo per ultimo:</span><span class="sxs-lookup"><span data-stu-id="117e7-109">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>  
  
 <span data-ttu-id="117e7-110">[!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="117e7-110">[!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]</span></span>  
  
 <span data-ttu-id="117e7-111">Per altre informazioni, vedere [Vincoli sui parametri di tipo](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="117e7-111">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="117e7-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="117e7-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="117e7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="117e7-113">See Also</span></span>  
 <span data-ttu-id="117e7-114"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="117e7-114"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="117e7-115">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="117e7-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="117e7-116">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="117e7-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="117e7-117">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="117e7-117">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="117e7-118">[Parole chiave per operatori](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="117e7-118">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 [<span data-ttu-id="117e7-119">Generics</span><span class="sxs-lookup"><span data-stu-id="117e7-119">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)

