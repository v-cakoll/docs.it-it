---
title: Sicurezza dei controlli WebBrowser
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 957c11a085c971a81e5baa81a5b797dd53f2451a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703427"
---
# <a name="webbrowser-security"></a><span data-ttu-id="fdf26-102">Sicurezza dei controlli WebBrowser</span><span class="sxs-lookup"><span data-stu-id="fdf26-102">WebBrowser Security</span></span>
<span data-ttu-id="fdf26-103">Il <xref:System.Windows.Forms.WebBrowser> controllo è progettato per funzionare con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="fdf26-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="fdf26-104">Il contenuto HTML visualizzato nel controllo può provenire da server Web esterno e può contenere codice non gestito sotto forma di script o i controlli Web.</span><span class="sxs-lookup"><span data-stu-id="fdf26-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="fdf26-105">Se si usa la <xref:System.Windows.Forms.WebBrowser> controllo in questo caso, il controllo è non meno sicura rispetto a Internet Explorer, ma gestiti <xref:System.Windows.Forms.WebBrowser> controllo non impedisce tale codice non gestito in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fdf26-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="fdf26-106">Per altre informazioni sui problemi di sicurezza relativi al ActiveX sottostante `WebBrowser` controllano, vedere [controllo WebBrowser](https://go.microsoft.com/fwlink/?LinkId=198812).</span><span class="sxs-lookup"><span data-stu-id="fdf26-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](https://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdf26-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdf26-107">See also</span></span>
- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="fdf26-108">Panoramica sul controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="fdf26-108">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- [<span data-ttu-id="fdf26-109">Controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="fdf26-109">WebBrowser Control</span></span>](https://go.microsoft.com/fwlink/?LinkId=198812)
