---
title: 'Procedura dettagliata: Creazione di un controllo composito con Visual Basic'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Visual Basic]
- user controls [Visual Basic]
- UserControl class [Windows Forms], walkthroughs
- user controls [Windows Forms], creating with Visual Basic
- controls [Windows Forms], composite controls
- composite controls [Windows Forms], creating
- custom controls [Windows Forms], creating
ms.assetid: f50e270e-4db2-409a-8319-6db6ca5c7daf
ms.openlocfilehash: abfb91c61ef72bfc1626b4cc4dcea42b75e2ab35
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040248"
---
# <a name="walkthrough-authoring-a-composite-control-with-visual-basic"></a><span data-ttu-id="64b68-102">Procedura dettagliata: Creazione di un controllo composito con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="64b68-102">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>
<span data-ttu-id="64b68-103">I controlli compositi consentono di creare e riutilizzare interfacce grafiche personalizzate.</span><span class="sxs-lookup"><span data-stu-id="64b68-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="64b68-104">Un controllo composito è sostanzialmente un componente con rappresentazione visiva.</span><span class="sxs-lookup"><span data-stu-id="64b68-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="64b68-105">Può essere composto da uno o più controlli per Windows Forms, componenti o blocchi di codice in grado di estenderne le funzionalità convalidando l'input dell'utente, modificando le proprietà della visualizzazione o effettuando altre attività richieste dall'autore.</span><span class="sxs-lookup"><span data-stu-id="64b68-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="64b68-106">I controlli compositi possono essere inseriti in Windows Forms al pari degli altri controlli.</span><span class="sxs-lookup"><span data-stu-id="64b68-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="64b68-107">Nella prima parte di questa procedura verrà creato un controllo composito semplice denominato `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="64b68-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="64b68-108">Nella seconda parte, le funzionalità di `ctlClock` verranno estese mediante ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="64b68-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="64b68-109">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="64b68-109">Creating the Project</span></span>
 <span data-ttu-id="64b68-110">Quando si crea un nuovo progetto è necessario specificarne il nome per impostare lo spazio dei nomi radice, il nome dell'assembly e il nome del progetto e assicurarsi che il componente predefinito sia inserito nello spazio dei nomi corretto.</span><span class="sxs-lookup"><span data-stu-id="64b68-110">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="64b68-111">Per creare la libreria di controlli ctlClockLib e il controllo ctlClock</span><span class="sxs-lookup"><span data-stu-id="64b68-111">To create the ctlClockLib control library and the ctlClock control</span></span>

1. <span data-ttu-id="64b68-112">Scegliere **Nuovo** dal menu **File**, quindi selezionare **Progetto** per aprire la finestra di dialogo **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="64b68-112">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>

2. <span data-ttu-id="64b68-113">Nell'elenco dei progetti di Visual Basic selezionare il modello di progetto **libreria di controlli Windows** , `ctlClockLib` digitare nella casella **nome** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="64b68-113">From the list of Visual Basic projects, select the **Windows Control Library** project template, type `ctlClockLib` in the **Name** box, and then click **OK**.</span></span>

     <span data-ttu-id="64b68-114">Per impostazione predefinita il nome del progetto, `ctlClockLib`, verrà assegnato anche allo spazio dei nomi radice.</span><span class="sxs-lookup"><span data-stu-id="64b68-114">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="64b68-115">Lo spazio dei nomi radice viene utilizzato per qualificare i nomi dei componenti dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="64b68-115">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="64b68-116">Se ad esempio due assembly forniscono componenti denominati `ctlClock`, sarà possibile specificare il componente `ctlClock` usando`ctlClockLib.ctlClock.`</span><span class="sxs-lookup"><span data-stu-id="64b68-116">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>

3. <span data-ttu-id="64b68-117">In Esplora soluzioni fare clic con il pulsante destro del mouse su **UserControl1.vb**, quindi fare clic su **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="64b68-117">In Solution Explorer, right-click **UserControl1.vb**, and then click **Rename**.</span></span> <span data-ttu-id="64b68-118">Modificare il nome file in `ctlClock.vb`.</span><span class="sxs-lookup"><span data-stu-id="64b68-118">Change the file name to `ctlClock.vb`.</span></span> <span data-ttu-id="64b68-119">Scegliere il pulsante **Sì** quando richiesto per rinominare tutti i riferimenti all'elemento di codice "UserControl1".</span><span class="sxs-lookup"><span data-stu-id="64b68-119">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>

    > [!NOTE]
    >  <span data-ttu-id="64b68-120">Per impostazione predefinita, un controllo composito eredita <xref:System.Windows.Forms.UserControl> dalla classe fornita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="64b68-120">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="64b68-121">La <xref:System.Windows.Forms.UserControl> classe fornisce la funzionalità richiesta da tutti i controlli compositi e implementa i metodi e le proprietà standard.</span><span class="sxs-lookup"><span data-stu-id="64b68-121">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>

4. <span data-ttu-id="64b68-122">Scegliere **Salva tutto** dal menu **File** per salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="64b68-122">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="adding-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="64b68-123">Aggiunta di componenti e controlli Windows al controllo composito</span><span class="sxs-lookup"><span data-stu-id="64b68-123">Adding Windows Controls and Components to the Composite Control</span></span>
 <span data-ttu-id="64b68-124">L'interfaccia visiva è parte integrante del controllo composito</span><span class="sxs-lookup"><span data-stu-id="64b68-124">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="64b68-125">e viene implementata mediante l'aggiunta di uno o più controlli Windows nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="64b68-125">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="64b68-126">Nella procedura riportata di seguito i controlli Windows verranno incorporati nel controllo composito e verrà scritto il codice per l'implementazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="64b68-126">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>

### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="64b68-127">Per aggiungere al controllo composito un oggetto Label e un oggetto Timer</span><span class="sxs-lookup"><span data-stu-id="64b68-127">To add a Label and a Timer to your composite control</span></span>

