---
title: Checked e Unchecked (Riferimenti per C#)
ms.date: 07/20/2015
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: 26ea8a7864d93b8d64661db2b0dc1df6634f989a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="dd7f1-102">Checked e Unchecked (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="dd7f1-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="dd7f1-103">È possibile eseguire istruzioni C# in contesti verificati o non verificati.</span><span class="sxs-lookup"><span data-stu-id="dd7f1-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="dd7f1-104">In un contesto verificato l'overflow aritmetico genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="dd7f1-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="dd7f1-105">In un contesto non verificato l'overflow aritmetico viene ignorato e il risultato è troncato.</span><span class="sxs-lookup"><span data-stu-id="dd7f1-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated.</span></span>  
  
-   <span data-ttu-id="dd7f1-106">[checked](../../../csharp/language-reference/keywords/checked.md) Specificare il contesto verificato.</span><span class="sxs-lookup"><span data-stu-id="dd7f1-106">[checked](../../../csharp/language-reference/keywords/checked.md) Specify checked context.</span></span>  
  
-   <span data-ttu-id="dd7f1-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Specificare il contesto non verificato.</span><span class="sxs-lookup"><span data-stu-id="dd7f1-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="dd7f1-108">Se né `checked` né `unchecked` vengono specificati, il contesto predefinito dipende da fattori esterni, ad esempio le opzioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="dd7f1-108">If neither `checked` nor `unchecked` is specified, the default context depends on external factors such as compiler options.</span></span>  
  
 <span data-ttu-id="dd7f1-109">Le operazioni seguenti sono interessate dal controllo di overflow:</span><span class="sxs-lookup"><span data-stu-id="dd7f1-109">The following operations are affected by the overflow checking:</span></span>  
  
-   <span data-ttu-id="dd7f1-110">Espressioni che usano gli operatori predefiniti seguenti su tipi integrali:</span><span class="sxs-lookup"><span data-stu-id="dd7f1-110">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="dd7f1-111">`++` `--` - (unario)   `+` -   `*` `/`</span><span class="sxs-lookup"><span data-stu-id="dd7f1-111">`++` `--` - (unary)   `+` -   `*` `/`</span></span>  
  
-   <span data-ttu-id="dd7f1-112">Conversioni numeriche esplicite tra tipi integrali.</span><span class="sxs-lookup"><span data-stu-id="dd7f1-112">Explicit numeric conversions between integral types.</span></span>  
  
 <span data-ttu-id="dd7f1-113">L'opzione del compilatore [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) consente di specificare il contesto verificato o non verificato per tutte le istruzioni aritmetiche su interi che non rientrano in modo esplicito nell'ambio di una parola chiave `checked` o `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="dd7f1-113">The [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) compiler option lets you specify checked or unchecked context for all integer arithmetic statements that are not explicitly in the scope of a `checked` or `unchecked` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd7f1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd7f1-114">See Also</span></span>  
 [<span data-ttu-id="dd7f1-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="dd7f1-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="dd7f1-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="dd7f1-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="dd7f1-117">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="dd7f1-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="dd7f1-118">Parole chiave per le istruzioni</span><span class="sxs-lookup"><span data-stu-id="dd7f1-118">Statement Keywords</span></span>](../../../csharp/language-reference/keywords/statement-keywords.md)
