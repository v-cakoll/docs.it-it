---
title: "Procedura dettagliata: Dimostrazione dell'ereditarietà visiva"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- form inheritance [Windows Forms], walkthroughs
- visual inheritance
- inheritance [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], visual inheritance
- Windows Forms, inheritance
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
ms.openlocfilehash: 6fd504269ae9afbfd02b58276582a644674e1e0f
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040317"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a><span data-ttu-id="cbbb2-102">Procedura dettagliata: Dimostrazione dell'ereditarietà visiva</span><span class="sxs-lookup"><span data-stu-id="cbbb2-102">Walkthrough: Demonstrating Visual Inheritance</span></span>

<span data-ttu-id="cbbb2-103">L'ereditarietà visiva consente di visualizzare i controlli nel form di base e di aggiungere nuovi controlli.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-103">Visual inheritance enables you to see the controls on the base form and to add new controls.</span></span> <span data-ttu-id="cbbb2-104">In questa procedura dettagliata verrà creato un form di base che verrà compilato in una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-104">In this walkthrough you will create a base form and compile it into a class library.</span></span> <span data-ttu-id="cbbb2-105">La libreria di classi verrà importata in un altro progetto e verrà creato un nuovo form che eredita dal form di base.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-105">You will import this class library into another project and create a new form that inherits from the base form.</span></span> <span data-ttu-id="cbbb2-106">Durante questa procedura dettagliata, si apprenderà come:</span><span class="sxs-lookup"><span data-stu-id="cbbb2-106">During this walkthrough, you will learn how to:</span></span>

- <span data-ttu-id="cbbb2-107">Creare un progetto di libreria di classi contenente un form di base.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-107">Create a class library project containing a base form.</span></span>

- <span data-ttu-id="cbbb2-108">Aggiungere un pulsante con proprietà che le classi derivate del form di base possono modificare.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-108">Add a button with properties that derived classes of the base form can modify.</span></span>

- <span data-ttu-id="cbbb2-109">Aggiungere un pulsante che non può essere modificato dagli eredi del form di base.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-109">Add a button that cannot be modified by inheritors of the base form.</span></span>

- <span data-ttu-id="cbbb2-110">Creare un progetto contenente un form che eredita da `BaseForm`.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-110">Create a project containing a form that inherits from `BaseForm`.</span></span>

<span data-ttu-id="cbbb2-111">Infine, questa procedura dettagliata illustrerà la differenza tra controlli privati e protetti in un form ereditato.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-111">Ultimately, this walkthrough will demonstrate the difference between private and protected controls on an inherited form.</span></span>

> [!CAUTION]
> <span data-ttu-id="cbbb2-112">Non tutti i controlli supportano l'ereditarietà visiva da un form di base.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-112">Not all controls support visual inheritance from a base form.</span></span> <span data-ttu-id="cbbb2-113">I controlli seguenti non supportano lo scenario descritto in questa procedura dettagliata:</span><span class="sxs-lookup"><span data-stu-id="cbbb2-113">The following controls do not support the scenario described in this walkthrough:</span></span>
>
>  <xref:System.Windows.Forms.WebBrowser>
>
>  <xref:System.Windows.Forms.ToolStrip>
>
>  <xref:System.Windows.Forms.ToolStripPanel>
>
>  <xref:System.Windows.Forms.TableLayoutPanel>
>
>  <xref:System.Windows.Forms.FlowLayoutPanel>
>
>  <xref:System.Windows.Forms.DataGridView>
>
>  <span data-ttu-id="cbbb2-114">Questi controlli nel form ereditato sono sempre di sola lettura, indipendentemente dai modificatori usati (`private`, `protected` o `public`).</span><span class="sxs-lookup"><span data-stu-id="cbbb2-114">These controls in the inherited form are always read-only regardless of the modifiers you use (`private`, `protected`, or `public`).</span></span>

