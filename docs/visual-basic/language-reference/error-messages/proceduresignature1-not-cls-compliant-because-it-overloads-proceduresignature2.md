---
title: "&lt;proceduresignature1&gt; non è conforme a CLS perché esegue l'overload &lt;proceduresignature2&gt; che differisce da esso solo per la matrice di tipi di parametro matrice o per numero di dimensioni dei tipi di parametro matrice"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords: BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9cdbd8edaefba4554e8de92cb600f045dc39f780
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2017
---
# <a name="ltproceduresignature1gt-is-not-cls-compliant-because-it-overloads-ltproceduresignature2gt-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="a679b-102">&lt;proceduresignature1&gt; non è conforme a CLS perché esegue l'overload &lt;proceduresignature2&gt; che differisce da esso solo per la matrice di tipi di parametro matrice o per numero di dimensioni dei tipi di parametro matrice</span><span class="sxs-lookup"><span data-stu-id="a679b-102">&lt;proceduresignature1&gt; is not CLS-compliant because it overloads &lt;proceduresignature2&gt; which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>
<span data-ttu-id="a679b-103">Una routine o proprietà è contrassegnata come `<CLSCompliant(True)>` quando viene eseguito l'override di un'altra routine o proprietà e l'unica differenza tra gli elenchi dei parametri è il livello di nidificazione di una matrice di matrici o il numero di dimensioni di una matrice.</span><span class="sxs-lookup"><span data-stu-id="a679b-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>  
  
 <span data-ttu-id="a679b-104">Nelle dichiarazioni di seguito, le dichiarazioni di seconda e terza generano questo errore.</span><span class="sxs-lookup"><span data-stu-id="a679b-104">In the following declarations, the second and third declarations generate this error.</span></span>  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 <span data-ttu-id="a679b-105">La seconda dichiarazione modifica il parametro unidimensionale originario `arrayParam` a una matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="a679b-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="a679b-106">La terza dichiarazione modifica `arrayParam` a una matrice bidimensionale (2 dimensioni).</span><span class="sxs-lookup"><span data-stu-id="a679b-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="a679b-107">Anche se Visual Basic consente l'overload per differiscono solo per una di queste modifiche, questo tipo di overload non è compatibile con il [indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="a679b-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="a679b-108">Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità.</span><span class="sxs-lookup"><span data-stu-id="a679b-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="a679b-109">L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="a679b-109">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="a679b-110">Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.</span><span class="sxs-lookup"><span data-stu-id="a679b-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="a679b-111">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="a679b-111">By default, this message is a warning.</span></span> <span data-ttu-id="a679b-112">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="a679b-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="a679b-113">**ID errore:** BC40035</span><span class="sxs-lookup"><span data-stu-id="a679b-113">**Error ID:** BC40035</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a679b-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a679b-114">To correct this error</span></span>  
  
-   <span data-ttu-id="a679b-115">Se è necessaria la conformità a CLS, definire overload a differenziarsi in più modi rispetto a quelle elencate in questa pagina della Guida.</span><span class="sxs-lookup"><span data-stu-id="a679b-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>  
  
-   <span data-ttu-id="a679b-116">Se è necessario che gli overload differiscono solo per le modifiche citate in questa Guida pagina, rimuovere il <xref:System.CLSCompliantAttribute> dalle definizioni o contrassegnarli come `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="a679b-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a679b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a679b-117">See Also</span></span>  
 [<span data-ttu-id="a679b-118">\<PAVE su > scrittura di codice conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="a679b-118">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)  
 [<span data-ttu-id="a679b-119">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="a679b-119">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [<span data-ttu-id="a679b-120">Overload</span><span class="sxs-lookup"><span data-stu-id="a679b-120">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
