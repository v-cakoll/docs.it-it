---
title: 'Procedura: Collegarsi a un oggetto o Web Page con il controllo LinkLabel di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Windows Forms, linking to objects
- Web page link control
- linking [Windows Forms], to other forms
- Windows Forms, linking to Web pages
- links [Windows Forms], to other forms
- LinkLabel control [Windows Forms], linking to object or Web page
- LinkLabel control [Windows Forms], examples
ms.assetid: 6c91c975-3cb7-4504-82f0-fc6255f8fb85
ms.openlocfilehash: 34d6807b874596bd46f11ff90052ab85cc93b5d5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705189"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a><span data-ttu-id="77c9b-102">Procedura: Collegarsi a un oggetto o Web Page con il controllo LinkLabel di Windows Form</span><span class="sxs-lookup"><span data-stu-id="77c9b-102">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="77c9b-103">I moduli di Windows <xref:System.Windows.Forms.LinkLabel> controllo consente di creare collegamenti ipertestuali nel form.</span><span class="sxs-lookup"><span data-stu-id="77c9b-103">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to create Web-style links on your form.</span></span> <span data-ttu-id="77c9b-104">Quando si fa clic sul collegamento, è possibile modificare il colore per indicare che il collegamento è stato visitato.</span><span class="sxs-lookup"><span data-stu-id="77c9b-104">When the link is clicked, you can change its color to indicate the link has been visited.</span></span> <span data-ttu-id="77c9b-105">Per altre informazioni su come modificare il colore, vedere [come: Modificare l'aspetto del controllo Windows Form LinkLabel](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span><span class="sxs-lookup"><span data-stu-id="77c9b-105">For more information on changing the color, see [How to: Change the Appearance of the Windows Forms LinkLabel Control](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span></span>  
  
## <a name="linking-to-another-form"></a><span data-ttu-id="77c9b-106">Collegamento a un altro formato</span><span class="sxs-lookup"><span data-stu-id="77c9b-106">Linking to Another Form</span></span>  
  
#### <a name="to-link-to-another-form-with-a-linklabel-control"></a><span data-ttu-id="77c9b-107">Il collegamento a un altro form con un controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="77c9b-107">To link to another form with a LinkLabel control</span></span>  
  
1.  <span data-ttu-id="77c9b-108">Impostare il <xref:System.Windows.Forms.LinkLabel.Text%2A> proprietà su un titolo appropriato.</span><span class="sxs-lookup"><span data-stu-id="77c9b-108">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
2.  <span data-ttu-id="77c9b-109">Impostare il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà per determinare quale parte della didascalia verrà indicato come collegamento.</span><span class="sxs-lookup"><span data-stu-id="77c9b-109">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span> <span data-ttu-id="77c9b-110">Come è indicato dipende dalle proprietà correlate all'aspetto dell'etichetta del collegamento.</span><span class="sxs-lookup"><span data-stu-id="77c9b-110">How it is indicated depends on the appearance-related properties of the link label.</span></span> <span data-ttu-id="77c9b-111">Il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> valore è rappresentato da un <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> contenente due numeri, la posizione del carattere iniziale e il numero di caratteri.</span><span class="sxs-lookup"><span data-stu-id="77c9b-111">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented by a <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> object containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="77c9b-112">Il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà può essere impostata nella finestra proprietà o nel codice in modo analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="77c9b-112">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property can be set in the Properties window or in code in a manner similar to the following:</span></span>  
  
    ```vb  
    ' In this code example, the link area has been set to begin  
    ' at the first character and extend for eight characters.  
    ' You may need to modify this based on the text entered in Step 1.  
    LinkLabel1.LinkArea = New LinkArea(0, 8)  
    ```  
  
    ```csharp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1.LinkArea = new LinkArea(0,8);  
    ```  
  
    ```cpp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1->LinkArea = LinkArea(0,8);  
    ```  
  