## <a name="create-a-class-library-project-containing-a-base-form"></a><span data-ttu-id="cbbb2-115">Creare un progetto di libreria di classi contenente un form di base</span><span class="sxs-lookup"><span data-stu-id="cbbb2-115">Create a class library project containing a base form</span></span>

1. <span data-ttu-id="cbbb2-116">In Visual Studio scegliere **nuovo** > **progetto** dal menu **file** per aprire la finestra di dialogo **nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="cbbb2-116">In Visual Studio, from the **File** menu, choose **New** > **Project** to open the **New Project** dialog box.</span></span>

2. <span data-ttu-id="cbbb2-117">Creare una Windows Forms Application denominata `BaseFormLibrary`.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-117">Create a Windows Forms application named `BaseFormLibrary`.</span></span>

3. <span data-ttu-id="cbbb2-118">Per creare una libreria di classi anziché una Windows Forms Application standard, in **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nodo del progetto **BaseFormLibrary** , quindi scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-118">To create a class library instead of a standard Windows Forms application, in **Solution Explorer**, right-click the **BaseFormLibrary** project node and then select **Properties**.</span></span>

4. <span data-ttu-id="cbbb2-119">Nelle proprietà del progetto modificare il **tipo di output** da **applicazione Windows** a libreria di **classi**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-119">In the properties for the project, change the **Output type** from **Windows Application** to **Class Library**.</span></span>

5. <span data-ttu-id="cbbb2-120">Scegliere **Salva tutto** dal menu **file** per salvare il progetto e i file nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-120">From the **File** menu, choose **Save All** to save the project and files to the default location.</span></span>

 <span data-ttu-id="cbbb2-121">Le due procedure seguenti consentono di aggiungere pulsanti al form di base.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-121">The next two procedures add buttons to the base form.</span></span> <span data-ttu-id="cbbb2-122">Per dimostrare l'ereditarietà visiva, si assegneranno ai pulsanti livelli di accesso diversi impostando le relative proprietà `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-122">To demonstrate visual inheritance, you will give the buttons different access levels by setting their `Modifiers` properties.</span></span>

## <a name="add-a-button-that-inheritors-of-the-base-form-can-modify"></a><span data-ttu-id="cbbb2-123">Aggiungere un pulsante che gli eredi del form di base possono modificare</span><span class="sxs-lookup"><span data-stu-id="cbbb2-123">Add a button that inheritors of the base form can modify</span></span>

1. <span data-ttu-id="cbbb2-124">Aprire **Form1** nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-124">Open **Form1** in the designer.</span></span>

2. <span data-ttu-id="cbbb2-125">Nella scheda **tutti Windows Forms** della **casella degli strumenti**fare doppio clic sul **pulsante** per aggiungere un pulsante al form.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-125">On the **All Windows Forms** tab of the **Toolbox**, double-click **Button** to add a button to the form.</span></span> <span data-ttu-id="cbbb2-126">Usare il mouse per posizionare e ridimensionare il pulsante.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-126">Use the mouse to position and resize the button.</span></span>

3. <span data-ttu-id="cbbb2-127">Nella finestra Proprietà impostare le seguenti proprietà del pulsante:</span><span class="sxs-lookup"><span data-stu-id="cbbb2-127">In the Properties window, set the following properties of the button:</span></span>

    - <span data-ttu-id="cbbb2-128">Impostare la proprietà **Text** su **Say Hello**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-128">Set the **Text** property to **Say Hello**.</span></span>

    - <span data-ttu-id="cbbb2-129">Impostare la proprietà **(Name)** su **btnProtected**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-129">Set the **(Name)** property to **btnProtected**.</span></span>

    - <span data-ttu-id="cbbb2-130">Impostare la proprietà Modifiers su **protected**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-130">Set the **Modifiers** property to **Protected**.</span></span> <span data-ttu-id="cbbb2-131">Ciò rende possibile per i form che ereditano da **Form1** per modificare le proprietà di **btnProtected**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-131">This makes it possible for forms that inherit from **Form1** to modify the properties of **btnProtected**.</span></span>

