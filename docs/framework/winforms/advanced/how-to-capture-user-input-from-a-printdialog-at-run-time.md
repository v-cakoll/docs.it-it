---
title: "Procedura: Acquisire l'Input dell'utente da un elemento PrintDialog in fase di esecuzione"
ms.date: 03/30/2017
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
ms.openlocfilehash: a15563560615f5b857220c0b548fc57f31ee4e09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527666"
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a>Procedura: Acquisire l'Input dell'utente da un elemento PrintDialog in fase di esecuzione
Mentre è possibile impostare le opzioni relative alla stampa in fase di progettazione, talvolta si desidera modificare queste opzioni in fase di esecuzione, probabilmente a causa di scelte effettuate dall'utente. È possibile acquisire l'input dell'utente per la stampa di un documento usando il <xref:System.Windows.Forms.PrintDialog> e il <xref:System.Drawing.Printing.PrintDocument> componenti.  
  
### <a name="to-change-print-options-programmatically"></a>Per modificare le opzioni di stampa a livello di codice  
  
1.  Aggiungere un <xref:System.Windows.Forms.PrintDialog> e un <xref:System.Drawing.Printing.PrintDocument> al form.  
  
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
  
3.  Visualizzare il <xref:System.Windows.Forms.PrintDialog> componente usando la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> (metodo).  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4.  Le scelte dell'utente stampa nella finestra di dialogo verranno copiate il <xref:System.Drawing.Printing.PrinterSettings> proprietà del <xref:System.Drawing.Printing.PrintDocument> componente.  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Stampare un File di testo con più pagine in Windows Form](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [Supporto per la stampa in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