1. <span data-ttu-id="64b68-128">In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlClock.vb**, quindi scegliere **Progettazione viste**.</span><span class="sxs-lookup"><span data-stu-id="64b68-128">In Solution Explorer, right-click **ctlClock.vb**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="64b68-129">Nella Casella degli strumenti espandere il nodo **Controlli comuni** e fare doppio clic su **Etichetta**.</span><span class="sxs-lookup"><span data-stu-id="64b68-129">In the Toolbox, expand the **Common Controls** node, and then double-click **Label**.</span></span>

     <span data-ttu-id="64b68-130">Un <xref:System.Windows.Forms.Label> controllo denominato `Label1` viene aggiunto al controllo nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="64b68-130">A <xref:System.Windows.Forms.Label> control named `Label1` is added to your control on the designer surface.</span></span>

3. <span data-ttu-id="64b68-131">Nella finestra di progettazione fare clic su **Label1**.</span><span class="sxs-lookup"><span data-stu-id="64b68-131">In the designer, click **Label1**.</span></span> <span data-ttu-id="64b68-132">Nella finestra Proprietà impostare le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="64b68-132">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="64b68-133">Proprietà</span><span class="sxs-lookup"><span data-stu-id="64b68-133">Property</span></span>|<span data-ttu-id="64b68-134">Modificare in</span><span class="sxs-lookup"><span data-stu-id="64b68-134">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="64b68-135">**Nome**</span><span class="sxs-lookup"><span data-stu-id="64b68-135">**Name**</span></span>|`lblDisplay`|
    |<span data-ttu-id="64b68-136">**Text**</span><span class="sxs-lookup"><span data-stu-id="64b68-136">**Text**</span></span>|`(blank space)`|
    |<span data-ttu-id="64b68-137">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="64b68-137">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="64b68-138">**Font.Size**</span><span class="sxs-lookup"><span data-stu-id="64b68-138">**Font.Size**</span></span>|`14`|

4. <span data-ttu-id="64b68-139">Nella **Casella degli strumenti** espandere il nodo **Componenti**, quindi fare doppio clic su **Timer**.</span><span class="sxs-lookup"><span data-stu-id="64b68-139">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>

     <span data-ttu-id="64b68-140">Poiché un <xref:System.Windows.Forms.Timer> è un componente, non ha alcuna rappresentazione visiva in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="64b68-140">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="64b68-141">non verrà visualizzato insieme ai controlli nell'area di progettazione bensì in Progettazione componenti, una barra delle applicazioni disposta nella parte inferiore dell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="64b68-141">Therefore, it does not appear with the controls on the designer surface, but rather in the Component Designer (a tray at the bottom of the designer surface).</span></span>

5. <span data-ttu-id="64b68-142">In Progettazione componenti fare clic su **Timer1**, quindi impostare la <xref:System.Windows.Forms.Timer.Interval%2A> proprietà su `1000` e la <xref:System.Windows.Forms.Timer.Enabled%2A> proprietà su `True`.</span><span class="sxs-lookup"><span data-stu-id="64b68-142">In the Component Designer, click **Timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `True`.</span></span>

     <span data-ttu-id="64b68-143">La <xref:System.Windows.Forms.Timer.Interval%2A> proprietà controlla la frequenza con cui viene selezionato il componente del timer.</span><span class="sxs-lookup"><span data-stu-id="64b68-143">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the timer component ticks.</span></span> <span data-ttu-id="64b68-144">Ogni volta che `Timer1` scatta, viene eseguito il codice nell'evento `Timer1_Tick`.</span><span class="sxs-lookup"><span data-stu-id="64b68-144">Each time `Timer1` ticks, it runs the code in the `Timer1_Tick` event.</span></span> <span data-ttu-id="64b68-145">L'intervallo rappresenta i millesimi di secondo che intercorrono tra uno scatto e l'altro.</span><span class="sxs-lookup"><span data-stu-id="64b68-145">The interval represents the number of milliseconds between ticks.</span></span>

6. <span data-ttu-id="64b68-146">In Progettazione componenti fare doppio clic su **Timer1** per passare all'evento `Timer1_Tick` di `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="64b68-146">In the Component Designer, double-click **Timer1** to go to the `Timer1_Tick` event for `ctlClock`.</span></span>

7. <span data-ttu-id="64b68-147">Modificare il codice in modo che risulti simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="64b68-147">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="64b68-148">Assicurarsi di cambiare il modificatore di accesso da `Private` a `Protected`.</span><span class="sxs-lookup"><span data-stu-id="64b68-148">Be sure to change the access modifier from `Private` to `Protected`.</span></span>

    ```vb
    Protected Sub Timer1_Tick(ByVal sender As Object, ByVal e As _
        System.EventArgs) Handles Timer1.Tick
        ' Causes the label to display the current time.
        lblDisplay.Text = Format(Now, "hh:mm:ss")
    End Sub
    ```

     <span data-ttu-id="64b68-149">Questo codice determinerà la visualizzazione dell'ora corrente in `lblDisplay`.</span><span class="sxs-lookup"><span data-stu-id="64b68-149">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="64b68-150">Poiché l'intervallo di `Timer1` è stato impostato su `1000`, l'evento verrà generato ogni mille millesimi di secondo, aggiornando quindi l'ora corrente ogni secondo.</span><span class="sxs-lookup"><span data-stu-id="64b68-150">Because the interval of `Timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>

8. <span data-ttu-id="64b68-151">Modificare il metodo in modo che sia sottoponibile a override.</span><span class="sxs-lookup"><span data-stu-id="64b68-151">Modify the method to be overridable.</span></span> <span data-ttu-id="64b68-152">Per ulteriori informazioni, vedere la sezione "Eredità da un controllo utente" riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="64b68-152">For more information, see the "Inheriting from a User Control" section below.</span></span>

    ```vb
    Protected Overridable Sub Timer1_Tick(ByVal sender As Object, ByVal _
        e As System.EventArgs) Handles Timer1.Tick
    ```

9. <span data-ttu-id="64b68-153">Scegliere **Salva tutto** dal menu **File** per salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="64b68-153">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="adding-properties-to-the-composite-control"></a><span data-ttu-id="64b68-154">Aggiunta di proprietà al controllo composito</span><span class="sxs-lookup"><span data-stu-id="64b68-154">Adding Properties to the Composite Control</span></span>
 <span data-ttu-id="64b68-155">Il controllo Clock incapsula ora un <xref:System.Windows.Forms.Label> controllo e un <xref:System.Windows.Forms.Timer> componente, ognuno con un proprio set di proprietà intrinseche.</span><span class="sxs-lookup"><span data-stu-id="64b68-155">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="64b68-156">Benché le singole proprietà di questi controlli non siano accessibili ai futuri utenti del controllo, è possibile creare ed esporre proprietà personalizzate scrivendo i blocchi di codice appropriati.</span><span class="sxs-lookup"><span data-stu-id="64b68-156">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="64b68-157">Nella procedura riportata di seguito verrà illustrato come aggiungere al controllo proprietà che consentono all'utente di modificare il colore dello sfondo e del testo.</span><span class="sxs-lookup"><span data-stu-id="64b68-157">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>

### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="64b68-158">Per aggiungere una proprietà al controllo composito</span><span class="sxs-lookup"><span data-stu-id="64b68-158">To add a property to your composite control</span></span>

1. <span data-ttu-id="64b68-159">In Esplora soluzioni fare clic con il pulsante destro del mouse su c**tlClock.vb**, quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="64b68-159">In Solution Explorer, right-click **ctlClock.vb**, and then click **View Code**.</span></span>

     <span data-ttu-id="64b68-160">Verrà visualizzato l'editor del codice per il controllo.</span><span class="sxs-lookup"><span data-stu-id="64b68-160">The Code Editor for your control opens.</span></span>

2. <span data-ttu-id="64b68-161">Individuare l'istruzione `Public Class ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="64b68-161">Locate the `Public Class ctlClock` statement.</span></span> <span data-ttu-id="64b68-162">Sotto tale riga, aggiungere il seguente codice.</span><span class="sxs-lookup"><span data-stu-id="64b68-162">Beneath it, type the following code.</span></span>

    ```vb
    Private colFColor as Color
    Private colBColor as Color
    ```

     <span data-ttu-id="64b68-163">Queste istruzioni consentono di creare le variabili private da utilizzare per la memorizzazione dei valori delle proprietà che verranno create.</span><span class="sxs-lookup"><span data-stu-id="64b68-163">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>

