---
title: '&#39;&lt;ElementName&gt; &#39; è obsoleta (avviso di Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vbc40008
- bc40008
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
ms.openlocfilehash: 4dc2d0b8eace9bc411a344b4f2c4c79f7e09ac22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586770"
---
# <a name="39ltelementnamegt39-is-obsolete-visual-basic-warning"></a><span data-ttu-id="a9444-102">&#39;&lt;ElementName&gt; &#39; è obsoleta (avviso di Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9444-102">&#39;&lt;elementname&gt;&#39; is obsolete (Visual Basic Warning)</span></span>
<span data-ttu-id="a9444-103">Un'istruzione prova ad accedere a un elemento di programmazione che è stato contrassegnato con l'attributo <xref:System.ObsoleteAttribute> e la direttiva di considerarlo come un avviso.</span><span class="sxs-lookup"><span data-stu-id="a9444-103">A statement attempts to access a programming element which has been marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as a warning.</span></span>  
  
 <span data-ttu-id="a9444-104">È possibile contrassegnare qualsiasi elemento di programmazione come non più in uso applicando <xref:System.ObsoleteAttribute> a tale elemento.</span><span class="sxs-lookup"><span data-stu-id="a9444-104">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="a9444-105">In questo caso, è possibile impostare la proprietà <xref:System.ObsoleteAttribute.IsError%2A> dell'attributo su `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="a9444-105">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="a9444-106">Se si imposta la proprietà su `True`, il compilatore considera il tentativo di usare l'elemento come un errore.</span><span class="sxs-lookup"><span data-stu-id="a9444-106">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="a9444-107">Se si imposta la proprietà su `False`, o si lascia l'impostazione predefinita `False`, il compilatore genera un avviso se si prova a usare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="a9444-107">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="a9444-108">Per impostazione predefinita, si tratta di un messaggio di avviso perché la proprietà <xref:System.ObsoleteAttribute.IsError%2A> di <xref:System.ObsoleteAttribute> è `False`.</span><span class="sxs-lookup"><span data-stu-id="a9444-108">By default, this message is a warning, because the <xref:System.ObsoleteAttribute.IsError%2A> property of <xref:System.ObsoleteAttribute> is `False`.</span></span> <span data-ttu-id="a9444-109">Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="a9444-109">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="a9444-110">**ID errore:** BC40008</span><span class="sxs-lookup"><span data-stu-id="a9444-110">**Error ID:** BC40008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a9444-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a9444-111">To correct this error</span></span>  
  
-   <span data-ttu-id="a9444-112">Verificare che nel riferimento del codice sorgente il nome dell'elemento sia stato digitato correttamente.</span><span class="sxs-lookup"><span data-stu-id="a9444-112">Ensure that the source-code reference is spelling the element name correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9444-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9444-113">See Also</span></span>  
 [<span data-ttu-id="a9444-114">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="a9444-114">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
