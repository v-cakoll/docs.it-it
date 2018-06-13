---
title: "Procedura dettagliata: dimostrazione dell'ereditarietà visiva"
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
ms.openlocfilehash: 61239d9b547be73a14618d41feeb9aeea9f8ded6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529701"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a><span data-ttu-id="24c58-102">Procedura dettagliata: dimostrazione dell'ereditarietà visiva</span><span class="sxs-lookup"><span data-stu-id="24c58-102">Walkthrough: Demonstrating Visual Inheritance</span></span>
<span data-ttu-id="24c58-103">L'ereditarietà visiva consente di visualizzare i controlli nel form di base e di aggiungere nuovi controlli.</span><span class="sxs-lookup"><span data-stu-id="24c58-103">Visual inheritance enables you to see the controls on the base form and to add new controls.</span></span> <span data-ttu-id="24c58-104">In questa procedura dettagliata verrà creato un form di base che verrà compilato in una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="24c58-104">In this walkthrough you will create a base form and compile it into a class library.</span></span> <span data-ttu-id="24c58-105">La libreria di classi verrà importata in un altro progetto e verrà creato un nuovo form che eredita dal form di base.</span><span class="sxs-lookup"><span data-stu-id="24c58-105">You will import this class library into another project and create a new form that inherits from the base form.</span></span> <span data-ttu-id="24c58-106">Durante questa procedura dettagliata, si apprenderà come:</span><span class="sxs-lookup"><span data-stu-id="24c58-106">During this walkthrough, you will learn how to:</span></span>  
  
-   <span data-ttu-id="24c58-107">Creare un progetto di libreria di classi contenente un form di base.</span><span class="sxs-lookup"><span data-stu-id="24c58-107">Create a class library project containing a base form.</span></span>  
  
-   <span data-ttu-id="24c58-108">Aggiungere un pulsante con proprietà che le classi derivate del form di base possono modificare.</span><span class="sxs-lookup"><span data-stu-id="24c58-108">Add a button with properties that derived classes of the base form can modify.</span></span>  
  
-   <span data-ttu-id="24c58-109">Aggiungere un pulsante che non può essere modificato dagli eredi del form di base.</span><span class="sxs-lookup"><span data-stu-id="24c58-109">Add a button that cannot be modified by inheritors of the base form.</span></span>  
  
-   <span data-ttu-id="24c58-110">Creare un progetto contenente un form che eredita da `BaseForm`.</span><span class="sxs-lookup"><span data-stu-id="24c58-110">Create a project containing a form that inherits from `BaseForm`.</span></span>  
  
 <span data-ttu-id="24c58-111">Infine, questa procedura dettagliata illustrerà la differenza tra controlli privati e protetti in un form ereditato.</span><span class="sxs-lookup"><span data-stu-id="24c58-111">Ultimately, this walkthrough will demonstrate the difference between private and protected controls on an inherited form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24c58-112">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="24c58-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="24c58-113">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="24c58-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="24c58-114">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="24c58-114">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="24c58-115">Non tutti i controlli supportano l'ereditarietà visiva da un form di base.</span><span class="sxs-lookup"><span data-stu-id="24c58-115">Not all controls support visual inheritance from a base form.</span></span> <span data-ttu-id="24c58-116">I controlli seguenti non supportano lo scenario descritto in questa procedura dettagliata:</span><span class="sxs-lookup"><span data-stu-id="24c58-116">The following controls do not support the scenario described in this walkthrough:</span></span>  
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
>  <span data-ttu-id="24c58-117">Questi controlli nel form ereditato sono sempre di sola lettura, indipendentemente dai modificatori usati (`private`, `protected` o `public`).</span><span class="sxs-lookup"><span data-stu-id="24c58-117">These controls in the inherited form are always read-only regardless of the modifiers you use (`private`, `protected`, or `public`).</span></span>  
  
## <a name="scenario-steps"></a><span data-ttu-id="24c58-118">Passaggi dello scenario</span><span class="sxs-lookup"><span data-stu-id="24c58-118">Scenario Steps</span></span>  
 <span data-ttu-id="24c58-119">Il primo passaggio consiste nella creazione del form di base.</span><span class="sxs-lookup"><span data-stu-id="24c58-119">The first step is to create the base form.</span></span>  
  