3. <span data-ttu-id="64b68-164">Sotto le dichiarazioni delle variabili del passaggio 2 inserire il seguente codice.</span><span class="sxs-lookup"><span data-stu-id="64b68-164">Insert the following code beneath the variable declarations from step 2.</span></span>

    ```vb
    ' Declares the name and type of the property.
    Property ClockBackColor() as Color
        ' Retrieves the value of the private variable colBColor.
        Get
            Return colBColor
        End Get
        ' Stores the selected value in the private variable colBColor, and
        ' updates the background color of the label control lblDisplay.
        Set(ByVal value as Color)
            colBColor = value
            lblDisplay.BackColor = colBColor
        End Set

    End Property
    ' Provides a similar set of instructions for the foreground color.
    Property ClockForeColor() as Color
        Get
            Return colFColor
        End Get
        Set(ByVal value as Color)
            colFColor = value
            lblDisplay.ForeColor = colFColor
        End Set
    End Property
    ```

     <span data-ttu-id="64b68-165">Nel codice riportato in precedenza vengono create due proprietà personalizzate, `ClockForeColor` e `ClockBackColor`, disponibili agli utenti successivi del controllo mediante l'utilizzo dell'istruzione `Property`.</span><span class="sxs-lookup"><span data-stu-id="64b68-165">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control by invoking the `Property` statement.</span></span> <span data-ttu-id="64b68-166">Le istruzioni `Get` e `Set` consentono di archiviare e recuperare il valore della proprietà e di inserire il codice per implementare le funzionalità appropriate per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="64b68-166">The `Get` and `Set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>

4. <span data-ttu-id="64b68-167">Scegliere **Salva tutto** dal menu **File** per salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="64b68-167">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="testing-the-control"></a><span data-ttu-id="64b68-168">Test del controllo</span><span class="sxs-lookup"><span data-stu-id="64b68-168">Testing the Control</span></span>
 <span data-ttu-id="64b68-169">I controlli non sono progetti autonomi e devono pertanto essere inseriti in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="64b68-169">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="64b68-170">Eseguire il test del comportamento del controllo in fase di esecuzione e sperimentare le proprietà con **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="64b68-170">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="64b68-171">Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di un](how-to-test-the-run-time-behavior-of-a-usercontrol.md)UserControl.</span><span class="sxs-lookup"><span data-stu-id="64b68-171">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

### <a name="to-test-your-control"></a><span data-ttu-id="64b68-172">Per eseguire il test del controllo</span><span class="sxs-lookup"><span data-stu-id="64b68-172">To test your control</span></span>

1. <span data-ttu-id="64b68-173">Per compilare il progetto ed eseguire il controllo in **UserControl Test Container**, premere F5.</span><span class="sxs-lookup"><span data-stu-id="64b68-173">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="64b68-174">Nella griglia della proprietà di Test Container, selezionare la proprietà `ClockBackColor`, quindi fare clic sulla freccia a discesa per visualizzare la tavolozza dei colori.</span><span class="sxs-lookup"><span data-stu-id="64b68-174">In the test container's property grid, select the `ClockBackColor` property, and then click the drop-down arrow to display the color palette.</span></span>

3. <span data-ttu-id="64b68-175">Scegliere un colore facendovi clic sopra.</span><span class="sxs-lookup"><span data-stu-id="64b68-175">Choose a color by clicking it.</span></span>

     <span data-ttu-id="64b68-176">Il colore di sfondo del controllo cambierà in base al colore selezionato.</span><span class="sxs-lookup"><span data-stu-id="64b68-176">The background color of your control changes to the color you selected.</span></span>

4. <span data-ttu-id="64b68-177">Usare una sequenza di eventi simile per verificare il corretto funzionamento della proprietà `ClockForeColor`.</span><span class="sxs-lookup"><span data-stu-id="64b68-177">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>

5. <span data-ttu-id="64b68-178">Per chiudere la finestra **UserControl Test Container**, scegliere **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="64b68-178">Click **Close** to close the **UserControl Test Container**.</span></span>

     <span data-ttu-id="64b68-179">In questa sezione e in quelle precedenti è stato illustrato come combinare componenti e controlli Windows con codici e package per aggiungere funzionalità personalizzate al modulo di un controllo composito.</span><span class="sxs-lookup"><span data-stu-id="64b68-179">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="64b68-180">Si è inoltre appreso come esporre le proprietà del controllo composito e come eseguire il test del controllo dopo averlo completato.</span><span class="sxs-lookup"><span data-stu-id="64b68-180">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="64b68-181">Nella sezione successiva verranno fornite informazioni sulla modalità di creazione di un controllo composito ereditato utilizzando `ctlClock` come base.</span><span class="sxs-lookup"><span data-stu-id="64b68-181">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>

## <a name="inheriting-from-a-composite-control"></a><span data-ttu-id="64b68-182">Eredità da un controllo composito</span><span class="sxs-lookup"><span data-stu-id="64b68-182">Inheriting from a Composite Control</span></span>
 <span data-ttu-id="64b68-183">Nelle sezioni precedenti si è appreso come combinare controlli, componenti e codice Windows in controlli compositi riutilizzabili.</span><span class="sxs-lookup"><span data-stu-id="64b68-183">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="64b68-184">Il controllo composito può ora essere usato come base per la compilazione di altri controlli.</span><span class="sxs-lookup"><span data-stu-id="64b68-184">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="64b68-185">Il processo di derivazione di una classe da una classe di base è detto *ereditarietà*.</span><span class="sxs-lookup"><span data-stu-id="64b68-185">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="64b68-186">In questa sezione verrà creato un controllo composito denominato `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="64b68-186">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="64b68-187">Il controllo verrà derivato dal relativo controllo padre, in questo caso `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="64b68-187">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="64b68-188">Verrà spiegato come estendere le funzionalità di `ctlClock` mediante l'override dei metodi padre e l'aggiunta di nuovi metodi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="64b68-188">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>

 <span data-ttu-id="64b68-189">Per creare un controllo ereditato, è innanzitutto necessario derivare il controllo dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="64b68-189">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="64b68-190">Questa operazione consente di creare un nuovo controllo, con le stesse proprietà, metodi e caratteristiche grafiche del controllo padre, che può essere anche utilizzato come base per l'aggiunta di una funzionalità nuova o modificata.</span><span class="sxs-lookup"><span data-stu-id="64b68-190">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>

### <a name="to-create-the-inherited-control"></a><span data-ttu-id="64b68-191">Per creare il controllo ereditato</span><span class="sxs-lookup"><span data-stu-id="64b68-191">To create the inherited control</span></span>

1. <span data-ttu-id="64b68-192">In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlClockLib**, scegliere **Aggiungi**, quindi **Controllo utente**.</span><span class="sxs-lookup"><span data-stu-id="64b68-192">In Solution Explorer, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>

     <span data-ttu-id="64b68-193">Viene aperta la finestra di dialogo **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="64b68-193">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="64b68-194">Selezionare il modello **Controllo utente ereditato**.</span><span class="sxs-lookup"><span data-stu-id="64b68-194">Select the **Inherited User Control** template.</span></span>

3. <span data-ttu-id="64b68-195">Nella casella **Nome** digitare `ctlAlarmClock.vb` e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="64b68-195">In the **Name** box, type `ctlAlarmClock.vb`, and then click **Add**.</span></span>

     <span data-ttu-id="64b68-196">Viene visualizzata la finestra di dialogo **Selezione ereditarietà**.</span><span class="sxs-lookup"><span data-stu-id="64b68-196">The **Inheritance Picker** dialog box appears.</span></span>

4. <span data-ttu-id="64b68-197">In **Nome componente** fare doppio clic su **ctlClock**.</span><span class="sxs-lookup"><span data-stu-id="64b68-197">Under **Component Name**, double-click **ctlClock**.</span></span>

5. <span data-ttu-id="64b68-198">In Esplora soluzioni scorrere i progetti correnti.</span><span class="sxs-lookup"><span data-stu-id="64b68-198">In Solution Explorer, browse through the current projects.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="64b68-199">Nel progetto corrente è stato aggiunto il file denominato **ctlAlarmClock.vb**.</span><span class="sxs-lookup"><span data-stu-id="64b68-199">A file called **ctlAlarmClock.vb** has been added to the current project.</span></span>

### <a name="adding-the-alarm-properties"></a><span data-ttu-id="64b68-200">Aggiunta delle proprietà per l'allarme</span><span class="sxs-lookup"><span data-stu-id="64b68-200">Adding the Alarm Properties</span></span>
 <span data-ttu-id="64b68-201">Le modalità di aggiunta delle proprietà a un controllo ereditato sono analoghe a quelle utilizzate per i controlli compositi.</span><span class="sxs-lookup"><span data-stu-id="64b68-201">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="64b68-202">Mediante la sintassi di dichiarazione delle proprietà si aggiungeranno ora al controllo due proprietà: `AlarmTime`, in cui viene memorizzato il valore della data e dell'ora in cui l'allarme deve essere disattivato, e `AlarmSet`, che indica se l'allarme è impostato o meno.</span><span class="sxs-lookup"><span data-stu-id="64b68-202">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>

#### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="64b68-203">Per aggiungere proprietà al controllo composito</span><span class="sxs-lookup"><span data-stu-id="64b68-203">To add properties to your composite control</span></span>

1. <span data-ttu-id="64b68-204">In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlAlarmClock**, quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="64b68-204">In Solution Explorer, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>

2. <span data-ttu-id="64b68-205">Individuare la dichiarazione di classe per il controllo ctlAlarmClock, visualizzato come `Public Class ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="64b68-205">Locate the class declaration for the ctlAlarmClock control, which appears as `Public Class ctlAlarmClock`.</span></span>  <span data-ttu-id="64b68-206">Inserire il codice seguente nella dichiarazione di classe.</span><span class="sxs-lookup"><span data-stu-id="64b68-206">In the class declaration, insert the following code.</span></span>

    ```vb
    Private dteAlarmTime As Date
    Private blnAlarmSet As Boolean
    ' These properties will be declared as Public to allow future
    ' developers to access them.
    Public Property AlarmTime() As Date
        Get
            Return dteAlarmTime
        End Get
        Set(ByVal value as Date)
            dteAlarmTime = value
        End Set
    End Property
    Public Property AlarmSet() As Boolean
        Get
            Return blnAlarmSet
        End Get
        Set(ByVal value as Boolean)
            blnAlarmSet = value
        End Set
    End Property
    ```

