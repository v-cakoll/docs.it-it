---
title: void (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a71cac30132417abce60cdde54322b5f2067d39d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="void-c-reference"></a><span data-ttu-id="c0e27-102">void (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c0e27-102">void (C# Reference)</span></span>
<span data-ttu-id="c0e27-103">Quando viene usato come tipo restituito per un metodo `void` specifica che il metodo non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="c0e27-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="c0e27-104">L'uso di `void` non è consentito nell'elenco di parametri di un metodo.</span><span class="sxs-lookup"><span data-stu-id="c0e27-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="c0e27-105">Un metodo che non accetta parametri e non restituisce alcun valore viene dichiarato come segue:</span><span class="sxs-lookup"><span data-stu-id="c0e27-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="c0e27-106">`void` si usa inoltre in un contesto unsafe per dichiarare un puntatore a un tipo sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c0e27-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="c0e27-107">Per altre informazioni, vedere [Tipi di puntatori](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="c0e27-107">For more information, see [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="c0e27-108">`void` è un alias per il tipo <xref:System.Void?displayProperty=nameWithType> di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c0e27-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c0e27-109">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c0e27-109">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c0e27-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0e27-110">See also</span></span>
 [<span data-ttu-id="c0e27-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="c0e27-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c0e27-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c0e27-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c0e27-113">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="c0e27-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="c0e27-114">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="c0e27-114">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="c0e27-115">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="c0e27-115">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="c0e27-116">Metodi</span><span class="sxs-lookup"><span data-stu-id="c0e27-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [<span data-ttu-id="c0e27-117">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="c0e27-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
