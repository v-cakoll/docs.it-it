---
title: Sicurezza dei controlli WebBrowser
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 730d8f692a44a06ea142bb870bbd961d5983c785
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534612"
---
# <a name="webbrowser-security"></a><span data-ttu-id="82b3c-102">Sicurezza dei controlli WebBrowser</span><span class="sxs-lookup"><span data-stu-id="82b3c-102">WebBrowser Security</span></span>
<span data-ttu-id="82b3c-103">Il <xref:System.Windows.Forms.WebBrowser> controllo è progettato per funzionare con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="82b3c-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="82b3c-104">Il contenuto HTML visualizzato nel controllo può provenire da server Web esterno e può contenere codice non gestito sotto forma di controlli Web o script.</span><span class="sxs-lookup"><span data-stu-id="82b3c-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="82b3c-105">Se si utilizza il <xref:System.Windows.Forms.WebBrowser> controllo in questo caso, il controllo è non meno sicuro rispetto a Internet Explorer, ma gestito <xref:System.Windows.Forms.WebBrowser> controllo non impedisce tale codice non gestito in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="82b3c-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="82b3c-106">Per ulteriori informazioni sui problemi di sicurezza relativi al ActiveX sottostante `WebBrowser` di controllo, vedere [controllo WebBrowser](http://go.microsoft.com/fwlink/?LinkId=198812).</span><span class="sxs-lookup"><span data-stu-id="82b3c-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](http://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82b3c-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82b3c-107">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 [<span data-ttu-id="82b3c-108">Panoramica sul controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="82b3c-108">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [<span data-ttu-id="82b3c-109">Controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="82b3c-109">WebBrowser Control</span></span>](http://go.microsoft.com/fwlink/?LinkId=198812)
