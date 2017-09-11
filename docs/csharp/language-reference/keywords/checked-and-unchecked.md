---
title: Checked e Unchecked (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: 17
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
ms.openlocfilehash: 744f59dbf7ee8370010ff76d4e9dde20490de403
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="679b6-102">Checked e Unchecked (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="679b6-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="679b6-103">È possibile eseguire istruzioni C# in contesti verificati o non verificati.</span><span class="sxs-lookup"><span data-stu-id="679b6-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="679b6-104">In un contesto verificato l'overflow aritmetico genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="679b6-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="679b6-105">In un contesto non verificato l'overflow aritmetico viene ignorato e il risultato è troncato.</span><span class="sxs-lookup"><span data-stu-id="679b6-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated.</span></span>  
  
-   <span data-ttu-id="679b6-106">[checked](../../../csharp/language-reference/keywords/checked.md) Specificare il contesto verificato.</span><span class="sxs-lookup"><span data-stu-id="679b6-106">[checked](../../../csharp/language-reference/keywords/checked.md) Specify checked context.</span></span>  
  
-   <span data-ttu-id="679b6-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Specificare il contesto non verificato.</span><span class="sxs-lookup"><span data-stu-id="679b6-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="679b6-108">Se né `checked` né `unchecked` vengono specificati, il contesto predefinito dipende da fattori esterni, ad esempio le opzioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="679b6-108">If neither `checked` nor `unchecked` is specified, the default context depends on external factors such as compiler options.</span></span>  
  
 <span data-ttu-id="679b6-109">Le operazioni seguenti sono interessate dal controllo di overflow:</span><span class="sxs-lookup"><span data-stu-id="679b6-109">The following operations are affected by the overflow checking:</span></span>  
  
-   <span data-ttu-id="679b6-110">Espressioni che usano gli operatori predefiniti seguenti su tipi integrali:</span><span class="sxs-lookup"><span data-stu-id="679b6-110">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="679b6-111">`++` `--` - (unario)   `+` -   `*` `/`</span><span class="sxs-lookup"><span data-stu-id="679b6-111">`++` `--` - (unary)   `+` -   `*` `/`</span></span>  
  
-   <span data-ttu-id="679b6-112">Conversioni numeriche esplicite tra tipi integrali.</span><span class="sxs-lookup"><span data-stu-id="679b6-112">Explicit numeric conversions between integral types.</span></span>  
  
 <span data-ttu-id="679b6-113">L'opzione del compilatore [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) consente di specificare il contesto verificato o non verificato per tutte le istruzioni aritmetiche su interi che non rientrano in modo esplicito nell'ambio di una parola chiave `checked` o `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="679b6-113">The [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) compiler option lets you specify checked or unchecked context for all integer arithmetic statements that are not explicitly in the scope of a `checked` or `unchecked` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="679b6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="679b6-114">See Also</span></span>  
 <span data-ttu-id="679b6-115">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="679b6-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="679b6-116">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="679b6-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="679b6-117">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="679b6-117">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="679b6-118">Parole chiave per le istruzioni</span><span class="sxs-lookup"><span data-stu-id="679b6-118">Statement Keywords</span></span>](../../../csharp/language-reference/keywords/statement-keywords.md)

