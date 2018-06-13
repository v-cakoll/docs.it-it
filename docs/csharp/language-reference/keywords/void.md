---
title: void (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: e66efc287fc3ed0fcc15963a827fccb788c38753
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267288"
---
# <a name="void-c-reference"></a><span data-ttu-id="e72e6-102">void (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e72e6-102">void (C# Reference)</span></span>
<span data-ttu-id="e72e6-103">Quando viene usato come tipo restituito per un metodo `void` specifica che il metodo non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="e72e6-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="e72e6-104">L'uso di `void` non è consentito nell'elenco di parametri di un metodo.</span><span class="sxs-lookup"><span data-stu-id="e72e6-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="e72e6-105">Un metodo che non accetta parametri e non restituisce alcun valore viene dichiarato come segue:</span><span class="sxs-lookup"><span data-stu-id="e72e6-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="e72e6-106">`void` si usa inoltre in un contesto unsafe per dichiarare un puntatore a un tipo sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e72e6-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="e72e6-107">Per altre informazioni, vedere [Tipi di puntatori](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="e72e6-107">For more information, see [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="e72e6-108">`void` è un alias per il tipo <xref:System.Void?displayProperty=nameWithType> di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e72e6-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e72e6-109">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e72e6-109">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e72e6-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e72e6-110">See also</span></span>
 [<span data-ttu-id="e72e6-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e72e6-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e72e6-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e72e6-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e72e6-113">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="e72e6-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="e72e6-114">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="e72e6-114">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="e72e6-115">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="e72e6-115">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="e72e6-116">Metodi</span><span class="sxs-lookup"><span data-stu-id="e72e6-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [<span data-ttu-id="e72e6-117">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="e72e6-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
