---
title: 'Procedura: Creare processi di stampa standard per Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: 816da93218e20f73f16c14769ed1a549dd3d8eb3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937657"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Procedura: Creare processi di stampa standard per Windows Form
Del processo di stampa in Windows Form è la <xref:System.Drawing.Printing.PrintDocument> componente, in particolare, il <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento. Scrivendo codice per gestire il <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento, è possibile specificare cosa stampare e come stamparlo.  
  
### <a name="to-create-a-print-job"></a>Per creare un processo di stampa  
  
1. Aggiungere un <xref:System.Drawing.Printing.PrintDocument> al form.  
  
2. Scrivere codice per gestire l'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> .  
  
     Dovrai la propria logica di stampa di codice. Inoltre, è necessario specificare il materiale da stampare.  
  
     Nell'esempio di codice seguente, viene creato un grafico di esempio sotto forma di un rettangolo rosso nel <xref:System.Drawing.Printing.PrintDocument.PrintPage> gestore eventi per agire come materiale da stampare.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     (Visual c# e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     È anche possibile scrivere codice per il <xref:System.Drawing.Printing.PrintDocument.BeginPrint> e <xref:System.Drawing.Printing.PrintDocument.EndPrint> eventi, includendo un intero che rappresenta il numero totale di pagine da stampare decrementato che mano che verrà stampate le pagine.  
  
    > [!NOTE]
    >  È possibile aggiungere un <xref:System.Windows.Forms.PrintDialog> al form per fornire un'interfaccia utente pulita ed efficienti (UI) per gli utenti. Impostando il <xref:System.Windows.Forms.PrintDialog.Document%2A> proprietà del <xref:System.Windows.Forms.PrintDialog> Abilita componente è possibile impostare le proprietà correlate alla stampa di documenti si lavora con sul form. Per altre informazioni sul <xref:System.Windows.Forms.PrintDialog> componente, vedere [componente PrintDialog](../controls/printdialog-component-windows-forms.md).  
  
     Per altre informazioni sulle specifiche di Windows Form i processi di stampa, incluse quelle sulla creazione di un processo di stampa a livello di codice, vedere <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Printing.PrintDocument>
- [Supporto per la stampa in Windows Forms](windows-forms-print-support.md)
