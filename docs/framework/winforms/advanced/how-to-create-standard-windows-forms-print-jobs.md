---
title: 'Procedura: creare processi di stampa standard per Windows Form'
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
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69499cdee7803de504e960b08754df33602cfcf6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Procedura: creare processi di stampa standard per Windows Form
Del processo di stampa in Windows Form è la <xref:System.Drawing.Printing.PrintDocument> componente, in particolare, il <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento. Mediante la scrittura di codice per gestire il <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento, è possibile specificare cosa stampare e come stamparlo.  
  
### <a name="to-create-a-print-job"></a>Per creare un processo di stampa  
  
1.  Aggiungere un <xref:System.Drawing.Printing.PrintDocument> componente al form.  
  
2.  Scrivere codice per gestire l'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>.  
  
     È necessario codice la propria logica di stampa. Inoltre, è necessario specificare il materiale per la stampa.  
  
     Nell'esempio di codice seguente viene creato un grafico di esempio nella forma di un rettangolo rosso nel <xref:System.Drawing.Printing.PrintDocument.PrintPage> gestore dell'evento come materiale da stampare.  
  
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
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
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
  
     È anche possibile scrivere codice per il <xref:System.Drawing.Printing.PrintDocument.BeginPrint> e <xref:System.Drawing.Printing.PrintDocument.EndPrint> eventi, includendo un intero che rappresenta il numero totale di pagine da stampare con decrementato di stampa di ogni pagina.  
  
    > [!NOTE]
    >  È possibile aggiungere un <xref:System.Windows.Forms.PrintDialog> componente al form per fornire un'interfaccia utente pulita ed efficiente (UI) per gli utenti. L'impostazione di <xref:System.Windows.Forms.PrintDialog.Document%2A> proprietà del <xref:System.Windows.Forms.PrintDialog> Abilita componente è possibile impostare proprietà relative alla stampa dei documenti si lavora con il modulo. Per ulteriori informazioni sul <xref:System.Windows.Forms.PrintDialog> componente, vedere [componente PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).  
  
     Per ulteriori informazioni sulle specifiche di Windows Form i processi di stampa, incluse informazioni sulla creazione di un processo di stampa a livello di codice, vedere <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Supporto per la stampa in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
