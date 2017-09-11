---
title: value (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- value_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
caps.latest.revision: 14
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
ms.openlocfilehash: 012cf622091687996fec477a8b5b821b190bbc29
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="value-c-reference"></a><span data-ttu-id="2dbb9-102">value (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2dbb9-102">value (C# Reference)</span></span>
<span data-ttu-id="2dbb9-103">La parola chiave contestuale `value` viene usata nella funzione di accesso set nelle dichiarazioni di proprietà ordinarie.</span><span class="sxs-lookup"><span data-stu-id="2dbb9-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="2dbb9-104">È simile a un parametro di input su un metodo.</span><span class="sxs-lookup"><span data-stu-id="2dbb9-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="2dbb9-105">La parola `value` fa riferimento al valore che il codice client tenta di assegnare alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="2dbb9-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="2dbb9-106">Nell'esempio seguente, `MyDerivedClass` ha una proprietà denominata `Name` che usa il parametro `value` per assegnare una nuova stringa al campo sottostante `name`.</span><span class="sxs-lookup"><span data-stu-id="2dbb9-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="2dbb9-107">Dal punto di vista del codice client, l'operazione viene scritta come assegnazione semplice.</span><span class="sxs-lookup"><span data-stu-id="2dbb9-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>  
  
 <span data-ttu-id="2dbb9-108">[!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2dbb9-108">[!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]</span></span>  
  
 <span data-ttu-id="2dbb9-109">Per altre informazioni sull'uso di `value`, vedere [Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="2dbb9-109">For more information about the use of `value`, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="2dbb9-110">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="2dbb9-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2dbb9-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2dbb9-111">See Also</span></span>  
 <span data-ttu-id="2dbb9-112">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="2dbb9-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="2dbb9-113">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2dbb9-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="2dbb9-114">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="2dbb9-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

