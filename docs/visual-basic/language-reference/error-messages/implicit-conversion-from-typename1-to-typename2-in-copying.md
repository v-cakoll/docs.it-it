---
title: La conversione implicita da &#39; &lt;NomeTipo1&gt; &#39; per &#39; &lt;in NomeTipo2&gt; &#39; quando il valore di &#39;ByRef&#39; parametro &#39; &lt; ParameterName&gt; &#39; nell'argomento corrispondente.
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: 9f05a5fbcbef828b4ffa920d8cade475cedb64d5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537236"
---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a><span data-ttu-id="9ec5c-102">La conversione implicita da &#39; &lt;NomeTipo1&gt; &#39; per &#39; &lt;in NomeTipo2&gt; &#39; quando il valore di &#39;ByRef&#39; parametro &#39; &lt; ParameterName&gt; &#39; nell'argomento corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9ec5c-102">Implicit conversion from &#39;&lt;typename1&gt;&#39; to &#39;&lt;typename2&gt;&#39; in copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument.</span></span>
<span data-ttu-id="9ec5c-103">Una routine viene chiamata con un [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argomento di tipo diverso rispetto a quello del parametro corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9ec5c-103">A procedure is called with a [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argument of a different type than that of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="9ec5c-104">Se si passa un argomento `ByRef`, Visual Basic copia a volte il valore dell'argomento in una variabile locale nella routine invece di passare un riferimento.</span><span class="sxs-lookup"><span data-stu-id="9ec5c-104">If you pass an argument `ByRef`, Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="9ec5c-105">In tal caso, quando la procedura termina, Visual Basic deve quindi copiare il valore della variabile locale nell'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="9ec5c-105">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="9ec5c-106">Se un valore dell'argomento `ByRef` viene copiato nella routine e l'argomento e il parametro sono dello stesso tipo, non è necessaria alcuna conversione.</span><span class="sxs-lookup"><span data-stu-id="9ec5c-106">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="9ec5c-107">Ma se i tipi sono diversi, Visual Basic deve convertire in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="9ec5c-107">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="9ec5c-108">Poiché non è possibile usare `CType` o una delle altre parole chiave di conversione in un argomento di routine o parametro, tale conversione è sempre implicita.</span><span class="sxs-lookup"><span data-stu-id="9ec5c-108">Because you cannot use `CType` or any of the other conversion keywords on a procedure argument or parameter, such a conversion is always implicit.</span></span>  
  
 <span data-ttu-id="9ec5c-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="9ec5c-109">By default, this message is a warning.</span></span> <span data-ttu-id="9ec5c-110">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="9ec5c-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="9ec5c-111">**ID errore:** BC41999</span><span class="sxs-lookup"><span data-stu-id="9ec5c-111">**Error ID:** BC41999</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9ec5c-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="9ec5c-112">To correct this error</span></span>  
  
-   <span data-ttu-id="9ec5c-113">Se possibile, usare un argomento chiamante dello stesso tipo del parametro di routine, in modo che Visual Basic non è necessario eseguire alcuna conversione.</span><span class="sxs-lookup"><span data-stu-id="9ec5c-113">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="9ec5c-114">Se è necessario chiamare la routine con un tipo di argomento diverso dal tipo del parametro, ma non è necessario restituire un valore nell'argomento chiamante, definire il parametro in modo che sia [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) invece che `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="9ec5c-114">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ec5c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ec5c-115">See also</span></span>
- [<span data-ttu-id="9ec5c-116">Routine</span><span class="sxs-lookup"><span data-stu-id="9ec5c-116">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="9ec5c-117">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="9ec5c-117">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="9ec5c-118">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="9ec5c-118">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="9ec5c-119">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="9ec5c-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
