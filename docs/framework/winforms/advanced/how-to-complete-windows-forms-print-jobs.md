---
title: Completamento dei processi di stampa
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: 62f67002bfbaf46e73bae06fdaff26efde865c06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182592"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>Procedura: completare processi di stampa in Windows Form
Spesso, gli elaboratori di testo e altre applicazioni che implicano la stampa offrono la possibilità di visualizzare un messaggio agli utenti che indica che un processo di stampa è stato completato. È possibile fornire questa funzionalità in <xref:System.Drawing.Printing.PrintDocument.EndPrint> Windows Form <xref:System.Drawing.Printing.PrintDocument> gestendo l'evento del componente.  
  
 La procedura seguente richiede la creazione di un'applicazione basata su Windows con un <xref:System.Drawing.Printing.PrintDocument> componente su di essa, che è il modo standard per abilitare la stampa da un'applicazione basata su Windows.The following procedure requires that you have created a Windows-based application with a component on it, which is the standard way of enabling printing from a Windows-based application. Per ulteriori informazioni sulla stampa <xref:System.Drawing.Printing.PrintDocument> da Windows Form utilizzando il componente, vedere [Procedura: Creare processi](how-to-create-standard-windows-forms-print-jobs.md)di stampa standard di Windows Form .  
  
### <a name="to-complete-a-print-job"></a>Per completare un processo di stampa  
  
1. Impostare <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> la <xref:System.Drawing.Printing.PrintDocument> proprietà del componente.  
  
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
  
     Nell'esempio di codice riportato di seguito viene visualizzata una finestra di messaggio che indica che la stampa del documento è terminata.  
  
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
  
     (Visual Cè e Visual C Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
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
- [Supporto per la stampa in Windows Form](windows-forms-print-support.md)