### <a name="adding-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="64b68-207">Aggiunta del controllo all'interfaccia grafica</span><span class="sxs-lookup"><span data-stu-id="64b68-207">Adding to the Graphical Interface of the Control</span></span>
 <span data-ttu-id="64b68-208">Il controllo ereditato presenta un'interfaccia grafica identica a quella del controllo dal quale eredita</span><span class="sxs-lookup"><span data-stu-id="64b68-208">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="64b68-209">e possiede gli stessi controlli costitutivi del controllo padre, ma le proprietà dei controlli costitutivi non sono disponibili, a meno che non siano state specificamente esposte.</span><span class="sxs-lookup"><span data-stu-id="64b68-209">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="64b68-210">Analogamente a qualsiasi altro controllo composito, è possibile aggiungere elementi all'interfaccia grafica di un controllo composito ereditato, utilizzando la medesima procedura.</span><span class="sxs-lookup"><span data-stu-id="64b68-210">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="64b68-211">In questo esempio verrà utilizzato un controllo label per aggiungere un effetto intermittente all'interfaccia grafica del controllo quando l'allarme suona.</span><span class="sxs-lookup"><span data-stu-id="64b68-211">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>

#### <a name="to-add-the-label-control"></a><span data-ttu-id="64b68-212">Per aggiungere il controllo label</span><span class="sxs-lookup"><span data-stu-id="64b68-212">To add the label control</span></span>

