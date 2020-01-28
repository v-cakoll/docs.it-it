---
title: 'Procedura: scegliere le stampanti collegate al computer di un utente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms], choosing printers
- printers [Windows Forms], choosing
ms.assetid: 63c1172b-2931-4ac0-953f-37f629494bbf
ms.openlocfilehash: 7fc2427468540ac0a1480f6140cbb34c3a0f1ab3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746506"
---
# <a name="how-to-choose-the-printers-attached-to-a-users-computer-in-windows-forms"></a>Procedura: selezionare le stampanti connesse al computer dell'utente in Windows Form
Spesso gli utenti vogliono scegliere una stampante diversa da quella predefinita. È possibile consentire agli utenti di selezionare una stampante tra quelle attualmente installate usando il componente <xref:System.Windows.Forms.PrintDialog> . Tramite il componente <xref:System.Windows.Forms.PrintDialog> , l'oggetto <xref:System.Windows.Forms.DialogResult> del componente <xref:System.Windows.Forms.PrintDialog> viene acquisito e usato per selezionare la stampante.  
  
 Nella procedura seguente viene selezionato un file di testo da stampare sulla stampante predefinita. Viene quindi creata un'istanza della classe <xref:System.Windows.Forms.PrintDialog> .  
  
### <a name="to-choose-a-printer-and-then-print-a-file"></a>Per selezionare una stampante e stampare un file  
  
1. Selezionare la stampante da usare tramite il componente <xref:System.Windows.Forms.PrintDialog>.  
  
     Nell'esempio di codice seguente vengono gestiti due eventi. Nel primo, un evento di <xref:System.Windows.Forms.Control.Click> del controllo <xref:System.Windows.Forms.Button>, viene creata un'istanza della classe <xref:System.Windows.Forms.PrintDialog> e la stampante selezionata dall'utente viene acquisita nella proprietà <xref:System.Windows.Forms.DialogResult>.  
  
     Nel secondo evento, il <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento del componente <xref:System.Drawing.Printing.PrintDocument>, un documento di esempio viene stampato sulla stampante specificata.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim PrintDialog1 As New PrintDialog()  
       PrintDialog1.Document = PrintDocument1  
       Dim result As DialogResult = PrintDialog1.ShowDialog()  
  
       If (result = DialogResult.OK) Then  
         PrintDocument1.Print()  
       End If   
  
    End Sub  
  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))          
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       PrintDialog printDialog1 = new PrintDialog();  
       printDialog1.Document = printDocument1;  
       DialogResult result = printDialog1.ShowDialog();  
       if (result == DialogResult.OK)  
       {  
          printDocument1.Print();  
       }  
    }  
  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          PrintDialog ^ printDialog1 = gcnew PrintDialog();  
          printDialog1->Document = printDocument1;  
          System::Windows::Forms::DialogResult result =   
             printDialog1->ShowDialog();  
          if (result == DialogResult::OK)  
          {  
             printDocument1->Print();  
          }  
       }  
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
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Supporto per la stampa in Windows Forms](windows-forms-print-support.md)
