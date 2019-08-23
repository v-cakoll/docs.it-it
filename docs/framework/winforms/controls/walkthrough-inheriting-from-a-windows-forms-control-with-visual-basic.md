---
title: 'Procedura dettagliata: Ereditarietà da un controllo Windows Forms con Visual Basic'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: fb58d7c8-b702-4478-ad31-b00cae118882
ms.openlocfilehash: 378d7b0c67791e6c48e9859e0546594df3ccc85e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931009"
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic"></a><span data-ttu-id="84053-102">Procedura dettagliata: Ereditarietà da un controllo Windows Forms con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84053-102">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>
<span data-ttu-id="84053-103">Con Visual Basic, è possibile creare controlli personalizzati avanzati tramite l' *ereditarietà*.</span><span class="sxs-lookup"><span data-stu-id="84053-103">With Visual Basic, you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="84053-104">L'ereditarietà consente di creare nuovi controlli che non solo conservano tutte le funzionalità proprie dei controlli Windows Forms standard, ma includono anche funzionalità personalizzate.</span><span class="sxs-lookup"><span data-stu-id="84053-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="84053-105">In questa procedura verrà creato un controllo ereditato semplice denominato `ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="84053-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="84053-106">Questo pulsante erediterà la funzionalità dal controllo Windows Forms <xref:System.Windows.Forms.Button> standard e esporrà una proprietà personalizzata denominata. `ButtonValue`</span><span class="sxs-lookup"><span data-stu-id="84053-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="84053-107">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="84053-107">Creating the Project</span></span>
 <span data-ttu-id="84053-108">Quando si crea un nuovo progetto è necessario specificarne il nome per impostare lo spazio dei nomi radice, il nome dell'assembly e il nome del progetto e assicurarsi che il componente predefinito sia inserito nello spazio dei nomi corretto.</span><span class="sxs-lookup"><span data-stu-id="84053-108">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="84053-109">Per creare la libreria di controlli ValueButtonLib e il controllo ValueButton</span><span class="sxs-lookup"><span data-stu-id="84053-109">To create the ValueButtonLib control library and the ValueButton control</span></span>

1. <span data-ttu-id="84053-110">Scegliere **Nuovo** dal menu **File**, quindi fare clic su **Progetto**. Verrà visualizzata la finestra di dialogo **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="84053-110">On the **File** menu, point to **New** and then click **Project** to open the **New Project** dialog box.</span></span>

2. <span data-ttu-id="84053-111">Selezionare il modello di progetto **libreria di controllo Windows Forms** dall'elenco di progetti Visual Basic e digitare `ValueButtonLib` nella casella **nome** .</span><span class="sxs-lookup"><span data-stu-id="84053-111">Select the **Windows Forms Control Library** project template from the list of Visual Basic projects, and type `ValueButtonLib` in the **Name** box.</span></span>

     <span data-ttu-id="84053-112">Per impostazione predefinita il nome del progetto, `ValueButtonLib`, verrà assegnato anche allo spazio dei nomi radice.</span><span class="sxs-lookup"><span data-stu-id="84053-112">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="84053-113">Lo spazio dei nomi radice viene utilizzato per qualificare i nomi dei componenti dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="84053-113">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="84053-114">Se ad esempio due assembly forniscono componenti denominati `ValueButton`, sarà possibile specificare il componente `ValueButton` utilizzando `ValueButtonLib.ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="84053-114">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="84053-115">Per ulteriori informazioni, vedere [Spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="84053-115">For more information, see [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>

3. <span data-ttu-id="84053-116">In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **UserControl1** e scegliere **Rinomina** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="84053-116">In **Solution Explorer**, right-click **UserControl1.vb**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="84053-117">Modificare il nome file in `ValueButton.vb`.</span><span class="sxs-lookup"><span data-stu-id="84053-117">Change the file name to `ValueButton.vb`.</span></span> <span data-ttu-id="84053-118">Scegliere il pulsante **Sì** quando richiesto per rinominare tutti i riferimenti all'elemento di codice "UserControl1".</span><span class="sxs-lookup"><span data-stu-id="84053-118">Click the **Yes** button when you are asked if you want to rename all references to the code element 'UserControl1'.</span></span>

4. <span data-ttu-id="84053-119">In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**.</span><span class="sxs-lookup"><span data-stu-id="84053-119">In **Solution Explorer**, click the **Show All Files** button.</span></span>

5. <span data-ttu-id="84053-120">Aprire il nodo **ValueButton.vb** per visualizzare il file del codice generato nella finestra di progettazione **ValueButton.Designer.vb**.</span><span class="sxs-lookup"><span data-stu-id="84053-120">Open the **ValueButton.vb** node to display the designer-generated code file, **ValueButton.Designer.vb**.</span></span> <span data-ttu-id="84053-121">Aprire il file nell'**editor di codice**.</span><span class="sxs-lookup"><span data-stu-id="84053-121">Open this file in the **Code Editor**.</span></span>

6. <span data-ttu-id="84053-122">Individuare l' `Class` istruzione, `Partial Public Class ValueButton`e modificare il tipo da cui il controllo eredita da <xref:System.Windows.Forms.UserControl> a <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="84053-122">Locate the `Class` statement, `Partial Public Class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="84053-123">Ciò consente al controllo ereditato di ereditare tutte le funzionalità del <xref:System.Windows.Forms.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="84053-123">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>

