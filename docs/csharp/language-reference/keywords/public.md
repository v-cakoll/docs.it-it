---
title: public (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 197ef4a2a8544d439b0c34ec14bb7752b760ea06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="public-c-reference"></a><span data-ttu-id="88d36-102">public (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="88d36-102">public (C# Reference)</span></span>
<span data-ttu-id="88d36-103">La parola chiave `public` è un modificatore di accesso per tipi e membri dei tipi.</span><span class="sxs-lookup"><span data-stu-id="88d36-103">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="88d36-104">L'accesso pubblico è il livello di accesso più permissivo.</span><span class="sxs-lookup"><span data-stu-id="88d36-104">Public access is the most permissive access level.</span></span> <span data-ttu-id="88d36-105">Non esistono restrizioni per i membri dell'accesso pubblico, come nel seguente esempio:</span><span class="sxs-lookup"><span data-stu-id="88d36-105">There are no restrictions on accessing public members, as in this example:</span></span>  
  
```  
class SampleClass  
{  
    public int x; // No access restrictions.  
}  
```  
  
 <span data-ttu-id="88d36-106">Per altre informazioni, vedere [Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) e [Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="88d36-106">See [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88d36-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="88d36-107">Example</span></span>  
 <span data-ttu-id="88d36-108">Nell'esempio seguente vengono dichiarate due classi, `PointTest` e `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="88d36-108">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="88d36-109">I membri pubblici `x` e `y` di `PointTest` sono accessibili direttamente da `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="88d36-109">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/public_1.cs)]  
  
 <span data-ttu-id="88d36-110">Se si modifica il livello di accesso `public` impostandolo su [private](../../../csharp/language-reference/keywords/private.md) o [protected](../../../csharp/language-reference/keywords/protected.md), viene visualizzato un messaggio di errore che</span><span class="sxs-lookup"><span data-stu-id="88d36-110">If you change the `public` access level to [private](../../../csharp/language-reference/keywords/private.md) or [protected](../../../csharp/language-reference/keywords/protected.md), you will get the error message:</span></span>  
  
 <span data-ttu-id="88d36-111">indica che PointTest.y è inaccessibile a causa del livello di protezione.</span><span class="sxs-lookup"><span data-stu-id="88d36-111">'PointTest.y' is inaccessible due to its protection level.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="88d36-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="88d36-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="88d36-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88d36-113">See Also</span></span>  
 [<span data-ttu-id="88d36-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="88d36-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="88d36-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="88d36-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="88d36-116">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="88d36-116">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="88d36-117">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="88d36-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="88d36-118">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="88d36-118">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="88d36-119">Livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="88d36-119">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="88d36-120">Modificatori</span><span class="sxs-lookup"><span data-stu-id="88d36-120">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="88d36-121">private</span><span class="sxs-lookup"><span data-stu-id="88d36-121">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="88d36-122">protected</span><span class="sxs-lookup"><span data-stu-id="88d36-122">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="88d36-123">internal</span><span class="sxs-lookup"><span data-stu-id="88d36-123">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