1. <span data-ttu-id="64b68-213">In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlAlarmClock** e scegliere **Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="64b68-213">In Solution Explorer, right-click **ctlAlarmClock**, and click **View Designer**.</span></span>

     <span data-ttu-id="64b68-214">Nella finestra principale viene aperta la finestra di progettazione per `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="64b68-214">The designer for `ctlAlarmClock` opens in the main window.</span></span>

2. <span data-ttu-id="64b68-215">Fare clic su `lblDisplay` (parte visualizzata del controllo) e osservare la finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="64b68-215">Click `lblDisplay` (the display portion of the control), and view the Properties window.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="64b68-216">Tutte le proprietà sono presenti ma inattive, ossia visualizzate in grigio.</span><span class="sxs-lookup"><span data-stu-id="64b68-216">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="64b68-217">Ciò indica che le proprietà sono native di `lblDisplay` e non è possibile accedervi né modificarle nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="64b68-217">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="64b68-218">Per impostazione predefinita i controlli contenuti in un controllo composito sono `Private` e le relative proprietà non sono accessibili.</span><span class="sxs-lookup"><span data-stu-id="64b68-218">By default, controls contained in a composite control are `Private`, and their properties are not accessible by any means.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="64b68-219">Se si desidera che gli utenti successivi del controllo composito abbiano accesso ai relativi controlli interni, dichiararli come `Public` o `Protected`.</span><span class="sxs-lookup"><span data-stu-id="64b68-219">If you want subsequent users of your composite control to have access to its internal controls, declare them as `Public` or `Protected`.</span></span> <span data-ttu-id="64b68-220">Sarà così possibile impostare e modificare le proprietà dei controlli contenuti nel controllo composito mediante il codice appropriato.</span><span class="sxs-lookup"><span data-stu-id="64b68-220">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>

3. <span data-ttu-id="64b68-221">Aggiungere un <xref:System.Windows.Forms.Label> controllo al controllo composito.</span><span class="sxs-lookup"><span data-stu-id="64b68-221">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>

4. <span data-ttu-id="64b68-222">Usando il mouse, trascinare il <xref:System.Windows.Forms.Label> controllo immediatamente sotto la casella di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="64b68-222">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="64b68-223">Nella finestra Proprietà impostare le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="64b68-223">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="64b68-224">Proprietà</span><span class="sxs-lookup"><span data-stu-id="64b68-224">Property</span></span>|<span data-ttu-id="64b68-225">Impostazione</span><span class="sxs-lookup"><span data-stu-id="64b68-225">Setting</span></span>|
    |--------------|-------------|
    |<span data-ttu-id="64b68-226">**Nome**</span><span class="sxs-lookup"><span data-stu-id="64b68-226">**Name**</span></span>|`lblAlarm`|
    |<span data-ttu-id="64b68-227">**Text**</span><span class="sxs-lookup"><span data-stu-id="64b68-227">**Text**</span></span>|<span data-ttu-id="64b68-228">**Allarme!**</span><span class="sxs-lookup"><span data-stu-id="64b68-228">**Alarm!**</span></span>|
    |<span data-ttu-id="64b68-229">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="64b68-229">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="64b68-230">**Visible**</span><span class="sxs-lookup"><span data-stu-id="64b68-230">**Visible**</span></span>|`False`|

### <a name="adding-the-alarm-functionality"></a><span data-ttu-id="64b68-231">Aggiunta della funzionalità di allarme</span><span class="sxs-lookup"><span data-stu-id="64b68-231">Adding the Alarm Functionality</span></span>
 <span data-ttu-id="64b68-232">Nelle procedure precedenti sono state aggiunte proprietà e un controllo in grado di abilitare la funzionalità di allarme nel controllo composito.</span><span class="sxs-lookup"><span data-stu-id="64b68-232">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="64b68-233">In questa procedura verrà aggiunto un codice che consente di confrontare l'ora corrente con l'ora dell'allarme e, se le ore risultano identiche, attivare un allarme sonoro e lampeggiante.</span><span class="sxs-lookup"><span data-stu-id="64b68-233">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to sound and flash an alarm.</span></span> <span data-ttu-id="64b68-234">Eseguendo l'override del metodo `Timer1_Tick` di `ctlClock` e aggiungendovi ulteriore codice sarà possibile estendere le capacità di `ctlAlarmClock` e conservare allo stesso le funzionalità intrinseche di `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="64b68-234">By overriding the `Timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>

#### <a name="to-override-the-timer1_tick-method-of-ctlclock"></a><span data-ttu-id="64b68-235">Per eseguire l'override del metodo Timer1_Tick di ctlClock</span><span class="sxs-lookup"><span data-stu-id="64b68-235">To override the Timer1_Tick method of ctlClock</span></span>

1. <span data-ttu-id="64b68-236">In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlAlarmClock.vb**, quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="64b68-236">In Solution Explorer, right-click **ctlAlarmClock.vb**, and then click **View Code**.</span></span>

2. <span data-ttu-id="64b68-237">Individuare l'istruzione `Private blnAlarmSet As Boolean`.</span><span class="sxs-lookup"><span data-stu-id="64b68-237">Locate the `Private blnAlarmSet As Boolean` statement.</span></span> <span data-ttu-id="64b68-238">e aggiungere subito dopo la seguente istruzione.</span><span class="sxs-lookup"><span data-stu-id="64b68-238">Immediately beneath it, add the following statement.</span></span>

    ```vb
    Dim blnColorTicker as Boolean
    ```

3. <span data-ttu-id="64b68-239">Individuare l'istruzione `End Class` nella parte inferiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="64b68-239">Locate the `End Class` statement at the bottom of the page.</span></span> <span data-ttu-id="64b68-240">Prima dell'istruzione `End Class` aggiungere il seguente codice.</span><span class="sxs-lookup"><span data-stu-id="64b68-240">Just before the `End Class` statement, add the following code.</span></span>

    ```vb
    Protected Overrides Sub Timer1_Tick(ByVal sender As Object, ByVal e _
        As System.EventArgs)
        ' Calls the Timer1_Tick method of ctlClock.
        MyBase.Timer1_Tick(sender, e)
        ' Checks to see if the Alarm is set.
        If AlarmSet = False Then
            Exit Sub
        End If
        ' If the date, hour, and minute of the alarm time are the same as
        ' now, flash and beep an alarm.
        If AlarmTime.Date = Now.Date And AlarmTime.Hour = Now.Hour And _
            AlarmTime.Minute = Now.Minute Then
            ' Sounds an audible beep.
            Beep()
            ' Sets lblAlarmVisible to True, and changes the background color based on the
            ' value of blnColorTicker. The background color of the label will
            ' flash once per tick of the clock.
            lblAlarm.Visible = True
            If blnColorTicker = False Then
                lblAlarm.BackColor = Color.PeachPuff
                blnColorTicker = True
            Else
                lblAlarm.BackColor = Color.Plum
                blnColorTicker = False
            End If
        Else
            ' Once the alarm has sounded for a minute, the label is made
            ' invisible again.
            lblAlarm.Visible = False
        End If
    End Sub
    ```

     <span data-ttu-id="64b68-241">Il codice appena aggiunto ha diverse funzioni.</span><span class="sxs-lookup"><span data-stu-id="64b68-241">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="64b68-242">Se si utilizza l'istruzione `Overrides`, il controllo utilizzerà questo metodo anziché il metodo ereditato dal controllo di base.</span><span class="sxs-lookup"><span data-stu-id="64b68-242">The `Overrides` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="64b68-243">Una volta chiamato, questo metodo chiamerà il metodo di cui esegue l'override utilizzando l'istruzione `MyBase.Timer1_Tick` e assicurando che tutte le funzionalità incorporate nel controllo originale vengano riprodotte in questo controllo.</span><span class="sxs-lookup"><span data-stu-id="64b68-243">When this method is called, it calls the method it overrides by invoking the `MyBase.Timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="64b68-244">Verrà quindi eseguito il codice aggiuntivo per incorporare la funzionalità di allarme.</span><span class="sxs-lookup"><span data-stu-id="64b68-244">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="64b68-245">Quando l'allarme viene attivato, viene visualizzato un controllo etichetta lampeggiante e viene emesso un segnale acustico.</span><span class="sxs-lookup"><span data-stu-id="64b68-245">A flashing label control will appear when the alarm occurs, and an audible beep will be heard.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="64b68-246">Poiché si esegue l'override di un gestore eventi ereditato, non è necessario specificare l'evento tramite la parola chiave `Handles`.</span><span class="sxs-lookup"><span data-stu-id="64b68-246">Because you are overriding an inherited event handler, you do not have to specify the event with the `Handles` keyword.</span></span> <span data-ttu-id="64b68-247">L'evento risulta già associato.</span><span class="sxs-lookup"><span data-stu-id="64b68-247">The event is already hooked up.</span></span> <span data-ttu-id="64b68-248">L'override riguarda l'implementazione del gestore.</span><span class="sxs-lookup"><span data-stu-id="64b68-248">All you are overriding is the implementation of the handler.</span></span>

     <span data-ttu-id="64b68-249">Il controllo dell'allarme è quasi completo.</span><span class="sxs-lookup"><span data-stu-id="64b68-249">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="64b68-250">L'unica operazione rimasta è l'implementazione di un sistema di disattivazione.</span><span class="sxs-lookup"><span data-stu-id="64b68-250">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="64b68-251">A tal fine, è necessario aggiungere codice al metodo `lblAlarm_Click`.</span><span class="sxs-lookup"><span data-stu-id="64b68-251">To do this, you will add code to the `lblAlarm_Click` method.</span></span>

#### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="64b68-252">Per implementare il metodo di disattivazione</span><span class="sxs-lookup"><span data-stu-id="64b68-252">To implement the shutoff method</span></span>

1. <span data-ttu-id="64b68-253">In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlAlarmClock.vb**, quindi scegliere **Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="64b68-253">In Solution Explorer, right-click **ctlAlarmClock.vb**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="64b68-254">Nella finestra di progettazione fare doppio clic sul controllo **lblAlarm**.</span><span class="sxs-lookup"><span data-stu-id="64b68-254">In the designer, double-click **lblAlarm**.</span></span> <span data-ttu-id="64b68-255">Nell'**editor di codice** verrà visualizzata la riga `Private Sub lblAlarm_Click`.</span><span class="sxs-lookup"><span data-stu-id="64b68-255">The **Code Editor** opens to the `Private Sub lblAlarm_Click` line.</span></span>

3. <span data-ttu-id="64b68-256">Modificare il metodo in modo che risulti simile al seguente codice.</span><span class="sxs-lookup"><span data-stu-id="64b68-256">Modify this method so that it resembles the following code.</span></span>

    ```vb
    Private Sub lblAlarm_Click(ByVal sender As Object, ByVal e As _
     System.EventArgs) Handles lblAlarm.Click
        ' Turns off the alarm.
        AlarmSet = False
        ' Hides the flashing label.
        lblAlarm.Visible = False
    End Sub
    ```

