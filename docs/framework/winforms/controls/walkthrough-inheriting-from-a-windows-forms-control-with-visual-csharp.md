---
title: Ereditare da un controllo
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 713ccf97a73ce9684b9124a121369f22751861d0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740132"
---
# <a name="walkthrough-inherit-from-a-windows-forms-control-with-c"></a><span data-ttu-id="2b4a4-102">Procedura dettagliata: ereditare da un controllo Windows Forms con C\#</span><span class="sxs-lookup"><span data-stu-id="2b4a4-102">Walkthrough: Inherit from a Windows Forms Control with C\#</span></span>

<span data-ttu-id="2b4a4-103">Con C#, è possibile creare controlli personalizzati avanzati tramite l' *ereditarietà*.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-103">With C#, you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="2b4a4-104">L'ereditarietà consente di creare nuovi controlli che non solo conservano tutte le funzionalità proprie dei controlli Windows Forms standard, ma includono anche funzionalità personalizzate.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="2b4a4-105">In questa procedura verrà creato un controllo ereditato semplice denominato `ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="2b4a4-106">Questo pulsante eredita le funzionalità dal controllo Windows Forms <xref:System.Windows.Forms.Button> standard ed espone una proprietà personalizzata denominata `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="2b4a4-107">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="2b4a4-107">Create the Project</span></span>

<span data-ttu-id="2b4a4-108">Quando si crea un nuovo progetto è necessario specificarne il nome per impostare lo spazio dei nomi radice, il nome dell'assembly e il nome del progetto e assicurarsi che il componente predefinito sia inserito nello spazio dei nomi corretto.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-108">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="2b4a4-109">Per creare la libreria di controlli ValueButtonLib e il controllo ValueButton</span><span class="sxs-lookup"><span data-stu-id="2b4a4-109">To create the ValueButtonLib control library and the ValueButton control</span></span>

1. <span data-ttu-id="2b4a4-110">In Visual Studio creare un nuovo progetto di **libreria di controllo Windows Forms** e denominarlo **ValueButtonLib**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-110">In Visual Studio, create a new **Windows Forms Control Library** project, and name it **ValueButtonLib**.</span></span>

     <span data-ttu-id="2b4a4-111">Per impostazione predefinita il nome del progetto, `ValueButtonLib`, verrà assegnato anche allo spazio dei nomi radice.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-111">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="2b4a4-112">Lo spazio dei nomi radice viene utilizzato per qualificare i nomi dei componenti dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-112">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="2b4a4-113">Se ad esempio due assembly forniscono componenti denominati `ValueButton`, sarà possibile specificare il componente `ValueButton` utilizzando `ValueButtonLib.ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-113">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="2b4a4-114">Per altre informazioni, vedere [Spazi dei nomi](../../../csharp/programming-guide/namespaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="2b4a4-114">For more information, see [Namespaces](../../../csharp/programming-guide/namespaces/index.md).</span></span>

2. <span data-ttu-id="2b4a4-115">In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **UserControl1.cs** e scegliere **Rinomina** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-115">In **Solution Explorer**, right-click **UserControl1.cs**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="2b4a4-116">Modificare il nome del file in **ValueButton.cs**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-116">Change the file name to **ValueButton.cs**.</span></span> <span data-ttu-id="2b4a4-117">Scegliere il pulsante **Sì** quando richiesto per rinominare tutti i riferimenti all'elemento di codice '`UserControl1`'.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-117">Click the **Yes** button when you are asked if you want to rename all references to the code element '`UserControl1`'.</span></span>

3. <span data-ttu-id="2b4a4-118">In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **ValueButton.cs** e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-118">In **Solution Explorer**, right-click **ValueButton.cs** and select **View Code**.</span></span>

4. <span data-ttu-id="2b4a4-119">Individuare la riga dell'istruzione `class`, `public partial class ValueButton`e modificare il tipo da cui il controllo eredita da <xref:System.Windows.Forms.UserControl> a <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-119">Locate the `class` statement line, `public partial class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="2b4a4-120">Ciò consente al controllo ereditato di ereditare tutte le funzionalità del controllo <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-120">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>

5. <span data-ttu-id="2b4a4-121">In **Esplora soluzioni** aprire il nodo **ValueButton.cs** per visualizzare il file del codice generato nella finestra di progettazione **ValueButton.Designer.cs**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-121">In **Solution Explorer**, open the **ValueButton.cs** node to display the designer-generated code file, **ValueButton.Designer.cs**.</span></span> <span data-ttu-id="2b4a4-122">Aprire il file nell'**editor di codice**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-122">Open this file in the **Code Editor**.</span></span>

6. <span data-ttu-id="2b4a4-123">Individuare il metodo `InitializeComponent` e rimuovere la riga che assegna la proprietà <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-123">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="2b4a4-124">Questa proprietà non esiste nel controllo <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-124">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>

