---
title: 'Procedura: Aggiungere controlli a Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 04597283a8ff2e21a0f227268671d3605eac6356
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343588"
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="14c6f-102">Procedura: Aggiungere controlli a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="14c6f-102">How to: Add Controls to Windows Forms</span></span>
<span data-ttu-id="14c6f-103">La maggior parte dei moduli sono progettati con l'aggiunta di controlli alla superficie del form per definire l'interfaccia utente (UI).</span><span class="sxs-lookup"><span data-stu-id="14c6f-103">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="14c6f-104">Oggetto *controllo* è un componente in un formato utilizzato per visualizzare informazioni o accettare l'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="14c6f-104">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="14c6f-105">Per altre informazioni sui controlli, vedere [Windows Forms Controls](index.md).</span><span class="sxs-lookup"><span data-stu-id="14c6f-105">For more information about controls, see [Windows Forms Controls](index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14c6f-106">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="14c6f-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="14c6f-107">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="14c6f-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="14c6f-108">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="14c6f-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="14c6f-109">Per disegnare un controllo in un form</span><span class="sxs-lookup"><span data-stu-id="14c6f-109">To draw a control on a form</span></span>  
  
1. <span data-ttu-id="14c6f-110">Aprire il form.</span><span class="sxs-lookup"><span data-stu-id="14c6f-110">Open the form.</span></span> <span data-ttu-id="14c6f-111">Per altre informazioni, vedere [Procedura: Visualizzare Windows Form nella finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="14c6f-111">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="14c6f-112">Nel **casella degli strumenti**, fare clic sul controllo da aggiungere al form.</span><span class="sxs-lookup"><span data-stu-id="14c6f-112">In the **Toolbox**, click the control you want to add to your form.</span></span>  
  
3. <span data-ttu-id="14c6f-113">Nel form, fare clic su cui l'angolo superiore sinistro del controllo da trovare e trascinare in cui si desidera l'angolo inferiore destro del controllo da individuare.</span><span class="sxs-lookup"><span data-stu-id="14c6f-113">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>  
  
     <span data-ttu-id="14c6f-114">Il controllo viene aggiunto al form con il percorso specificato e le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="14c6f-114">The control is added to the form with the specified location and size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="14c6f-115">Ogni controllo ha una dimensione predefinita definita.</span><span class="sxs-lookup"><span data-stu-id="14c6f-115">Each control has a default size defined.</span></span> <span data-ttu-id="14c6f-116">È possibile aggiungere un controllo al form nella dimensione predefinita del controllo trascinandolo dal **casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="14c6f-116">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>  
  
### <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="14c6f-117">Trascinare un controllo a un form</span><span class="sxs-lookup"><span data-stu-id="14c6f-117">To drag a control to a form</span></span>  
  
1. <span data-ttu-id="14c6f-118">Aprire il form.</span><span class="sxs-lookup"><span data-stu-id="14c6f-118">Open the form.</span></span> <span data-ttu-id="14c6f-119">Per altre informazioni, vedere [Procedura: Visualizzare Windows Form nella finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="14c6f-119">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="14c6f-120">Nel **casella degli strumenti**, scegliere il controllo desiderato e trascinarlo nel form.</span><span class="sxs-lookup"><span data-stu-id="14c6f-120">In the **Toolbox**, click the control you want and drag it to your form.</span></span>  
  
     <span data-ttu-id="14c6f-121">Il controllo viene aggiunto al form nella posizione specificata nella dimensione predefinita.</span><span class="sxs-lookup"><span data-stu-id="14c6f-121">The control is added to the form at the specified location in its default size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="14c6f-122">È possibile fare doppio clic su un controllo nel **casella degli strumenti** per aggiungerlo all'angolo superiore sinistro del form nella dimensione predefinita.</span><span class="sxs-lookup"><span data-stu-id="14c6f-122">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>  
  
     <span data-ttu-id="14c6f-123">È anche possibile aggiungere dinamicamente controlli a un form in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="14c6f-123">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="14c6f-124">Nell'esempio di codice seguente, un <xref:System.Windows.Forms.TextBox> controllo verrà aggiunto al modulo quando un <xref:System.Windows.Forms.Button> si fa clic sul controllo.</span><span class="sxs-lookup"><span data-stu-id="14c6f-124">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="14c6f-125">La procedura seguente presuppone l'esistenza di un form con un **sul pulsante** controllo `Button1`, già posizionato su di esso.</span><span class="sxs-lookup"><span data-stu-id="14c6f-125">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="14c6f-126">Per aggiungere un controllo a un form a livello di codice</span><span class="sxs-lookup"><span data-stu-id="14c6f-126">To add a control to a form programmatically</span></span>  
  
1. <span data-ttu-id="14c6f-127">Nel metodo che gestisce il pulsante `Click` evento all'interno di classe del modulo, inserire il codice simile al seguente per aggiungere un riferimento alla variabile di controllo, imposta il controllo `Location`e aggiungere il controllo.</span><span class="sxs-lookup"><span data-stu-id="14c6f-127">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>  
  
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
    >  <span data-ttu-id="14c6f-128">È anche possibile aggiungere codice per inizializzare le altre proprietà del controllo.</span><span class="sxs-lookup"><span data-stu-id="14c6f-128">You can also add code to initialize other properties of the control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="14c6f-129">Si potrebbe esporre il computer locale a un rischio per la sicurezza attraverso la rete facendo riferimento a un malintenzionato `UserControl`.</span><span class="sxs-lookup"><span data-stu-id="14c6f-129">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="14c6f-130">Questa è solo un problema nel caso di un utente con un controllo personalizzato, seguito dall'utente erroneamente aggiungendolo al progetto.</span><span class="sxs-lookup"><span data-stu-id="14c6f-130">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14c6f-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14c6f-131">See also</span></span>

- [<span data-ttu-id="14c6f-132">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="14c6f-132">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="14c6f-133">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="14c6f-133">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="14c6f-134">Procedura: Ridimensionare i controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="14c6f-134">How to: Resize Controls on Windows Forms</span></span>](how-to-resize-controls-on-windows-forms.md)
- [<span data-ttu-id="14c6f-135">Procedura: Impostare il testo visualizzato dal controllo di un Windows Form</span><span class="sxs-lookup"><span data-stu-id="14c6f-135">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="14c6f-136">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="14c6f-136">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
