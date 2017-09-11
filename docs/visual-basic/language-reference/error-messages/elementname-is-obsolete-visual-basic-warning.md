---
title: "&quot;&lt;elementname&gt;&quot; è obsoleto (avviso di Visual Basic) | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40008
- bc40008
dev_langs:
- VB
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
caps.latest.revision: 12
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
ms.openlocfilehash: 77708f052f7aec7a5da2b24605ba3bd794f83979
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="39ltelementnamegt39-is-obsolete-visual-basic-warning"></a><span data-ttu-id="22bc1-102">'&lt;elementname&gt;' è obsoleto (avviso di Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22bc1-102">&#39;&lt;elementname&gt;&#39; is obsolete (Visual Basic Warning)</span></span>
<span data-ttu-id="22bc1-103">Un'istruzione tenta di accedere a un elemento di programmazione che è stato contrassegnato con il <xref:System.ObsoleteAttribute>attributo e la direttiva di considerarla come un avviso.</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="22bc1-103">A statement attempts to access a programming element which has been marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as a warning.</span></span>  
  
 <span data-ttu-id="22bc1-104">È possibile contrassegnare gli elementi di programmazione come non più in uso, applicando <xref:System.ObsoleteAttribute>a tale</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="22bc1-104">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="22bc1-105">In questo caso, è possibile impostare l'attributo <xref:System.ObsoleteAttribute.IsError%2A>a una proprietà `True` o `False`.</xref:System.ObsoleteAttribute.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="22bc1-105">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="22bc1-106">Se si imposta la proprietà su `True`, il compilatore considera il tentativo di usare l'elemento come un errore.</span><span class="sxs-lookup"><span data-stu-id="22bc1-106">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="22bc1-107">Se si imposta la proprietà su `False`, o si lascia l'impostazione predefinita `False`, il compilatore genera un avviso se si prova a usare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="22bc1-107">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="22bc1-108">Per impostazione predefinita, questo messaggio è un avviso, poiché il <xref:System.ObsoleteAttribute.IsError%2A>proprietà <xref:System.ObsoleteAttribute>è `False`.</xref:System.ObsoleteAttribute> </xref:System.ObsoleteAttribute.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="22bc1-108">By default, this message is a warning, because the <xref:System.ObsoleteAttribute.IsError%2A> property of <xref:System.ObsoleteAttribute> is `False`.</span></span> <span data-ttu-id="22bc1-109">Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="22bc1-109">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="22bc1-110">**ID errore:** BC40008</span><span class="sxs-lookup"><span data-stu-id="22bc1-110">**Error ID:** BC40008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="22bc1-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="22bc1-111">To correct this error</span></span>  
  
-   <span data-ttu-id="22bc1-112">Verificare che nel riferimento del codice sorgente il nome dell'elemento sia stato digitato correttamente.</span><span class="sxs-lookup"><span data-stu-id="22bc1-112">Ensure that the source-code reference is spelling the element name correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22bc1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22bc1-113">See Also</span></span>  
 [<span data-ttu-id="22bc1-114">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="22bc1-114">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

