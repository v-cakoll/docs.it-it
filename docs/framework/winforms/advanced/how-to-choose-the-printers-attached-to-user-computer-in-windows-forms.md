---
title: 'Procedura: Selezionare le stampanti connesse a un utente&#39;s Computer in Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms], choosing printers
- printers [Windows Forms], choosing
ms.assetid: 63c1172b-2931-4ac0-953f-37f629494bbf
ms.openlocfilehash: 10f45fadab0f3480d4c475ff8ee448b8d1cddb13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572812"
---
# <a name="how-to-choose-the-printers-attached-to-a-user39s-computer-in-windows-forms"></a>Procedura: Selezionare le stampanti connesse a un utente&#39;s Computer in Windows Form
Spesso gli utenti vogliono scegliere una stampante diversa da quella predefinita. È possibile consentire agli utenti di selezionare una stampante tra quelle attualmente installate usando il componente <xref:System.Windows.Forms.PrintDialog> . Tramite il componente <xref:System.Windows.Forms.PrintDialog> , l'oggetto <xref:System.Windows.Forms.DialogResult> del componente <xref:System.Windows.Forms.PrintDialog> viene acquisito e usato per selezionare la stampante.  
  
 Nella procedura seguente viene selezionato un file di testo da stampare sulla stampante predefinita. Viene quindi creata un'istanza della classe <xref:System.Windows.Forms.PrintDialog> .  
  
### <a name="to-choose-a-printer-and-then-print-a-file"></a>Per selezionare una stampante e stampare un file  
  
1.  Selezionare la stampante da usare tramite il <xref:System.Windows.Forms.PrintDialog> componente.  
  
     Nell'esempio di codice seguente vengono gestiti due eventi. Nel primo, un <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> evento, il <xref:System.Windows.Forms.PrintDialog> viene creata un'istanza di classe e la stampante selezionata dall'utente viene acquisita nella <xref:System.Windows.Forms.DialogResult> proprietà.  
  
     Nel secondo caso, il <xref:System.Drawing.Printing.PrintDocument.PrintPage> eventi del <xref:System.Drawing.Printing.PrintDocument> componente, un documento di esempio viene stampato sulla stampante specificata.  
  
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
  
     (Visual c# e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
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
- [Supporto per la stampa in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
