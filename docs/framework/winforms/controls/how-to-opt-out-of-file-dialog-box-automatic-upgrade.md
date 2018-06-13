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
ms.openlocfilehash: 380f8abe502c37e57207c43696158c1e3bdc7697
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532487"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Procedura: Rifiutare esplicitamente l'aggiornamento automatico della finestra di dialogo File
Quando il <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> classi vengono utilizzate in un'applicazione, l'aspetto e comportamento dipendono dalla versione di Windows è in esecuzione l'applicazione. Quando un'applicazione che è stata creata il [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] oppure viene visualizzato in precedenza su [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> vengono visualizzati automaticamente con il [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] aspetto e comportamento. A partire dal [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], è possibile rifiutare esplicitamente l'aggiornamento automatico per visualizzare il <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> con un [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-aspetto e il comportamento.  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Per rifiutare esplicitamente l'aggiornamento automatico della finestra di dialogo File  
  
1.  Impostare il <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> proprietà di <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog> per `false` prima di visualizzare la finestra di dialogo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.FileDialog>