7. <span data-ttu-id="2b4a4-125">Per salvare il progetto, scegliere **Salva tutto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-125">From the **File** menu, choose **Save All** to save the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b4a4-126">Non è più disponibile alcuna finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-126">A visual designer is no longer available.</span></span> <span data-ttu-id="2b4a4-127">Poiché il controllo <xref:System.Windows.Forms.Button> esegue un disegno personalizzato, non è possibile modificarne l'aspetto nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-127">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="2b4a4-128">La relativa rappresentazione visiva sarà esattamente identica a quella della classe da cui eredita (ovvero <xref:System.Windows.Forms.Button>), a meno che non venga modificata nel codice.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-128">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span> <span data-ttu-id="2b4a4-129">È comunque possibile aggiungere nell'area di progettazione i componenti che non dispongono di elementi dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-129">You can still add components, which have no UI elements, to the design surface.</span></span>

## <a name="add-a-property-to-your-inherited-control"></a><span data-ttu-id="2b4a4-130">Aggiungere una proprietà al controllo ereditato</span><span class="sxs-lookup"><span data-stu-id="2b4a4-130">Add a Property to Your Inherited Control</span></span>

<span data-ttu-id="2b4a4-131">Un possibile utilizzo dei controlli Windows Forms ereditati è la creazione di controlli aventi aspetto e funzionalità identici ai controlli standard Windows Forms, ma che espongono proprietà personalizzate.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-131">One possible use of inherited Windows Forms controls is the creation of controls that are identical in look and feel of standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="2b4a4-132">In questa sezione verrà illustrata la modalità di aggiunta della proprietà `ButtonValue` al controllo.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-132">In this section, you will add a property called `ButtonValue` to your control.</span></span>

### <a name="to-add-the-value-property"></a><span data-ttu-id="2b4a4-133">Per aggiungere la proprietà Value</span><span class="sxs-lookup"><span data-stu-id="2b4a4-133">To add the Value property</span></span>

1. <span data-ttu-id="2b4a4-134">In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **ValueButton.cs**, quindi scegliere **Visualizza codice** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-134">In **Solution Explorer**, right-click **ValueButton.cs**, and then click **View Code** from the shortcut menu.</span></span>

2. <span data-ttu-id="2b4a4-135">Individuare l'istruzione `class`.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-135">Locate the `class` statement.</span></span> <span data-ttu-id="2b4a4-136">Sotto `{` digitare il seguente codice:</span><span class="sxs-lookup"><span data-stu-id="2b4a4-136">Immediately after the `{`, type the following code:</span></span>

    ```csharp
    // Creates the private variable that will store the value of your
    // property.
    private int varValue;
    // Declares the property.
    public int ButtonValue
    {
       // Sets the method for retrieving the value of your property.
       get
       {
          return varValue;
       }
       // Sets the method for setting the value of your property.
       set
       {
          varValue = value;
       }
    }
    ```

     <span data-ttu-id="2b4a4-137">Questo codice consente di impostare i metodi per la memorizzazione e il recupero della proprietà `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-137">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="2b4a4-138">L'istruzione `get` consente di impostare il valore restituito sul valore memorizzato nella variabile privata `varValue`, mentre l'istruzione `set` consente di impostare il valore della variabile privata mediante la parola chiave `value`.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-138">The `get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `set` statement sets the value of the private variable by use of the `value` keyword.</span></span>

3. <span data-ttu-id="2b4a4-139">Per salvare il progetto, scegliere **Salva tutto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-139">From the **File** menu, choose **Save All** to save the project.</span></span>

## <a name="test-the-control"></a><span data-ttu-id="2b4a4-140">Testare il controllo</span><span class="sxs-lookup"><span data-stu-id="2b4a4-140">Test the control</span></span>

<span data-ttu-id="2b4a4-141">I controlli non sono progetti autonomi e devono pertanto essere inseriti in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-141">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="2b4a4-142">Per testare il controllo, è necessario creare un progetto di test in cui eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-142">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="2b4a4-143">È inoltre necessario rendere il controllo accessibile al progetto di test compilandolo.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-143">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="2b4a4-144">In questa sezione verrà illustrato come compilare un controllo ed eseguirne il test in un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-144">In this section, you will build your control and test it in a Windows Form.</span></span>

### <a name="to-build-your-control"></a><span data-ttu-id="2b4a4-145">Per compilare il controllo</span><span class="sxs-lookup"><span data-stu-id="2b4a4-145">To build your control</span></span>

<span data-ttu-id="2b4a4-146">Scegliere **Compila soluzione** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-146">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="2b4a4-147">La compilazione dovrebbe essere completata senza errori del compilatore o avvisi.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-147">The build should be successful with no compiler errors or warnings.</span></span>

### <a name="to-create-a-test-project"></a><span data-ttu-id="2b4a4-148">Per creare un progetto di test</span><span class="sxs-lookup"><span data-stu-id="2b4a4-148">To create a test project</span></span>

1. <span data-ttu-id="2b4a4-149">Scegliere **Aggiungi** dal menu **File**, quindi fare clic su **Nuovo progetto**. Verrà visualizzata la finestra di dialogo **Aggiungi nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-149">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="2b4a4-150">Selezionare il nodo **Windows** sotto il nodo **Visual C#** e fare clic su **Windows Forms Application**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-150">Select the **Windows** node, beneath the **Visual C#** node, and click **Windows Forms Application**.</span></span>

