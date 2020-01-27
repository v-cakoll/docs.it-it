---
title: Completa processi di stampa
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: b8ef4fa05b2107247181e82b72389f9503507135
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746500"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>Procedura: completare processi di stampa in Windows Form
Spesso, i processori di Word e le altre applicazioni che coinvolgono la stampa offrono la possibilità di visualizzare un messaggio agli utenti per completare un processo di stampa. È possibile fornire questa funzionalità nel Windows Forms gestendo l'evento <xref:System.Drawing.Printing.PrintDocument.EndPrint> del componente <xref:System.Drawing.Printing.PrintDocument>.  
  
 Per la procedura seguente è necessario aver creato un'applicazione basata su Windows con un componente <xref:System.Drawing.Printing.PrintDocument>, che rappresenta il modo standard per abilitare la stampa da un'applicazione basata su Windows. Per altre informazioni sulla stampa da Windows Forms usando il componente <xref:System.Drawing.Printing.PrintDocument>, vedere [procedura: creare processi di stampa Windows Forms standard](how-to-create-standard-windows-forms-print-jobs.md).  
  
### <a name="to-complete-a-print-job"></a>Per completare un processo di stampa  
  
1. Impostare la proprietà <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> del componente <xref:System.Drawing.Printing.PrintDocument>.  
  
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
  
     Nell'esempio di codice seguente viene visualizzata una finestra di messaggio che indica che il documento ha terminato la stampa.  
  
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
  
     (Visual C# e Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
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
