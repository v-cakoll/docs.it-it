---
title: <membername> non conforme a CLS non consentito in un'interfaccia conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: e572189b958612bf9527c82ce702df3ab929a23f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409400"
---
# <a name="non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="69588-102">\<membername> non conforme a CLS non consentito in un'interfaccia conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="69588-102">Non-CLS-compliant \<membername> is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="69588-103">Una proprietà, una routine o un evento in un'interfaccia è contrassegnato come `<CLSCompliant(True)>` quando l'interfaccia stessa è contrassegnata come `<CLSCompliant(False)>` o non è contrassegnata.</span><span class="sxs-lookup"><span data-stu-id="69588-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="69588-104">Affinché un'interfaccia sia conforme all'indipendenza del [linguaggio e ai componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) , tutti i relativi membri devono essere conformi.</span><span class="sxs-lookup"><span data-stu-id="69588-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="69588-105">Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità.</span><span class="sxs-lookup"><span data-stu-id="69588-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="69588-106">L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="69588-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="69588-107">Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.</span><span class="sxs-lookup"><span data-stu-id="69588-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="69588-108">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="69588-108">By default, this message is a warning.</span></span> <span data-ttu-id="69588-109">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="69588-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="69588-110">**ID errore:** BC40033</span><span class="sxs-lookup"><span data-stu-id="69588-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="69588-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="69588-111">To correct this error</span></span>  
  
- <span data-ttu-id="69588-112">Se è necessaria la conformità a CLS e si ha il controllo sul codice sorgente dell'interfaccia, contrassegnare l'interfaccia come `<CLSCompliant(True)>` se tutti i relativi membri fossero conformi.</span><span class="sxs-lookup"><span data-stu-id="69588-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
- <span data-ttu-id="69588-113">Se è necessaria la conformità a CLS e non si ha il controllo sul codice sorgente dell'interfaccia o se non si è idonei per essere conforme, definire questo membro all'interno di un'interfaccia diversa.</span><span class="sxs-lookup"><span data-stu-id="69588-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
- <span data-ttu-id="69588-114">Se è necessario che il membro rimanga all'interno dell'interfaccia corrente, rimuovere <xref:System.CLSCompliantAttribute> dalla relativa definizione o contrassegnarlo come `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="69588-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69588-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69588-115">See also</span></span>

- [<span data-ttu-id="69588-116">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="69588-116">Interface Statement</span></span>](../statements/interface-statement.md)
