---
title: Collegamento a un oggetto o a una pagina Web con il controllo LinkLabel
description: Informazioni su come creare collegamenti di tipo Web a un oggetto o a una pagina Web con il controllo LinkLabel Windows Forms.
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
ms.openlocfilehash: a5fb1c03e9a8d82fe77f4133ba04c42114787d23
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618312"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a><span data-ttu-id="62433-103">Procedura: eseguire il collegamento a un oggetto o a una pagina Web con il controllo LinkLabel di Windows Form</span><span class="sxs-lookup"><span data-stu-id="62433-103">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>

<span data-ttu-id="62433-104">Il <xref:System.Windows.Forms.LinkLabel> controllo Windows Forms consente di creare collegamenti di tipo Web nel form.</span><span class="sxs-lookup"><span data-stu-id="62433-104">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to create Web-style links on your form.</span></span> <span data-ttu-id="62433-105">Quando si fa clic sul collegamento, è possibile modificarne il colore per indicare che è stato visitato il collegamento.</span><span class="sxs-lookup"><span data-stu-id="62433-105">When the link is clicked, you can change its color to indicate the link has been visited.</span></span> <span data-ttu-id="62433-106">Per ulteriori informazioni sulla modifica del colore, vedere [procedura: modificare l'aspetto del controllo LinkLabel Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span><span class="sxs-lookup"><span data-stu-id="62433-106">For more information on changing the color, see [How to: Change the Appearance of the Windows Forms LinkLabel Control](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span></span>

## <a name="linking-to-another-form"></a><span data-ttu-id="62433-107">Collegamento a un altro modulo</span><span class="sxs-lookup"><span data-stu-id="62433-107">Linking to Another Form</span></span>

#### <a name="to-link-to-another-form-with-a-linklabel-control"></a><span data-ttu-id="62433-108">Per creare un collegamento a un altro form con un controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="62433-108">To link to another form with a LinkLabel control</span></span>

1. <span data-ttu-id="62433-109">Impostare la <xref:System.Windows.Forms.LinkLabel.Text%2A> proprietà su una didascalia appropriata.</span><span class="sxs-lookup"><span data-stu-id="62433-109">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>

2. <span data-ttu-id="62433-110">Impostare la <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà per determinare la parte della didascalia che verrà indicata come collegamento.</span><span class="sxs-lookup"><span data-stu-id="62433-110">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span> <span data-ttu-id="62433-111">Il modo in cui viene indicato dipende dalle proprietà correlate all'aspetto dell'etichetta di collegamento.</span><span class="sxs-lookup"><span data-stu-id="62433-111">How it is indicated depends on the appearance-related properties of the link label.</span></span> <span data-ttu-id="62433-112">Il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> valore è rappresentato da un <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> oggetto contenente due numeri, la posizione iniziale del carattere e il numero di caratteri.</span><span class="sxs-lookup"><span data-stu-id="62433-112">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented by a <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> object containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="62433-113">La <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà può essere impostata nell'finestra proprietà o nel codice in un modo simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="62433-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property can be set in the Properties window or in code in a manner similar to the following:</span></span>

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

3. <span data-ttu-id="62433-114">Nel <xref:System.Windows.Forms.LinkLabel.LinkClicked> gestore dell'evento richiamare il <xref:System.Windows.Forms.Form.Show%2A> metodo per aprire un altro form nel progetto e impostare la <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> proprietà su `true` .</span><span class="sxs-lookup"><span data-stu-id="62433-114">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, invoke the <xref:System.Windows.Forms.Form.Show%2A> method to open another form in the project, and set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="62433-115">Un'istanza della <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> classe contiene un riferimento al <xref:System.Windows.Forms.LinkLabel> controllo su cui è stato fatto clic, pertanto non è necessario eseguire il cast dell' `sender` oggetto.</span><span class="sxs-lookup"><span data-stu-id="62433-115">An instance of the <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> class carries a reference to the <xref:System.Windows.Forms.LinkLabel> control that was clicked, so there is no need to cast the `sender` object.</span></span>

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

## <a name="linking-to-a-web-page"></a><span data-ttu-id="62433-116">Collegamento a una pagina Web</span><span class="sxs-lookup"><span data-stu-id="62433-116">Linking to a Web Page</span></span>

<span data-ttu-id="62433-117">Il <xref:System.Windows.Forms.LinkLabel> controllo può essere utilizzato anche per visualizzare una pagina Web con il browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="62433-117">The <xref:System.Windows.Forms.LinkLabel> control can also be used to display a Web page with the default browser.</span></span>

#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a><span data-ttu-id="62433-118">Per avviare Internet Explorer e collegarsi a una pagina Web con un controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="62433-118">To start Internet Explorer and link to a Web page with a LinkLabel control</span></span>

1. <span data-ttu-id="62433-119">Impostare la <xref:System.Windows.Forms.LinkLabel.Text%2A> proprietà su una didascalia appropriata.</span><span class="sxs-lookup"><span data-stu-id="62433-119">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>

2. <span data-ttu-id="62433-120">Impostare la <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà per determinare la parte della didascalia che verrà indicata come collegamento.</span><span class="sxs-lookup"><span data-stu-id="62433-120">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>

3. <span data-ttu-id="62433-121">Nel <xref:System.Windows.Forms.LinkLabel.LinkClicked> gestore eventi, nel mezzo di un blocco di gestione delle eccezioni, chiamare una seconda procedura che imposta la <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> proprietà su `true` e utilizza il <xref:System.Diagnostics.Process.Start%2A> metodo per avviare il browser predefinito con un URL.</span><span class="sxs-lookup"><span data-stu-id="62433-121">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, in the midst of an exception-handling block, call a second procedure that sets the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true` and uses the <xref:System.Diagnostics.Process.Start%2A> method to start the default browser with a URL.</span></span> <span data-ttu-id="62433-122">Per usare il <xref:System.Diagnostics.Process.Start%2A> metodo è necessario aggiungere un riferimento allo <xref:System.Diagnostics?displayProperty=nameWithType> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="62433-122">To use the <xref:System.Diagnostics.Process.Start%2A> method you need to add a reference to the <xref:System.Diagnostics?displayProperty=nameWithType> namespace.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="62433-123">Se il codice riportato di seguito viene eseguito in un ambiente con attendibilità parziale, ad esempio in un'unità condivisa, il compilatore JIT ha esito negativo quando `VisitLink` viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="62433-123">If the code below is run in a partial-trust environment (such as on a shared drive), the JIT compiler fails when the `VisitLink` method is called.</span></span> <span data-ttu-id="62433-124">L' `System.Diagnostics.Process.Start` istruzione causa una richiesta di collegamento che ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="62433-124">The `System.Diagnostics.Process.Start` statement causes a link demand that fails.</span></span> <span data-ttu-id="62433-125">Intercettando l'eccezione quando `VisitLink` viene chiamato il metodo, il codice seguente assicura che se il compilatore JIT non riesce, l'errore viene gestito normalmente.</span><span class="sxs-lookup"><span data-stu-id="62433-125">By catching the exception when the `VisitLink` method is called, the code below ensures that if the JIT compiler fails, the error is handled gracefully.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="62433-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62433-126">See also</span></span>

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- [<span data-ttu-id="62433-127">Panoramica del controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="62433-127">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="62433-128">Procedura: modificare l'aspetto del controllo LinkLabel di Windows Form</span><span class="sxs-lookup"><span data-stu-id="62433-128">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [<span data-ttu-id="62433-129">Controllo LinkLabel</span><span class="sxs-lookup"><span data-stu-id="62433-129">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
