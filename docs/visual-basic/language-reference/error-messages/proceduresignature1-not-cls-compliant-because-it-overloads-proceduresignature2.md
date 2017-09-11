---
title: "&lt;proceduresignature1&gt; non è conforme a CLS perché esegue l&quot;overload &lt;proceduresignature2&gt; che differisce da esso solo per matrice di tipi di parametro matrice o per la classificazione dei tipi di parametro matrice | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40035
- bc40035
dev_langs:
- VB
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
caps.latest.revision: 11
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
ms.openlocfilehash: d106f59e3faa317f67ee92ddcec8416eeff745d4
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="ltproceduresignature1gt-is-not-cls-compliant-because-it-overloads-ltproceduresignature2gt-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="1dd81-102">&lt;proceduresignature1&gt; non è conforme a CLS perché esegue l'overload &lt;proceduresignature2&gt; che differisce da esso solo per matrice di tipi di parametro matrice o per la classificazione dei tipi di parametro matrice</span><span class="sxs-lookup"><span data-stu-id="1dd81-102">&lt;proceduresignature1&gt; is not CLS-compliant because it overloads &lt;proceduresignature2&gt; which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>
<span data-ttu-id="1dd81-103">Una routine o proprietà è contrassegnata come `<CLSCompliant(True)>` quando esegue l'override di un'altra routine o una proprietà e l'unica differenza tra gli elenchi dei parametri è il livello di nidificazione di una matrice di matrici o il rango di una matrice.</span><span class="sxs-lookup"><span data-stu-id="1dd81-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>  
  
 <span data-ttu-id="1dd81-104">Nel seguente elenco, le dichiarazioni di seconda e terza generano questo errore.</span><span class="sxs-lookup"><span data-stu-id="1dd81-104">In the following declarations, the second and third declarations generate this error.</span></span>  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 <span data-ttu-id="1dd81-105">La seconda dichiarazione modifica il parametro unidimensionale originario `arrayParam` a una matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="1dd81-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="1dd81-106">La terza dichiarazione modifica `arrayParam` a una matrice bidimensionale (2 dimensioni).</span><span class="sxs-lookup"><span data-stu-id="1dd81-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="1dd81-107">Visual Basic consente di overload per differiscano solo una di queste modifiche, questo tipo di overload non è conforme con la [indipendenza del linguaggio e componenti indipendenti dal linguaggio](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span><span class="sxs-lookup"><span data-stu-id="1dd81-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span></span>  
  
 <span data-ttu-id="1dd81-108">Quando si applica il <xref:System.CLSCompliantAttribute>a un elemento di programmazione, impostare l'attributo `isCompliant` parametro al metodo `True` o `False` per indicare la conformità o la non conformità.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="1dd81-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="1dd81-109">L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="1dd81-109">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="1dd81-110">Se non si applica il <xref:System.CLSCompliantAttribute>a un elemento, viene considerato come non conforme.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="1dd81-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="1dd81-111">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="1dd81-111">By default, this message is a warning.</span></span> <span data-ttu-id="1dd81-112">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="1dd81-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="1dd81-113">**ID errore:** BC40035</span><span class="sxs-lookup"><span data-stu-id="1dd81-113">**Error ID:** BC40035</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1dd81-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="1dd81-114">To correct this error</span></span>  
  
-   <span data-ttu-id="1dd81-115">Se è necessaria la conformità a CLS, definire overload per differenziarsi in più modi rispetto a quelle elencate in questa pagina della Guida in linea.</span><span class="sxs-lookup"><span data-stu-id="1dd81-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>  
  
-   <span data-ttu-id="1dd81-116">Se è necessario che gli overload differiscono solo per le modifiche citate in questa Guida di pagina, rimuovere il <xref:System.CLSCompliantAttribute>dalle definizioni o contrassegnarli come `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="1dd81-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dd81-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dd81-117">See Also</span></span>  
 <span data-ttu-id="1dd81-118">[\<PAVE su > la scrittura di codice conforme a CLS](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3) </span><span class="sxs-lookup"><span data-stu-id="1dd81-118">[\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3) </span></span>  
<span data-ttu-id="1dd81-119"> [Overload di routine](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="1dd81-119"> [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md) </span></span>  
<span data-ttu-id="1dd81-120"> [Overload](../../../visual-basic/language-reference/modifiers/overloads.md)</span><span class="sxs-lookup"><span data-stu-id="1dd81-120"> [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)</span></span>