4. <span data-ttu-id="64b68-257">Scegliere **Salva tutto** dal menu **File** per salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="64b68-257">On the **File** menu, click **Save All** to save the project.</span></span>

### <a name="using-the-inherited-control-on-a-form"></a><span data-ttu-id="64b68-258">Utilizzo del controllo ereditato in un modulo</span><span class="sxs-lookup"><span data-stu-id="64b68-258">Using the Inherited Control on a Form</span></span>
 <span data-ttu-id="64b68-259">È possibile testare il controllo ereditato nello stesso modo in cui è stato testato il controllo `ctlClock`della classe base: Per compilare il progetto ed eseguire il controllo in **UserControl Test Container**, premere F5.</span><span class="sxs-lookup"><span data-stu-id="64b68-259">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="64b68-260">Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di un](how-to-test-the-run-time-behavior-of-a-usercontrol.md)UserControl.</span><span class="sxs-lookup"><span data-stu-id="64b68-260">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

 <span data-ttu-id="64b68-261">Per utilizzare il controllo è necessario inserirlo in un modulo.</span><span class="sxs-lookup"><span data-stu-id="64b68-261">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="64b68-262">Come i controlli compositi standard, i controlli compositi ereditati non possono essere autonomi e devono essere inclusi in un modulo o in un altro contenitore.</span><span class="sxs-lookup"><span data-stu-id="64b68-262">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="64b68-263">Poiché `ctlAlarmClock` include un maggior numero di funzionalità, per eseguire il test è necessario aggiungere del codice.</span><span class="sxs-lookup"><span data-stu-id="64b68-263">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="64b68-264">In questa procedura verrà scritto un semplice programma per la verifica delle funzionalità di `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="64b68-264">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="64b68-265">Verrà inoltre scritto il codice per impostare e visualizzare la proprietà `AlarmTime` di `ctlAlarmClock` e verrà eseguito il test delle funzionalità intrinseche del controllo.</span><span class="sxs-lookup"><span data-stu-id="64b68-265">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>

#### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="64b68-266">Per compilare e aggiungere il controllo a un modulo di test</span><span class="sxs-lookup"><span data-stu-id="64b68-266">To build and add your control to a test form</span></span>

1. <span data-ttu-id="64b68-267">In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlClockLib**, quindi scegliere **Compila**.</span><span class="sxs-lookup"><span data-stu-id="64b68-267">In Solution Explorer, right-click **ctlClockLib**, and then click **Build**.</span></span>

2. <span data-ttu-id="64b68-268">Scegliere **Aggiungi** dal menu **File**e quindi fare clic su **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="64b68-268">On the **File** menu, point to **Add**, and then click **New Project**.</span></span>

3. <span data-ttu-id="64b68-269">Aggiungere un nuovo progetto **Applicazione Windows** alla soluzione e denominarlo `Test`.</span><span class="sxs-lookup"><span data-stu-id="64b68-269">Add a new **Windows Application** project to the solution, and name it `Test`.</span></span>

     <span data-ttu-id="64b68-270">Il progetto **Test** verrà aggiunto a Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="64b68-270">The **Test** project is added to Solution Explorer.</span></span>

4. <span data-ttu-id="64b68-271">In Esplora soluzioni fare clic con il pulsante destro del mouse sul nodo di progetto `Test`, quindi scegliere **Aggiungi riferimento** per visualizzare la finestra di dialogo **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="64b68-271">In Solution Explorer, right-click the `Test` project node, and then click **Add Reference** to display the **Add Reference** dialog box.</span></span>

5. <span data-ttu-id="64b68-272">Scegliere la scheda **Progetti**.</span><span class="sxs-lookup"><span data-stu-id="64b68-272">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="64b68-273">Il progetto **ctlClockLib** verrà elencato in **Nome progetto**.</span><span class="sxs-lookup"><span data-stu-id="64b68-273">The project **ctlClockLib** will be listed under **Project Name**.</span></span> <span data-ttu-id="64b68-274">Fare doppio clic su **ctlClockLib** per aggiungere il riferimento al progetto di test.</span><span class="sxs-lookup"><span data-stu-id="64b68-274">Double-click **ctlClockLib** to add the reference to the test project.</span></span>

6. <span data-ttu-id="64b68-275">In Esplora soluzioni fare clic con il pulsante destro del mouse su **Test**, quindi scegliere **Compila**.</span><span class="sxs-lookup"><span data-stu-id="64b68-275">In Solution Explorer, right-click **Test**, and then click **Build**.</span></span>

7. <span data-ttu-id="64b68-276">Nella **Casella degli strumenti** espandere il nodo **Componenti ctlClockLib**.</span><span class="sxs-lookup"><span data-stu-id="64b68-276">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>

8. <span data-ttu-id="64b68-277">Fare doppio clic su **ctlAlarmClock** per aggiungere un'istanza di `ctlAlarmClock` al modulo.</span><span class="sxs-lookup"><span data-stu-id="64b68-277">Double-click **ctlAlarmClock** to add an instance of `ctlAlarmClock` to your form.</span></span>

9. <span data-ttu-id="64b68-278">Nella **casella degli strumenti**individuare e fare doppio clic su **DateTimePicker** per aggiungere <xref:System.Windows.Forms.DateTimePicker> un controllo al form, quindi aggiungere un <xref:System.Windows.Forms.Label> controllo facendo doppio clic su **etichetta**.</span><span class="sxs-lookup"><span data-stu-id="64b68-278">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>

10. <span data-ttu-id="64b68-279">Posizionare mediante il mouse i controlli in un punto del modulo di facile accesso.</span><span class="sxs-lookup"><span data-stu-id="64b68-279">Use the mouse to position the controls in a convenient place on the form.</span></span>

11. <span data-ttu-id="64b68-280">Impostare le proprietà dei controlli come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="64b68-280">Set the properties of these controls in the following manner.</span></span>

    |<span data-ttu-id="64b68-281">Control</span><span class="sxs-lookup"><span data-stu-id="64b68-281">Control</span></span>|<span data-ttu-id="64b68-282">Proprietà</span><span class="sxs-lookup"><span data-stu-id="64b68-282">Property</span></span>|<span data-ttu-id="64b68-283">Value</span><span class="sxs-lookup"><span data-stu-id="64b68-283">Value</span></span>|
    |-------------|--------------|-----------|
    |`label1`|<span data-ttu-id="64b68-284">**Text**</span><span class="sxs-lookup"><span data-stu-id="64b68-284">**Text**</span></span>|`(blank space)`|
    ||<span data-ttu-id="64b68-285">**Nome**</span><span class="sxs-lookup"><span data-stu-id="64b68-285">**Name**</span></span>|`lblTest`|
    |`dateTimePicker1`|<span data-ttu-id="64b68-286">**Nome**</span><span class="sxs-lookup"><span data-stu-id="64b68-286">**Name**</span></span>|`dtpTest`|
    ||<span data-ttu-id="64b68-287">**Format**</span><span class="sxs-lookup"><span data-stu-id="64b68-287">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|

12. <span data-ttu-id="64b68-288">Nella finestra di progettazione fare doppio clic su **dtpTest**.</span><span class="sxs-lookup"><span data-stu-id="64b68-288">In the designer, double-click **dtpTest**.</span></span>

     <span data-ttu-id="64b68-289">Nell'**Editor di codice** viene visualizzato `Private Sub dtpTest_ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="64b68-289">The **Code Editor** opens to `Private Sub dtpTest_ValueChanged`.</span></span>

