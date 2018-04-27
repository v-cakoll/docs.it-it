---
title: 'Procedura: visualizzare collegamenti ipertestuali con il controllo RichTextBox Windows Form'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying Web links
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], linking to Web pages
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b82a5251cb5e1f632d126105cfae5cf2b8f62fc0
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="68e26-102">Procedura: visualizzare collegamenti ipertestuali con il controllo RichTextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="68e26-102">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="68e26-103">Windows Form <xref:System.Windows.Forms.RichTextBox> controllo può visualizzare i collegamenti Web colorati e sottolineati.</span><span class="sxs-lookup"><span data-stu-id="68e26-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display Web links as colored and underlined.</span></span> <span data-ttu-id="68e26-104">È possibile scrivere codice che apre una finestra del browser che mostra il sito Web specificato nel testo del collegamento quando viene selezionato il collegamento.</span><span class="sxs-lookup"><span data-stu-id="68e26-104">You can write code that opens a browser window showing the Web site specified in the link text when the link is clicked.</span></span>  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a><span data-ttu-id="68e26-105">Il collegamento a una pagina Web con il controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="68e26-105">To link to a Web page with the RichTextBox control</span></span>  
  
1.  <span data-ttu-id="68e26-106">Impostare il <xref:System.Windows.Forms.RichTextBox.Text%2A> proprietà in una stringa che include un URL valido (ad esempio, "http://www.microsoft.com/").</span><span class="sxs-lookup"><span data-stu-id="68e26-106">Set the <xref:System.Windows.Forms.RichTextBox.Text%2A> property to a string that includes a valid URL (for example, "http://www.microsoft.com/").</span></span>  
  
2.  <span data-ttu-id="68e26-107">Verificare che il <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> è impostata su `true` (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="68e26-107">Make sure the <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> property is set to `true` (the default).</span></span>  
  
3.  <span data-ttu-id="68e26-108">Creare una nuova istanza globale di <xref:System.Diagnostics.Process> oggetto.</span><span class="sxs-lookup"><span data-stu-id="68e26-108">Create a new global instance of the <xref:System.Diagnostics.Process> object.</span></span>  
  
4.  <span data-ttu-id="68e26-109">Scrivere un gestore eventi per il <xref:System.Windows.Forms.RichTextBox.LinkClicked> evento che invia al browser il testo desiderato.</span><span class="sxs-lookup"><span data-stu-id="68e26-109">Write an event handler for the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event that sends the browser the desired text.</span></span>  
  
     <span data-ttu-id="68e26-110">Nell'esempio seguente, il <xref:System.Windows.Forms.RichTextBox.LinkClicked> evento consente di aprire un'istanza di Internet Explorer per l'URL specificato nella <xref:System.Windows.Forms.RichTextBox.Text%2A> proprietà del <xref:System.Windows.Forms.RichTextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="68e26-110">In the example below, the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event opens an instance of Internet Explorer to the URL specified in the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="68e26-111">Questo esempio si presuppone un form con un <xref:System.Windows.Forms.RichTextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="68e26-111">This example assumes a form with a <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="68e26-112">Nella chiamata di <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> metodo, si verificherà un <xref:System.Security.SecurityException> eccezione se si esegue il codice in un contesto parzialmente attendibile a causa di privilegi sufficienti.</span><span class="sxs-lookup"><span data-stu-id="68e26-112">In calling the <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> method, you will encounter a <xref:System.Security.SecurityException> exception if you are running the code in a partial-trust context because of insufficient privileges.</span></span> <span data-ttu-id="68e26-113">Per altre informazioni, vedere [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).</span><span class="sxs-lookup"><span data-stu-id="68e26-113">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
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
  
     <span data-ttu-id="68e26-114">([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) È necessario inizializzare processo `p`, che è possibile effettuare includendo l'istruzione seguente nel costruttore del form:</span><span class="sxs-lookup"><span data-stu-id="68e26-114">([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) You must initialize process `p`, which you can do by including the following statement in the constructor of your form:</span></span>  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     <span data-ttu-id="68e26-115">(Visual c#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="68e26-115">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="68e26-116">È importante arrestare immediatamente il processo che è stato creato dopo aver completato le operazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="68e26-116">It is important to immediately stop the process you have created once you have finished working with it.</span></span> <span data-ttu-id="68e26-117">Riferimento al codice presentato in precedenza, il codice per arrestare il processo potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="68e26-117">Referring to the code presented above, your code to stop the process might look like this:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="68e26-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68e26-118">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>  
 <xref:System.Windows.Forms.RichTextBox.LinkClicked>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="68e26-119">Controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="68e26-119">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="68e26-120">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="68e26-120">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