7. <span data-ttu-id="84053-124">Individuare il `InitializeComponent` metodo e rimuovere la riga che assegna la <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="84053-124">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="84053-125">Questa proprietà non esiste nel <xref:System.Windows.Forms.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="84053-125">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>

8. <span data-ttu-id="84053-126">Per salvare il progetto, scegliere **Salva tutto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="84053-126">From the **File** menu, choose **Save All** to save the project.</span></span>

     <span data-ttu-id="84053-127">Si noti che non sarà più disponibile alcuna finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="84053-127">Note that a visual designer is no longer available.</span></span> <span data-ttu-id="84053-128">Poiché il <xref:System.Windows.Forms.Button> controllo esegue un disegno personalizzato, non è possibile modificarne l'aspetto nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="84053-128">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="84053-129">La relativa rappresentazione visiva sarà esattamente identica a quella della classe da cui eredita (ovvero), <xref:System.Windows.Forms.Button>a meno che non venga modificata nel codice.</span><span class="sxs-lookup"><span data-stu-id="84053-129">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span>

> [!NOTE]
> <span data-ttu-id="84053-130">È comunque possibile aggiungere nell'area di progettazione i componenti che non dispongono di elementi dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="84053-130">You can still add components, which have no UI elements, to the design surface.</span></span>

## <a name="adding-a-property-to-your-inherited-control"></a><span data-ttu-id="84053-131">Aggiunta di una proprietà al controllo ereditato</span><span class="sxs-lookup"><span data-stu-id="84053-131">Adding a Property to Your Inherited Control</span></span>
 <span data-ttu-id="84053-132">Un possibile utilizzo dei controlli Windows Forms ereditati è la creazione di controlli aventi aspetto e funzionalità identici ai controlli standard Windows Forms, ma che espongono proprietà personalizzate.</span><span class="sxs-lookup"><span data-stu-id="84053-132">One possible use of inherited Windows Forms controls is the creation of controls that are identical in appearance and behavior (look and feel) to standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="84053-133">In questa sezione verrà illustrata la modalità di aggiunta della proprietà `ButtonValue` al controllo.</span><span class="sxs-lookup"><span data-stu-id="84053-133">In this section, you will add a property called `ButtonValue` to your control.</span></span>

### <a name="to-add-the-value-property"></a><span data-ttu-id="84053-134">Per aggiungere la proprietà Value</span><span class="sxs-lookup"><span data-stu-id="84053-134">To add the Value property</span></span>

1. <span data-ttu-id="84053-135">In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **ValueButton.vb**, quindi scegliere **Visualizza codice** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="84053-135">In **Solution Explorer**, right-click **ValueButton.vb**, and then click **View Code** from the shortcut menu.</span></span>

2. <span data-ttu-id="84053-136">Individuare l'istruzione `Public Class ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="84053-136">Locate the `Public Class ValueButton` statement.</span></span> <span data-ttu-id="84053-137">Sotto questa istruzione digitare il seguente codice:</span><span class="sxs-lookup"><span data-stu-id="84053-137">Immediately beneath this statement, type the following code:</span></span>

    ```vb
    ' Creates the private variable that will store the value of your
    ' property.
    Private varValue as integer
    ' Declares the property.
    Property ButtonValue() as Integer
    ' Sets the method for retrieving the value of your property.
       Get
          Return varValue
       End Get
    ' Sets the method for setting the value of your property.
       Set(ByVal Value as Integer)
          varValue = Value
       End Set
    End Property
    ```

     <span data-ttu-id="84053-138">Questo codice consente di impostare i metodi per la memorizzazione e il recupero della proprietà `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="84053-138">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="84053-139">L'istruzione `Get` consente di impostare il valore restituito sul valore memorizzato nella variabile privata `varValue`, mentre l'istruzione `Set` consente di impostare il valore della variabile privata mediante la parola chiave `Value`.</span><span class="sxs-lookup"><span data-stu-id="84053-139">The `Get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `Set` statement sets the value of the private variable by use of the `Value` keyword.</span></span>

