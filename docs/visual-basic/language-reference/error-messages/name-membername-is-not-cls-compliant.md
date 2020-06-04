---
title: Il nome <membername> non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 45c9332237dffc7311daeedaf36035d9e9958415
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397181"
---
# <a name="name-membername-is-not-cls-compliant"></a><span data-ttu-id="237d3-102">Il nome \<membername> non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="237d3-102">Name \<membername> is not CLS-compliant</span></span>
<span data-ttu-id="237d3-103">Un assembly è contrassegnato come `<CLSCompliant(True)>` ma espone un membro con un nome che inizia con un carattere di sottolineatura ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="237d3-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="237d3-104">Un elemento di programmazione può contenere uno o più caratteri di sottolineatura, ma deve essere conforme all' [indipendenza del linguaggio e ai componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), non deve iniziare con un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="237d3-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="237d3-105">Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="237d3-105">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="237d3-106">Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità.</span><span class="sxs-lookup"><span data-stu-id="237d3-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="237d3-107">L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="237d3-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="237d3-108">Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.</span><span class="sxs-lookup"><span data-stu-id="237d3-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="237d3-109">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="237d3-109">By default, this message is a warning.</span></span> <span data-ttu-id="237d3-110">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="237d3-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="237d3-111">**ID errore:** BC40031</span><span class="sxs-lookup"><span data-stu-id="237d3-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="237d3-112">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="237d3-112">To correct this error</span></span>  
  
- <span data-ttu-id="237d3-113">Se si ha il controllo sul codice sorgente, modificare il nome del membro in modo che non inizi con un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="237d3-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
- <span data-ttu-id="237d3-114">Se è necessario che il nome del membro rimanga invariato, rimuovere <xref:System.CLSCompliantAttribute> dalla relativa definizione o contrassegnarlo come `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="237d3-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="237d3-115">È comunque possibile contrassegnare l'assembly come `<CLSCompliant(True)>` .</span><span class="sxs-lookup"><span data-stu-id="237d3-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="237d3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="237d3-116">See also</span></span>

- [<span data-ttu-id="237d3-117">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="237d3-117">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="237d3-118">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="237d3-118">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
