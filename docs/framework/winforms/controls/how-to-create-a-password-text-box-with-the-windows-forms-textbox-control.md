---
title: Crea una casella di testo password con il controllo TextBox
description: Informazioni su come crea un testo Windows Forms che Visualizza i caratteri segnaposto mentre un utente digita una stringa.
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
ms.openlocfilehash: 6d7e61eefa44ce3152aa77e3922bde471a4aeaf3
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904312"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a>Procedura: creare una casella di testo Password con il controllo TextBox Windows Form

Una casella password è una casella di testo Windows Forms che Visualizza i caratteri segnaposto mentre un utente digita una stringa.

### <a name="to-create-a-password-text-box"></a>Per creare una casella di testo password

1. Impostare la <xref:System.Windows.Forms.TextBox.PasswordChar%2A> proprietà del <xref:System.Windows.Forms.TextBox> controllo su un carattere specifico.

    La <xref:System.Windows.Forms.TextBox.PasswordChar%2A> proprietà specifica il carattere visualizzato nella casella di testo. Se, ad esempio, si desidera visualizzare gli asterischi nella casella password, specificare * per la <xref:System.Windows.Forms.TextBox.PasswordChar%2A> proprietà nell'finestra Proprietà. Quindi, indipendentemente dal carattere che un utente digita nella casella di testo, viene visualizzato un asterisco.

2. Opzionale Impostare la <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> Proprietà. La proprietà determina il numero di caratteri che possono essere digitati nella casella di testo. Se viene superata la lunghezza massima, il sistema emette un segnale acustico e la casella di testo non accetta più caratteri. Si noti che è possibile che non si desideri eseguire questa operazione perché la lunghezza massima di una password può essere usata per gli hacker che tentano di indovinare la password.

    Nell'esempio di codice seguente viene illustrato come inizializzare una casella di testo che accetterà una stringa con un massimo di 14 caratteri e visualizzerà gli asterischi al posto della stringa. La `InitializeMyControl` stored procedure non verrà eseguita automaticamente, ma deve essere chiamata.

    > [!IMPORTANT]
    > Utilizzando la <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Proprietà in una casella di testo è possibile garantire che altri utenti non possano determinare la password di un utente se osservano l'utente che lo immette. Questa misura di sicurezza non copre alcun tipo di archiviazione o trasmissione della password che può verificarsi a causa della logica dell'applicazione. Poiché il testo immesso non è crittografato in alcun modo, è consigliabile considerarlo come tutti gli altri dati riservati. Anche se non viene visualizzato come tale, la password viene comunque considerata come una stringa di testo normale (a meno che non siano state implementate misure di sicurezza aggiuntive).

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

- <xref:System.Windows.Forms.TextBox>
- [Cenni preliminari sul controllo TextBox](textbox-control-overview-windows-forms.md)
- [Procedura: controllare il punto di inserimento in un controllo TextBox Windows Form](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedura: creare una casella di testo in sola lettura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Procedura: inserire virgolette in una stringa](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedura: selezionare testo nel controllo TextBox Windows Form](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Procedura: visualizzare più righe nel controllo TextBox Windows Form](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Controllo TextBox](textbox-control-windows-forms.md)