4. <span data-ttu-id="cbbb2-132">Fare doppio clic sul pulsante **Say Hello** per aggiungere un gestore eventi per l'evento **Click** .</span><span class="sxs-lookup"><span data-stu-id="cbbb2-132">Double-click the **Say Hello** button to add an event handler for the **Click** event.</span></span>

5. <span data-ttu-id="cbbb2-133">Aggiungere la riga di codice seguente al gestore eventi:</span><span class="sxs-lookup"><span data-stu-id="cbbb2-133">Add the following line of code to the event handler:</span></span>

    ```vb
    MessageBox.Show("Hello, World!")
    ```

    ```csharp
    MessageBox.Show("Hello, World!");
    ```

## <a name="add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a><span data-ttu-id="cbbb2-134">Aggiungere un pulsante che non può essere modificato dagli eredi del form di base</span><span class="sxs-lookup"><span data-stu-id="cbbb2-134">Add a button that cannot be modified by inheritors of the base form</span></span>

1. <span data-ttu-id="cbbb2-135">Passare alla visualizzazione progettazione facendo clic sulla scheda **Form1. vb [Design], Form1.cs [Design] o Form1. jsl [Progettazione]** sopra l'editor di codice o premendo F7.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-135">Switch to design view by clicking the **Form1.vb [Design], Form1.cs [Design], or Form1.jsl [Design]** tab above the code editor, or by pressing F7.</span></span>

2. <span data-ttu-id="cbbb2-136">Aggiungere un secondo pulsante e impostarne le proprietà come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cbbb2-136">Add a second button and set its properties as follows:</span></span>

    - <span data-ttu-id="cbbb2-137">Impostare la proprietà **Text** su **Say Goodbye**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-137">Set the **Text** property to **Say Goodbye**.</span></span>

    - <span data-ttu-id="cbbb2-138">Impostare la proprietà **(Name)** su **btnPrivate**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-138">Set the **(Name)** property to **btnPrivate**.</span></span>

    - <span data-ttu-id="cbbb2-139">Impostare la proprietà Modifiers su **private**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-139">Set the **Modifiers** property to **Private**.</span></span> <span data-ttu-id="cbbb2-140">Ciò rende impossibile per i form che ereditano da **Form1** per modificare le proprietà di **btnPrivate**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-140">This makes it impossible for forms that inherit from **Form1** to modify the properties of **btnPrivate**.</span></span>

3. <span data-ttu-id="cbbb2-141">Fare doppio clic sul pulsante **Say Goodbye** per aggiungere un gestore eventi per l'evento **Click** .</span><span class="sxs-lookup"><span data-stu-id="cbbb2-141">Double-click the **Say Goodbye** button to add an event handler for the **Click** event.</span></span> <span data-ttu-id="cbbb2-142">Inserire la riga di codice seguente nella routine evento:</span><span class="sxs-lookup"><span data-stu-id="cbbb2-142">Place the following line of code in the event procedure:</span></span>

    ```vb
    MessageBox.Show("Goodbye!")
    ```

    ```csharp
    MessageBox.Show("Goodbye!");
    ```

4. <span data-ttu-id="cbbb2-143">Dal menu **Compila** scegliere **Compila libreria BaseFormLibrary** per compilare la libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-143">From the **Build** menu, choose **Build BaseForm Library** to build the class library.</span></span>

     <span data-ttu-id="cbbb2-144">Dopo aver compilato la libreria, è possibile creare un nuovo progetto che eredita dal form appena creato.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-144">Once the library is built, you can create a new project that inherits from the form you just created.</span></span>

## <a name="create-a-project-containing-a-form-that-inherits-from-the-base-form"></a><span data-ttu-id="cbbb2-145">Creare un progetto contenente un form che eredita dal form di base</span><span class="sxs-lookup"><span data-stu-id="cbbb2-145">Create a project containing a form that inherits from the base form</span></span>