#### <a name="to-create-a-class-library-project-containing-a-base-form"></a><span data-ttu-id="24c58-120">Per creare un progetto di libreria di classi contenente un form di base</span><span class="sxs-lookup"><span data-stu-id="24c58-120">To create a class library project containing a base form</span></span>  
  
1.  <span data-ttu-id="24c58-121">Dal **File** menu, scegliere **New**e quindi **progetto** per aprire la **nuovo progetto** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="24c58-121">From the **File** menu, choose **New**, and then **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="24c58-122">Creare un'applicazione Windows Form denominata `BaseFormLibrary`.</span><span class="sxs-lookup"><span data-stu-id="24c58-122">Create a Windows Forms application named `BaseFormLibrary`.</span></span>  
  
3.  <span data-ttu-id="24c58-123">Per creare una libreria di classi anziché un'applicazione Windows Form standard, in **Esplora**, fare doppio clic su di **BaseFormLibrary** nodo del progetto e quindi selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="24c58-123">To create a class library instead of a standard Windows Forms application, in **Solution Explorer**, right-click the **BaseFormLibrary** project node and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="24c58-124">Nelle proprietà del progetto, modificare il **tipo di Output** da **applicazione Windows** a **libreria di classi**.</span><span class="sxs-lookup"><span data-stu-id="24c58-124">In the properties for the project, change the **Output type** from **Windows Application** to **Class Library**.</span></span>  
  
5.  <span data-ttu-id="24c58-125">Dal **File** menu, scegliere **Salva tutto** per salvare il file di progetto e nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="24c58-125">From the **File** menu, choose **Save All** to save the project and files to the default location.</span></span>  
  
 <span data-ttu-id="24c58-126">Le due procedure seguenti consentono di aggiungere pulsanti al form di base.</span><span class="sxs-lookup"><span data-stu-id="24c58-126">The next two procedures add buttons to the base form.</span></span> <span data-ttu-id="24c58-127">Per dimostrare l'ereditarietà visiva, si assegneranno ai pulsanti livelli di accesso diversi impostando le relative proprietà `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="24c58-127">To demonstrate visual inheritance, you will give the buttons different access levels by setting their `Modifiers` properties.</span></span>  
  
#### <a name="to-add-a-button-that-inheritors-of-the-base-form-can-modify"></a><span data-ttu-id="24c58-128">Per aggiungere un pulsante che gli eredi del form di base possono modificare</span><span class="sxs-lookup"><span data-stu-id="24c58-128">To add a button that inheritors of the base form can modify</span></span>  
  
1.  <span data-ttu-id="24c58-129">Aprire **Form1** nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="24c58-129">Open **Form1** in the designer.</span></span>  
  
2.  <span data-ttu-id="24c58-130">Nel **tutti i Windows Form** scheda della finestra di **della casella degli strumenti**, fare doppio clic su **pulsante** per aggiungere un pulsante al form.</span><span class="sxs-lookup"><span data-stu-id="24c58-130">On the **All Windows Forms** tab of the **Toolbox**, double-click **Button** to add a button to the form.</span></span> <span data-ttu-id="24c58-131">Usare il mouse per posizionare e ridimensionare il pulsante.</span><span class="sxs-lookup"><span data-stu-id="24c58-131">Use the mouse to position and resize the button.</span></span>  
  
3.  <span data-ttu-id="24c58-132">Nella finestra Proprietà impostare le seguenti proprietà del pulsante:</span><span class="sxs-lookup"><span data-stu-id="24c58-132">In the Properties window, set the following properties of the button:</span></span>  
  
    -   <span data-ttu-id="24c58-133">Impostare il **testo** proprietà **Say Hello**.</span><span class="sxs-lookup"><span data-stu-id="24c58-133">Set the **Text** property to **Say Hello**.</span></span>  
  
    -   <span data-ttu-id="24c58-134">Impostare il **(nome)** proprietà **btnProtected**.</span><span class="sxs-lookup"><span data-stu-id="24c58-134">Set the **(Name)** property to **btnProtected**.</span></span>  
  
    -   <span data-ttu-id="24c58-135">Impostare il**modificatori** proprietà **Protected**.</span><span class="sxs-lookup"><span data-stu-id="24c58-135">Set the**Modifiers** property to **Protected**.</span></span> <span data-ttu-id="24c58-136">Questo rende possibile per i form che ereditano da **Form1** per modificare le proprietà di **btnProtected**.</span><span class="sxs-lookup"><span data-stu-id="24c58-136">This makes it possible for forms that inherit from **Form1** to modify the properties of **btnProtected**.</span></span>  
  
