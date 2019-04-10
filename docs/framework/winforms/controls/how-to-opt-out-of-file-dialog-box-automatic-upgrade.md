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
ms.openlocfilehash: a4be35617e8be1c6c83ac6f2d06e03b6cbb2977f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301100"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Procedura: Rifiutare esplicitamente l'aggiornamento automatico della finestra di dialogo File
Quando la <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> classi vengono usate in un'applicazione, l'aspetto e il comportamento dipendono dalla versione di Windows in cui viene eseguita l'applicazione. Quando un'applicazione che è stata creata il [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] o in precedenza viene visualizzato nella [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> vengono automaticamente visualizzate con il [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] aspetto e comportamento. A partire dal [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], è possibile rifiutare esplicitamente l'aggiornamento automatico per visualizzare il <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> con un [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-aspetto e il comportamento.  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Per rifiutare esplicitamente l'aggiornamento automatico della finestra di dialogo File  
  
1. Impostare il <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> proprietà di <xref:System.Windows.Forms.OpenFileDialog> oppure <xref:System.Windows.Forms.SaveFileDialog> a `false` prima di visualizzare la finestra di dialogo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FileDialog>
