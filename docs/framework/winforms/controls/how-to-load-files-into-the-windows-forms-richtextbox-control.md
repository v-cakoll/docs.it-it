---
title: Carica i file nel controllo RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying files
- examples [Windows Forms], text boxes
- .rtf files [Windows Forms], opening in RichTextBox control
- RTF files [Windows Forms], opening in RichTextBox control
- text files [Windows Forms], displaying in RichTextBox control
- .rtf files [Windows Forms], displaying in RichTextBox control
- RichTextBox control [Windows Forms], opening files
- RTF files [Windows Forms], displaying in RichTextBox control
ms.assetid: c03451be-f285-4428-a71a-c41e002cc919
ms.openlocfilehash: c31e004ea4cd0821b5f18f0ab0fe2708e6ac4b59
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736293"
---
# <a name="how-to-load-files-into-the-windows-forms-richtextbox-control"></a>Procedura: caricare file nel controllo RichTextBox Windows Form

Il controllo <xref:System.Windows.Forms.RichTextBox> Windows Form consente di visualizzare un file come testo normale, testo normale Unicode o in formato RTF (Rich-Text Format). Per eseguire questa operazione, chiamare il metodo <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> . È anche possibile usare <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> per caricare dati da un flusso. Per altre informazioni, vedere <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.

### <a name="to-load-a-file-into-the-richtextbox-control"></a>Per caricare un file nel controllo RichTextBox

1. Determinare il percorso del file da aprire usando il componente <xref:System.Windows.Forms.OpenFileDialog> . Per una panoramica, vedere [Cenni preliminari sul componente OpenFileDialog](openfiledialog-component-overview-windows-forms.md).

2. Chiamare il metodo <xref:System.Windows.Forms.RichTextBox.LoadFile%2A><xref:System.Windows.Forms.RichTextBox> specificando il file da caricare e, facoltativamente, un tipo di file. Nell'esempio seguente il file da caricare viene preso dalla proprietà <xref:System.Windows.Forms.OpenFileDialog> del componente <xref:System.Windows.Forms.FileDialog.FileName%2A> . Se si chiama il metodo usando come unico argomento un nome di file, si presuppone che il tipo del file sia RTF. Per specificare un altro tipo di file, chiamare il metodo con un valore dell'enumerazione <xref:System.Windows.Forms.RichTextBoxStreamType> come secondo argomento.

    Nell'esempio seguente viene visualizzato il componente <xref:System.Windows.Forms.OpenFileDialog> quando si fa clic su un pulsante. Il file selezionato viene quindi aperto e visualizzato nel controllo <xref:System.Windows.Forms.RichTextBox> . In questo esempio si presuppone l'esistenza di un form contenente un pulsante`btnOpenFile`.

    ```vb
    Private Sub btnOpenFile_Click(ByVal sender As System.Object, _
       ByVal e As System.EventArgs) Handles btnOpenFile.Click
         If OpenFileDialog1.ShowDialog() = DialogResult.OK Then
           RichTextBox1.LoadFile(OpenFileDialog1.FileName, _
              RichTextBoxStreamType.RichText)
          End If
    End Sub
    ```

    ```csharp
    private void btnOpenFile_Click(object sender, System.EventArgs e)
    {
       if(openFileDialog1.ShowDialog() == DialogResult.OK)
       {
         richTextBox1.LoadFile(openFileDialog1.FileName, RichTextBoxStreamType.RichText);
       }
    }
    ```

    ```cpp
    private:
       void btnOpenFile_Click(System::Object ^  sender,
          System::EventArgs ^  e)
       {
          if(openFileDialog1->ShowDialog() == DialogResult::OK)
          {
             richTextBox1->LoadFile(openFileDialog1->FileName,
                RichTextBoxStreamType::RichText);
          }
       }
    ```

    (Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.

    ```csharp
    this.btnOpenFile.Click += new System.EventHandler(this. btnOpenFile_Click);
    ```

    ```cpp
    this->btnOpenFile->Click += gcnew
       System::EventHandler(this, &Form1::btnOpenFile_Click);
    ```

    > [!IMPORTANT]
    > Per eseguire questo processo, l'assembly può richiede un livello di privilegio concesso dalla classe <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> . Se l'esecuzione avviene in un contesto parzialmente attendibile, è possibile che il processo generi un'eccezione dovuta a privilegi insufficienti. Per altre informazioni, vedere [Code Access Security Basics](../../misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.RichTextBox.LoadFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [Controllo RichTextBox](richtextbox-control-windows-forms.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