4.  <span data-ttu-id="24c58-137">Fare doppio clic su di **Say Hello** pulsante per aggiungere un gestore eventi per il **fare clic su** evento.</span><span class="sxs-lookup"><span data-stu-id="24c58-137">Double-click the **Say Hello** button to add an event handler for the **Click** event.</span></span>  
  
5.  <span data-ttu-id="24c58-138">Aggiungere la riga di codice seguente al gestore eventi:</span><span class="sxs-lookup"><span data-stu-id="24c58-138">Add the following line of code to the event handler:</span></span>  
  
    ```vb  
    MessageBox.Show("Hello, World!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Hello, World!");  
    ```  
  
#### <a name="to-add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a><span data-ttu-id="24c58-139">Per aggiungere un pulsante che non può essere modificato dagli eredi del form di base</span><span class="sxs-lookup"><span data-stu-id="24c58-139">To add a button that cannot be modified by inheritors of the base form</span></span>  
  
1.  <span data-ttu-id="24c58-140">Passare alla visualizzazione Progettazione fare clic su di **Form1. vb [Design], Form1. cs [Design] o Form1.jsl [Progettazione]** scheda sopra l'editor di codice o premendo F7.</span><span class="sxs-lookup"><span data-stu-id="24c58-140">Switch to design view by clicking the **Form1.vb [Design], Form1.cs [Design], or Form1.jsl [Design]** tab above the code editor, or by pressing F7.</span></span>  
  
2.  <span data-ttu-id="24c58-141">Aggiungere un secondo pulsante e impostarne le proprietà come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="24c58-141">Add a second button and set its properties as follows:</span></span>  
  
    -   <span data-ttu-id="24c58-142">Impostare il **testo** proprietà **Say Goodbye**.</span><span class="sxs-lookup"><span data-stu-id="24c58-142">Set the **Text** property to **Say Goodbye**.</span></span>  
  
    -   <span data-ttu-id="24c58-143">Impostare il **(nome)** proprietà **btnPrivate**.</span><span class="sxs-lookup"><span data-stu-id="24c58-143">Set the **(Name)** property to **btnPrivate**.</span></span>  
  
    -   <span data-ttu-id="24c58-144">Impostare il **modificatori** proprietà **privata**.</span><span class="sxs-lookup"><span data-stu-id="24c58-144">Set the **Modifiers** property to **Private**.</span></span> <span data-ttu-id="24c58-145">Questo rende impossibile form che ereditano da **Form1** per modificare le proprietà di **btnPrivate**.</span><span class="sxs-lookup"><span data-stu-id="24c58-145">This makes it impossible for forms that inherit from **Form1** to modify the properties of **btnPrivate**.</span></span>  
  
3.  <span data-ttu-id="24c58-146">Fare doppio clic su di **Say Goodbye** pulsante per aggiungere un gestore eventi per il **fare clic su** evento.</span><span class="sxs-lookup"><span data-stu-id="24c58-146">Double-click the **Say Goodbye** button to add an event handler for the **Click** event.</span></span> <span data-ttu-id="24c58-147">Inserire la riga di codice seguente nella routine evento:</span><span class="sxs-lookup"><span data-stu-id="24c58-147">Place the following line of code in the event procedure:</span></span>  
  
    ```vb  
    MessageBox.Show("Goodbye!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Goodbye!");  
    ```  
  
4.  <span data-ttu-id="24c58-148">Dal **compilare** menu, scegliere **BaseFormLibrary** per compilare la libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="24c58-148">From the **Build** menu, choose **Build BaseForm Library** to build the class library.</span></span>  
  
     <span data-ttu-id="24c58-149">Dopo aver compilato la libreria, è possibile creare un nuovo progetto che eredita dal form appena creato.</span><span class="sxs-lookup"><span data-stu-id="24c58-149">Once the library is built, you can create a new project that inherits from the form you just created.</span></span>  
  
#### <a name="to-create-a-project-containing-a-form-that-inherits-from-the-base-form"></a><span data-ttu-id="24c58-150">Per creare un progetto contenente un form che eredita dal form di base</span><span class="sxs-lookup"><span data-stu-id="24c58-150">To create a project containing a form that inherits from the base form</span></span>  
  
