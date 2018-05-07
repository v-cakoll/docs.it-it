---
title: 'Procedura: salvare file con il controllo RichTextBox Windows Form'
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
ms.openlocfilehash: c50b2f3309c1f811b29e824327a709e2cc4bd791
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a>Procedura: salvare file con il controllo RichTextBox Windows Form
Windows Form <xref:System.Windows.Forms.RichTextBox> controllo consente di scrivere le informazioni da visualizzare in uno dei seguenti formati:  
  
-   Testo normale  
  
-   Testo normale Unicode  
  
-   Il formato RTF (RICH)  
  
-   RTF con spazi al posto di oggetti OLE  
  
-   Testo normale con una rappresentazione testuale di oggetti OLE  
  
 Per salvare un file, chiamare il <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> metodo. È inoltre possibile utilizzare il **SaveFile** per salvare i dati in un flusso. Per altre informazioni, vedere <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.  
  
### <a name="to-save-the-contents-of-the-control-to-a-file"></a>Per salvare il contenuto del controllo in un file  
  
1.  Determinare il percorso del file da salvare.  
  
     Per eseguire questa operazione in un'applicazione reale, in genere si utilizzerà il <xref:System.Windows.Forms.SaveFileDialog> componente. Per una panoramica, vedere [Cenni preliminari sul componente SaveFileDialog](../../../../docs/framework/winforms/controls/savefiledialog-component-overview-windows-forms.md).  
  
2.  Chiamare il <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> metodo il <xref:System.Windows.Forms.RichTextBox> (controllo), specificando il file da salvare e, facoltativamente, un tipo di file. Se si chiama il metodo con un nome di file come unico argomento, il file verrà salvato in formato RTF. Per specificare un altro tipo di file, chiamare il metodo con un valore dell'enumerazione <xref:System.Windows.Forms.RichTextBoxStreamType> come secondo argomento.  
  
     Nell'esempio seguente, il percorso impostato per il percorso del file RTF è il **documenti** cartella. Questo percorso viene utilizzato perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows sarà inclusa in questa cartella. Questa scelta consente anche agli utenti con livelli di accesso di sistema minimi eseguire in modo sicuro l'applicazione. Nell'esempio seguente si presuppone un form con un <xref:System.Windows.Forms.RichTextBox> controllo già aggiunto.  
  
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
    >  Questo esempio crea un nuovo file, se il file non esiste. Se un'applicazione deve creare un file, tale applicazione richiede accesso Create per la cartella. Le autorizzazioni vengono impostate tramite gli elenchi di controllo di accesso. Se il file esiste già, l'applicazione deve solo accesso in scrittura, un privilegio minore. Dove possibile, è più sicuro per creare il file durante la distribuzione e concedere solo accesso in lettura a un singolo file, anziché creare l'accesso per una cartella. Inoltre, è più sicuro scrivere dati nelle cartelle utente anziché nella cartella radice o nella cartella dei file di programma.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RichTextBox>  
 [Controllo RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
