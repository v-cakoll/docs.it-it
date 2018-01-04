---
title: 'Procedura: Visualizzare il componente PrintDialog'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d955febe528add4b774766a3b204f96eef5a119d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-the-printdialog-component"></a>Procedura: Visualizzare il componente PrintDialog
Il <xref:System.Windows.Forms.PrintDialog> componente è la casella di dialogo di stampa Windows standard che familiarità con molti utenti. Poiché gli utenti saranno immediatamente dimestichezza, si rivela particolarmente vantaggioso per l'utilizzo di <xref:System.Windows.Forms.PrintDialog> componente.  
  
### <a name="to-display-the-printdialog-component"></a>Per visualizzare il componente PrintDialog  
  
-   Chiamare il <xref:System.Windows.Forms.Form.ShowDialog%2A> metodo all'interno di codice dell'applicazione.  
  
     Una volta visualizzato il componente, gli utenti potranno usarlo, impostando le proprietà del processo di stampa. Queste proprietà vengono salvate nel <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` classe (e <xref:System.Drawing.Printing.PageSettings> classe, se l'utente accede il [PageSetupDialog (componente)](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) tramite il <xref:System.Windows.Forms.PrintDialog> componente) associata al processo di stampa. Sarà quindi possibile effettuare chiamate alle proprietà così impostate per determinare le specifiche del processo di stampa.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Creare processi di stampa standard per Windows Form](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [Procedura: Acquisire l'input dell'utente da un elemento PrintDialog in fase di esecuzione](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 [Controllo PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [Componente PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 [Supporto per la stampa in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [Controlli Windows Form](../../../../docs/framework/winforms/controls/index.md)
