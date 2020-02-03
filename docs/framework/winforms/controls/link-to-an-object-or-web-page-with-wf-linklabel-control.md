---
title: Collegamento a un oggetto o a una pagina Web con il controllo LinkLabel
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
ms.openlocfilehash: 1669a9d6aba39b02d228c735701ca4e31c8f8291
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745203"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a><span data-ttu-id="2a300-102">Procedura: eseguire il collegamento a un oggetto o a una pagina Web con il controllo LinkLabel di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2a300-102">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>

<span data-ttu-id="2a300-103">Il controllo Windows Forms <xref:System.Windows.Forms.LinkLabel> consente di creare collegamenti di tipo Web nel form.</span><span class="sxs-lookup"><span data-stu-id="2a300-103">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to create Web-style links on your form.</span></span> <span data-ttu-id="2a300-104">Quando si fa clic sul collegamento, è possibile modificarne il colore per indicare che è stato visitato il collegamento.</span><span class="sxs-lookup"><span data-stu-id="2a300-104">When the link is clicked, you can change its color to indicate the link has been visited.</span></span> <span data-ttu-id="2a300-105">Per ulteriori informazioni sulla modifica del colore, vedere [procedura: modificare l'aspetto del controllo LinkLabel Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span><span class="sxs-lookup"><span data-stu-id="2a300-105">For more information on changing the color, see [How to: Change the Appearance of the Windows Forms LinkLabel Control](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span></span>

## <a name="linking-to-another-form"></a><span data-ttu-id="2a300-106">Collegamento a un altro modulo</span><span class="sxs-lookup"><span data-stu-id="2a300-106">Linking to Another Form</span></span>

#### <a name="to-link-to-another-form-with-a-linklabel-control"></a><span data-ttu-id="2a300-107">Per creare un collegamento a un altro form con un controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="2a300-107">To link to another form with a LinkLabel control</span></span>

1. <span data-ttu-id="2a300-108">Impostare la proprietà <xref:System.Windows.Forms.LinkLabel.Text%2A> su una didascalia appropriata.</span><span class="sxs-lookup"><span data-stu-id="2a300-108">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>

2. <span data-ttu-id="2a300-109">Impostare la proprietà <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> per determinare quale parte della didascalia verrà indicata come collegamento.</span><span class="sxs-lookup"><span data-stu-id="2a300-109">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span> <span data-ttu-id="2a300-110">Il modo in cui viene indicato dipende dalle proprietà correlate all'aspetto dell'etichetta di collegamento.</span><span class="sxs-lookup"><span data-stu-id="2a300-110">How it is indicated depends on the appearance-related properties of the link label.</span></span> <span data-ttu-id="2a300-111">Il valore <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> è rappresentato da un oggetto <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> contenente due numeri, la posizione iniziale del carattere e il numero di caratteri.</span><span class="sxs-lookup"><span data-stu-id="2a300-111">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented by a <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> object containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="2a300-112">È possibile impostare la proprietà <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> nel Finestra Proprietà o nel codice in un modo simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="2a300-112">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property can be set in the Properties window or in code in a manner similar to the following:</span></span>

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

3. <span data-ttu-id="2a300-113">Nel gestore dell'evento <xref:System.Windows.Forms.LinkLabel.LinkClicked> richiamare il metodo <xref:System.Windows.Forms.Form.Show%2A> per aprire un altro form nel progetto e impostare la proprietà <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="2a300-113">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, invoke the <xref:System.Windows.Forms.Form.Show%2A> method to open another form in the project, and set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2a300-114">Un'istanza della classe <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> trasporta un riferimento al controllo <xref:System.Windows.Forms.LinkLabel> su cui è stato fatto clic, pertanto non è necessario eseguire il cast dell'oggetto `sender`.</span><span class="sxs-lookup"><span data-stu-id="2a300-114">An instance of the <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> class carries a reference to the <xref:System.Windows.Forms.LinkLabel> control that was clicked, so there is no need to cast the `sender` object.</span></span>

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

## <a name="linking-to-a-web-page"></a><span data-ttu-id="2a300-115">Collegamento a una pagina Web</span><span class="sxs-lookup"><span data-stu-id="2a300-115">Linking to a Web Page</span></span>

<span data-ttu-id="2a300-116">Il controllo <xref:System.Windows.Forms.LinkLabel> può essere utilizzato anche per visualizzare una pagina Web con il browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="2a300-116">The <xref:System.Windows.Forms.LinkLabel> control can also be used to display a Web page with the default browser.</span></span>

#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a><span data-ttu-id="2a300-117">Per avviare Internet Explorer e collegarsi a una pagina Web con un controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="2a300-117">To start Internet Explorer and link to a Web page with a LinkLabel control</span></span>

1. <span data-ttu-id="2a300-118">Impostare la proprietà <xref:System.Windows.Forms.LinkLabel.Text%2A> su una didascalia appropriata.</span><span class="sxs-lookup"><span data-stu-id="2a300-118">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>

2. <span data-ttu-id="2a300-119">Impostare la proprietà <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> per determinare quale parte della didascalia verrà indicata come collegamento.</span><span class="sxs-lookup"><span data-stu-id="2a300-119">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>

3. <span data-ttu-id="2a300-120">Nel gestore dell'evento <xref:System.Windows.Forms.LinkLabel.LinkClicked>, nel mezzo di un blocco di gestione delle eccezioni, chiamare una seconda procedura che imposta la proprietà <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> su `true` e usa il metodo <xref:System.Diagnostics.Process.Start%2A> per avviare il browser predefinito con un URL.</span><span class="sxs-lookup"><span data-stu-id="2a300-120">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, in the midst of an exception-handling block, call a second procedure that sets the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true` and uses the <xref:System.Diagnostics.Process.Start%2A> method to start the default browser with a URL.</span></span> <span data-ttu-id="2a300-121">Per usare il metodo <xref:System.Diagnostics.Process.Start%2A> è necessario aggiungere un riferimento allo spazio dei nomi <xref:System.Diagnostics?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2a300-121">To use the <xref:System.Diagnostics.Process.Start%2A> method you need to add a reference to the <xref:System.Diagnostics?displayProperty=nameWithType> namespace.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2a300-122">Se il codice riportato di seguito viene eseguito in un ambiente con attendibilità parziale, ad esempio in un'unità condivisa, il compilatore JIT ha esito negativo quando viene chiamato il metodo `VisitLink`.</span><span class="sxs-lookup"><span data-stu-id="2a300-122">If the code below is run in a partial-trust environment (such as on a shared drive), the JIT compiler fails when the `VisitLink` method is called.</span></span> <span data-ttu-id="2a300-123">L'istruzione `System.Diagnostics.Process.Start` causa un errore di richiesta di collegamento.</span><span class="sxs-lookup"><span data-stu-id="2a300-123">The `System.Diagnostics.Process.Start` statement causes a link demand that fails.</span></span> <span data-ttu-id="2a300-124">Intercettando l'eccezione quando viene chiamato il metodo `VisitLink`, il codice seguente assicura che se il compilatore JIT non riesce, l'errore viene gestito normalmente.</span><span class="sxs-lookup"><span data-stu-id="2a300-124">By catching the exception when the `VisitLink` method is called, the code below ensures that if the JIT compiler fails, the error is handled gracefully.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2a300-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a300-125">See also</span></span>

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2a300-126">Panoramica sul controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="2a300-126">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="2a300-127">Procedura: Modificare l'aspetto del controllo LinkLabel di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2a300-127">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [<span data-ttu-id="2a300-128">Controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="2a300-128">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
