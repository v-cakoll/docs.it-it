---
title: 'Procedura: Rifiutare esplicitamente l''aggiornamento automatico della finestra di dialogo File'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 01be9e29c00f39125c8ee645242e986fac178ba2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="e89ad-102">Procedura: Rifiutare esplicitamente l'aggiornamento automatico della finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="e89ad-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="e89ad-103">Quando il <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> classi vengono utilizzate in un'applicazione, l'aspetto e comportamento dipendono dalla versione di Windows è in esecuzione l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e89ad-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="e89ad-104">Quando un'applicazione che è stata creata il [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] oppure viene visualizzato in precedenza su [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> vengono visualizzati automaticamente con il [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] aspetto e comportamento.</span><span class="sxs-lookup"><span data-stu-id="e89ad-104">When an application that was created on the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] or earlier is displayed on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] appearance and behavior.</span></span> <span data-ttu-id="e89ad-105">A partire dal [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], è possibile rifiutare esplicitamente l'aggiornamento automatico per visualizzare il <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> con un [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-aspetto e il comportamento.</span><span class="sxs-lookup"><span data-stu-id="e89ad-105">Starting in the [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="e89ad-106">Per rifiutare esplicitamente l'aggiornamento automatico della finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="e89ad-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1.  <span data-ttu-id="e89ad-107">Impostare il <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> proprietà di <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog> per `false` prima di visualizzare la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="e89ad-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e89ad-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e89ad-108">See Also</span></span>  
 <xref:System.Windows.Forms.FileDialog>
