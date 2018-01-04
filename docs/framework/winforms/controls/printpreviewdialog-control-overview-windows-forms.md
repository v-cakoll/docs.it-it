---
title: Cenni preliminari sul controllo PrintPreviewDialog (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintPreviewDialog
helpviewer_keywords: PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed071a4d38a0167ac9414ee7d383736dd38a62a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Cenni preliminari sul controllo PrintPreviewDialog (Windows Form)
Windows Form <xref:System.Windows.Forms.PrintPreviewDialog> controllo è una finestra di dialogo preconfigurata che consente di visualizzare come un [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) verrà stampato. Utilizzato all'interno dell'applicazione basate su Windows come semplice soluzione anziché configurare la propria finestra di dialogo. Il controllo contiene pulsanti per la stampa, l'ingrandimento, la visualizzazione di una o più pagine e la chiusura della finestra di dialogo.  
  
## <a name="key-properties-and-methods"></a>Metodi e proprietà chiave  
 Proprietà chiave del controllo è <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, che imposta il documento da visualizzare in anteprima. Il documento deve essere un <xref:System.Drawing.Printing.PrintDocument> oggetto. Per visualizzare la finestra di dialogo, è necessario chiamare il relativo <xref:System.Windows.Forms.Form.ShowDialog%2A> metodo. Anti-aliasing può visualizzare il testo più uniforme, ma può inoltre consentire la visualizzazione. Per utilizzarla, impostare il <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> proprietà `true`.  
  
 Alcune proprietà sono disponibili tramite il <xref:System.Windows.Forms.PrintPreviewControl> che il <xref:System.Windows.Forms.PrintPreviewDialog> contiene. (Non è necessario aggiungere questo <xref:System.Windows.Forms.PrintPreviewControl> al form; viene automaticamente incluso all'interno di <xref:System.Windows.Forms.PrintPreviewDialog> quando si aggiunge la finestra di dialogo al form.) Esempi di proprietà disponibili tramite il <xref:System.Windows.Forms.PrintPreviewControl> sono il <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> e <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> che determinano il numero di pagine visualizzate orizzontalmente e verticalmente il controllo. È possibile accedere il <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> proprietà come `PrintPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], o `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [Panoramica sul controllo PrintPreviewControl](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [Controllo PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [Controlli e componenti della finestra di dialogo](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
