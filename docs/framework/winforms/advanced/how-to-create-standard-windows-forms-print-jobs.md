---
title: Creazione di processi di stampa standard
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
ms.openlocfilehash: d9607de7c74132e0d7dce605b16d62c79b7dbccb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182573"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Procedura: creare processi di stampa standard per Windows Form
La base della stampa in <xref:System.Drawing.Printing.PrintDocument> Windows Form è <xref:System.Drawing.Printing.PrintDocument.PrintPage> il componente, più specificamente, l'evento. Scrivendo il codice <xref:System.Drawing.Printing.PrintDocument.PrintPage> per gestire l'evento, è possibile specificare cosa stampare e come stamparlo.  
  
### <a name="to-create-a-print-job"></a>Per creare un processo di stampa  
  
1. Aggiungere <xref:System.Drawing.Printing.PrintDocument> un componente al form.  
  
2. Scrivere codice per gestire l'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> .  
  
     Dovrai codificare la tua logica di stampa. Inoltre, è necessario specificare il materiale da stampare.  
  
     Nell'esempio di codice seguente, nel gestore eventi viene <xref:System.Drawing.Printing.PrintDocument.PrintPage> creato un elemento grafico di esempio a forma di rettangolo rosso per fungere da materiale da stampare.  
  
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
  
     (Visual Cè e Visual C Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
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
  
     È anche possibile scrivere codice <xref:System.Drawing.Printing.PrintDocument.BeginPrint> <xref:System.Drawing.Printing.PrintDocument.EndPrint> per gli eventi e , includendo ad esempio un numero intero che rappresenta il numero totale di pagine da stampare che viene decrementato durante la stampa di ogni pagina.  
  
    > [!NOTE]
    > È possibile <xref:System.Windows.Forms.PrintDialog> aggiungere un componente al form per fornire agli utenti un'interfaccia utente pulita ed efficiente. L'impostazione <xref:System.Windows.Forms.PrintDialog.Document%2A> <xref:System.Windows.Forms.PrintDialog> della proprietà del componente consente di impostare le proprietà relative al documento di stampa che si sta lavorando nel modulo. Per ulteriori informazioni <xref:System.Windows.Forms.PrintDialog> sul componente, vedere [PrintDialog Component](../controls/printdialog-component-windows-forms.md).  
  
     Per ulteriori informazioni sulle specifiche dei processi di stampa di Windows Form, <xref:System.Drawing.Printing.PrintPageEventArgs>inclusa la creazione di un processo di stampa a livello di codice, vedere .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Printing.PrintDocument>
- [Supporto per la stampa in Windows Form](windows-forms-print-support.md)
