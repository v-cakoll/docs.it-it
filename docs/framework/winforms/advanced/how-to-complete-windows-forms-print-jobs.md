---
title: 'Procedura: Completare processi di stampa in Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: a95e07596a10e67d32fdd0af036a14e8d66390c7
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053027"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>Procedura: Completare processi di stampa in Windows Form
Spesso, elaboratori di testo e altre applicazioni che eseguono processi di stampa fornirà l'opzione per visualizzare un messaggio agli utenti che un processo di stampa è stato completato. È possibile fornire questa funzionalità nei tuoi moduli di Windows tramite la gestione di <xref:System.Drawing.Printing.PrintDocument.EndPrint> eventi del <xref:System.Drawing.Printing.PrintDocument> componente.  
  
 La procedura seguente richiede che è stata creata un'applicazione basata su Windows con un <xref:System.Drawing.Printing.PrintDocument> componente su di esso, che è il metodo standard per consentire la stampa da un'applicazione basata su Windows. Per altre informazioni sulla stampa di Windows Form usando la <xref:System.Drawing.Printing.PrintDocument> componente, vedere [come: Creare processi di stampa Standard Windows Forms](how-to-create-standard-windows-forms-print-jobs.md).  
  
### <a name="to-complete-a-print-job"></a>Per completare un processo di stampa  
  
1. Impostare il <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> proprietà del <xref:System.Drawing.Printing.PrintDocument> componente.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2. Scrivere codice per gestire l'evento <xref:System.Drawing.Printing.PrintDocument.EndPrint> .  
  
     Nell'esempio di codice seguente, verrà visualizzata una finestra di messaggio, che indica che il documento ha terminato la stampa.  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,   
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +   
          " has finished printing.");  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     (Visual C# e Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Printing.PrintDocument>
- [Supporto per la stampa in Windows Forms](windows-forms-print-support.md)
