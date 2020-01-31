---
title: Aggiungere controlli
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 560089a23fbcccb0f0d5683a95ad06dd9c59556d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743964"
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="36262-102">Procedura: Aggiungere controlli a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="36262-102">How to: Add Controls to Windows Forms</span></span>

<span data-ttu-id="36262-103">La maggior parte dei moduli è progettata mediante l'aggiunta di controlli all'area del form per definire un'interfaccia utente (UI).</span><span class="sxs-lookup"><span data-stu-id="36262-103">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="36262-104">Un *controllo* è un componente di un form usato per visualizzare informazioni o accettare l'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="36262-104">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="36262-105">Per ulteriori informazioni sui controlli, vedere [controlli Windows Forms](index.md).</span><span class="sxs-lookup"><span data-stu-id="36262-105">For more information about controls, see [Windows Forms Controls](index.md).</span></span>

## <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="36262-106">Per creare un controllo in un form</span><span class="sxs-lookup"><span data-stu-id="36262-106">To draw a control on a form</span></span>

1. <span data-ttu-id="36262-107">Aprire il modulo.</span><span class="sxs-lookup"><span data-stu-id="36262-107">Open the form.</span></span> <span data-ttu-id="36262-108">Per altre informazioni, vedere [procedura: visualizzare Windows Forms nella finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="36262-108">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="36262-109">Nella **casella degli strumenti**fare clic sul controllo che si desidera aggiungere al form.</span><span class="sxs-lookup"><span data-stu-id="36262-109">In the **Toolbox**, click the control you want to add to your form.</span></span>

3. <span data-ttu-id="36262-110">Nel modulo, fare clic su dove si desidera posizionare l'angolo superiore sinistro del controllo e trascinare verso il punto in cui si desidera posizionare l'angolo inferiore destro del controllo.</span><span class="sxs-lookup"><span data-stu-id="36262-110">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>

    <span data-ttu-id="36262-111">Il controllo viene aggiunto al form con la posizione e le dimensioni specificate.</span><span class="sxs-lookup"><span data-stu-id="36262-111">The control is added to the form with the specified location and size.</span></span>

    > [!NOTE]
    > <span data-ttu-id="36262-112">Ogni controllo ha una dimensione predefinita definita.</span><span class="sxs-lookup"><span data-stu-id="36262-112">Each control has a default size defined.</span></span> <span data-ttu-id="36262-113">È possibile aggiungere un controllo al form nelle dimensioni predefinite del controllo trascinandoli dalla **casella degli strumenti** nel form.</span><span class="sxs-lookup"><span data-stu-id="36262-113">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>

## <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="36262-114">Per trascinare un controllo in un form</span><span class="sxs-lookup"><span data-stu-id="36262-114">To drag a control to a form</span></span>

1. <span data-ttu-id="36262-115">Aprire il modulo.</span><span class="sxs-lookup"><span data-stu-id="36262-115">Open the form.</span></span> <span data-ttu-id="36262-116">Per altre informazioni, vedere [procedura: visualizzare Windows Forms nella finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="36262-116">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="36262-117">Nella **casella degli strumenti**fare clic sul controllo desiderato e trascinarlo nel form.</span><span class="sxs-lookup"><span data-stu-id="36262-117">In the **Toolbox**, click the control you want and drag it to your form.</span></span>

    <span data-ttu-id="36262-118">Il controllo viene aggiunto al form in corrispondenza della posizione specificata nelle dimensioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="36262-118">The control is added to the form at the specified location in its default size.</span></span>

    > [!NOTE]
    > <span data-ttu-id="36262-119">È possibile fare doppio clic su un controllo nella **casella degli strumenti** per aggiungerlo all'angolo superiore sinistro del form in base alle dimensioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="36262-119">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>

    <span data-ttu-id="36262-120">È anche possibile aggiungere controlli in modo dinamico a un modulo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="36262-120">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="36262-121">Nell'esempio di codice seguente, un controllo <xref:System.Windows.Forms.TextBox> verrà aggiunto al form quando si fa clic su un controllo <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="36262-121">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>

    > [!NOTE]
    > <span data-ttu-id="36262-122">La procedura seguente richiede l'esistenza di un form con un controllo **Button** , `Button1`, già inserito.</span><span class="sxs-lookup"><span data-stu-id="36262-122">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>

## <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="36262-123">Per aggiungere un controllo a un modulo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="36262-123">To add a control to a form programmatically</span></span>

1. <span data-ttu-id="36262-124">Nel metodo che gestisce l'evento `Click` del pulsante all'interno della classe del form, inserire codice simile al seguente per aggiungere un riferimento alla variabile di controllo, impostare la `Location`del controllo e aggiungere il controllo.</span><span class="sxs-lookup"><span data-stu-id="36262-124">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>

    ```vb
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
       Dim MyText As New TextBox()
       MyText.Location = New Point(25, 25)
       Me.Controls.Add(MyText)
    End Sub
    ```

    ```csharp
    private void button1_Click(object sender, System.EventArgs e)
    {
       TextBox myText = new TextBox();
       myText.Location = new Point(25,25);
       this.Controls.Add (myText);
    }
    ```

    ```cpp
    private:
      System::Void button1_Click(System::Object ^  sender,
        System::EventArgs ^  e)
      {
        TextBox ^ myText = gcnew TextBox();
        myText->Location = Point(25,25);
        this->Controls->Add(myText);
      }
    ```

    > [!NOTE]
    > <span data-ttu-id="36262-125">È anche possibile aggiungere codice per inizializzare altre proprietà del controllo.</span><span class="sxs-lookup"><span data-stu-id="36262-125">You can also add code to initialize other properties of the control.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="36262-126">È possibile esporre il computer locale a un rischio di sicurezza attraverso la rete facendo riferimento a una `UserControl`dannosa.</span><span class="sxs-lookup"><span data-stu-id="36262-126">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="36262-127">Questo potrebbe costituire un problema solo nel caso di un utente malintenzionato che crea un controllo personalizzato dannoso, seguito da un'operazione erroneamente aggiunta al progetto.</span><span class="sxs-lookup"><span data-stu-id="36262-127">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="36262-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36262-128">See also</span></span>

- [<span data-ttu-id="36262-129">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="36262-129">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="36262-130">Procedura: Ridimensionare i controlli di un Windows Form</span><span class="sxs-lookup"><span data-stu-id="36262-130">How to: Resize Controls on Windows Forms</span></span>](how-to-resize-controls-on-windows-forms.md)
- [<span data-ttu-id="36262-131">Procedura: Impostare il testo visualizzato da un controllo Windows Form</span><span class="sxs-lookup"><span data-stu-id="36262-131">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="36262-132">Controlli da utilizzare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="36262-132">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
