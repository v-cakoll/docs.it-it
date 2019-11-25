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
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Procedura: Rifiutare esplicitamente l'aggiornamento automatico della finestra di dialogo File
Quando le classi <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> vengono utilizzate in un'applicazione, l'aspetto e il comportamento dipendono dalla versione di Windows su cui è in esecuzione l'applicazione. Quando un'applicazione creata in .NET Framework 2,0 o versioni precedenti viene visualizzata in Windows Vista, <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> vengono visualizzati automaticamente con l'aspetto e il comportamento di Windows Vista. A partire da .NET Framework 3,0, è possibile rifiutare esplicitamente l'aggiornamento automatico per visualizzare i <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> con un aspetto e un comportamento di tipo [!INCLUDE[winxp](../../../../includes/winxp-md.md)].  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Per rifiutare esplicitamente l'aggiornamento automatico della finestra di dialogo File  
  
1. Impostare la proprietà <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> di <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog> su `false` prima di visualizzare la finestra di dialogo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FileDialog>