3. <span data-ttu-id="2b4a4-151">Nella casella **nome** immettere **test**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-151">In the **Name** box, enter **Test**.</span></span>

4. <span data-ttu-id="2b4a4-152">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Riferimenti** del progetto di test, quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida per visualizzare la finestra di dialogo **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-152">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>

5. <span data-ttu-id="2b4a4-153">Scegliere la scheda **Progetti**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-153">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="2b4a4-154">Il progetto ValueButtonLib verrà elencato in **nome progetto**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-154">Your ValueButtonLib project will be listed under **Project Name**.</span></span> <span data-ttu-id="2b4a4-155">Fare doppio clic sul progetto per cui si desidera aggiungere il riferimento al progetto di test.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-155">Double-click the project to add the reference to the test project.</span></span>

6. <span data-ttu-id="2b4a4-156">In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **Test** e scegliere **Compila**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-156">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>

### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="2b4a4-157">Per aggiungere il controllo al modulo</span><span class="sxs-lookup"><span data-stu-id="2b4a4-157">To add your control to the form</span></span>

1. <span data-ttu-id="2b4a4-158">In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **Form1.cs**, quindi scegliere **Visualizza finestra di progettazione** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-158">In **Solution Explorer**, right-click **Form1.cs** and choose **View Designer** from the shortcut menu.</span></span>

2. <span data-ttu-id="2b4a4-159">Nella **casella degli strumenti**selezionare **Componenti ValueButtonLib**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-159">In the **Toolbox**, select **ValueButtonLib Components**.</span></span> <span data-ttu-id="2b4a4-160">Fare doppio clic su **ValueButton**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-160">Double-click **ValueButton**.</span></span>

     <span data-ttu-id="2b4a4-161">Nel modulo verrà visualizzato un controllo **ValueButton**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-161">A **ValueButton** appears on the form.</span></span>

3. <span data-ttu-id="2b4a4-162">Fare clic con il pulsante destro del mouse su **ValueButton**, quindi scegliere **Proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-162">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>

4. <span data-ttu-id="2b4a4-163">Nella finestra **Proprietà** esaminare le proprietà del controllo.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-163">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="2b4a4-164">Si noti che le proprietà sono identiche a quelle esposte da un pulsante standard, ad eccezione del fatto che è presente una proprietà aggiuntiva, ButtonValue.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-164">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, ButtonValue.</span></span>

5. <span data-ttu-id="2b4a4-165">Impostare la proprietà **ButtonValue** su **5**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-165">Set the **ButtonValue** property to **5**.</span></span>

6. <span data-ttu-id="2b4a4-166">Nella scheda **tutti Windows Forms** della **casella degli strumenti**fare doppio clic su **etichetta** per aggiungere un controllo <xref:System.Windows.Forms.Label> al modulo.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-166">In the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>

7. <span data-ttu-id="2b4a4-167">Posizionare l'etichetta al centro del modulo.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-167">Relocate the label to the center of the form.</span></span>

8. <span data-ttu-id="2b4a4-168">Fare doppio clic su `valueButton1`.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-168">Double-click `valueButton1`.</span></span>

     <span data-ttu-id="2b4a4-169">Nell'**editor di codice** verrà visualizzato l'evento `valueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-169">The **Code Editor** opens to the `valueButton1_Click` event.</span></span>

9. <span data-ttu-id="2b4a4-170">Inserire la seguente riga di codice.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-170">Insert the following line of code.</span></span>

    ```csharp
    label1.Text = valueButton1.ButtonValue.ToString();
    ```

10. <span data-ttu-id="2b4a4-171">In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **Test** quindi scegliere **Imposta** come progetto di avvio dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-171">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>

11. <span data-ttu-id="2b4a4-172">Scegliere **Avvia debug** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-172">From the **Debug** menu, select **Start Debugging**.</span></span>

     <span data-ttu-id="2b4a4-173">Viene visualizzato `Form1`.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-173">`Form1` appears.</span></span>

12. <span data-ttu-id="2b4a4-174">Fare clic su `valueButton1`.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-174">Click `valueButton1`.</span></span>

     <span data-ttu-id="2b4a4-175">Il numero "5" verrà visualizzato in `label1`, a significare che la proprietà `ButtonValue` del controllo ereditato è stata passata a `label1` mediante il metodo `valueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-175">The numeral '5' is displayed in `label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `label1` through the `valueButton1_Click` method.</span></span> <span data-ttu-id="2b4a4-176">Il controllo `ValueButton` erediterà tutte le funzionalità del pulsante standard per Windows Forms, ma esporrà una proprietà personalizzata aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="2b4a4-176">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b4a4-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b4a4-177">See also</span></span>

- [<span data-ttu-id="2b4a4-178">Procedura: Visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="2b4a4-178">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="2b4a4-179">Procedura dettagliata: Modifica di un controllo composito con Visual C#</span><span class="sxs-lookup"><span data-stu-id="2b4a4-179">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