1. <span data-ttu-id="cbbb2-146">Dal menu **file** scegliere **Aggiungi** , quindi **nuovo progetto** per aprire la finestra di dialogo **Aggiungi nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="cbbb2-146">From the **File** menu, choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="cbbb2-147">Creare una Windows Forms Application denominata `InheritanceTest`.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-147">Create a Windows Forms application named `InheritanceTest`.</span></span>

## <a name="add-an-inherited-form"></a><span data-ttu-id="cbbb2-148">Aggiungere un form ereditato</span><span class="sxs-lookup"><span data-stu-id="cbbb2-148">Add an inherited form</span></span>

1. <span data-ttu-id="cbbb2-149">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **InheritanceTest** , scegliere **Aggiungi**, quindi selezionare **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-149">In **Solution Explorer**, right-click the **InheritanceTest** project, select **Add**, and then select **New Item**.</span></span>

2. <span data-ttu-id="cbbb2-150">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare la categoria **Windows Forms** (se si dispone di un elenco di categorie), quindi selezionare il modello di **modulo ereditato** .</span><span class="sxs-lookup"><span data-stu-id="cbbb2-150">In the **Add New Item** dialog box, select the **Windows Forms** category (if you have a list of categories) and then select the **Inherited Form** template.</span></span>

3. <span data-ttu-id="cbbb2-151">Lasciare il nome `Form2` predefinito e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-151">Leave the default name of `Form2` and then click **Add**.</span></span>

4. <span data-ttu-id="cbbb2-152">Nella finestra di dialogo **Selezione ereditarietà** selezionare **Form1** dal progetto **BaseFormLibrary** come modulo da cui ereditare e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-152">In the **Inheritance Picker** dialog box, select **Form1** from the **BaseFormLibrary** project as the form to inherit from and click **OK**.</span></span>

     <span data-ttu-id="cbbb2-153">In questo modo viene creato un modulo nel progetto **InheritanceTest** che deriva dal form in **BaseFormLibrary**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-153">This creates a form in the **InheritanceTest** project that derives from the form in **BaseFormLibrary**.</span></span>

