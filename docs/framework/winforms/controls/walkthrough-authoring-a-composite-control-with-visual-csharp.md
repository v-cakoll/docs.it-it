---
title: 'Procedura dettagliata: modifica di un controllo composito con Visual C#'
ms.date: 03/30/2017
dev_langs:
- CSharp
helpviewer_keywords:
- custom controls [C#]
- user controls [Windows Forms], creating with Visual C#
- UserControl class [Windows Forms], walkthroughs
- user controls [C#]
- custom controls [Windows Forms], creating
ms.assetid: f88481a8-c746-4a36-9479-374ce5f2e91f
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3ad9aad026a1a6a1266845736d7651db77fd5d5c
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546724"
---
# <a name="walkthrough-author-a-composite-control-with-c"></a><span data-ttu-id="9ad96-102">Procedura dettagliata: creazione di un controllo composito con CWalkthrough: Author a Composite Control with C\#</span><span class="sxs-lookup"><span data-stu-id="9ad96-102">Walkthrough: Author a Composite Control with C\#</span></span>

<span data-ttu-id="9ad96-103">I controlli compositi consentono di creare e riutilizzare interfacce grafiche personalizzate.</span><span class="sxs-lookup"><span data-stu-id="9ad96-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="9ad96-104">Un controllo composito è sostanzialmente un componente con rappresentazione visiva.</span><span class="sxs-lookup"><span data-stu-id="9ad96-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="9ad96-105">Può essere composto da uno o più controlli per Windows Forms, componenti o blocchi di codice in grado di estenderne le funzionalità convalidando l'input dell'utente, modificando le proprietà della visualizzazione o effettuando altre attività richieste dall'autore.</span><span class="sxs-lookup"><span data-stu-id="9ad96-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="9ad96-106">I controlli compositi possono essere inseriti in Windows Forms al pari degli altri controlli.</span><span class="sxs-lookup"><span data-stu-id="9ad96-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="9ad96-107">Nella prima parte di questa procedura verrà creato un controllo composito semplice denominato `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="9ad96-108">Nella seconda parte, le funzionalità di `ctlClock` verranno estese mediante ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="9ad96-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="9ad96-109">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="9ad96-109">Create the Project</span></span>

<span data-ttu-id="9ad96-110">Quando si crea un nuovo progetto è necessario specificarne il nome per impostare lo spazio dei nomi radice, il nome dell'assembly e il nome del progetto e assicurarsi che il componente predefinito sia inserito nello spazio dei nomi corretto.</span><span class="sxs-lookup"><span data-stu-id="9ad96-110">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="9ad96-111">Per creare la libreria di controlli ctlClockLib e il controllo ctlClock</span><span class="sxs-lookup"><span data-stu-id="9ad96-111">To create the ctlClockLib control library and the ctlClock control</span></span>

1. <span data-ttu-id="9ad96-112">In Visual Studio creare un nuovo progetto Libreria di controlli **Windows Form** e denominarlo **ctlClockLib**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-112">In Visual Studio, create a new **Windows Forms Control Library** project, and name it **ctlClockLib**.</span></span>

     <span data-ttu-id="9ad96-113">Per impostazione predefinita il nome del progetto, `ctlClockLib`, verrà assegnato anche allo spazio dei nomi radice.</span><span class="sxs-lookup"><span data-stu-id="9ad96-113">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="9ad96-114">Lo spazio dei nomi radice viene utilizzato per qualificare i nomi dei componenti dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9ad96-114">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="9ad96-115">Se ad esempio due assembly forniscono componenti denominati `ctlClock`, sarà possibile specificare il componente `ctlClock` usando`ctlClockLib.ctlClock.`</span><span class="sxs-lookup"><span data-stu-id="9ad96-115">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>

2. <span data-ttu-id="9ad96-116">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **UserControl1.cs**, quindi **scegliere Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-116">In **Solution Explorer**, right-click **UserControl1.cs**, and then click **Rename**.</span></span> <span data-ttu-id="9ad96-117">Modificare il nome file in `ctlClock.cs`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-117">Change the file name to `ctlClock.cs`.</span></span> <span data-ttu-id="9ad96-118">Fare clic sul pulsante **Sì** quando viene chiesto se si desidera rinominare tutti i riferimenti all'elemento di codice "UserControl1".</span><span class="sxs-lookup"><span data-stu-id="9ad96-118">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>

    > [!NOTE]
    > <span data-ttu-id="9ad96-119">Per impostazione predefinita, un <xref:System.Windows.Forms.UserControl> controllo composito eredita dalla classe fornita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="9ad96-119">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="9ad96-120">La <xref:System.Windows.Forms.UserControl> classe fornisce le funzionalità richieste da tutti i controlli compositi e implementa metodi e proprietà standard.</span><span class="sxs-lookup"><span data-stu-id="9ad96-120">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>

3. <span data-ttu-id="9ad96-121">Scegliere **Salva tutto** dal menu **File** per salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="9ad96-121">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="add-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="9ad96-122">Aggiunta di controlli e componenti di Windows al controllo compositoAdd Windows Controls and Components to the Composite Control</span><span class="sxs-lookup"><span data-stu-id="9ad96-122">Add Windows Controls and Components to the Composite Control</span></span>

<span data-ttu-id="9ad96-123">L'interfaccia visiva è parte integrante del controllo composito</span><span class="sxs-lookup"><span data-stu-id="9ad96-123">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="9ad96-124">e viene implementata mediante l'aggiunta di uno o più controlli Windows nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="9ad96-124">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="9ad96-125">Nella procedura riportata di seguito i controlli Windows verranno incorporati nel controllo composito e verrà scritto il codice per l'implementazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9ad96-125">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>

### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="9ad96-126">Per aggiungere al controllo composito un oggetto Label e un oggetto Timer</span><span class="sxs-lookup"><span data-stu-id="9ad96-126">To add a Label and a Timer to your composite control</span></span>

1. <span data-ttu-id="9ad96-127">In **Esplora soluzioni**fare clic con il pulsante destro del mouse **su ctlClock.cs**, quindi scegliere Visualizza finestra di **progettazione**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-127">In **Solution Explorer**, right-click **ctlClock.cs**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="9ad96-128">Nella **Casella degli strumenti**espandere il nodo **Controlli comuni** , quindi fare doppio clic su **Etichetta**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-128">In the **Toolbox**, expand the **Common Controls** node, and then double-click **Label**.</span></span>

     <span data-ttu-id="9ad96-129">Un <xref:System.Windows.Forms.Label> controllo `label1` denominato viene aggiunto al controllo nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="9ad96-129">A <xref:System.Windows.Forms.Label> control named `label1` is added to your control on the designer surface.</span></span>

3. <span data-ttu-id="9ad96-130">Nella finestra di progettazione fare clic su **label1**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-130">In the designer, click **label1**.</span></span> <span data-ttu-id="9ad96-131">Nella finestra Proprietà impostare le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="9ad96-131">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="9ad96-132">Proprietà</span><span class="sxs-lookup"><span data-stu-id="9ad96-132">Property</span></span>|<span data-ttu-id="9ad96-133">Modificare in</span><span class="sxs-lookup"><span data-stu-id="9ad96-133">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="9ad96-134">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9ad96-134">**Name**</span></span>|`lblDisplay`|
    |<span data-ttu-id="9ad96-135">**Testo**</span><span class="sxs-lookup"><span data-stu-id="9ad96-135">**Text**</span></span>|`(blank space)`|
    |<span data-ttu-id="9ad96-136">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="9ad96-136">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="9ad96-137">**Font.Size**</span><span class="sxs-lookup"><span data-stu-id="9ad96-137">**Font.Size**</span></span>|`14`|

4. <span data-ttu-id="9ad96-138">Nella **Casella degli strumenti** espandere il nodo **Componenti**, quindi fare doppio clic su **Timer**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-138">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>

     <span data-ttu-id="9ad96-139">Poiché <xref:System.Windows.Forms.Timer> un oggetto è un componente, non dispone di alcuna rappresentazione visiva in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9ad96-139">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="9ad96-140">Pertanto, non viene visualizzato con i controlli nell'area di progettazione, ma piuttosto in **Progettazione componenti** (un vassoio nella parte inferiore dell'area di progettazione).</span><span class="sxs-lookup"><span data-stu-id="9ad96-140">Therefore, it does not appear with the controls on the designer surface, but rather in the **Component Designer** (a tray at the bottom of the designer surface).</span></span>

5. <span data-ttu-id="9ad96-141">In **Progettazione componenti**fare clic su <xref:System.Windows.Forms.Timer.Interval%2A> **timer1**, quindi impostare la proprietà su `1000` e la <xref:System.Windows.Forms.Timer.Enabled%2A> proprietà su `true`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-141">In the **Component Designer**, click **timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>

     <span data-ttu-id="9ad96-142">La <xref:System.Windows.Forms.Timer.Interval%2A> proprietà controlla la <xref:System.Windows.Forms.Timer> frequenza con cui il componente viene selezionato.</span><span class="sxs-lookup"><span data-stu-id="9ad96-142">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the <xref:System.Windows.Forms.Timer> component ticks.</span></span> <span data-ttu-id="9ad96-143">Ogni volta che `timer1` scatta, viene eseguito il codice nell'evento `timer1_Tick`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-143">Each time `timer1` ticks, it runs the code in the `timer1_Tick` event.</span></span> <span data-ttu-id="9ad96-144">L'intervallo rappresenta i millesimi di secondo che intercorrono tra uno scatto e l'altro.</span><span class="sxs-lookup"><span data-stu-id="9ad96-144">The interval represents the number of milliseconds between ticks.</span></span>

6. <span data-ttu-id="9ad96-145">In **Progettazione componenti**fare doppio clic su `timer1_Tick` **timer1** per passare all'evento per `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-145">In the **Component Designer**, double-click **timer1** to go to the `timer1_Tick` event for `ctlClock`.</span></span>

7. <span data-ttu-id="9ad96-146">Modificare il codice in modo che risulti simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="9ad96-146">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="9ad96-147">Assicurarsi di cambiare il modificatore di accesso da `private` a `protected`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-147">Be sure to change the access modifier from `private` to `protected`.</span></span>

    ```csharp
    protected void timer1_Tick(object sender, System.EventArgs e)
    {
        // Causes the label to display the current time.
        lblDisplay.Text = DateTime.Now.ToLongTimeString();
    }
    ```

     <span data-ttu-id="9ad96-148">Questo codice determinerà la visualizzazione dell'ora corrente in `lblDisplay`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-148">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="9ad96-149">Poiché l'intervallo di `timer1` è stato impostato su `1000`, l'evento verrà generato ogni mille millesimi di secondo, aggiornando quindi l'ora corrente ogni secondo.</span><span class="sxs-lookup"><span data-stu-id="9ad96-149">Because the interval of `timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>

8. <span data-ttu-id="9ad96-150">Modificare il metodo in modo che sia sottoponibile a override con la parola chiave `virtual`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-150">Modify the method to be overridable with the `virtual` keyword.</span></span> <span data-ttu-id="9ad96-151">Per ulteriori informazioni, vedere la sezione "Eredità da un controllo utente" riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="9ad96-151">For more information, see the  "Inheriting from a User Control" section below.</span></span>

    ```csharp
    protected virtual void timer1_Tick(object sender, System.EventArgs e)
    ```

9. <span data-ttu-id="9ad96-152">Scegliere **Salva tutto** dal menu **File** per salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="9ad96-152">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="add-properties-to-the-composite-control"></a><span data-ttu-id="9ad96-153">Aggiunta di proprietà al controllo compositoAdd Properties to the Composite Control</span><span class="sxs-lookup"><span data-stu-id="9ad96-153">Add Properties to the Composite Control</span></span>

<span data-ttu-id="9ad96-154">Il controllo orologio ora <xref:System.Windows.Forms.Label> incapsula <xref:System.Windows.Forms.Timer> un controllo e un componente, ognuno con il proprio set di proprietà intrinseche.</span><span class="sxs-lookup"><span data-stu-id="9ad96-154">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="9ad96-155">Benché le singole proprietà di questi controlli non siano accessibili ai futuri utenti del controllo, è possibile creare ed esporre proprietà personalizzate scrivendo i blocchi di codice appropriati.</span><span class="sxs-lookup"><span data-stu-id="9ad96-155">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="9ad96-156">Nella procedura riportata di seguito verrà illustrato come aggiungere al controllo proprietà che consentono all'utente di modificare il colore dello sfondo e del testo.</span><span class="sxs-lookup"><span data-stu-id="9ad96-156">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>

### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="9ad96-157">Per aggiungere una proprietà al controllo composito</span><span class="sxs-lookup"><span data-stu-id="9ad96-157">To add a property to your composite control</span></span>

1. <span data-ttu-id="9ad96-158">In **Esplora soluzioni**fare clic con il **pulsante**destro del mouse su ctlClock.cs , quindi **scegliere Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-158">In **Solution Explorer**, right-click **ctlClock.cs**, and then click **View Code**.</span></span>

     <span data-ttu-id="9ad96-159">Verrà aperto **l'editor** di codice per il controllo.</span><span class="sxs-lookup"><span data-stu-id="9ad96-159">The **Code Editor** for your control opens.</span></span>

2. <span data-ttu-id="9ad96-160">Individuare l'istruzione `public partial class ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-160">Locate the `public partial class ctlClock` statement.</span></span> <span data-ttu-id="9ad96-161">Sotto la parentesi graffa aperta (`{)`, digitare il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="9ad96-161">Beneath the opening brace (`{)`, type the following code.</span></span>

    ```csharp
    private Color colFColor;
    private Color colBColor;
    ```

     <span data-ttu-id="9ad96-162">Queste istruzioni consentono di creare le variabili private da utilizzare per la memorizzazione dei valori delle proprietà che verranno create.</span><span class="sxs-lookup"><span data-stu-id="9ad96-162">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>

3. <span data-ttu-id="9ad96-163">Immettere o incollare il codice seguente sotto le dichiarazioni di variabile del passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="9ad96-163">Enter or paste the following code beneath the variable declarations from step 2.</span></span>

    ```csharp
    // Declares the name and type of the property.
    public Color ClockBackColor
    {
        // Retrieves the value of the private variable colBColor.
        get
        {
            return colBColor;
        }
        // Stores the selected value in the private variable colBColor, and
        // updates the background color of the label control lblDisplay.
        set
        {
            colBColor = value;
            lblDisplay.BackColor = colBColor;
        }
    }
    // Provides a similar set of instructions for the foreground color.
    public Color ClockForeColor
    {
        get
        {
            return colFColor;
        }
        set
        {
            colFColor = value;
            lblDisplay.ForeColor = colFColor;
        }
    }
    ```

     <span data-ttu-id="9ad96-164">Nel codice riportato in precedenza vengono create due proprietà personalizzate, `ClockForeColor` e `ClockBackColor`, disponibili agli utenti successivi del controllo.</span><span class="sxs-lookup"><span data-stu-id="9ad96-164">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control.</span></span> <span data-ttu-id="9ad96-165">Le istruzioni `get` e `set` consentono di archiviare e recuperare il valore della proprietà e di inserire il codice per implementare le funzionalità appropriate per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="9ad96-165">The `get` and `set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>

4. <span data-ttu-id="9ad96-166">Scegliere **Salva tutto** dal menu **File** per salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="9ad96-166">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="test-the-control"></a><span data-ttu-id="9ad96-167">Testare il controllo</span><span class="sxs-lookup"><span data-stu-id="9ad96-167">Test the Control</span></span>

<span data-ttu-id="9ad96-168">I controlli non sono applicazioni autonome e devono pertanto essere inseriti in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="9ad96-168">Controls are not stand-alone applications; they must be hosted in a container.</span></span> <span data-ttu-id="9ad96-169">Eseguire il test del comportamento del controllo in fase di esecuzione e sperimentare le proprietà con **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-169">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="9ad96-170">Per altre informazioni, vedere [Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="9ad96-170">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

### <a name="to-test-your-control"></a><span data-ttu-id="9ad96-171">Per eseguire il test del controllo</span><span class="sxs-lookup"><span data-stu-id="9ad96-171">To test your control</span></span>

1. <span data-ttu-id="9ad96-172">Premere **F5** per compilare il progetto ed eseguire il controllo in **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-172">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="9ad96-173">Nella griglia della proprietà di Test Container, selezionare la proprietà `ClockBackColor`, quindi fare clic sulla freccia a discesa per visualizzare la tavolozza dei colori.</span><span class="sxs-lookup"><span data-stu-id="9ad96-173">In the test container's property grid, locate the `ClockBackColor` property, and then select the property to display the color palette.</span></span>

3. <span data-ttu-id="9ad96-174">Scegliere un colore facendovi clic sopra.</span><span class="sxs-lookup"><span data-stu-id="9ad96-174">Choose a color by clicking it.</span></span>

   <span data-ttu-id="9ad96-175">Il colore di sfondo del controllo cambierà in base al colore selezionato.</span><span class="sxs-lookup"><span data-stu-id="9ad96-175">The background color of your control changes to the color you selected.</span></span>

4. <span data-ttu-id="9ad96-176">Usare una sequenza di eventi simile per verificare il corretto funzionamento della proprietà `ClockForeColor`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-176">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>

   <span data-ttu-id="9ad96-177">In questa sezione e in quelle precedenti è stato illustrato come combinare componenti e controlli Windows con codici e package per aggiungere funzionalità personalizzate al modulo di un controllo composito.</span><span class="sxs-lookup"><span data-stu-id="9ad96-177">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="9ad96-178">Si è inoltre appreso come esporre le proprietà del controllo composito e come eseguire il test del controllo dopo averlo completato.</span><span class="sxs-lookup"><span data-stu-id="9ad96-178">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="9ad96-179">Nella sezione successiva verranno fornite informazioni sulla modalità di creazione di un controllo composito ereditato utilizzando `ctlClock` come base.</span><span class="sxs-lookup"><span data-stu-id="9ad96-179">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>

## <a name="inherit-from-a-composite-control"></a><span data-ttu-id="9ad96-180">Ereditare da un controllo compositoInherit from a Composite Control</span><span class="sxs-lookup"><span data-stu-id="9ad96-180">Inherit from a Composite Control</span></span>

<span data-ttu-id="9ad96-181">Nelle sezioni precedenti si è appreso come combinare controlli, componenti e codice Windows in controlli compositi riutilizzabili.</span><span class="sxs-lookup"><span data-stu-id="9ad96-181">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="9ad96-182">Il controllo composito può ora essere usato come base per la compilazione di altri controlli.</span><span class="sxs-lookup"><span data-stu-id="9ad96-182">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="9ad96-183">Il processo di derivazione di una classe da una classe di base è detto *ereditarietà*.</span><span class="sxs-lookup"><span data-stu-id="9ad96-183">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="9ad96-184">In questa sezione verrà creato un controllo composito denominato `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-184">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="9ad96-185">Il controllo verrà derivato dal relativo controllo padre, in questo caso `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-185">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="9ad96-186">Verrà spiegato come estendere le funzionalità di `ctlClock` mediante l'override dei metodi padre e l'aggiunta di nuovi metodi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="9ad96-186">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>

<span data-ttu-id="9ad96-187">Per creare un controllo ereditato, è innanzitutto necessario derivare il controllo dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="9ad96-187">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="9ad96-188">Questa operazione consente di creare un nuovo controllo, con le stesse proprietà, metodi e caratteristiche grafiche del controllo padre, che può essere anche utilizzato come base per l'aggiunta di una funzionalità nuova o modificata.</span><span class="sxs-lookup"><span data-stu-id="9ad96-188">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>

### <a name="to-create-the-inherited-control"></a><span data-ttu-id="9ad96-189">Per creare il controllo ereditato</span><span class="sxs-lookup"><span data-stu-id="9ad96-189">To create the inherited control</span></span>

1. <span data-ttu-id="9ad96-190">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **ctlClockLib**, **scegliere Aggiungi**, quindi Controllo **utente**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-190">In **Solution Explorer**, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>

     <span data-ttu-id="9ad96-191">Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento** .</span><span class="sxs-lookup"><span data-stu-id="9ad96-191">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="9ad96-192">Selezionare il modello **Controllo utente ereditato**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-192">Select the **Inherited User Control** template.</span></span>

3. <span data-ttu-id="9ad96-193">Nella casella **Nome** digitare `ctlAlarmClock.cs` e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-193">In the **Name** box, type `ctlAlarmClock.cs`, and then click **Add**.</span></span>

     <span data-ttu-id="9ad96-194">Viene visualizzata la finestra di dialogo **Selezione ereditarietà**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-194">The **Inheritance Picker** dialog box appears.</span></span>

4. <span data-ttu-id="9ad96-195">In **Nome componente** fare doppio clic su **ctlClock**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-195">Under **Component Name**, double-click **ctlClock**.</span></span>

5. <span data-ttu-id="9ad96-196">In **Esplora soluzioni**scorrere i progetti correnti.</span><span class="sxs-lookup"><span data-stu-id="9ad96-196">In **Solution Explorer**, browse through the current projects.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9ad96-197">Nel progetto corrente è stato aggiunto il file denominato **ctlAlarmClock.cs**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-197">A file called **ctlAlarmClock.cs** has been added to the current project.</span></span>

### <a name="add-the-alarm-properties"></a><span data-ttu-id="9ad96-198">Aggiungere le proprietà dell'allarme</span><span class="sxs-lookup"><span data-stu-id="9ad96-198">Add the Alarm Properties</span></span>

<span data-ttu-id="9ad96-199">Le modalità di aggiunta delle proprietà a un controllo ereditato sono analoghe a quelle utilizzate per i controlli compositi.</span><span class="sxs-lookup"><span data-stu-id="9ad96-199">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="9ad96-200">Mediante la sintassi di dichiarazione delle proprietà si aggiungeranno ora al controllo due proprietà: `AlarmTime`, in cui viene memorizzato il valore della data e dell'ora in cui l'allarme deve essere disattivato, e `AlarmSet`, che indica se l'allarme è impostato o meno.</span><span class="sxs-lookup"><span data-stu-id="9ad96-200">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>

#### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="9ad96-201">Per aggiungere proprietà al controllo composito</span><span class="sxs-lookup"><span data-stu-id="9ad96-201">To add properties to your composite control</span></span>

1. <span data-ttu-id="9ad96-202">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **ctlAlarmClock**, quindi **scegliere Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-202">In **Solution Explorer**, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>

2. <span data-ttu-id="9ad96-203">Individuare l'istruzione `public class`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-203">Locate the `public class` statement.</span></span> <span data-ttu-id="9ad96-204">Si noti che il controllo eredita da `ctlClockLib.ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-204">Note that your control inherits from `ctlClockLib.ctlClock`.</span></span> <span data-ttu-id="9ad96-205">Sotto la parentesi graffa aperta (`{)`, digitare il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="9ad96-205">Beneath the opening brace (`{)` statement, type the following code.</span></span>

    ```csharp
    private DateTime dteAlarmTime;
    private bool blnAlarmSet;
    // These properties will be declared as public to allow future
    // developers to access them.
    public DateTime AlarmTime
    {
        get
        {
            return dteAlarmTime;
        }
        set
        {
            dteAlarmTime = value;
        }
    }
    public bool AlarmSet
    {
        get
        {
            return blnAlarmSet;
        }
        set
        {
            blnAlarmSet = value;
        }
    }
    ```

### <a name="add-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="9ad96-206">Aggiungi all'interfaccia grafica del controllo</span><span class="sxs-lookup"><span data-stu-id="9ad96-206">Add to the Graphical Interface of the Control</span></span>

<span data-ttu-id="9ad96-207">Il controllo ereditato presenta un'interfaccia grafica identica a quella del controllo dal quale eredita</span><span class="sxs-lookup"><span data-stu-id="9ad96-207">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="9ad96-208">e possiede gli stessi controlli costitutivi del controllo padre, ma le proprietà dei controlli costitutivi non sono disponibili, a meno che non siano state specificamente esposte.</span><span class="sxs-lookup"><span data-stu-id="9ad96-208">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="9ad96-209">Analogamente a qualsiasi altro controllo composito, è possibile aggiungere elementi all'interfaccia grafica di un controllo composito ereditato, utilizzando la medesima procedura.</span><span class="sxs-lookup"><span data-stu-id="9ad96-209">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="9ad96-210">In questo esempio verrà utilizzato un controllo label per aggiungere un effetto intermittente all'interfaccia grafica del controllo quando l'allarme suona.</span><span class="sxs-lookup"><span data-stu-id="9ad96-210">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>

#### <a name="to-add-the-label-control"></a><span data-ttu-id="9ad96-211">Per aggiungere il controllo label</span><span class="sxs-lookup"><span data-stu-id="9ad96-211">To add the label control</span></span>

1. <span data-ttu-id="9ad96-212">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **ctlAlarmClock**, quindi **scegliere Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-212">In **Solution Explorer**, right-click **ctlAlarmClock**, and then click **View Designer**.</span></span>

     <span data-ttu-id="9ad96-213">Nella finestra principale viene aperta la finestra di progettazione per `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-213">The designer for `ctlAlarmClock` opens in the main window.</span></span>

2. <span data-ttu-id="9ad96-214">Fare clic sulla parte visualizzata del controllo e osservare la finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="9ad96-214">Click the display portion of the control, and view the Properties window.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9ad96-215">Tutte le proprietà sono presenti ma inattive, ossia visualizzate in grigio.</span><span class="sxs-lookup"><span data-stu-id="9ad96-215">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="9ad96-216">Ciò indica che le proprietà sono native di `lblDisplay` e non è possibile accedervi né modificarle nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="9ad96-216">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="9ad96-217">Per impostazione predefinita i controlli contenuti in un controllo composito sono `private` e le relative proprietà non sono accessibili.</span><span class="sxs-lookup"><span data-stu-id="9ad96-217">By default, controls contained in a composite control are `private`, and their properties are not accessible by any means.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9ad96-218">Se si desidera che gli utenti successivi del controllo composito abbiano accesso ai relativi controlli interni, dichiararli come `public` o `protected`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-218">If you want subsequent users of your composite control to have access to its internal controls, declare them as `public` or `protected`.</span></span> <span data-ttu-id="9ad96-219">Sarà così possibile impostare e modificare le proprietà dei controlli contenuti nel controllo composito mediante il codice appropriato.</span><span class="sxs-lookup"><span data-stu-id="9ad96-219">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>

3. <span data-ttu-id="9ad96-220">Aggiungere <xref:System.Windows.Forms.Label> un controllo al controllo composito.</span><span class="sxs-lookup"><span data-stu-id="9ad96-220">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>

4. <span data-ttu-id="9ad96-221">Utilizzando il mouse, <xref:System.Windows.Forms.Label> trascinare il controllo immediatamente sotto la casella di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="9ad96-221">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="9ad96-222">Nella finestra Proprietà impostare le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="9ad96-222">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="9ad96-223">Proprietà</span><span class="sxs-lookup"><span data-stu-id="9ad96-223">Property</span></span>|<span data-ttu-id="9ad96-224">Impostazione</span><span class="sxs-lookup"><span data-stu-id="9ad96-224">Setting</span></span>|
    |--------------|-------------|
    |<span data-ttu-id="9ad96-225">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9ad96-225">**Name**</span></span>|`lblAlarm`|
    |<span data-ttu-id="9ad96-226">**Testo**</span><span class="sxs-lookup"><span data-stu-id="9ad96-226">**Text**</span></span>|<span data-ttu-id="9ad96-227">**Allarme!**</span><span class="sxs-lookup"><span data-stu-id="9ad96-227">**Alarm!**</span></span>|
    |<span data-ttu-id="9ad96-228">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="9ad96-228">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="9ad96-229">**Visibile**</span><span class="sxs-lookup"><span data-stu-id="9ad96-229">**Visible**</span></span>|`false`|

### <a name="add-the-alarm-functionality"></a><span data-ttu-id="9ad96-230">Aggiungere la funzionalità di allarme</span><span class="sxs-lookup"><span data-stu-id="9ad96-230">Add the Alarm Functionality</span></span>

<span data-ttu-id="9ad96-231">Nelle procedure precedenti sono state aggiunte proprietà e un controllo in grado di abilitare la funzionalità di allarme nel controllo composito.</span><span class="sxs-lookup"><span data-stu-id="9ad96-231">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="9ad96-232">In questa procedura verrà aggiunto un codice che consente di confrontare l'ora corrente con l'ora dell'allarme e, se le ore risultano identiche, attivare un allarme lampeggiante.</span><span class="sxs-lookup"><span data-stu-id="9ad96-232">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to flash an alarm.</span></span> <span data-ttu-id="9ad96-233">Eseguendo l'override del metodo `timer1_Tick` di `ctlClock` e aggiungendovi ulteriore codice sarà possibile estendere le capacità di `ctlAlarmClock` e conservare allo stesso le funzionalità intrinseche di `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-233">By overriding the `timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>

#### <a name="to-override-the-timer1_tick-method-of-ctlclock"></a><span data-ttu-id="9ad96-234">Per eseguire l'override del metodo Timer1_Tick di ctlClock</span><span class="sxs-lookup"><span data-stu-id="9ad96-234">To override the timer1_Tick method of ctlClock</span></span>

1. <span data-ttu-id="9ad96-235">Nell'\*\*editor di codice \*\* individuare l'istruzione `private bool blnAlarmSet;`</span><span class="sxs-lookup"><span data-stu-id="9ad96-235">In the **Code Editor**, locate the `private bool blnAlarmSet;` statement.</span></span> <span data-ttu-id="9ad96-236">e aggiungere subito dopo la seguente istruzione.</span><span class="sxs-lookup"><span data-stu-id="9ad96-236">Immediately beneath it, add the following statement.</span></span>

    ```csharp
    private bool blnColorTicker;
    ```

2. <span data-ttu-id="9ad96-237">Nell'**editor di codice** individuare la parentesi graffa di chiusura (`})`) alla fine della classe.</span><span class="sxs-lookup"><span data-stu-id="9ad96-237">In the **Code Editor**, locate the closing brace (`})` at the end of the class.</span></span> <span data-ttu-id="9ad96-238">Aggiungere il seguente codice prima della parentesi graffa.</span><span class="sxs-lookup"><span data-stu-id="9ad96-238">Just before the brace, add the following code.</span></span>

    ```csharp
    protected override void timer1_Tick(object sender, System.EventArgs e)
    {
        // Calls the Timer1_Tick method of ctlClock.
        base.timer1_Tick(sender, e);
        // Checks to see if the alarm is set.
        if (AlarmSet == false)
            return;
        else
            // If the date, hour, and minute of the alarm time are the same as
            // the current time, flash an alarm.
        {
            if (AlarmTime.Date == DateTime.Now.Date && AlarmTime.Hour ==
                DateTime.Now.Hour && AlarmTime.Minute == DateTime.Now.Minute)
            {
                // Sets lblAlarmVisible to true, and changes the background color based on
                // the value of blnColorTicker. The background color of the label
                // will flash once per tick of the clock.
                lblAlarm.Visible = true;
                if (blnColorTicker == false)
                {
                    lblAlarm.BackColor = Color.Red;
                    blnColorTicker = true;
                }
                else
                {
                    lblAlarm.BackColor = Color.Blue;
                    blnColorTicker = false;
                }
            }
            else
            {
                // Once the alarm has sounded for a minute, the label is made
                // invisible again.
                lblAlarm.Visible = false;
            }
        }
    }
    ```

     <span data-ttu-id="9ad96-239">Il codice appena aggiunto ha diverse funzioni.</span><span class="sxs-lookup"><span data-stu-id="9ad96-239">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="9ad96-240">Se si utilizza l'istruzione `override`, il controllo utilizzerà questo metodo anziché il metodo ereditato dal controllo di base.</span><span class="sxs-lookup"><span data-stu-id="9ad96-240">The `override` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="9ad96-241">Una volta chiamato, questo metodo chiamerà il metodo di cui esegue l'override utilizzando l'istruzione `base.timer1_Tick` e assicurando che tutte le funzionalità incorporate nel controllo originale vengano riprodotte in questo controllo.</span><span class="sxs-lookup"><span data-stu-id="9ad96-241">When this method is called, it calls the method it overrides by invoking the `base.timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="9ad96-242">Verrà quindi eseguito il codice aggiuntivo per incorporare la funzionalità di allarme.</span><span class="sxs-lookup"><span data-stu-id="9ad96-242">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="9ad96-243">Quando l'allarme viene attivato, verrà visualizzato un controllo label intermittente.</span><span class="sxs-lookup"><span data-stu-id="9ad96-243">A flashing label control will appear when the alarm occurs.</span></span>

     <span data-ttu-id="9ad96-244">Il controllo dell'allarme è quasi completo.</span><span class="sxs-lookup"><span data-stu-id="9ad96-244">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="9ad96-245">L'unica operazione rimasta è l'implementazione di un sistema di disattivazione.</span><span class="sxs-lookup"><span data-stu-id="9ad96-245">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="9ad96-246">A tal fine, è necessario aggiungere codice al metodo `lblAlarm_Click`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-246">To do this, you will add code to the `lblAlarm_Click` method.</span></span>

#### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="9ad96-247">Per implementare il metodo di disattivazione</span><span class="sxs-lookup"><span data-stu-id="9ad96-247">To implement the shutoff method</span></span>

1. <span data-ttu-id="9ad96-248">In **Esplora soluzioni**fare clic con il pulsante destro del mouse **su ctlAlarmClock.cs**, quindi scegliere Visualizza finestra di **progettazione**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-248">In **Solution Explorer**, right-click **ctlAlarmClock.cs**, and then click **View Designer**.</span></span>

     <span data-ttu-id="9ad96-249">Viene aperta la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="9ad96-249">The designer opens.</span></span>

2. <span data-ttu-id="9ad96-250">Aggiungere un pulsante al controllo.</span><span class="sxs-lookup"><span data-stu-id="9ad96-250">Add a button to the control.</span></span> <span data-ttu-id="9ad96-251">Impostare le proprietà del pulsante come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9ad96-251">Set the properties of the button as follows.</span></span>

    |<span data-ttu-id="9ad96-252">Proprietà</span><span class="sxs-lookup"><span data-stu-id="9ad96-252">Property</span></span>|<span data-ttu-id="9ad96-253">valore</span><span class="sxs-lookup"><span data-stu-id="9ad96-253">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="9ad96-254">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9ad96-254">**Name**</span></span>|`btnAlarmOff`|
    |<span data-ttu-id="9ad96-255">**Testo**</span><span class="sxs-lookup"><span data-stu-id="9ad96-255">**Text**</span></span>|<span data-ttu-id="9ad96-256">**Disabilita allarme**</span><span class="sxs-lookup"><span data-stu-id="9ad96-256">**Disable Alarm**</span></span>|

3. <span data-ttu-id="9ad96-257">Nella finestra di progettazione fare doppio clic su **btnAlarmOff**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-257">In the designer, double-click **btnAlarmOff**.</span></span>

     <span data-ttu-id="9ad96-258">Nell'**editor di codice** verrà visualizzata la riga `private void btnAlarmOff_Click`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-258">The **Code Editor** opens to the `private void btnAlarmOff_Click` line.</span></span>

4. <span data-ttu-id="9ad96-259">Modificare il metodo in modo che risulti simile al seguente codice.</span><span class="sxs-lookup"><span data-stu-id="9ad96-259">Modify this method so that it resembles the following code.</span></span>

    ```csharp
    private void btnAlarmOff_Click(object sender, System.EventArgs e)
    {
        // Turns off the alarm.
        AlarmSet = false;
        // Hides the flashing label.
        lblAlarm.Visible = false;
    }
    ```

5. <span data-ttu-id="9ad96-260">Scegliere **Salva tutto** dal menu **File** per salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="9ad96-260">On the **File** menu, click **Save All** to save the project.</span></span>

### <a name="use-the-inherited-control-on-a-form"></a><span data-ttu-id="9ad96-261">Utilizzare il controllo ereditato in un modulo</span><span class="sxs-lookup"><span data-stu-id="9ad96-261">Use the Inherited Control on a Form</span></span>

<span data-ttu-id="9ad96-262">È possibile testare il controllo ereditato nello stesso `ctlClock`modo in cui è stato testato il controllo della classe base, : premere **F5** per compilare il progetto ed eseguire il controllo in **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-262">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="9ad96-263">Per altre informazioni, vedere [Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="9ad96-263">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

<span data-ttu-id="9ad96-264">Per utilizzare il controllo è necessario inserirlo in un modulo.</span><span class="sxs-lookup"><span data-stu-id="9ad96-264">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="9ad96-265">Come i controlli compositi standard, i controlli compositi ereditati non possono essere autonomi e devono essere inclusi in un modulo o in un altro contenitore.</span><span class="sxs-lookup"><span data-stu-id="9ad96-265">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="9ad96-266">Poiché `ctlAlarmClock` include un maggior numero di funzionalità, per eseguire il test è necessario aggiungere del codice.</span><span class="sxs-lookup"><span data-stu-id="9ad96-266">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="9ad96-267">In questa procedura verrà scritto un semplice programma per la verifica delle funzionalità di `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-267">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="9ad96-268">Verrà inoltre scritto il codice per impostare e visualizzare la proprietà `AlarmTime` di `ctlAlarmClock` e verrà eseguito il test delle funzionalità intrinseche del controllo.</span><span class="sxs-lookup"><span data-stu-id="9ad96-268">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>

#### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="9ad96-269">Per compilare e aggiungere il controllo a un modulo di test</span><span class="sxs-lookup"><span data-stu-id="9ad96-269">To build and add your control to a test form</span></span>

1. <span data-ttu-id="9ad96-270">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **ctlClockLib**, quindi **scegliere Compila**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-270">In **Solution Explorer**, right-click **ctlClockLib**, and then click **Build**.</span></span>

2. <span data-ttu-id="9ad96-271">Aggiungere un nuovo progetto **applicazione Windows Form** alla soluzione e denominarlo **Test**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-271">Add a new **Windows Forms Application** project to the solution, and name it **Test**.</span></span>

3. <span data-ttu-id="9ad96-272">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nodo **Riferimenti** per il progetto di test.</span><span class="sxs-lookup"><span data-stu-id="9ad96-272">In **Solution Explorer**, right-click the **References** node for your test project.</span></span> <span data-ttu-id="9ad96-273">Fare clic su **Aggiungi riferimento** per visualizzare la finestra di dialogo **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-273">Click **Add Reference** to display the **Add Reference** dialog box.</span></span> <span data-ttu-id="9ad96-274">Scegliere la scheda **Progetti**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-274">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="9ad96-275">Il progetto `ctlClockLib` verrà elencato in **Nome progetto**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-275">Your `ctlClockLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="9ad96-276">Fare doppio clic sul progetto per cui si desidera aggiungere il riferimento al progetto di test.</span><span class="sxs-lookup"><span data-stu-id="9ad96-276">Double-click the project to add the reference to the test project.</span></span>

4. <span data-ttu-id="9ad96-277">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **Test**, quindi **scegliere Compila**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-277">In **Solution Explorer**, right-click **Test**, and then click **Build**.</span></span>

5. <span data-ttu-id="9ad96-278">Nella **Casella degli strumenti** espandere il nodo **Componenti ctlClockLib**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-278">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>

6. <span data-ttu-id="9ad96-279">Fare doppio clic su **ctlAlarmClock** per aggiungere una copia di `ctlAlarmClock` al modulo.</span><span class="sxs-lookup"><span data-stu-id="9ad96-279">Double-click **ctlAlarmClock** to add a copy of `ctlAlarmClock` to your form.</span></span>

7. <span data-ttu-id="9ad96-280">Nella **Casella degli strumenti**individuare e fare doppio <xref:System.Windows.Forms.DateTimePicker> clic su **DateTimePicker** per aggiungere un controllo al form, quindi aggiungere un <xref:System.Windows.Forms.Label> controllo facendo doppio clic su **Etichetta**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-280">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>

8. <span data-ttu-id="9ad96-281">Posizionare mediante il mouse i controlli in un punto del modulo di facile accesso.</span><span class="sxs-lookup"><span data-stu-id="9ad96-281">Use the mouse to position the controls in a convenient place on the form.</span></span>

9. <span data-ttu-id="9ad96-282">Impostare le proprietà dei controlli come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9ad96-282">Set the properties of these controls in the following manner.</span></span>

    |<span data-ttu-id="9ad96-283">Controllo</span><span class="sxs-lookup"><span data-stu-id="9ad96-283">Control</span></span>|<span data-ttu-id="9ad96-284">Proprietà</span><span class="sxs-lookup"><span data-stu-id="9ad96-284">Property</span></span>|<span data-ttu-id="9ad96-285">valore</span><span class="sxs-lookup"><span data-stu-id="9ad96-285">Value</span></span>|
    |-------------|--------------|-----------|
    |`label1`|<span data-ttu-id="9ad96-286">**Testo**</span><span class="sxs-lookup"><span data-stu-id="9ad96-286">**Text**</span></span>|`(blank space)`|
    ||<span data-ttu-id="9ad96-287">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9ad96-287">**Name**</span></span>|`lblTest`|
    |`dateTimePicker1`|<span data-ttu-id="9ad96-288">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9ad96-288">**Name**</span></span>|`dtpTest`|
    ||<span data-ttu-id="9ad96-289">**Format**</span><span class="sxs-lookup"><span data-stu-id="9ad96-289">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|

10. <span data-ttu-id="9ad96-290">Nella finestra di progettazione fare doppio clic su **dtpTest**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-290">In the designer, double-click **dtpTest**.</span></span>

     <span data-ttu-id="9ad96-291">Nell'**Editor di codice** viene visualizzato `private void dtpTest_ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-291">The **Code Editor** opens to `private void dtpTest_ValueChanged`.</span></span>

11. <span data-ttu-id="9ad96-292">Modificare il codice in modo che risulti simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="9ad96-292">Modify the code so that it resembles the following.</span></span>

    ```csharp
    private void dtpTest_ValueChanged(object sender, System.EventArgs e)
    {
        ctlAlarmClock1.AlarmTime = dtpTest.Value;
        ctlAlarmClock1.AlarmSet = true;
        lblTest.Text = "Alarm Time is " +
            ctlAlarmClock1.AlarmTime.ToShortTimeString();
    }
    ```

12. <span data-ttu-id="9ad96-293">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **Test**, quindi scegliere Imposta come progetto **di avvio**.</span><span class="sxs-lookup"><span data-stu-id="9ad96-293">In **Solution Explorer**, right-click **Test**, and then click **Set as StartUp Project**.</span></span>

13. <span data-ttu-id="9ad96-294">Scegliere **Avvia** **debug**dal menu Debug .</span><span class="sxs-lookup"><span data-stu-id="9ad96-294">On the **Debug** menu, click **Start Debugging**.</span></span>

     <span data-ttu-id="9ad96-295">Verrà avviato il programma di test.</span><span class="sxs-lookup"><span data-stu-id="9ad96-295">The test program starts.</span></span> <span data-ttu-id="9ad96-296">Si noti che l'ora corrente viene aggiornata nel `ctlAlarmClock` <xref:System.Windows.Forms.DateTimePicker> controllo e che l'ora di inizio viene visualizzata nel controllo.</span><span class="sxs-lookup"><span data-stu-id="9ad96-296">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>

14. <span data-ttu-id="9ad96-297">Fare <xref:System.Windows.Forms.DateTimePicker> clic sul punto in cui vengono visualizzati i minuti dell'ora.</span><span class="sxs-lookup"><span data-stu-id="9ad96-297">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>

15. <span data-ttu-id="9ad96-298">Utilizzando la tastiera, impostare un valore per i minuti maggiore di un minuto rispetto all'ora corrente visualizzata da `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-298">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>

     <span data-ttu-id="9ad96-299">L'ora per l'impostazione dell'allarme è visualizzata in `lblTest`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-299">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="9ad96-300">Attendere che l'ora visualizzata raggiunga l'ora di impostazione dell'allarme.</span><span class="sxs-lookup"><span data-stu-id="9ad96-300">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="9ad96-301">Quando l'ora visualizzata raggiunge l'ora su cui è impostato l'allarme `lblAlarm` lampeggerà.</span><span class="sxs-lookup"><span data-stu-id="9ad96-301">When the displayed time reaches the time to which the alarm is set, the `lblAlarm` will flash.</span></span>

16. <span data-ttu-id="9ad96-302">Disattivare l'allarme facendo clic su `btnAlarmOff`.</span><span class="sxs-lookup"><span data-stu-id="9ad96-302">Turn off the alarm by clicking `btnAlarmOff`.</span></span> <span data-ttu-id="9ad96-303">A questo punto è possibile reimpostare l'allarme.</span><span class="sxs-lookup"><span data-stu-id="9ad96-303">You may now reset the alarm.</span></span>

<span data-ttu-id="9ad96-304">In questo articolo sono stati trattati una serie di concetti chiave.</span><span class="sxs-lookup"><span data-stu-id="9ad96-304">This article has covered a number of key concepts.</span></span> <span data-ttu-id="9ad96-305">Si è appreso come creare un controllo composito combinando controlli e componenti in un contenitore controllo composito</span><span class="sxs-lookup"><span data-stu-id="9ad96-305">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="9ad96-306">e come aggiungere proprietà al controllo e scrivere il codice per l'implementazione di funzionalità personalizzate.</span><span class="sxs-lookup"><span data-stu-id="9ad96-306">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="9ad96-307">Nell'ultima sezione sono state illustrate l'estensione delle funzionalità di uno specifico controllo composito mediante ereditarietà e la modifica delle funzionalità dei metodi host mediante override.</span><span class="sxs-lookup"><span data-stu-id="9ad96-307">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ad96-308">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ad96-308">See also</span></span>

- [<span data-ttu-id="9ad96-309">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="9ad96-309">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="9ad96-310">Procedura: visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="9ad96-310">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="9ad96-311">Procedura dettagliata: eredità da un controllo di Windows Form con Visual C#</span><span class="sxs-lookup"><span data-stu-id="9ad96-311">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
