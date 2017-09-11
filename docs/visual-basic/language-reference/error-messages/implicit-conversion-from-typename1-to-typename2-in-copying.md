---
title: La conversione implicita da &quot;&lt;NomeTipo1&gt;&quot;a&quot;&lt;in NomeTipo2&gt;&quot;in copiando il valore del parametro &quot;ByRef&quot; &quot;&lt;parametername&gt;&quot; argomento corrispondente. | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc41999
- bc41999
dev_langs:
- VB
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0d69bc5074ed5ef2f58010b3477752d3aa6a4b26
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a><span data-ttu-id="223cd-103">La conversione implicita da '&lt;NomeTipo1&gt;'a'&lt;in NomeTipo2&gt;'in copiando il valore del parametro 'ByRef' '&lt;parametername&gt;' argomento corrispondente.</span><span class="sxs-lookup"><span data-stu-id="223cd-103">Implicit conversion from &#39;&lt;typename1&gt;&#39; to &#39;&lt;typename2&gt;&#39; in copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument.</span></span>
<span data-ttu-id="223cd-104">Viene chiamata una routine con un [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argomento di tipo diverso rispetto a quello del parametro corrispondente.</span><span class="sxs-lookup"><span data-stu-id="223cd-104">A procedure is called with a [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argument of a different type than that of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="223cd-105">Se si passa un argomento `ByRef`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] talvolta copia il valore dell'argomento in una variabile locale nella routine anziché passare un riferimento.</span><span class="sxs-lookup"><span data-stu-id="223cd-105">If you pass an argument `ByRef`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="223cd-106">In tal caso, quando viene restituito, la procedura [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] dovrà quindi copiare il valore della variabile locale nell'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="223cd-106">In such a case, when the procedure returns, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="223cd-107">Se un valore dell'argomento `ByRef` viene copiato nella routine e l'argomento e il parametro sono dello stesso tipo, non è necessaria alcuna conversione.</span><span class="sxs-lookup"><span data-stu-id="223cd-107">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="223cd-108">Tuttavia, se i tipi sono diversi, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] necessario convertirli in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="223cd-108">But if the types are different, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must convert in both directions.</span></span> <span data-ttu-id="223cd-109">Poiché non è possibile utilizzare `CType` o una delle altre parole chiave di conversione in un argomento di routine o parametro, tale conversione è sempre implicita.</span><span class="sxs-lookup"><span data-stu-id="223cd-109">Because you cannot use `CType` or any of the other conversion keywords on a procedure argument or parameter, such a conversion is always implicit.</span></span>  
  
 <span data-ttu-id="223cd-110">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="223cd-110">By default, this message is a warning.</span></span> <span data-ttu-id="223cd-111">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="223cd-111">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="223cd-112">**ID errore:** BC41999</span><span class="sxs-lookup"><span data-stu-id="223cd-112">**Error ID:** BC41999</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="223cd-113">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="223cd-113">To correct this error</span></span>  
  
-   <span data-ttu-id="223cd-114">Se possibile, utilizzare un argomento chiamante dello stesso tipo del parametro di routine, pertanto [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] non è necessario effettuare alcuna conversione.</span><span class="sxs-lookup"><span data-stu-id="223cd-114">If possible, use a calling argument of the same type as the procedure parameter, so [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="223cd-115">Se è necessario chiamare la routine con un argomento di tipo diverso dal tipo di parametro ma non è necessario restituire un valore nell'argomento di chiamata, definire il parametro come [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) anziché `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="223cd-115">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="223cd-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="223cd-116">See Also</span></span>  
 <span data-ttu-id="223cd-117">[Procedure](../../../visual-basic/programming-guide/language-features/procedures/index.md) </span><span class="sxs-lookup"><span data-stu-id="223cd-117">[Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md) </span></span>  
<span data-ttu-id="223cd-118"> [Gli argomenti e parametri di routine](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="223cd-118"> [Procedure Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="223cd-119"> [Passaggio di argomenti per valore e per riferimento](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="223cd-119"> [Passing Arguments by Value and by Reference](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="223cd-120"> [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="223cd-120"> [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)</span></span>