1.  <span data-ttu-id="24c58-151">Dal **File** menu, scegliere **Aggiungi** e quindi **nuovo progetto** per aprire la **Aggiungi nuovo progetto** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="24c58-151">From the **File** menu, choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="24c58-152">Creare un'applicazione Windows Form denominata `InheritanceTest`.</span><span class="sxs-lookup"><span data-stu-id="24c58-152">Create a Windows Forms application named `InheritanceTest`.</span></span>  
  
#### <a name="to-add-an-inherited-form"></a><span data-ttu-id="24c58-153">Per aggiungere un form ereditato</span><span class="sxs-lookup"><span data-stu-id="24c58-153">To add an inherited form</span></span>  
  
1.  <span data-ttu-id="24c58-154">In **Esplora**, fare doppio clic sul **InheritanceTest** progetto, selezionare **Aggiungi**, quindi selezionare**nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="24c58-154">In **Solution Explorer**, right-click the **InheritanceTest** project, select **Add**, and then select**New Item**.</span></span>  
  
2.  <span data-ttu-id="24c58-155">Nel **Aggiungi nuovo elemento** la finestra di dialogo, seleziona il **Windows Form** categoria (se si dispone di un elenco di categorie) e quindi selezionare il **Form ereditato** modello.</span><span class="sxs-lookup"><span data-stu-id="24c58-155">In the **Add New Item** dialog box, select the **Windows Forms** category (if you have a list of categories) and then select the **Inherited Form** template.</span></span>  
  
3.  <span data-ttu-id="24c58-156">Lasciare il nome predefinito di `Form2` e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="24c58-156">Leave the default name of `Form2` and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="24c58-157">Nel **Selezione ereditarietà** nella finestra di dialogo **Form1** dal **BaseFormLibrary** progetto come form da cui ereditare e fare clic su **OK** .</span><span class="sxs-lookup"><span data-stu-id="24c58-157">In the **Inheritance Picker** dialog box, select **Form1** from the **BaseFormLibrary** project as the form to inherit from and click **OK**.</span></span>  
  
     <span data-ttu-id="24c58-158">Verrà creato un form nel **InheritanceTest** progetto da cui deriva il form in **BaseFormLibrary**.</span><span class="sxs-lookup"><span data-stu-id="24c58-158">This creates a form in the **InheritanceTest** project that derives from the form in **BaseFormLibrary**.</span></span>  
  
5.  <span data-ttu-id="24c58-159">Aprire il form ereditato (**Form2**) nella finestra di progettazione facendo doppio clic su esso, se non è già aperto.</span><span class="sxs-lookup"><span data-stu-id="24c58-159">Open the inherited form (**Form2**) in the designer by double-clicking it, if it is not already open.</span></span>  
  
     <span data-ttu-id="24c58-160">Nella finestra di progettazione, i pulsanti ereditati dispongono di un simbolo (![Schermata VisualBasicInheritanceSymbol](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.gif "vbInheritanceGlyph")) nell'angolo superiore, che indica che vengono ereditate.</span><span class="sxs-lookup"><span data-stu-id="24c58-160">In the designer, the inherited buttons have a symbol (![VisualBasicInheritanceSymbol screenshot](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.gif "vbInheritanceGlyph")) in their upper corner, indicating they are inherited.</span></span>  
  
6.  <span data-ttu-id="24c58-161">Selezionare il **Say Hello** pulsante e osservare i quadratini di ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="24c58-161">Select the **Say Hello** button and observe the resize handles.</span></span> <span data-ttu-id="24c58-162">Poiché questo pulsante è protetto, gli eredi possono spostarlo, ridimensionarlo, modificarne la didascalia e apportare altre modifiche.</span><span class="sxs-lookup"><span data-stu-id="24c58-162">Because this button is protected, the inheritors can move it, resize it, change its caption, and make other modifications.</span></span>  
  
7.  <span data-ttu-id="24c58-163">Selezionare privato **Say Goodbye** pulsante e notare che non dispone di quadratini di ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="24c58-163">Select the private **Say Goodbye** button, and notice that it does not have resize handles.</span></span> <span data-ttu-id="24c58-164">Inoltre, nel **proprietà** finestra, le proprietà di questo pulsante vengono visualizzate in grigio per indicare che non possono essere modificate.</span><span class="sxs-lookup"><span data-stu-id="24c58-164">Additionally, in the **Properties** window, the properties of this button are grayed to indicate they cannot be modified.</span></span>  
  
