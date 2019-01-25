---
title: Sicurezza dei controlli WebBrowser
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 4c69f1c39d3a22db361fef1ffb65f21aa9d75128
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736273"
---
# <a name="webbrowser-security"></a><span data-ttu-id="f49be-102">Sicurezza dei controlli WebBrowser</span><span class="sxs-lookup"><span data-stu-id="f49be-102">WebBrowser Security</span></span>
<span data-ttu-id="f49be-103">Il <xref:System.Windows.Forms.WebBrowser> controllo è progettato per funzionare con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="f49be-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="f49be-104">Il contenuto HTML visualizzato nel controllo può provenire da server Web esterno e può contenere codice non gestito sotto forma di script o i controlli Web.</span><span class="sxs-lookup"><span data-stu-id="f49be-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="f49be-105">Se si usa la <xref:System.Windows.Forms.WebBrowser> controllo in questo caso, il controllo è non meno sicura rispetto a Internet Explorer, ma gestiti <xref:System.Windows.Forms.WebBrowser> controllo non impedisce tale codice non gestito in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f49be-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="f49be-106">Per altre informazioni sui problemi di sicurezza relativi al ActiveX sottostante `WebBrowser` controllano, vedere [controllo WebBrowser](https://go.microsoft.com/fwlink/?LinkId=198812).</span><span class="sxs-lookup"><span data-stu-id="f49be-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](https://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f49be-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f49be-107">See also</span></span>
- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="f49be-108">Panoramica sul controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="f49be-108">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)
- [<span data-ttu-id="f49be-109">Controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="f49be-109">WebBrowser Control</span></span>](https://go.microsoft.com/fwlink/?LinkId=198812)