3.  <span data-ttu-id="77c9b-113">Nel <xref:System.Windows.Forms.LinkLabel.LinkClicked> gestore dell'evento, richiamare il <xref:System.Windows.Forms.Form.Show%2A> metodo per aprire un'altra forma nel progetto e impostare il <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="77c9b-113">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, invoke the <xref:System.Windows.Forms.Form.Show%2A> method to open another form in the project, and set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="77c9b-114">Un'istanza del <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> classe contiene un riferimento al <xref:System.Windows.Forms.LinkLabel> controllo che è stato selezionato, in modo che non è necessario eseguire il cast di `sender` oggetto.</span><span class="sxs-lookup"><span data-stu-id="77c9b-114">An instance of the <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> class carries a reference to the <xref:System.Windows.Forms.LinkLabel> control that was clicked, so there is no need to cast the `sender` object.</span></span>  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked(ByVal Sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       ' Show another form.  
       Dim f2 As New Form()  
       f2.Show  
       LinkLabel1.LinkVisited = True  
    End Sub  
    ```  
  
    ```csharp  
    protected void linkLabel1_LinkClicked(object sender, System. Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       // Show another form.  
       Form f2 = new Form();  
       f2.Show();  
       linkLabel1.LinkVisited = true;  
    }  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Show another form.  
          Form ^ f2 = new Form();  
          f2->Show();  
          linkLabel1->LinkVisited = true;  
       }  
    ```  
  
## <a name="linking-to-a-web-page"></a><span data-ttu-id="77c9b-115">Collegamento a una pagina Web</span><span class="sxs-lookup"><span data-stu-id="77c9b-115">Linking to a Web Page</span></span>  
 <span data-ttu-id="77c9b-116">Il <xref:System.Windows.Forms.LinkLabel> controllo può essere usato anche per visualizzare una pagina Web con il browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="77c9b-116">The <xref:System.Windows.Forms.LinkLabel> control can also be used to display a Web page with the default browser.</span></span>  
  
#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a><span data-ttu-id="77c9b-117">Per avviare Internet Explorer e collegamento a una pagina Web con un controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="77c9b-117">To start Internet Explorer and link to a Web page with a LinkLabel control</span></span>  
  
1.  <span data-ttu-id="77c9b-118">Impostare il <xref:System.Windows.Forms.LinkLabel.Text%2A> proprietà su un titolo appropriato.</span><span class="sxs-lookup"><span data-stu-id="77c9b-118">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
2.  <span data-ttu-id="77c9b-119">Impostare il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà per determinare quale parte della didascalia verrà indicato come collegamento.</span><span class="sxs-lookup"><span data-stu-id="77c9b-119">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
3.  <span data-ttu-id="77c9b-120">Nel <xref:System.Windows.Forms.LinkLabel.LinkClicked> gestore dell'evento, in corrispondenza di un blocco di gestione delle eccezioni, chiamare una seconda stored procedure che consente di impostare il <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> proprietà `true` e Usa il <xref:System.Diagnostics.Process.Start%2A> metodo per avviare il browser predefinito con un URL.</span><span class="sxs-lookup"><span data-stu-id="77c9b-120">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, in the midst of an exception-handling block, call a second procedure that sets the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true` and uses the <xref:System.Diagnostics.Process.Start%2A> method to start the default browser with a URL.</span></span> <span data-ttu-id="77c9b-121">Usare la <xref:System.Diagnostics.Process.Start%2A> è necessario aggiungere un riferimento al metodo il <xref:System.Diagnostics?displayProperty=nameWithType> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="77c9b-121">To use the <xref:System.Diagnostics.Process.Start%2A> method you need to add a reference to the <xref:System.Diagnostics?displayProperty=nameWithType> namespace.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="77c9b-122">Se il codice seguente viene eseguito in un ambiente parzialmente attendibile (ad esempio in un'unità condivisa), il compilatore JIT non riesce quando il `VisitLink` viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="77c9b-122">If the code below is run in a partial-trust environment (such as on a shared drive), the JIT compiler fails when the `VisitLink` method is called.</span></span> <span data-ttu-id="77c9b-123">Il `System.Diagnostics.Process.Start` istruzione provoca una richiesta di collegamento che ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="77c9b-123">The `System.Diagnostics.Process.Start` statement causes a link demand that fails.</span></span> <span data-ttu-id="77c9b-124">Per intercettare l'eccezione generata quando il `VisitLink` viene chiamato il metodo, il codice seguente garantisce che se il compilatore JIT non riesce, l'errore viene gestito normalmente.</span><span class="sxs-lookup"><span data-stu-id="77c9b-124">By catching the exception when the `VisitLink` method is called, the code below ensures that if the JIT compiler fails, the error is handled gracefully.</span></span>  
  
    ```vb  
    Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       Try  
          VisitLink()  
       Catch ex As Exception  
          ' The error message  
          MessageBox.Show("Unable to open link that was clicked.")  
       End Try  
    End Sub  
  
    Sub VisitLink()  
       ' Change the color of the link text by setting LinkVisited   
       ' to True.  
       LinkLabel1.LinkVisited = True  
       ' Call the Process.Start method to open the default browser   
       ' with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com")  
    End Sub  
    ```  
  
    ```csharp  
    private void linkLabel1_LinkClicked(object sender, System.Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       try  
       {  
          VisitLink();  
       }  
       catch (Exception ex )  
       {  
          MessageBox.Show("Unable to open link that was clicked.");  
       }  
    }  
  
    private void VisitLink()  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to true.  
       linkLabel1.LinkVisited = true;  
       //Call the Process.Start method to open the default browser   
       //with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com");  
    }  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          try  
          {  
             VisitLink();  
          }  
          catch (Exception ^ ex)  
          {  
             MessageBox::Show("Unable to open link that was clicked.");  
          }  
       }  
    private:  
       void VisitLink()  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to true.  
          linkLabel1->LinkVisited = true;  
          // Call the Process.Start method to open the default browser   
          // with a URL:  
          System::Diagnostics::Process::Start("http://www.microsoft.com");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="77c9b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77c9b-125">See also</span></span>
- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- [<span data-ttu-id="77c9b-126">Panoramica sul controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="77c9b-126">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="77c9b-127">Procedura: Modificare l'aspetto del controllo Windows Form LinkLabel</span><span class="sxs-lookup"><span data-stu-id="77c9b-127">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [<span data-ttu-id="77c9b-128">Controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="77c9b-128">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
