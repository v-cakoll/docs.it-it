---
title: Conversione implicita da '<typename1>' a '<typename2>' quando il valore del parametro 'ByRef' '<parametername>' viene ricopiato nell'argomento corrispondente
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: f875206b15ee048311e43624e197e78413de522e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279617"
---
# <a name="implicit-conversion-from-typename1-to-typename2-in-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument"></a><span data-ttu-id="4cdaa-102">La conversione implicita da '\<NomeTipo1 >' a '\<in NomeTipo2 >' quando il valore del parametro 'ByRef' '\<nomeparametro >' nell'argomento corrispondente.</span><span class="sxs-lookup"><span data-stu-id="4cdaa-102">Implicit conversion from '\<typename1>' to '\<typename2>' in copying the value of 'ByRef' parameter '\<parametername>' back to the matching argument.</span></span>
<span data-ttu-id="4cdaa-103">Una routine viene chiamata con un [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argomento di tipo diverso rispetto a quello del parametro corrispondente.</span><span class="sxs-lookup"><span data-stu-id="4cdaa-103">A procedure is called with a [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argument of a different type than that of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="4cdaa-104">Se si passa un argomento `ByRef`, Visual Basic copia a volte il valore dell'argomento in una variabile locale nella routine invece di passare un riferimento.</span><span class="sxs-lookup"><span data-stu-id="4cdaa-104">If you pass an argument `ByRef`, Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="4cdaa-105">In tal caso, quando la procedura termina, Visual Basic deve quindi copiare il valore della variabile locale nell'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="4cdaa-105">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="4cdaa-106">Se un valore dell'argomento `ByRef` viene copiato nella routine e l'argomento e il parametro sono dello stesso tipo, non è necessaria alcuna conversione.</span><span class="sxs-lookup"><span data-stu-id="4cdaa-106">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="4cdaa-107">Ma se i tipi sono diversi, Visual Basic deve convertire in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="4cdaa-107">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="4cdaa-108">Poiché non è possibile usare `CType` o una delle altre parole chiave di conversione in un argomento di routine o parametro, tale conversione è sempre implicita.</span><span class="sxs-lookup"><span data-stu-id="4cdaa-108">Because you cannot use `CType` or any of the other conversion keywords on a procedure argument or parameter, such a conversion is always implicit.</span></span>  
  
 <span data-ttu-id="4cdaa-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="4cdaa-109">By default, this message is a warning.</span></span> <span data-ttu-id="4cdaa-110">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="4cdaa-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="4cdaa-111">**ID errore:** BC41999</span><span class="sxs-lookup"><span data-stu-id="4cdaa-111">**Error ID:** BC41999</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4cdaa-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="4cdaa-112">To correct this error</span></span>  
  
-   <span data-ttu-id="4cdaa-113">Se possibile, usare un argomento chiamante dello stesso tipo del parametro di routine, in modo che Visual Basic non è necessario eseguire alcuna conversione.</span><span class="sxs-lookup"><span data-stu-id="4cdaa-113">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="4cdaa-114">Se è necessario chiamare la routine con un tipo di argomento diverso dal tipo del parametro, ma non è necessario restituire un valore nell'argomento chiamante, definire il parametro in modo che sia [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) invece che `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="4cdaa-114">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cdaa-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cdaa-115">See also</span></span>
- [<span data-ttu-id="4cdaa-116">Routine</span><span class="sxs-lookup"><span data-stu-id="4cdaa-116">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="4cdaa-117">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="4cdaa-117">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="4cdaa-118">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="4cdaa-118">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="4cdaa-119">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="4cdaa-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
