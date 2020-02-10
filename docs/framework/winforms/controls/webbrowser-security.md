---
title: Sicurezza dei controlli WebBrowser
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: b25cabca050d06dbfe97c563eb56622d1f21be54
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095255"
---
# <a name="webbrowser-security"></a><span data-ttu-id="081e5-102">Sicurezza dei controlli WebBrowser</span><span class="sxs-lookup"><span data-stu-id="081e5-102">WebBrowser Security</span></span>
<span data-ttu-id="081e5-103">Il controllo <xref:System.Windows.Forms.WebBrowser> è progettato per funzionare solo con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="081e5-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="081e5-104">Il contenuto HTML visualizzato nel controllo può provenire da server Web esterni e può contenere codice non gestito sotto forma di script o controlli Web.</span><span class="sxs-lookup"><span data-stu-id="081e5-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="081e5-105">Se si utilizza il controllo <xref:System.Windows.Forms.WebBrowser> in questa situazione, il controllo non è meno sicuro di Internet Explorer, ma il controllo <xref:System.Windows.Forms.WebBrowser> gestito non impedisce l'esecuzione di tale codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="081e5-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="081e5-106">Per ulteriori informazioni sui problemi di sicurezza relativi al controllo `WebBrowser` ActiveX sottostante, vedere [controllo WebBrowser](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="081e5-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="081e5-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="081e5-107">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="081e5-108">Panoramica sul controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="081e5-108">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- <span data-ttu-id="081e5-109">[Controllo WebBrowser](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="081e5-109">[WebBrowser Control](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span></span>
