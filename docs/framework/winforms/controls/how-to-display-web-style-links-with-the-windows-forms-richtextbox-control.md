---
title: 'Procedura: Visualizzare collegamenti ipertestuali con il controllo RichTextBox di Windows Forms'
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
ms.openlocfilehash: 05d9ad4766584b59cca7c31f49b737d4696a9921
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053544"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>Procedura: Visualizzare collegamenti ipertestuali con il controllo RichTextBox di Windows Forms
I moduli di Windows <xref:System.Windows.Forms.RichTextBox> controllo può visualizzare i collegamenti Web colorati e sottolineato. È possibile scrivere codice che consente di aprire una finestra del browser con il sito Web specificato nel testo del collegamento quando viene selezionato il collegamento.  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>Il collegamento a una pagina Web con il controllo RichTextBox  
  
1. Impostare il <xref:System.Windows.Forms.RichTextBox.Text%2A> proprietà in una stringa che include un URL valido (ad esempio, "http://www.microsoft.com/").  
  
2. Assicurarsi che il <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> è impostata su `true` (predefinito).  
  
3. Creare una nuova istanza globale di <xref:System.Diagnostics.Process> oggetto.  
  
4. Scrivere un gestore eventi per il <xref:System.Windows.Forms.RichTextBox.LinkClicked> eventi che invia il testo desiderato nel browser.  
  
     Nell'esempio seguente, il <xref:System.Windows.Forms.RichTextBox.LinkClicked> eventi apre un'istanza di Internet Explorer all'URL specificato nella <xref:System.Windows.Forms.RichTextBox.Text%2A> proprietà del <xref:System.Windows.Forms.RichTextBox> controllo. Questo esempio si presuppone un form con un <xref:System.Windows.Forms.RichTextBox> controllo.  
  
    > [!IMPORTANT]
    >  Nella chiamata il <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> metodo, si verificherà un <xref:System.Security.SecurityException> eccezioni se si esegue il codice in un contesto parzialmente attendibile a causa di privilegi sufficienti. Per altre informazioni, vedere [Code Access Security Basics](../../misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).  
  
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
  
     (Visual C++) È necessario inizializzare il processo `p`, a questo scopo, includendo l'istruzione seguente nel costruttore del form:  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     (Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
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
  
     È importante arrestare immediatamente il processo che è stato creato dopo aver completato le operazioni desiderate. Il codice per arrestare il processo che fa riferimento al codice presentato in precedenza, potrebbe essere simile al seguente:  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [Controllo RichTextBox](richtextbox-control-windows-forms.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
