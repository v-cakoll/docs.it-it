---
title: "Procedura: Rifiutare esplicitamente l'aggiornamento automatico della finestra di dialogo File"
ms.date: 03/30/2017
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
ms.openlocfilehash: e12134768d41589dedbeb5a00cab4244c7324f97
ms.sourcegitcommit: 90f0bee0e8a416e45c78fa3ad4c91ef00e5228d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2019
ms.locfileid: "66722619"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="46c8d-102">Procedura: Rifiutare esplicitamente l'aggiornamento automatico della finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="46c8d-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="46c8d-103">Quando la <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> classi vengono usate in un'applicazione, l'aspetto e il comportamento dipendono dalla versione di Windows in cui viene eseguita l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="46c8d-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="46c8d-104">Quando un'applicazione che è stata creata il [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] o in precedenza viene visualizzato nella [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> vengono automaticamente visualizzate con il [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] aspetto e comportamento.</span><span class="sxs-lookup"><span data-stu-id="46c8d-104">When an application that was created on the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] or earlier is displayed on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] appearance and behavior.</span></span> <span data-ttu-id="46c8d-105">A partire da .NET Framework 3.0, è possibile rifiutare esplicitamente l'aggiornamento automatico per visualizzare il <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> con un [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-aspetto e il comportamento.</span><span class="sxs-lookup"><span data-stu-id="46c8d-105">Starting in the .NET Framework 3.0, you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="46c8d-106">Per rifiutare esplicitamente l'aggiornamento automatico della finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="46c8d-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1. <span data-ttu-id="46c8d-107">Impostare il <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> proprietà di <xref:System.Windows.Forms.OpenFileDialog> oppure <xref:System.Windows.Forms.SaveFileDialog> a `false` prima di visualizzare la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="46c8d-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c8d-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46c8d-108">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
