---
title: Salva file con il controllo RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- RTF files [Windows Forms], saving in RichTextBox control
- examples [Windows Forms], text boxes
- saving files [Windows Forms], RichTextBox control
- files [Windows Forms], saving with RichTextBox control
- RichTextBox control [Windows Forms], saving files
- .rtf files [Windows Forms], saving in RichTextBox control
- text files [Windows Forms], saving from RichTextBox control
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
ms.openlocfilehash: a87b93a53347aeba54f944b0f4c455aa272ea243
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744814"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a>Procedura: salvare file con il controllo RichTextBox Windows Form

Il Windows Forms controllo <xref:System.Windows.Forms.RichTextBox> può scrivere le informazioni visualizzate in uno dei diversi formati:

- Testo normale

- Testo normale Unicode

- Formato Rich Text (RTF)

- RTF con spazi al posto degli oggetti OLE

- Testo normale con rappresentazione testuale di oggetti OLE

Per salvare un file, chiamare il metodo <xref:System.Windows.Forms.RichTextBox.SaveFile%2A>. È anche possibile usare il metodo **SaveFile** per salvare i dati in un flusso. Per altre informazioni, vedere <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.

### <a name="to-save-the-contents-of-the-control-to-a-file"></a>Per salvare il contenuto del controllo in un file

1. Determinare il percorso del file da salvare.

    Per eseguire questa operazione in un'applicazione reale, si usa in genere il componente <xref:System.Windows.Forms.SaveFileDialog>. Per una panoramica, vedere [Cenni preliminari sul componente SaveFileDialog](savefiledialog-component-overview-windows-forms.md).

2. Chiamare il metodo <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> del controllo <xref:System.Windows.Forms.RichTextBox>, specificando il file da salvare e, facoltativamente, un tipo di file. Se si chiama il metodo con un nome di file come unico argomento, il file verrà salvato come RTF. Per specificare un altro tipo di file, chiamare il metodo con un valore dell'enumerazione <xref:System.Windows.Forms.RichTextBoxStreamType> come secondo argomento.

    Nell'esempio riportato di seguito, il percorso impostato per il percorso del file di testo RTF è la cartella **documenti** . Questo percorso viene usato perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includa questa cartella. La scelta di questa località consente anche agli utenti con livelli di accesso di sistema minimi di eseguire l'applicazione in modo sicuro. Nell'esempio seguente si presuppone un modulo con un controllo <xref:System.Windows.Forms.RichTextBox> già aggiunto.

    ```vb
    Public Sub SaveFile()
       ' You should replace the bold file name in the
       ' sample below with a file name of your own choosing.
       RichTextBox1.SaveFile(System.Environment.GetFolderPath _
       (System.Environment.SpecialFolder.Personal) _
       & "\Testdoc.rtf", _
          RichTextBoxStreamType.RichNoOleObjs)
    End Sub
    ```

    ```csharp
    public void SaveFile()
    {
       // You should replace the bold file name in the
       // sample below with a file name of your own choosing.
       // Note the escape character used (@) when specifying the path.
       richTextBox1.SaveFile(System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\Testdoc.rtf",
          RichTextBoxStreamType.RichNoOleObjs);
    }
    ```

    ```cpp
    public:
       void SaveFile()
       {
          // You should replace the bold file name in the
          // sample below with a file name of your own choosing.
          richTextBox1->SaveFile(String::Concat
             (System::Environment::GetFolderPath
             (System::Environment::SpecialFolder::Personal),
             "\\Testdoc.rtf"), RichTextBoxStreamType::RichNoOleObjs);
       }
    ```

    > [!IMPORTANT]
    > Questo esempio crea un nuovo file, se il file non esiste. Se un'applicazione deve creare un file, l'applicazione deve creare l'accesso per la cartella. Le autorizzazioni vengono impostate tramite gli elenchi di controllo di accesso. Se il file esiste già, l'applicazione deve avere solo l'accesso in scrittura, un privilegio minore. Laddove possibile, è più sicuro creare il file durante la distribuzione e concedere solo l'accesso in lettura a un singolo file, anziché creare l'accesso per una cartella. Inoltre, è più sicuro scrivere dati nelle cartelle utente anziché nella cartella radice o nella cartella dei file di programma.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [Controllo RichTextBox](richtextbox-control-windows-forms.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
