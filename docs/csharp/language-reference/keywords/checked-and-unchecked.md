---
title: Checked e Unchecked - Riferimenti per C#
ms.custom: seodec18
ms.date: 05/15/2018
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: 7abc19e0657330752e7798d060516c48aa402297
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771768"
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="5e0ad-102">Checked e Unchecked (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5e0ad-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="5e0ad-103">È possibile eseguire istruzioni C# in contesti verificati o non verificati.</span><span class="sxs-lookup"><span data-stu-id="5e0ad-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="5e0ad-104">In un contesto verificato l'overflow aritmetico genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5e0ad-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="5e0ad-105">In un contesto non verificato, l'overflow aritmetico viene ignorato e il risultato viene troncato mediante l'eliminazione di tutti i bit più significativi che non corrispondono al tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5e0ad-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>  
  
- <span data-ttu-id="5e0ad-106">[checked](checked.md) Specificare il contesto verificato.</span><span class="sxs-lookup"><span data-stu-id="5e0ad-106">[checked](checked.md) Specify checked context.</span></span>  
  
- <span data-ttu-id="5e0ad-107">[unchecked](unchecked.md) Specificare il contesto non verificato.</span><span class="sxs-lookup"><span data-stu-id="5e0ad-107">[unchecked](unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="5e0ad-108">Le operazioni seguenti sono interessate dal controllo di overflow:</span><span class="sxs-lookup"><span data-stu-id="5e0ad-108">The following operations are affected by the overflow checking:</span></span>  
  
- <span data-ttu-id="5e0ad-109">Espressioni che usano gli operatori predefiniti seguenti su tipi integrali:</span><span class="sxs-lookup"><span data-stu-id="5e0ad-109">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="5e0ad-110">`++`, `--`, `-` unario, `+`, `-`, `*`, `/`</span><span class="sxs-lookup"><span data-stu-id="5e0ad-110">`++`, `--`, unary `-`, `+`, `-`, `*`, `/`</span></span>  
  
- <span data-ttu-id="5e0ad-111">Conversioni numeriche esplicite tra tipi integrali oppure da `float` o `double` a un tipo integrale.</span><span class="sxs-lookup"><span data-stu-id="5e0ad-111">Explicit numeric conversions between integral types, or from `float` or `double` to an integral type.</span></span>  
  
 <span data-ttu-id="5e0ad-112">Se non si specifica `checked` né `unchecked`, il contesto predefinito per le espressioni non costanti (espressioni che vengono valutate in fase di esecuzione) è definito dal valore dell'opzione del compilatore [-checked](../compiler-options/checked-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5e0ad-112">If neither `checked` nor `unchecked` is specified, the default context for non-constant expressions (expressions that are evaluated at run time) is defined by the value of the [-checked](../compiler-options/checked-compiler-option.md) compiler option.</span></span> <span data-ttu-id="5e0ad-113">Per impostazione predefinita il valore di tale opzione non è impostato e le operazioni aritmetiche vengono eseguite in un contesto non verificato.</span><span class="sxs-lookup"><span data-stu-id="5e0ad-113">By default the value of that option is unset and arithmetic operations are executed in an unchecked context.</span></span>
 
 <span data-ttu-id="5e0ad-114">Per le espressioni costanti (espressioni che possono essere valutate per intero in fase di compilazione), il contesto predefinito viene sempre controllato.</span><span class="sxs-lookup"><span data-stu-id="5e0ad-114">For constant expressions (expressions that can be fully evaluated at compile time), the default context is always checked.</span></span> <span data-ttu-id="5e0ad-115">A meno che un'espressione costante non venga posizionata in modo esplicito in un contesto non verificato, gli overflow che si verificano durante la valutazione in fase di compilazione dell'espressione causano errori in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="5e0ad-115">Unless a constant expression is explicitly placed in an unchecked context, overflows that occur during the compile-time evaluation of the expression cause compile-time errors.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5e0ad-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e0ad-116">See also</span></span>

- [<span data-ttu-id="5e0ad-117">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="5e0ad-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5e0ad-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5e0ad-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5e0ad-119">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="5e0ad-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="5e0ad-120">Parole chiave per le istruzioni</span><span class="sxs-lookup"><span data-stu-id="5e0ad-120">Statement Keywords</span></span>](statement-keywords.md)
