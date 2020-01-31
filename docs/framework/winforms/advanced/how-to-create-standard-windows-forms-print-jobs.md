---
title: Creare processi di stampa standard
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
ms.openlocfilehash: 4850dc901630179cc44fefda7e25bbabcfb4725f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741513"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Procedura: creare processi di stampa standard per Windows Form
Il fondamento della stampa in Windows Forms è costituito dal componente <xref:System.Drawing.Printing.PrintDocument>, più in particolare, dal <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento. Scrivendo il codice per gestire l'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>, è possibile specificare gli elementi da stampare e la relativa modalità di stampa.  
  
### <a name="to-create-a-print-job"></a>Per creare un processo di stampa  
  
1. Aggiungere un componente <xref:System.Drawing.Printing.PrintDocument> al modulo.  
  
2. Scrivere codice per gestire l'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> .  
  
     Dovrai scrivere codice per la tua logica di stampa. Inoltre, sarà necessario specificare il materiale da stampare.  
  
     Nell'esempio di codice seguente viene creato un grafico di esempio nella forma di un rettangolo rosso nel gestore dell'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> per agire come materiale da stampare.  
  
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
  
     (Visual C# e Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
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
  
     È anche possibile scrivere il codice per gli eventi <xref:System.Drawing.Printing.PrintDocument.BeginPrint> e <xref:System.Drawing.Printing.PrintDocument.EndPrint>, incluso un intero che rappresenta il numero totale di pagine da stampare che viene decrementato Man mano che ogni pagina viene stampata.  
  
    > [!NOTE]
    > È possibile aggiungere un componente <xref:System.Windows.Forms.PrintDialog> al modulo per fornire agli utenti un'interfaccia utente pulita ed efficiente. L'impostazione della proprietà <xref:System.Windows.Forms.PrintDialog.Document%2A> del componente <xref:System.Windows.Forms.PrintDialog> consente di impostare le proprietà correlate al documento di stampa che si sta utilizzando nel form. Per ulteriori informazioni sul componente <xref:System.Windows.Forms.PrintDialog>, vedere [componente PrintDialog](../controls/printdialog-component-windows-forms.md).  
  
     Per ulteriori informazioni sulle specifiche di Windows Forms processi di stampa, inclusa la modalità di creazione di un processo di stampa a livello di codice, vedere <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Printing.PrintDocument>
- [Supporto per la stampa in Windows Forms](windows-forms-print-support.md)