3. <span data-ttu-id="84053-140">Per salvare il progetto, scegliere **Salva tutto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="84053-140">From the **File** menu, choose **Save All** to save the project.</span></span>

## <a name="testing-your-control"></a><span data-ttu-id="84053-141">Test del controllo</span><span class="sxs-lookup"><span data-stu-id="84053-141">Testing Your Control</span></span>
 <span data-ttu-id="84053-142">I controlli non sono progetti autonomi e devono pertanto essere inseriti in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="84053-142">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="84053-143">Per testare il controllo, è necessario creare un progetto di test in cui eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="84053-143">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="84053-144">È inoltre necessario rendere il controllo accessibile al progetto di test compilandolo.</span><span class="sxs-lookup"><span data-stu-id="84053-144">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="84053-145">In questa sezione verrà illustrato come compilare un controllo ed eseguirne il test in un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="84053-145">In this section, you will build your control and test it in a Windows Form.</span></span>

### <a name="to-build-your-control"></a><span data-ttu-id="84053-146">Per compilare il controllo</span><span class="sxs-lookup"><span data-stu-id="84053-146">To build your control</span></span>

1. <span data-ttu-id="84053-147">Scegliere **Compila soluzione** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="84053-147">On the **Build** menu, click **Build Solution**.</span></span>

     <span data-ttu-id="84053-148">La compilazione dovrebbe essere completata senza errori del compilatore o avvisi.</span><span class="sxs-lookup"><span data-stu-id="84053-148">The build should be successful with no compiler errors or warnings.</span></span>

### <a name="to-create-a-test-project"></a><span data-ttu-id="84053-149">Per creare un progetto di test</span><span class="sxs-lookup"><span data-stu-id="84053-149">To create a test project</span></span>

1. <span data-ttu-id="84053-150">Scegliere **Aggiungi** dal menu **File**, quindi fare clic su **Nuovo progetto**. Verrà visualizzata la finestra di dialogo **Aggiungi nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="84053-150">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="84053-151">Selezionare il nodo progetti Visual Basic e fare clic su **Windows Forms applicazione**.</span><span class="sxs-lookup"><span data-stu-id="84053-151">Select the Visual Basic projects node, and click **Windows Forms Application**.</span></span>

3. <span data-ttu-id="84053-152">Nella casella **Nome** digitare `Test`.</span><span class="sxs-lookup"><span data-stu-id="84053-152">In the **Name** box, type `Test`.</span></span>

4. <span data-ttu-id="84053-153">In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**.</span><span class="sxs-lookup"><span data-stu-id="84053-153">In **Solution Explorer**, click the **Show All Files** button.</span></span>

5. <span data-ttu-id="84053-154">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Riferimenti** del progetto di test, quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida per visualizzare la finestra di dialogo **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="84053-154">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>

6. <span data-ttu-id="84053-155">Fare clic sulla scheda **Progetti**.</span><span class="sxs-lookup"><span data-stu-id="84053-155">Click the **Projects** tab.</span></span>

