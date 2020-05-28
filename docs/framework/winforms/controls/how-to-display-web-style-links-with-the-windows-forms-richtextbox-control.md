---
title: Visualizzare collegamenti di tipo Web con il controllo RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying Web links
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], linking to Web pages
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
ms.openlocfilehash: 06ed304e566bb437a2353dd330d7de5328f2a729
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144825"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>Procedura: visualizzare collegamenti ipertestuali con il controllo RichTextBox Windows Form

Il <xref:System.Windows.Forms.RichTextBox> controllo Windows Forms può visualizzare i collegamenti Web come colorati e sottolineati. È possibile scrivere codice che apre una finestra del browser in cui viene visualizzato il sito Web specificato nel testo del collegamento quando si fa clic sul collegamento.

### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>Per eseguire il collegamento a una pagina Web con il controllo RichTextBox

1. Impostare la <xref:System.Windows.Forms.RichTextBox.Text%2A> proprietà su una stringa che include un URL valido, ad esempio " https://www.microsoft.com/ ".

2. Verificare che la <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> proprietà sia impostata su `true` (impostazione predefinita).

3. Creare una nuova istanza globale dell' <xref:System.Diagnostics.Process> oggetto.

4. Scrivere un gestore eventi per l' <xref:System.Windows.Forms.RichTextBox.LinkClicked> evento che invia al browser il testo desiderato.

    Nell'esempio seguente l' <xref:System.Windows.Forms.RichTextBox.LinkClicked> evento apre un'istanza di Internet Explorer all'URL specificato nella <xref:System.Windows.Forms.RichTextBox.Text%2A> proprietà del <xref:System.Windows.Forms.RichTextBox> controllo. In questo esempio si presuppone un form con un <xref:System.Windows.Forms.RichTextBox> controllo.

    > [!IMPORTANT]
    > <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>Quando si chiama il metodo, si verificherà un' <xref:System.Security.SecurityException> eccezione se si esegue il codice in un contesto parzialmente attendibile a causa di privilegi insufficienti. Per altre informazioni, vedere [Code Access Security Basics](../../misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).

    ```vb
    Public p As New System.Diagnostics.Process
    Private Sub RichTextBox1_LinkClicked _
       (ByVal sender As Object, ByVal e As _
       System.Windows.Forms.LinkClickedEventArgs) _
       Handles RichTextBox1.LinkClicked
          ' Call Process.Start method to open a browser
          ' with link text as URL.
          p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText)
    End Sub
    ```

    ```csharp
    public System.Diagnostics.Process p = new System.Diagnostics.Process();

    private void richTextBox1_LinkClicked(object sender,
    System.Windows.Forms.LinkClickedEventArgs e)
    {
       // Call Process.Start method to open a browser
       // with link text as URL.
       p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText);
    }
    ```

    ```cpp
    public:
       System::Diagnostics::Process ^ p;

    private:
       void richTextBox1_LinkClicked(System::Object ^  sender,
          System::Windows::Forms::LinkClickedEventArgs ^  e)
       {
          // Call Process.Start method to open a browser
          // with link text as URL.
          p = System::Diagnostics::Process::Start("IExplore.exe",
             e->LinkText);
       }
    ```

    (Visual C++) È necessario inizializzare `p` il processo, operazione che è possibile eseguire includendo l'istruzione seguente nel costruttore del form:

    ```cpp
    p = gcnew System::Diagnostics::Process();
    ```

    (Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.

    ```csharp
    this.richTextBox1.LinkClicked += new
       System.Windows.Forms.LinkClickedEventHandler
       (this.richTextBox1_LinkClicked);
    ```

    ```cpp
    this->richTextBox1->LinkClicked += gcnew
       System::Windows::Forms::LinkClickedEventHandler
       (this, &Form1::richTextBox1_LinkClicked);
    ```

    È importante arrestare immediatamente il processo creato dopo averne terminato l'utilizzo. Facendo riferimento al codice illustrato in precedenza, il codice per arrestare il processo potrebbe essere simile al seguente:

    ```vb
    Public Sub StopWebProcess()
       p.Kill()
    End Sub
    ```

    ```csharp
    public void StopWebProcess()
    {
       p.Kill();
    }
    ```

    ```cpp
    public: void StopWebProcess()
    {
       p->Kill();
    }
    ```

## <a name="see-also"></a>Vedi anche

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [Controllo RichTextBox](richtextbox-control-windows-forms.md)
- [Controlli da utilizzare in Windows Form](controls-to-use-on-windows-forms.md)
