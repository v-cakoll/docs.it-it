---
title: 'Procedura: visualizzare collegamenti ipertestuali con il controllo RichTextBox Windows Form'
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
ms.openlocfilehash: bd813d479cd4dfb61a08d9a8c4a4e7612084e878
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532607"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>Procedura: visualizzare collegamenti ipertestuali con il controllo RichTextBox Windows Form
Windows Form <xref:System.Windows.Forms.RichTextBox> controllo può visualizzare i collegamenti Web colorati e sottolineati. È possibile scrivere codice che apre una finestra del browser che mostra il sito Web specificato nel testo del collegamento quando viene selezionato il collegamento.  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>Il collegamento a una pagina Web con il controllo RichTextBox  
  
1.  Impostare il <xref:System.Windows.Forms.RichTextBox.Text%2A> proprietà in una stringa che include un URL valido (ad esempio, "http://www.microsoft.com/").  
  
2.  Verificare che il <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> è impostata su `true` (impostazione predefinita).  
  
3.  Creare una nuova istanza globale di <xref:System.Diagnostics.Process> oggetto.  
  
4.  Scrivere un gestore eventi per il <xref:System.Windows.Forms.RichTextBox.LinkClicked> evento che invia al browser il testo desiderato.  
  
     Nell'esempio seguente, il <xref:System.Windows.Forms.RichTextBox.LinkClicked> evento consente di aprire un'istanza di Internet Explorer per l'URL specificato nella <xref:System.Windows.Forms.RichTextBox.Text%2A> proprietà del <xref:System.Windows.Forms.RichTextBox> controllo. Questo esempio si presuppone un form con un <xref:System.Windows.Forms.RichTextBox> controllo.  
  
    > [!IMPORTANT]
    >  Nella chiamata di <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> metodo, si verificherà un <xref:System.Security.SecurityException> eccezione se si esegue il codice in un contesto parzialmente attendibile a causa di privilegi sufficienti. Per altre informazioni, vedere [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).  
  
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
  
     ([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) È necessario inizializzare processo `p`, che è possibile effettuare includendo l'istruzione seguente nel costruttore del form:  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     (Visual c#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
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
  
     È importante arrestare immediatamente il processo che è stato creato dopo aver completato le operazioni desiderate. Riferimento al codice presentato in precedenza, il codice per arrestare il processo potrebbe essere simile al seguente:  
  
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
 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>  
 <xref:System.Windows.Forms.RichTextBox.LinkClicked>  
 <xref:System.Windows.Forms.RichTextBox>  
 [Controllo RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
