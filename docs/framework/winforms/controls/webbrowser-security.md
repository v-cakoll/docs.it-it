---
title: Sicurezza dei controlli WebBrowser
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0d84f0c70619324bbbd38a2961914f88ac42671
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="webbrowser-security"></a><span data-ttu-id="f1821-102">Sicurezza dei controlli WebBrowser</span><span class="sxs-lookup"><span data-stu-id="f1821-102">WebBrowser Security</span></span>
<span data-ttu-id="f1821-103">Il <xref:System.Windows.Forms.WebBrowser> controllo è progettato per funzionare con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="f1821-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="f1821-104">Il contenuto HTML visualizzato nel controllo può provenire da server Web esterno e può contenere codice non gestito sotto forma di controlli Web o script.</span><span class="sxs-lookup"><span data-stu-id="f1821-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="f1821-105">Se si utilizza il <xref:System.Windows.Forms.WebBrowser> controllo in questo caso, il controllo è non meno sicuro rispetto a Internet Explorer, ma gestito <xref:System.Windows.Forms.WebBrowser> controllo non impedisce tale codice non gestito in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f1821-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="f1821-106">Per ulteriori informazioni sui problemi di sicurezza relativi al ActiveX sottostante `WebBrowser` di controllo, vedere [controllo WebBrowser](http://go.microsoft.com/fwlink/?LinkId=198812).</span><span class="sxs-lookup"><span data-stu-id="f1821-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](http://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1821-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1821-107">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 [<span data-ttu-id="f1821-108">Panoramica sul controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="f1821-108">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [<span data-ttu-id="f1821-109">Controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="f1821-109">WebBrowser Control</span></span>](http://go.microsoft.com/fwlink/?LinkId=198812)
