---
title: void - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: 0624b547ee2586334ac35d366ae3c8dfd14963ee
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742769"
---
# <a name="void-c-reference"></a><span data-ttu-id="36d3e-102">void (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="36d3e-102">void (C# Reference)</span></span>

<span data-ttu-id="36d3e-103">Quando viene usato come tipo restituito per un metodo `void` specifica che il metodo non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="36d3e-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="36d3e-104">L'uso di `void` non è consentito nell'elenco di parametri di un metodo.</span><span class="sxs-lookup"><span data-stu-id="36d3e-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="36d3e-105">Un metodo che non accetta parametri e non restituisce alcun valore viene dichiarato come segue:</span><span class="sxs-lookup"><span data-stu-id="36d3e-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="36d3e-106">`void` si usa inoltre in un contesto unsafe per dichiarare un puntatore a un tipo sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="36d3e-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="36d3e-107">Per altre informazioni, vedere [Tipi di puntatori](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="36d3e-107">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="36d3e-108">`void` è un alias per il tipo <xref:System.Void?displayProperty=nameWithType> di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="36d3e-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="36d3e-109">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="36d3e-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="36d3e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36d3e-110">See also</span></span>

- [<span data-ttu-id="36d3e-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="36d3e-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="36d3e-112">Parole chiave C#</span><span class="sxs-lookup"><span data-stu-id="36d3e-112">C# keywords</span></span>](index.md)
- [<span data-ttu-id="36d3e-113">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="36d3e-113">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="36d3e-114">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="36d3e-114">Value types</span></span>](../builtin-types/value-types.md)
- [<span data-ttu-id="36d3e-115">Metodi</span><span class="sxs-lookup"><span data-stu-id="36d3e-115">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="36d3e-116">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="36d3e-116">Unsafe code and pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