5. <span data-ttu-id="cbbb2-154">Aprire il form ereditato (**Form2**) nella finestra di progettazione facendo doppio clic su di esso, se non è già aperto.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-154">Open the inherited form (**Form2**) in the designer by double-clicking it, if it is not already open.</span></span>

     <span data-ttu-id="cbbb2-155">Nella finestra di progettazione i pulsanti ereditati hanno un simbolo (</span><span class="sxs-lookup"><span data-stu-id="cbbb2-155">In the designer, the inherited buttons have a symbol (</span></span>![Screenshot del simbolo di ereditarietà del Visual Basic.](./media/walkthrough-demonstrating-visual-inheritance/visual-basic-inheritance-glyph.gif)<span data-ttu-id="cbbb2-157">) nell'angolo superiore, a indicare che vengono ereditate.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-157">) in their upper corner, indicating they are inherited.</span></span>

6. <span data-ttu-id="cbbb2-158">Selezionare il pulsante **Say Hello** e osservare i quadratini di ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-158">Select the **Say Hello** button and observe the resize handles.</span></span> <span data-ttu-id="cbbb2-159">Poiché questo pulsante è protetto, gli eredi possono spostarlo, ridimensionarlo, modificarne la didascalia e apportare altre modifiche.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-159">Because this button is protected, the inheritors can move it, resize it, change its caption, and make other modifications.</span></span>

7. <span data-ttu-id="cbbb2-160">Selezionare il pulsante privato **Say Goodbye** e notare che non sono presenti handle di ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-160">Select the private **Say Goodbye** button, and notice that it does not have resize handles.</span></span> <span data-ttu-id="cbbb2-161">Inoltre, nella finestra **Proprietà** le proprietà del pulsante sono visualizzate in grigio per indicare che non possono essere modificate.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-161">Additionally, in the **Properties** window, the properties of this button are grayed to indicate they cannot be modified.</span></span>

8. <span data-ttu-id="cbbb2-162">Se si usa Visual C#:</span><span class="sxs-lookup"><span data-stu-id="cbbb2-162">If you are using Visual C#:</span></span>

    1. <span data-ttu-id="cbbb2-163">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **Form1** nel progetto **InheritanceTest** , quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-163">In **Solution Explorer**, right-click **Form1** in the **InheritanceTest** project and then choose **Delete**.</span></span> <span data-ttu-id="cbbb2-164">Nella finestra di messaggio visualizzata fare clic su **OK** per confermare l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-164">In the message box that appears, click **OK** to confirm the deletion.</span></span>

    2. <span data-ttu-id="cbbb2-165">Aprire il file Program.cs e modificare la riga `Application.Run(new Form1());` in `Application.Run(new Form2());`.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-165">Open the Program.cs file and change the line `Application.Run(new Form1());` to `Application.Run(new Form2());`.</span></span>

9. <span data-ttu-id="cbbb2-166">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **InheritanceTest** e selezionare **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-166">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Set As Startup Project**.</span></span>

10. <span data-ttu-id="cbbb2-167">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **InheritanceTest** e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-167">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Properties**.</span></span>

11. <span data-ttu-id="cbbb2-168">Nelle pagine delle proprietà di **InheritanceTest** impostare l' **oggetto di avvio** in modo che sia il formato ereditato (**Form2**).</span><span class="sxs-lookup"><span data-stu-id="cbbb2-168">In the **InheritanceTest** property pages, set the **Startup object** to be the inherited form (**Form2**).</span></span>

12. <span data-ttu-id="cbbb2-169">Premere **F5** per eseguire l'applicazione e osservare il comportamento del form ereditato.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-169">Press **F5** to run the application, and observe the behavior of the inherited form.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cbbb2-170">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cbbb2-170">Next steps</span></span>

<span data-ttu-id="cbbb2-171">L'ereditarietà per i controlli utente funziona in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-171">Inheritance for user controls works in much the same way.</span></span> <span data-ttu-id="cbbb2-172">Aprire un nuovo progetto di libreria di classi e aggiungere un controllo utente.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-172">Open a new class library project and add a user control.</span></span> <span data-ttu-id="cbbb2-173">Inserire controlli costitutivi e compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-173">Place constituent controls on it and compile the project.</span></span> <span data-ttu-id="cbbb2-174">Aprire un altro progetto di libreria di classi e aggiungere un riferimento alla libreria di classi compilata.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-174">Open another new class library project and add a reference to the compiled class library.</span></span> <span data-ttu-id="cbbb2-175">Provare anche ad aggiungere un controllo ereditato (tramite la finestra di dialogo **Aggiungi nuovi elementi** ) al progetto e a usare la **Selezione ereditarietà**.</span><span class="sxs-lookup"><span data-stu-id="cbbb2-175">Also, try adding an inherited control (through the **Add New Items** dialog box) to the project and using the **Inheritance Picker**.</span></span> <span data-ttu-id="cbbb2-176">Aggiungere un controllo utente e modificare l' `Inherits` istruzione (`:` in Visual C#).</span><span class="sxs-lookup"><span data-stu-id="cbbb2-176">Add a user control, and change the `Inherits` (`:` in Visual C#) statement.</span></span> <span data-ttu-id="cbbb2-177">Per altre informazioni, vedere [Procedura: Eredita Windows Forms](how-to-inherit-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="cbbb2-177">For more information, see [How to: Inherit Windows Forms](how-to-inherit-windows-forms.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cbbb2-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbbb2-178">See also</span></span>

- [<span data-ttu-id="cbbb2-179">Procedura: Eredita Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cbbb2-179">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="cbbb2-180">Ereditarietà visiva di Windows Form</span><span class="sxs-lookup"><span data-stu-id="cbbb2-180">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="cbbb2-181">Windows Form</span><span class="sxs-lookup"><span data-stu-id="cbbb2-181">Windows Forms</span></span>](../index.md)
