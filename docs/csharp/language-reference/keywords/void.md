---
title: void (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- void_CSharpKeyword
- void
dev_langs:
- CSharp
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
caps.latest.revision: 15
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
ms.openlocfilehash: d1bd7ece5ce3b558c616a4eb3a4668c3c13eb1cb
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="void-c-reference"></a><span data-ttu-id="e55d9-102">void (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e55d9-102">void (C# Reference)</span></span>
<span data-ttu-id="e55d9-103">Quando viene usato come tipo restituito per un metodo `void` specifica che il metodo non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="e55d9-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="e55d9-104">L'uso di `void` non è consentito nell'elenco di parametri di un metodo.</span><span class="sxs-lookup"><span data-stu-id="e55d9-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="e55d9-105">Un metodo che non accetta parametri e non restituisce alcun valore viene dichiarato come segue:</span><span class="sxs-lookup"><span data-stu-id="e55d9-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="e55d9-106">`void` si usa inoltre in un contesto unsafe per dichiarare un puntatore a un tipo sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e55d9-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="e55d9-107">Per altre informazioni, vedere [Tipi di puntatori](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="e55d9-107">For more information, see [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="e55d9-108">`void` è un alias per il tipo <xref:System.Void?displayProperty=fullName> di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e55d9-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=fullName> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e55d9-109">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e55d9-109">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e55d9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e55d9-110">See also</span></span>
 <span data-ttu-id="e55d9-111">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e55d9-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e55d9-112">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e55d9-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e55d9-113">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="e55d9-113">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="e55d9-114">[Tipi di riferimento](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="e55d9-114">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="e55d9-115">[Tipi di valore](../../../csharp/language-reference/keywords/value-types.md) </span><span class="sxs-lookup"><span data-stu-id="e55d9-115">[Value Types](../../../csharp/language-reference/keywords/value-types.md) </span></span>  
 <span data-ttu-id="e55d9-116">[Metodi](../../../csharp/programming-guide/classes-and-structs/methods.md) </span><span class="sxs-lookup"><span data-stu-id="e55d9-116">[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md) </span></span>  
 [<span data-ttu-id="e55d9-117">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="e55d9-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)

