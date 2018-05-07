---
title: 'Procedura: creare una casella di testo Password con il controllo TextBox Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], entering passwords
- password boxes [Windows Forms], creating
- PasswordChar property in text boxes
- passwords [Windows Forms], input mask
- passwords [Windows Forms], password text box
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
ms.openlocfilehash: 41bfb2bc1a1ead5bb289264c44145b88721efe49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a>Procedura: creare una casella di testo Password con il controllo TextBox Windows Form
Una casella della password è una casella di testo di Windows Form che consente di visualizzare caratteri segnaposto mentre l'utente digita una stringa.  
  
### <a name="to-create-a-password-text-box"></a>Per creare una casella di testo password  
  
1.  Impostare il <xref:System.Windows.Forms.TextBox.PasswordChar%2A> proprietà del <xref:System.Windows.Forms.TextBox> controllo a un carattere specifico.  
  
     Il <xref:System.Windows.Forms.TextBox.PasswordChar%2A> proprietà specifica il carattere visualizzato nella casella di testo. Ad esempio, se si desidera asterischi visualizzati nella casella password, specificare * per il <xref:System.Windows.Forms.TextBox.PasswordChar%2A> proprietà nella finestra Proprietà. Quindi, indipendentemente dal qual è il carattere di un utente digita nella casella di testo, viene visualizzato un asterisco.  
  
2.  (Facoltativo) Impostare il <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> proprietà. La proprietà determina il numero di caratteri può essere digitato nella casella di testo. Se viene superata la lunghezza massima, il sistema genera un segnale acustico e la casella di testo non accetta ulteriori caratteri. Si noti che non si consiglia di eseguire questa operazione come la lunghezza massima di una password possono essere utilizzata da utenti malintenzionati che tentano di indovinare la password.  
  
     Esempio di codice seguente viene illustrato come inizializzare una casella di testo che accetta una stringa fino a 14 caratteri e visualizzano gli asterischi al posto della stringa. Il `InitializeMyControl` procedura non verrà eseguito automaticamente; deve essere chiamato.  
  
    > [!IMPORTANT]
    >  Utilizzo di <xref:System.Windows.Forms.TextBox.PasswordChar%2A> proprietà in una casella di testo può garantire che altri utenti non sarà in grado di determinare una password, se si osserva l'utente immetterlo. Questa misura di sicurezza non comprende una sorta di archiviazione o la trasmissione della password che possono verificarsi a causa della logica dell'applicazione. Poiché il testo immesso non è crittografato in alcun modo, è necessario considerare come qualsiasi altro tipo di dati riservati. Anche se non viene visualizzato di conseguenza, la password verrà comunque considerata come una stringa di testo normale (a meno che non è stato implementato un aggiuntiva di sicurezza).  
  
    ```vb  
    Private Sub InitializeMyControl()  
       ' Set to no text.  
       TextBox1.Text = ""  
       ' The password character is an asterisk.  
       TextBox1.PasswordChar = "*"  
       ' The control will allow no more than 14 characters.  
       TextBox1.MaxLength = 14  
    End Sub  
    ```  
  
    ```csharp  
    private void InitializeMyControl()  
    {  
       // Set to no text.  
       textBox1.Text = "";  
       // The password character is an asterisk.  
       textBox1.PasswordChar = '*';  
       // The control will allow no more than 14 characters.  
       textBox1.MaxLength = 14;  
    }  
    ```  
  
    ```cpp  
    private:  
       void InitializeMyControl()  
       {  
          // Set to no text.  
          textBox1->Text = "";  
          // The password character is an asterisk.  
          textBox1->PasswordChar = '*';  
          // The control will allow no more than 14 characters.  
          textBox1->MaxLength = 14;  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.TextBox>  
 [Cenni preliminari sul controllo TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Procedura: Creare una casella di testo in sola lettura](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [Procedura: Inserire virgolette in una stringa](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Procedura: Selezionare testo nel controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [Procedura: Visualizzare più righe nel controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [Controllo TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
