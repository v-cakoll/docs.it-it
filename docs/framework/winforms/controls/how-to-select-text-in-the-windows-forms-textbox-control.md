---
title: 'Procedura: Selezionare testo nel controllo TextBox di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
ms.openlocfilehash: 3bb1245cd47084935d632ff345a32058db6074e1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321712"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a>Procedura: Selezionare testo nel controllo TextBox di Windows Forms
È possibile selezionare il testo a livello di codice nei moduli di Windows <xref:System.Windows.Forms.TextBox> controllo. Ad esempio, se si crea una funzione che cerca il testo per una determinata stringa, è possibile selezionare il testo da mostrare all'utente il lettore della posizione della stringa trovata.  
  
### <a name="to-select-text-programmatically"></a>Per selezionare il testo a livello di codice  
  
1. Impostare il <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> proprietà all'inizio del testo che si desidera selezionare.  
  
     Il <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> proprietà è un numero che indica il punto di inserimento all'interno della stringa di testo, con 0 la posizione più a sinistra. Se il <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> proprietà è impostata su un valore uguale o maggiore del numero di caratteri nella casella di testo, il punto di inserimento viene posizionato dopo l'ultimo carattere.  
  
2. Impostare il <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> proprietà per la lunghezza del testo che si desidera selezionare.  
  
     Il <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> proprietà è un valore numerico che imposta la larghezza del punto di inserimento. L'impostazione di <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> su un numero maggiore di 0 fa sì che tale numero di caratteri da selezionare, a partire dal punto di inserimento corrente.  
  
3. (Facoltativo) Accedere al testo selezionato tramite i <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> proprietà.  
  
     Il codice seguente consente di selezionare il contenuto del testo di una finestra quando il controllo <xref:System.Windows.Forms.Control.Enter> evento si verifica. In questo esempio controlla se la casella di testo ha un valore per il <xref:System.Windows.Forms.TextBox.Text%2A> proprietà non `null` o una stringa vuota. Quando la casella di testo riceve lo stato attivo, viene selezionato il testo corrente nella casella di testo. Il `TextBox1_Enter` gestore dell'evento deve essere associato al controllo; per altre informazioni, vedere [come: Creare i gestori eventi in fase di esecuzione per Windows Form](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Per testare questo esempio, premere il tasto Tab fino a quando la casella di testo ha lo stato attivo. Se si fa clic nella casella di testo, il testo è deselezionato.  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TextBox>
- [Panoramica del controllo TextBox](textbox-control-overview-windows-forms.md)
- [Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedura: Creare una casella di testo di sola lettura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Procedura: Inserire virgolette in una stringa](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedura: Visualizzare più righe nel controllo TextBox di Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Controllo TextBox](textbox-control-windows-forms.md)