13. <span data-ttu-id="64b68-290">Modificare il codice in modo che risulti simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="64b68-290">Modify the code so that it resembles the following.</span></span>

    ```vb
    Private Sub dtpTest_ValueChanged(ByVal sender As Object, ByVal e As _
        System.EventArgs) Handles dtpTest.ValueChanged
        ctlAlarmClock1.AlarmTime = dtpTest.Value
        ctlAlarmClock1.AlarmSet = True
        lblTest.Text = "Alarm Time is " & Format(ctlAlarmClock1.AlarmTime, _
            "hh:mm")
    End Sub
    ```

14. <span data-ttu-id="64b68-291">In Esplora soluzioni fare clic con il pulsante destro del mouse su **Test** e scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="64b68-291">In Solution Explorer, right-click **Test**, and then click **Set as StartUp Project**.</span></span>

15. <span data-ttu-id="64b68-292">Scegliere **Avvia debug** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="64b68-292">On the **Debug** menu, click **Start Debugging**.</span></span>

     <span data-ttu-id="64b68-293">Verrà avviato il programma di test.</span><span class="sxs-lookup"><span data-stu-id="64b68-293">The test program starts.</span></span> <span data-ttu-id="64b68-294">Si noti che l'ora corrente viene aggiornata nel `ctlAlarmClock` controllo e che l'ora di inizio viene visualizzata <xref:System.Windows.Forms.DateTimePicker> nel controllo.</span><span class="sxs-lookup"><span data-stu-id="64b68-294">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>

16. <span data-ttu-id="64b68-295">Fare clic <xref:System.Windows.Forms.DateTimePicker> sul punto in cui vengono visualizzati i minuti dell'ora.</span><span class="sxs-lookup"><span data-stu-id="64b68-295">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>

17. <span data-ttu-id="64b68-296">Utilizzando la tastiera, impostare un valore per i minuti maggiore di un minuto rispetto all'ora corrente visualizzata da `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="64b68-296">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>

     <span data-ttu-id="64b68-297">L'ora per l'impostazione dell'allarme è visualizzata in `lblTest`.</span><span class="sxs-lookup"><span data-stu-id="64b68-297">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="64b68-298">Attendere che l'ora visualizzata raggiunga l'ora di impostazione dell'allarme.</span><span class="sxs-lookup"><span data-stu-id="64b68-298">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="64b68-299">Quando l'ora visualizzata raggiunge l'ora su cui è impostato l'allarme, verrà emesso un segnale acustico e `lblAlarm` lampeggerà.</span><span class="sxs-lookup"><span data-stu-id="64b68-299">When the displayed time reaches the time to which the alarm is set, the beep will sound and `lblAlarm` will flash.</span></span>

18. <span data-ttu-id="64b68-300">Disattivare l'allarme facendo clic su `lblAlarm`.</span><span class="sxs-lookup"><span data-stu-id="64b68-300">Turn off the alarm by clicking `lblAlarm`.</span></span> <span data-ttu-id="64b68-301">A questo punto è possibile reimpostare l'allarme.</span><span class="sxs-lookup"><span data-stu-id="64b68-301">You may now reset the alarm.</span></span>

     <span data-ttu-id="64b68-302">In questa procedura dettagliata sono stati trattati diversi concetti chiave.</span><span class="sxs-lookup"><span data-stu-id="64b68-302">This walkthrough has covered a number of key concepts.</span></span> <span data-ttu-id="64b68-303">Si è appreso come creare un controllo composito combinando controlli e componenti in un contenitore controllo composito</span><span class="sxs-lookup"><span data-stu-id="64b68-303">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="64b68-304">e come aggiungere proprietà al controllo e scrivere il codice per l'implementazione di funzionalità personalizzate.</span><span class="sxs-lookup"><span data-stu-id="64b68-304">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="64b68-305">Nell'ultima sezione sono state illustrate l'estensione delle funzionalità di uno specifico controllo composito mediante ereditarietà e la modifica delle funzionalità dei metodi host mediante override.</span><span class="sxs-lookup"><span data-stu-id="64b68-305">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>

## <a name="see-also"></a><span data-ttu-id="64b68-306">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64b68-306">See also</span></span>

- [<span data-ttu-id="64b68-307">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="64b68-307">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="64b68-308">Procedura: Crea controlli compositi</span><span class="sxs-lookup"><span data-stu-id="64b68-308">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="64b68-309">Procedura: Visualizza un controllo nella finestra di dialogo Scegli elementi della casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="64b68-309">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
