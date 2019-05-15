---
title: Come visualizzare il componente PrintDialog
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: de0acc655bbcf0cfc017d594545fae56cc27f981
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637447"
---
# <a name="how-to-display-the-printdialog-component"></a>Come visualizzare il componente PrintDialog

Il <xref:System.Windows.Forms.PrintDialog> componente è la finestra di dialogo Stampa di Windows standard che molti utenti risulterà familiare con. Poiché gli utenti saranno subito in grado di con esso, si rivela particolarmente vantaggioso per l'utilizzo di <xref:System.Windows.Forms.PrintDialog> componente.

## <a name="to-display-the-printdialog-component"></a>Per visualizzare il componente PrintDialog

- Chiamare il <xref:System.Windows.Forms.Form.ShowDialog%2A> metodo dal codice dell'applicazione.

     Una volta visualizzato il componente, gli utenti potranno usarlo, impostando le proprietà del processo di stampa. Queste proprietà vengono salvate nel <xref:System.Drawing.Printing.PrinterSettings> classe (e il <xref:System.Drawing.Printing.PageSettings> classe, se l'utente accede il [componente PageSetupDialog](pagesetupdialog-component-windows-forms.md) attraverso il <xref:System.Windows.Forms.PrintDialog> componente) associata al processo di stampa. Sarà quindi possibile effettuare chiamate alle proprietà così impostate per determinare le specifiche del processo di stampa.

## <a name="see-also"></a>Vedere anche

- [Procedura: Creare processi di stampa Standard di Windows Form](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [Procedura: Acquisire l'Input dell'utente da un elemento PrintDialog in fase di esecuzione](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [Controllo PrintPreviewDialog](printpreviewdialog-control-windows-forms.md)
- [Componente PrintDialog](printdialog-component-windows-forms.md)
- [Supporto per la stampa in Windows Forms](../advanced/windows-forms-print-support.md)
- [Controlli Windows Form](index.md)