8.  <span data-ttu-id="24c58-165">Se si utilizza Visual c#:</span><span class="sxs-lookup"><span data-stu-id="24c58-165">If you are using Visual C#:</span></span>  
  
    1.  <span data-ttu-id="24c58-166">In **Esplora**, fare doppio clic su **Form1** nel **InheritanceTest** del progetto e quindi scegliere **eliminare**.</span><span class="sxs-lookup"><span data-stu-id="24c58-166">In **Solution Explorer**, right-click **Form1** in the **InheritanceTest** project and then choose **Delete**.</span></span> <span data-ttu-id="24c58-167">Nella finestra di messaggio che viene visualizzato, fare clic su **OK** per confermare l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="24c58-167">In the message box that appears, click **OK** to confirm the deletion.</span></span>  
  
    2.  <span data-ttu-id="24c58-168">Aprire il file Program.cs e modificare la riga `Application.Run(new Form1());` in `Application.Run(new Form2());`.</span><span class="sxs-lookup"><span data-stu-id="24c58-168">Open the Program.cs file and change the line `Application.Run(new Form1());` to `Application.Run(new Form2());`.</span></span>  
  
9. <span data-ttu-id="24c58-169">In **Esplora**, fare doppio clic su di **InheritanceTest** del progetto e selezionare **imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="24c58-169">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Set As Startup Project**.</span></span>  
  
10. <span data-ttu-id="24c58-170">In **Esplora**, fare doppio clic su di **InheritanceTest** del progetto e selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="24c58-170">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Properties**.</span></span>  
  
11. <span data-ttu-id="24c58-171">Nel **InheritanceTest** pagine delle proprietà, impostare il **oggetto di avvio** per il form ereditato (**Form2**).</span><span class="sxs-lookup"><span data-stu-id="24c58-171">In the **InheritanceTest** property pages, set the **Startup object** to be the inherited form (**Form2**).</span></span>  
  
12. <span data-ttu-id="24c58-172">Premere F5 per eseguire l'applicazione e osservare il comportamento del form ereditato.</span><span class="sxs-lookup"><span data-stu-id="24c58-172">Press F5 to run the application, and observe the behavior of the inherited form.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="24c58-173">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="24c58-173">Next Steps</span></span>  
 <span data-ttu-id="24c58-174">L'ereditarietà per i controlli utente funziona in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="24c58-174">Inheritance for user controls works in much the same way.</span></span> <span data-ttu-id="24c58-175">Aprire un nuovo progetto di libreria di classi e aggiungere un controllo utente.</span><span class="sxs-lookup"><span data-stu-id="24c58-175">Open a new class library project and add a user control.</span></span> <span data-ttu-id="24c58-176">Inserire controlli costitutivi e compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="24c58-176">Place constituent controls on it and compile the project.</span></span> <span data-ttu-id="24c58-177">Aprire un altro progetto di libreria di classi e aggiungere un riferimento alla libreria di classi compilata.</span><span class="sxs-lookup"><span data-stu-id="24c58-177">Open another new class library project and add a reference to the compiled class library.</span></span> <span data-ttu-id="24c58-178">Inoltre, provare ad aggiungere un controllo ereditato (tramite il **aggiungere nuovi elementi** la finestra di dialogo) al progetto e l'utilizzo di **Selezione ereditarietà**.</span><span class="sxs-lookup"><span data-stu-id="24c58-178">Also, try adding an inherited control (through the **Add New Items** dialog box) to the project and using the **Inheritance Picker**.</span></span> <span data-ttu-id="24c58-179">Aggiungere un controllo utente e modificare il `Inherits` (`:` in Visual c#) istruzione.</span><span class="sxs-lookup"><span data-stu-id="24c58-179">Add a user control, and change the `Inherits` (`:` in Visual C#) statement.</span></span> <span data-ttu-id="24c58-180">Per ulteriori informazioni, vedere [procedura: ereditare Windows Form](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="24c58-180">For more information, see [How to: Inherit Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24c58-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24c58-181">See Also</span></span>  
 [<span data-ttu-id="24c58-182">Procedura: ereditare Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24c58-182">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [<span data-ttu-id="24c58-183">Ereditarietà visiva di Windows Form</span><span class="sxs-lookup"><span data-stu-id="24c58-183">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [<span data-ttu-id="24c58-184">Windows Form</span><span class="sxs-lookup"><span data-stu-id="24c58-184">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)
