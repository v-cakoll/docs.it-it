---
title: Parola chiave public (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 84a3bc49b6eea047d518edc01dab7f2301854b6a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484157"
---
# <a name="public-c-reference"></a><span data-ttu-id="93d09-102">public (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="93d09-102">public (C# Reference)</span></span>

<span data-ttu-id="93d09-103">La parola chiave `public` è un modificatore di accesso per tipi e membri dei tipi.</span><span class="sxs-lookup"><span data-stu-id="93d09-103">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="93d09-104">L'accesso pubblico è il livello di accesso più permissivo.</span><span class="sxs-lookup"><span data-stu-id="93d09-104">Public access is the most permissive access level.</span></span> <span data-ttu-id="93d09-105">Non esistono restrizioni per i membri dell'accesso pubblico, come nel seguente esempio:</span><span class="sxs-lookup"><span data-stu-id="93d09-105">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="93d09-106">Per altre informazioni, vedere [Modificatori di accesso](../../programming-guide/classes-and-structs/access-modifiers.md) e [Livelli di accessibilità](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="93d09-106">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="93d09-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="93d09-107">Example</span></span>

<span data-ttu-id="93d09-108">Nell'esempio seguente vengono dichiarate due classi, `PointTest` e `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="93d09-108">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="93d09-109">I membri pubblici `x` e `y` di `PointTest` sono accessibili direttamente da `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="93d09-109">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="93d09-110">Se si modifica il livello di accesso `public` impostandolo su [private](private.md) o [protected](protected.md), viene visualizzato un messaggio di errore che</span><span class="sxs-lookup"><span data-stu-id="93d09-110">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="93d09-111">indica che PointTest.y è inaccessibile a causa del livello di protezione.</span><span class="sxs-lookup"><span data-stu-id="93d09-111">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="93d09-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="93d09-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="93d09-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93d09-113">See also</span></span>

- [<span data-ttu-id="93d09-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="93d09-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="93d09-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="93d09-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="93d09-116">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="93d09-116">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="93d09-117">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="93d09-117">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="93d09-118">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="93d09-118">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="93d09-119">Livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="93d09-119">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="93d09-120">Modificatori</span><span class="sxs-lookup"><span data-stu-id="93d09-120">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="93d09-121">private</span><span class="sxs-lookup"><span data-stu-id="93d09-121">private</span></span>](private.md)
- [<span data-ttu-id="93d09-122">protected</span><span class="sxs-lookup"><span data-stu-id="93d09-122">protected</span></span>](protected.md)
- [<span data-ttu-id="93d09-123">internal</span><span class="sxs-lookup"><span data-stu-id="93d09-123">internal</span></span>](internal.md)