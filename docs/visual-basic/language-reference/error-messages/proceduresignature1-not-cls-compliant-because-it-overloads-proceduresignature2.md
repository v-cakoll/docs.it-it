---
title: <proceduresignature1> non è conforme a CLS perché esegue l'overload di <proceduresignature2> che differisce da esso solo per la matrice dei tipi di parametro matrice o per il numero di dimensioni dei tipi di parametro matrice
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 6143ebfbe7f131b0e196e531ed4282c8333be4ea
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250175"
---
# <a name="proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="da98d-102">il > \<proceduresignature1 non è conforme a CLS perché viene sottoposto a overload \<proceduresignature2 > che differisce da esso solo per matrice di tipi di parametro di matrice o per il rango dei tipi di parametro di matrice</span><span class="sxs-lookup"><span data-stu-id="da98d-102">\<proceduresignature1> is not CLS-compliant because it overloads \<proceduresignature2> which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>

<span data-ttu-id="da98d-103">Una routine o una proprietà è contrassegnata come `<CLSCompliant(True)>` quando esegue l'override di un'altra routine o proprietà e l'unica differenza tra gli elenchi di parametri è il livello di nidificazione di una matrice di matrici o il rango di una matrice.</span><span class="sxs-lookup"><span data-stu-id="da98d-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>
  
 <span data-ttu-id="da98d-104">Nelle dichiarazioni seguenti la seconda e la terza dichiarazione generano questo errore:</span><span class="sxs-lookup"><span data-stu-id="da98d-104">In the following declarations, the second and third declarations generate this error:</span></span>
  
 `Overloads Sub ProcessArray(arrayParam() As Integer)`  
  
 `Overloads Sub ProcessArray(arrayParam()() As Integer)`  
  
 `Overloads Sub ProcessArray(arrayParam(,) As Integer)`  
  
 <span data-ttu-id="da98d-105">La seconda dichiarazione modifica il parametro unidimensionale originale `arrayParam` in una matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="da98d-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="da98d-106">La terza dichiarazione cambia `arrayParam` in una matrice bidimensionale (Rank 2).</span><span class="sxs-lookup"><span data-stu-id="da98d-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="da98d-107">Sebbene Visual Basic consentano gli overload di differire solo per una di queste modifiche, tale overload non è conforme all' [indipendenza del linguaggio e ai componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="da98d-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="da98d-108">Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità.</span><span class="sxs-lookup"><span data-stu-id="da98d-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="da98d-109">L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="da98d-109">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="da98d-110">Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.</span><span class="sxs-lookup"><span data-stu-id="da98d-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="da98d-111">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="da98d-111">By default, this message is a warning.</span></span> <span data-ttu-id="da98d-112">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="da98d-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="da98d-113">**ID errore:** BC40035</span><span class="sxs-lookup"><span data-stu-id="da98d-113">**Error ID:** BC40035</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="da98d-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="da98d-114">To correct this error</span></span>  
  
- <span data-ttu-id="da98d-115">Se è necessaria la conformità a CLS, definire gli overload per distinguerli tra loro in più modi rispetto alle modifiche citate in questa pagina della guida.</span><span class="sxs-lookup"><span data-stu-id="da98d-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>
- <span data-ttu-id="da98d-116">Se è necessario che gli overload differiscano solo per le modifiche citate in questa pagina della guida, rimuovere il <xref:System.CLSCompliantAttribute> dalle definizioni o contrassegnarle come `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="da98d-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="da98d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da98d-117">See also</span></span>

- [<span data-ttu-id="da98d-118">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="da98d-118">Procedure Overloading</span></span>](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="da98d-119">Overload</span><span class="sxs-lookup"><span data-stu-id="da98d-119">Overloads</span></span>](../modifiers/overloads.md)
