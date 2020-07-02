---
title: Selezionare il testo nel controllo TextBox
description: Informazioni su come selezionare il testo a livello di codice nel controllo TextBox Windows Forms. Viene inoltre illustrato come avvisare visivamente il lettore della posizione della stringa trovata.
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
ms.openlocfilehash: b8fdaff76461c4d6766dfc6afaef5e814d982834
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621561"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a>Procedura: selezionare testo nel controllo TextBox Windows Form
È possibile selezionare il testo a livello di codice nel <xref:System.Windows.Forms.TextBox> controllo Windows Forms. Se, ad esempio, si crea una funzione che cerca un testo per una determinata stringa, è possibile selezionare il testo per avvisare visivamente il lettore della posizione della stringa trovata.  
  
### <a name="to-select-text-programmatically"></a>Per selezionare il testo a livello di codice  
  
1. Impostare la <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> proprietà sull'inizio del testo che si desidera selezionare.  
  
     La <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> proprietà è un numero che indica il punto di inserimento all'interno della stringa di testo, con 0 è la posizione più a sinistra. Se la <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> proprietà è impostata su un valore maggiore o uguale al numero di caratteri nella casella di testo, il punto di inserimento viene inserito dopo l'ultimo carattere.  
  
2. Impostare la <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> proprietà sulla lunghezza del testo che si desidera selezionare.  
  
     La <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> proprietà è un valore numerico che imposta la larghezza del punto di inserimento. <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>Se si imposta su un numero maggiore di 0, viene selezionato il numero di caratteri, a partire dal punto di inserimento corrente.  
  
3. Opzionale Accedere al testo selezionato tramite la <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> Proprietà.  
  
     Il codice seguente consente di selezionare il contenuto di una casella di testo quando <xref:System.Windows.Forms.Control.Enter> si verifica l'evento del controllo. Questo esempio controlla se la casella di testo contiene un valore per la <xref:System.Windows.Forms.TextBox.Text%2A> proprietà che non è `null` o una stringa vuota. Quando la casella di testo riceve lo stato attivo, viene selezionato il testo corrente nella casella di testo. Il `TextBox1_Enter` gestore eventi deve essere associato al controllo. per ulteriori informazioni, vedere [procedura: creare gestori eventi in fase di esecuzione per Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Per testare questo esempio, premere il tasto TAB fino a quando la casella di testo non ha lo stato attivo. Se si fa clic nella casella di testo, il testo viene deselezionato.  
  
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
- [Cenni preliminari sul controllo TextBox](textbox-control-overview-windows-forms.md)
- [Procedura: controllare il punto di inserimento in un controllo TextBox Windows Form](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedura: creare una casella di testo Password con il controllo TextBox Windows Form](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedura: creare una casella di testo in sola lettura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Procedura: inserire virgolette in una stringa](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedura: visualizzare più righe nel controllo TextBox Windows Form](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Controllo TextBox](textbox-control-windows-forms.md)