7. <span data-ttu-id="84053-156">Scegliere la scheda **Progetti**.</span><span class="sxs-lookup"><span data-stu-id="84053-156">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="84053-157">Il progetto `ValueButtonLib` verrà elencato in **Nome progetto**.</span><span class="sxs-lookup"><span data-stu-id="84053-157">Your `ValueButtonLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="84053-158">Fare doppio clic sul progetto per cui si desidera aggiungere il riferimento al progetto di test.</span><span class="sxs-lookup"><span data-stu-id="84053-158">Double-click the project to add the reference to the test project.</span></span>

8. <span data-ttu-id="84053-159">In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **Test** e scegliere **Compila**.</span><span class="sxs-lookup"><span data-stu-id="84053-159">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>

### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="84053-160">Per aggiungere il controllo al modulo</span><span class="sxs-lookup"><span data-stu-id="84053-160">To add your control to the form</span></span>

1. <span data-ttu-id="84053-161">In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **Form1.vb**, quindi scegliere **Visualizza finestra di progettazione** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="84053-161">In **Solution Explorer**, right-click **Form1.vb** and choose **View Designer** from the shortcut menu.</span></span>

2. <span data-ttu-id="84053-162">Nella **Casella degli strumenti** fare clic su **Componenti ValueButtonLib**.</span><span class="sxs-lookup"><span data-stu-id="84053-162">In the **Toolbox**, click **ValueButtonLib Components**.</span></span> <span data-ttu-id="84053-163">Fare doppio clic su **ValueButton**.</span><span class="sxs-lookup"><span data-stu-id="84053-163">Double-click **ValueButton**.</span></span>

     <span data-ttu-id="84053-164">Nel modulo verrà visualizzato un controllo **ValueButton**.</span><span class="sxs-lookup"><span data-stu-id="84053-164">A **ValueButton** appears on the form.</span></span>

3. <span data-ttu-id="84053-165">Fare clic con il pulsante destro del mouse su **ValueButton**, quindi scegliere **Proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="84053-165">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>

4. <span data-ttu-id="84053-166">Nella finestra **Proprietà** esaminare le proprietà del controllo.</span><span class="sxs-lookup"><span data-stu-id="84053-166">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="84053-167">Tali proprietà sono identiche a quelle esposte da un pulsante standard, con la differenza che è disponibile anche la proprietà `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="84053-167">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, `ButtonValue`.</span></span>

5. <span data-ttu-id="84053-168">Impostare la proprietà `ButtonValue` su `5`.</span><span class="sxs-lookup"><span data-stu-id="84053-168">Set the `ButtonValue` property to `5`.</span></span>

6. <span data-ttu-id="84053-169">Nella scheda **tutti Windows Forms** della **casella degli strumenti**fare doppio clic su **etichetta** per aggiungere un <xref:System.Windows.Forms.Label> controllo al form.</span><span class="sxs-lookup"><span data-stu-id="84053-169">On the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>

7. <span data-ttu-id="84053-170">Posizionare l'etichetta al centro del modulo.</span><span class="sxs-lookup"><span data-stu-id="84053-170">Relocate the label to the center of the form.</span></span>

8. <span data-ttu-id="84053-171">Doppio clic su `ValueButton1`.</span><span class="sxs-lookup"><span data-stu-id="84053-171">Double-click `ValueButton1`.</span></span>

     <span data-ttu-id="84053-172">Nell'**editor di codice** verrà visualizzato l'evento `ValueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="84053-172">The **Code Editor** opens to the `ValueButton1_Click` event.</span></span>

9. <span data-ttu-id="84053-173">Digitare la seguente riga di codice.</span><span class="sxs-lookup"><span data-stu-id="84053-173">Type the following line of code.</span></span>

    ```vb
    Label1.Text = CStr(ValueButton1.ButtonValue)
    ```

10. <span data-ttu-id="84053-174">In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **Test** quindi scegliere **Imposta** come progetto di avvio dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="84053-174">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>

11. <span data-ttu-id="84053-175">Scegliere **Avvia debug** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="84053-175">From the **Debug** menu, select **Start Debugging**.</span></span>

     <span data-ttu-id="84053-176">Viene visualizzato `Form1`.</span><span class="sxs-lookup"><span data-stu-id="84053-176">`Form1` appears.</span></span>

12. <span data-ttu-id="84053-177">Fare clic su `Valuebutton1`.</span><span class="sxs-lookup"><span data-stu-id="84053-177">Click `Valuebutton1`.</span></span>

     <span data-ttu-id="84053-178">Il numero "5" verrà visualizzato in `Label1`, a significare che la proprietà `ButtonValue` del controllo ereditato è stata passata a `Label1` mediante il metodo `ValueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="84053-178">The numeral '5' is displayed in `Label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `Label1` through the `ValueButton1_Click` method.</span></span> <span data-ttu-id="84053-179">Il controllo `ValueButton` erediterà tutte le funzionalità del pulsante standard per Windows Forms, ma esporrà una proprietà personalizzata aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="84053-179">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>

## <a name="see-also"></a><span data-ttu-id="84053-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84053-180">See also</span></span>

- [<span data-ttu-id="84053-181">Procedura dettagliata: Creazione di un controllo composito con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84053-181">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="84053-182">Procedura: Visualizza un controllo nella finestra di dialogo Scegli elementi della casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="84053-182">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="84053-183">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="84053-183">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="84053-184">Nozioni fondamentali sull'ereditarietà (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84053-184">Inheritance basics (Visual Basic)</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
