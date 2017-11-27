---
title: 'Procedura: acquisire l''input dell''utente da un elemento PrintDialog in fase di esecuzione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print options [Windows Forms], changing at run time
- printing [Windows Forms], options
- print options
- run time [Windows Forms], changing print options
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6c942cb5f005177b74dd25a9725b4990553adbb8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a>Procedura: acquisire l'input dell'utente da un elemento PrintDialog in fase di esecuzione
Sebbene sia possibile impostare le opzioni relative alla stampa in fase di progettazione, si potrebbe desiderare di modificare queste opzioni in fase di esecuzione, probabilmente a causa delle scelte effettuate dall'utente. È possibile acquisire l'input dell'utente per la stampa di un documento usando il <xref:System.Windows.Forms.PrintDialog> e <xref:System.Drawing.Printing.PrintDocument> componenti.  
  
### <a name="to-change-print-options-programmatically"></a>Per modificare le opzioni di stampa a livello di codice  
  
1.  Aggiungere un <xref:System.Windows.Forms.PrintDialog> e <xref:System.Drawing.Printing.PrintDocument> componente al form.  
  
2.  Impostare il <xref:System.Windows.Forms.PrintDialog.Document%2A> proprietà del <xref:System.Windows.Forms.PrintDialog> per il <xref:System.Drawing.Printing.PrintDocument> aggiunto al form.  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3.  Visualizzazione di <xref:System.Windows.Forms.PrintDialog> componente utilizzando il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo.  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4.  Le scelte dell'utente stampa dalla finestra di dialogo verranno copiate il <xref:System.Drawing.Printing.PrinterSettings> proprietà del <xref:System.Drawing.Printing.PrintDocument> componente.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: stampare un file di testo con più pagine in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 [Supporto per la stampa in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
