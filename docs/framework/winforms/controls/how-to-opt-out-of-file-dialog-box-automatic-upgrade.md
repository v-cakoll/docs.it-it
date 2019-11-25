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
ms.openlocfilehash: bbde260cc7f05226c9b06325b45708e1cde3cf8c
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976892"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="4ece9-102">Procedura: Rifiutare esplicitamente l'aggiornamento automatico della finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="4ece9-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="4ece9-103">Quando le classi <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> vengono utilizzate in un'applicazione, l'aspetto e il comportamento dipendono dalla versione di Windows su cui è in esecuzione l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ece9-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="4ece9-104">Quando un'applicazione creata in .NET Framework 2,0 o versioni precedenti viene visualizzata in Windows Vista, <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> vengono visualizzati automaticamente con l'aspetto e il comportamento di Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="4ece9-104">When an application that was created on the .NET Framework 2.0 or earlier is displayed on Windows Vista, <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the Windows Vista appearance and behavior.</span></span> <span data-ttu-id="4ece9-105">A partire da .NET Framework 3,0, è possibile rifiutare esplicitamente l'aggiornamento automatico per visualizzare i <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> con un aspetto e un comportamento di tipo [!INCLUDE[winxp](../../../../includes/winxp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ece9-105">Starting in the .NET Framework 3.0, you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="4ece9-106">Per rifiutare esplicitamente l'aggiornamento automatico della finestra di dialogo File</span><span class="sxs-lookup"><span data-stu-id="4ece9-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1. <span data-ttu-id="4ece9-107">Impostare la proprietà <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> di <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog> su `false` prima di visualizzare la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="4ece9-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ece9-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ece9-108">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
