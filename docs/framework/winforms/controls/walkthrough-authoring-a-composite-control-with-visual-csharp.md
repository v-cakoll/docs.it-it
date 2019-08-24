---
title: 'Procedura dettagliata: Modifica di un controllo composito con Visual C#'
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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d1af6c0e013f82569eed8d085df0249f4fb991bb
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015689"
---
# <a name="walkthrough-author-a-composite-control-with-c"></a><span data-ttu-id="eb190-102">Procedura dettagliata: Creare un controllo composito con C\#</span><span class="sxs-lookup"><span data-stu-id="eb190-102">Walkthrough: Author a Composite Control with C\#</span></span>

<span data-ttu-id="eb190-103">I controlli compositi consentono di creare e riutilizzare interfacce grafiche personalizzate.</span><span class="sxs-lookup"><span data-stu-id="eb190-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="eb190-104">Un controllo composito è sostanzialmente un componente con rappresentazione visiva.</span><span class="sxs-lookup"><span data-stu-id="eb190-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="eb190-105">Può essere composto da uno o più controlli per Windows Forms, componenti o blocchi di codice in grado di estenderne le funzionalità convalidando l'input dell'utente, modificando le proprietà della visualizzazione o effettuando altre attività richieste dall'autore.</span><span class="sxs-lookup"><span data-stu-id="eb190-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="eb190-106">I controlli compositi possono essere inseriti in Windows Forms al pari degli altri controlli.</span><span class="sxs-lookup"><span data-stu-id="eb190-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="eb190-107">Nella prima parte di questa procedura verrà creato un controllo composito semplice denominato `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="eb190-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="eb190-108">Nella seconda parte, le funzionalità di `ctlClock` verranno estese mediante ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="eb190-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="eb190-109">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="eb190-109">Create the Project</span></span>

<span data-ttu-id="eb190-110">Quando si crea un nuovo progetto è necessario specificarne il nome per impostare lo spazio dei nomi radice, il nome dell'assembly e il nome del progetto e assicurarsi che il componente predefinito sia inserito nello spazio dei nomi corretto.</span><span class="sxs-lookup"><span data-stu-id="eb190-110">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="eb190-111">Per creare la libreria di controlli ctlClockLib e il controllo ctlClock</span><span class="sxs-lookup"><span data-stu-id="eb190-111">To create the ctlClockLib control library and the ctlClock control</span></span>

1. <span data-ttu-id="eb190-112">In Visual Studio creare un nuovo progetto di **libreria di controllo Windows Forms** e denominarlo **ctlClockLib**.</span><span class="sxs-lookup"><span data-stu-id="eb190-112">In Visual Studio, create a new **Windows Forms Control Library** project, and name it **ctlClockLib**.</span></span>

     <span data-ttu-id="eb190-113">Per impostazione predefinita il nome del progetto, `ctlClockLib`, verrà assegnato anche allo spazio dei nomi radice.</span><span class="sxs-lookup"><span data-stu-id="eb190-113">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="eb190-114">Lo spazio dei nomi radice viene utilizzato per qualificare i nomi dei componenti dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="eb190-114">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="eb190-115">Se ad esempio due assembly forniscono componenti denominati `ctlClock`, sarà possibile specificare il componente `ctlClock` usando`ctlClockLib.ctlClock.`</span><span class="sxs-lookup"><span data-stu-id="eb190-115">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>

2. <span data-ttu-id="eb190-116">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **UserControl1.cs**e quindi scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="eb190-116">In **Solution Explorer**, right-click **UserControl1.cs**, and then click **Rename**.</span></span> <span data-ttu-id="eb190-117">Modificare il nome file in `ctlClock.cs`.</span><span class="sxs-lookup"><span data-stu-id="eb190-117">Change the file name to `ctlClock.cs`.</span></span> <span data-ttu-id="eb190-118">Scegliere il pulsante **Sì** quando richiesto per rinominare tutti i riferimenti all'elemento di codice "UserControl1".</span><span class="sxs-lookup"><span data-stu-id="eb190-118">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>

    > [!NOTE]
    > <span data-ttu-id="eb190-119">Per impostazione predefinita, un controllo composito eredita <xref:System.Windows.Forms.UserControl> dalla classe fornita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="eb190-119">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="eb190-120">La <xref:System.Windows.Forms.UserControl> classe fornisce la funzionalità richiesta da tutti i controlli compositi e implementa i metodi e le proprietà standard.</span><span class="sxs-lookup"><span data-stu-id="eb190-120">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>

3. <span data-ttu-id="eb190-121">Scegliere **Salva tutto** dal menu **File** per salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="eb190-121">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="add-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="eb190-122">Aggiungere i controlli e i componenti di Windows al controllo composito</span><span class="sxs-lookup"><span data-stu-id="eb190-122">Add Windows Controls and Components to the Composite Control</span></span>

<span data-ttu-id="eb190-123">L'interfaccia visiva è parte integrante del controllo composito</span><span class="sxs-lookup"><span data-stu-id="eb190-123">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="eb190-124">e viene implementata mediante l'aggiunta di uno o più controlli Windows nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="eb190-124">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="eb190-125">Nella procedura riportata di seguito i controlli Windows verranno incorporati nel controllo composito e verrà scritto il codice per l'implementazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="eb190-125">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>

### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="eb190-126">Per aggiungere al controllo composito un oggetto Label e un oggetto Timer</span><span class="sxs-lookup"><span data-stu-id="eb190-126">To add a Label and a Timer to your composite control</span></span>

1. <span data-ttu-id="eb190-127">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **ctlClock.cs**, quindi scegliere **Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="eb190-127">In **Solution Explorer**, right-click **ctlClock.cs**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="eb190-128">Nella **Casella degli strumenti** espandere il nodo **Controlli comuni** e fare doppio clic su **Etichetta**.</span><span class="sxs-lookup"><span data-stu-id="eb190-128">In the **Toolbox**, expand the **Common Controls** node, and then double-click **Label**.</span></span>

     <span data-ttu-id="eb190-129">Un <xref:System.Windows.Forms.Label> controllo denominato `label1` viene aggiunto al controllo nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="eb190-129">A <xref:System.Windows.Forms.Label> control named `label1` is added to your control on the designer surface.</span></span>

3. <span data-ttu-id="eb190-130">Nella finestra di progettazione fare clic su **label1**.</span><span class="sxs-lookup"><span data-stu-id="eb190-130">In the designer, click **label1**.</span></span> <span data-ttu-id="eb190-131">Nella finestra Proprietà impostare le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="eb190-131">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="eb190-132">Proprietà</span><span class="sxs-lookup"><span data-stu-id="eb190-132">Property</span></span>|<span data-ttu-id="eb190-133">Modificare in</span><span class="sxs-lookup"><span data-stu-id="eb190-133">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="eb190-134">**Nome**</span><span class="sxs-lookup"><span data-stu-id="eb190-134">**Name**</span></span>|`lblDisplay`|
    |<span data-ttu-id="eb190-135">**Text**</span><span class="sxs-lookup"><span data-stu-id="eb190-135">**Text**</span></span>|`(blank space)`|
    |<span data-ttu-id="eb190-136">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="eb190-136">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="eb190-137">**Font.Size**</span><span class="sxs-lookup"><span data-stu-id="eb190-137">**Font.Size**</span></span>|`14`|

4. <span data-ttu-id="eb190-138">Nella **Casella degli strumenti** espandere il nodo **Componenti**, quindi fare doppio clic su **Timer**.</span><span class="sxs-lookup"><span data-stu-id="eb190-138">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>

     <span data-ttu-id="eb190-139">Poiché un <xref:System.Windows.Forms.Timer> è un componente, non ha alcuna rappresentazione visiva in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="eb190-139">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="eb190-140">non verrà visualizzato insieme ai controlli nell'area di progettazione bensì in **Progettazione componenti**, una barra delle applicazioni disposta nella parte inferiore dell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="eb190-140">Therefore, it does not appear with the controls on the designer surface, but rather in the **Component Designer** (a tray at the bottom of the designer surface).</span></span>

5. <span data-ttu-id="eb190-141">In **Progettazione componenti**fare clic su **Timer1**, quindi impostare la <xref:System.Windows.Forms.Timer.Interval%2A> proprietà su `1000` e la <xref:System.Windows.Forms.Timer.Enabled%2A> proprietà su `true`.</span><span class="sxs-lookup"><span data-stu-id="eb190-141">In the **Component Designer**, click **timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>

     <span data-ttu-id="eb190-142">La <xref:System.Windows.Forms.Timer.Interval%2A> proprietà controlla la frequenza con cui il <xref:System.Windows.Forms.Timer> componente viene selezionato.</span><span class="sxs-lookup"><span data-stu-id="eb190-142">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the <xref:System.Windows.Forms.Timer> component ticks.</span></span> <span data-ttu-id="eb190-143">Ogni volta che `timer1` scatta, viene eseguito il codice nell'evento `timer1_Tick`.</span><span class="sxs-lookup"><span data-stu-id="eb190-143">Each time `timer1` ticks, it runs the code in the `timer1_Tick` event.</span></span> <span data-ttu-id="eb190-144">L'intervallo rappresenta i millesimi di secondo che intercorrono tra uno scatto e l'altro.</span><span class="sxs-lookup"><span data-stu-id="eb190-144">The interval represents the number of milliseconds between ticks.</span></span>

6. <span data-ttu-id="eb190-145">In **Progettazione componenti** fare doppio clic su **timer1** per passare all'evento di `timer1_Tick` per `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="eb190-145">In the **Component Designer**, double-click **timer1** to go to the `timer1_Tick` event for `ctlClock`.</span></span>

7. <span data-ttu-id="eb190-146">Modificare il codice in modo che risulti simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="eb190-146">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="eb190-147">Assicurarsi di cambiare il modificatore di accesso da `private` a `protected`.</span><span class="sxs-lookup"><span data-stu-id="eb190-147">Be sure to change the access modifier from `private` to `protected`.</span></span>

    ```csharp
    protected void timer1_Tick(object sender, System.EventArgs e)
    {
        // Causes the label to display the current time.
        lblDisplay.Text = DateTime.Now.ToLongTimeString();
    }
    ```

     <span data-ttu-id="eb190-148">Questo codice determinerà la visualizzazione dell'ora corrente in `lblDisplay`.</span><span class="sxs-lookup"><span data-stu-id="eb190-148">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="eb190-149">Poiché l'intervallo di `timer1` è stato impostato su `1000`, l'evento verrà generato ogni mille millesimi di secondo, aggiornando quindi l'ora corrente ogni secondo.</span><span class="sxs-lookup"><span data-stu-id="eb190-149">Because the interval of `timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>

8. <span data-ttu-id="eb190-150">Modificare il metodo in modo che sia sottoponibile a override con la parola chiave `virtual`.</span><span class="sxs-lookup"><span data-stu-id="eb190-150">Modify the method to be overridable with the `virtual` keyword.</span></span> <span data-ttu-id="eb190-151">Per ulteriori informazioni, vedere la sezione "Eredità da un controllo utente" riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="eb190-151">For more information, see the  "Inheriting from a User Control" section below.</span></span>

    ```csharp
    protected virtual void timer1_Tick(object sender, System.EventArgs e)
    ```

9. <span data-ttu-id="eb190-152">Scegliere **Salva tutto** dal menu **File** per salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="eb190-152">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="add-properties-to-the-composite-control"></a><span data-ttu-id="eb190-153">Aggiungere proprietà al controllo composito</span><span class="sxs-lookup"><span data-stu-id="eb190-153">Add Properties to the Composite Control</span></span>

<span data-ttu-id="eb190-154">Il controllo Clock incapsula ora un <xref:System.Windows.Forms.Label> controllo e un <xref:System.Windows.Forms.Timer> componente, ognuno con un proprio set di proprietà intrinseche.</span><span class="sxs-lookup"><span data-stu-id="eb190-154">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="eb190-155">Benché le singole proprietà di questi controlli non siano accessibili ai futuri utenti del controllo, è possibile creare ed esporre proprietà personalizzate scrivendo i blocchi di codice appropriati.</span><span class="sxs-lookup"><span data-stu-id="eb190-155">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="eb190-156">Nella procedura riportata di seguito verrà illustrato come aggiungere al controllo proprietà che consentono all'utente di modificare il colore dello sfondo e del testo.</span><span class="sxs-lookup"><span data-stu-id="eb190-156">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>

### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="eb190-157">Per aggiungere una proprietà al controllo composito</span><span class="sxs-lookup"><span data-stu-id="eb190-157">To add a property to your composite control</span></span>

1. <span data-ttu-id="eb190-158">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **ctlClock.cs**, quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="eb190-158">In **Solution Explorer**, right-click **ctlClock.cs**, and then click **View Code**.</span></span>

     <span data-ttu-id="eb190-159">Verrà visualizzato l'**editor del codice** per il controllo.</span><span class="sxs-lookup"><span data-stu-id="eb190-159">The **Code Editor** for your control opens.</span></span>

2. <span data-ttu-id="eb190-160">Individuare l'istruzione `public partial class ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="eb190-160">Locate the `public partial class ctlClock` statement.</span></span> <span data-ttu-id="eb190-161">Sotto la parentesi graffa aperta (`{)`, digitare il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="eb190-161">Beneath the opening brace (`{)`, type the following code.</span></span>

    ```csharp
    private Color colFColor;
    private Color colBColor;
    ```

     <span data-ttu-id="eb190-162">Queste istruzioni consentono di creare le variabili private da utilizzare per la memorizzazione dei valori delle proprietà che verranno create.</span><span class="sxs-lookup"><span data-stu-id="eb190-162">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>

3. <span data-ttu-id="eb190-163">Immettere o incollare il codice seguente sotto le dichiarazioni delle variabili del passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="eb190-163">Enter or paste the following code beneath the variable declarations from step 2.</span></span>

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

     <span data-ttu-id="eb190-164">Nel codice riportato in precedenza vengono create due proprietà personalizzate, `ClockForeColor` e `ClockBackColor`, disponibili agli utenti successivi del controllo.</span><span class="sxs-lookup"><span data-stu-id="eb190-164">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control.</span></span> <span data-ttu-id="eb190-165">Le istruzioni `get` e `set` consentono di archiviare e recuperare il valore della proprietà e di inserire il codice per implementare le funzionalità appropriate per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="eb190-165">The `get` and `set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>

4. <span data-ttu-id="eb190-166">Scegliere **Salva tutto** dal menu **File** per salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="eb190-166">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="test-the-control"></a><span data-ttu-id="eb190-167">Testare il controllo</span><span class="sxs-lookup"><span data-stu-id="eb190-167">Test the Control</span></span>

<span data-ttu-id="eb190-168">I controlli non sono applicazioni autonome e devono pertanto essere inseriti in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="eb190-168">Controls are not stand-alone applications; they must be hosted in a container.</span></span> <span data-ttu-id="eb190-169">Eseguire il test del comportamento del controllo in fase di esecuzione e sperimentare le proprietà con **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="eb190-169">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="eb190-170">Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di un](how-to-test-the-run-time-behavior-of-a-usercontrol.md)UserControl.</span><span class="sxs-lookup"><span data-stu-id="eb190-170">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

### <a name="to-test-your-control"></a><span data-ttu-id="eb190-171">Per eseguire il test del controllo</span><span class="sxs-lookup"><span data-stu-id="eb190-171">To test your control</span></span>

1. <span data-ttu-id="eb190-172">Premere **F5** per compilare il progetto ed eseguire il controllo in **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="eb190-172">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="eb190-173">Nella griglia della proprietà di Test Container, selezionare la proprietà `ClockBackColor`, quindi fare clic sulla freccia a discesa per visualizzare la tavolozza dei colori.</span><span class="sxs-lookup"><span data-stu-id="eb190-173">In the test container's property grid, locate the `ClockBackColor` property, and then select the property to display the color palette.</span></span>

3. <span data-ttu-id="eb190-174">Scegliere un colore facendovi clic sopra.</span><span class="sxs-lookup"><span data-stu-id="eb190-174">Choose a color by clicking it.</span></span>

   <span data-ttu-id="eb190-175">Il colore di sfondo del controllo cambierà in base al colore selezionato.</span><span class="sxs-lookup"><span data-stu-id="eb190-175">The background color of your control changes to the color you selected.</span></span>

4. <span data-ttu-id="eb190-176">Usare una sequenza di eventi simile per verificare il corretto funzionamento della proprietà `ClockForeColor`.</span><span class="sxs-lookup"><span data-stu-id="eb190-176">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>

   <span data-ttu-id="eb190-177">In questa sezione e in quelle precedenti è stato illustrato come combinare componenti e controlli Windows con codici e package per aggiungere funzionalità personalizzate al modulo di un controllo composito.</span><span class="sxs-lookup"><span data-stu-id="eb190-177">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="eb190-178">Si è inoltre appreso come esporre le proprietà del controllo composito e come eseguire il test del controllo dopo averlo completato.</span><span class="sxs-lookup"><span data-stu-id="eb190-178">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="eb190-179">Nella sezione successiva verranno fornite informazioni sulla modalità di creazione di un controllo composito ereditato utilizzando `ctlClock` come base.</span><span class="sxs-lookup"><span data-stu-id="eb190-179">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>

## <a name="inherit-from-a-composite-control"></a><span data-ttu-id="eb190-180">Ereditare da un controllo composito</span><span class="sxs-lookup"><span data-stu-id="eb190-180">Inherit from a Composite Control</span></span>

<span data-ttu-id="eb190-181">Nelle sezioni precedenti si è appreso come combinare controlli, componenti e codice Windows in controlli compositi riutilizzabili.</span><span class="sxs-lookup"><span data-stu-id="eb190-181">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="eb190-182">Il controllo composito può ora essere usato come base per la compilazione di altri controlli.</span><span class="sxs-lookup"><span data-stu-id="eb190-182">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="eb190-183">Il processo di derivazione di una classe da una classe di base è detto *ereditarietà*.</span><span class="sxs-lookup"><span data-stu-id="eb190-183">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="eb190-184">In questa sezione verrà creato un controllo composito denominato `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="eb190-184">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="eb190-185">Il controllo verrà derivato dal relativo controllo padre, in questo caso `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="eb190-185">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="eb190-186">Verrà spiegato come estendere le funzionalità di `ctlClock` mediante l'override dei metodi padre e l'aggiunta di nuovi metodi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="eb190-186">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>

<span data-ttu-id="eb190-187">Per creare un controllo ereditato, è innanzitutto necessario derivare il controllo dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="eb190-187">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="eb190-188">Questa operazione consente di creare un nuovo controllo, con le stesse proprietà, metodi e caratteristiche grafiche del controllo padre, che può essere anche utilizzato come base per l'aggiunta di una funzionalità nuova o modificata.</span><span class="sxs-lookup"><span data-stu-id="eb190-188">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>

### <a name="to-create-the-inherited-control"></a><span data-ttu-id="eb190-189">Per creare il controllo ereditato</span><span class="sxs-lookup"><span data-stu-id="eb190-189">To create the inherited control</span></span>

1. <span data-ttu-id="eb190-190">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **CtlClockLib**, scegliere **Aggiungi**, quindi fare clic su **controllo utente**.</span><span class="sxs-lookup"><span data-stu-id="eb190-190">In **Solution Explorer**, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>

     <span data-ttu-id="eb190-191">Viene aperta la finestra di dialogo **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="eb190-191">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="eb190-192">Selezionare il modello **Controllo utente ereditato**.</span><span class="sxs-lookup"><span data-stu-id="eb190-192">Select the **Inherited User Control** template.</span></span>

3. <span data-ttu-id="eb190-193">Nella casella **Nome** digitare `ctlAlarmClock.cs` e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="eb190-193">In the **Name** box, type `ctlAlarmClock.cs`, and then click **Add**.</span></span>

     <span data-ttu-id="eb190-194">Viene visualizzata la finestra di dialogo **Selezione ereditarietà**.</span><span class="sxs-lookup"><span data-stu-id="eb190-194">The **Inheritance Picker** dialog box appears.</span></span>

4. <span data-ttu-id="eb190-195">In **Nome componente** fare doppio clic su **ctlClock**.</span><span class="sxs-lookup"><span data-stu-id="eb190-195">Under **Component Name**, double-click **ctlClock**.</span></span>

5. <span data-ttu-id="eb190-196">In **Esplora soluzioni**esplorare i progetti correnti.</span><span class="sxs-lookup"><span data-stu-id="eb190-196">In **Solution Explorer**, browse through the current projects.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eb190-197">Nel progetto corrente è stato aggiunto il file denominato **ctlAlarmClock.cs**.</span><span class="sxs-lookup"><span data-stu-id="eb190-197">A file called **ctlAlarmClock.cs** has been added to the current project.</span></span>

### <a name="add-the-alarm-properties"></a><span data-ttu-id="eb190-198">Aggiungere le proprietà dell'allarme</span><span class="sxs-lookup"><span data-stu-id="eb190-198">Add the Alarm Properties</span></span>

<span data-ttu-id="eb190-199">Le modalità di aggiunta delle proprietà a un controllo ereditato sono analoghe a quelle utilizzate per i controlli compositi.</span><span class="sxs-lookup"><span data-stu-id="eb190-199">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="eb190-200">Mediante la sintassi di dichiarazione delle proprietà si aggiungeranno ora al controllo due proprietà: `AlarmTime`, in cui viene memorizzato il valore della data e dell'ora in cui l'allarme deve essere disattivato, e `AlarmSet`, che indica se l'allarme è impostato o meno.</span><span class="sxs-lookup"><span data-stu-id="eb190-200">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>

#### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="eb190-201">Per aggiungere proprietà al controllo composito</span><span class="sxs-lookup"><span data-stu-id="eb190-201">To add properties to your composite control</span></span>

1. <span data-ttu-id="eb190-202">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **ctlAlarmClock**, quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="eb190-202">In **Solution Explorer**, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>

2. <span data-ttu-id="eb190-203">Individuare l'istruzione `public class`.</span><span class="sxs-lookup"><span data-stu-id="eb190-203">Locate the `public class` statement.</span></span> <span data-ttu-id="eb190-204">Si noti che il controllo eredita da `ctlClockLib.ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="eb190-204">Note that your control inherits from `ctlClockLib.ctlClock`.</span></span> <span data-ttu-id="eb190-205">Sotto la parentesi graffa aperta (`{)`, digitare il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="eb190-205">Beneath the opening brace (`{)` statement, type the following code.</span></span>

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

### <a name="add-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="eb190-206">Aggiungere all'interfaccia grafica del controllo</span><span class="sxs-lookup"><span data-stu-id="eb190-206">Add to the Graphical Interface of the Control</span></span>

<span data-ttu-id="eb190-207">Il controllo ereditato presenta un'interfaccia grafica identica a quella del controllo dal quale eredita</span><span class="sxs-lookup"><span data-stu-id="eb190-207">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="eb190-208">e possiede gli stessi controlli costitutivi del controllo padre, ma le proprietà dei controlli costitutivi non sono disponibili, a meno che non siano state specificamente esposte.</span><span class="sxs-lookup"><span data-stu-id="eb190-208">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="eb190-209">Analogamente a qualsiasi altro controllo composito, è possibile aggiungere elementi all'interfaccia grafica di un controllo composito ereditato, utilizzando la medesima procedura.</span><span class="sxs-lookup"><span data-stu-id="eb190-209">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="eb190-210">In questo esempio verrà utilizzato un controllo label per aggiungere un effetto intermittente all'interfaccia grafica del controllo quando l'allarme suona.</span><span class="sxs-lookup"><span data-stu-id="eb190-210">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>

#### <a name="to-add-the-label-control"></a><span data-ttu-id="eb190-211">Per aggiungere il controllo label</span><span class="sxs-lookup"><span data-stu-id="eb190-211">To add the label control</span></span>

1. <span data-ttu-id="eb190-212">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **ctlAlarmClock**, quindi scegliere **Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="eb190-212">In **Solution Explorer**, right-click **ctlAlarmClock**, and then click **View Designer**.</span></span>

     <span data-ttu-id="eb190-213">Nella finestra principale viene aperta la finestra di progettazione per `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="eb190-213">The designer for `ctlAlarmClock` opens in the main window.</span></span>

2. <span data-ttu-id="eb190-214">Fare clic sulla parte visualizzata del controllo e osservare la finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="eb190-214">Click the display portion of the control, and view the Properties window.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eb190-215">Tutte le proprietà sono presenti ma inattive, ossia visualizzate in grigio.</span><span class="sxs-lookup"><span data-stu-id="eb190-215">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="eb190-216">Ciò indica che le proprietà sono native di `lblDisplay` e non è possibile accedervi né modificarle nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="eb190-216">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="eb190-217">Per impostazione predefinita i controlli contenuti in un controllo composito sono `private` e le relative proprietà non sono accessibili.</span><span class="sxs-lookup"><span data-stu-id="eb190-217">By default, controls contained in a composite control are `private`, and their properties are not accessible by any means.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eb190-218">Se si desidera che gli utenti successivi del controllo composito abbiano accesso ai relativi controlli interni, dichiararli come `public` o `protected`.</span><span class="sxs-lookup"><span data-stu-id="eb190-218">If you want subsequent users of your composite control to have access to its internal controls, declare them as `public` or `protected`.</span></span> <span data-ttu-id="eb190-219">Sarà così possibile impostare e modificare le proprietà dei controlli contenuti nel controllo composito mediante il codice appropriato.</span><span class="sxs-lookup"><span data-stu-id="eb190-219">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>

3. <span data-ttu-id="eb190-220">Aggiungere un <xref:System.Windows.Forms.Label> controllo al controllo composito.</span><span class="sxs-lookup"><span data-stu-id="eb190-220">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>

4. <span data-ttu-id="eb190-221">Usando il mouse, trascinare il <xref:System.Windows.Forms.Label> controllo immediatamente sotto la casella di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="eb190-221">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="eb190-222">Nella finestra Proprietà impostare le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="eb190-222">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="eb190-223">Proprietà</span><span class="sxs-lookup"><span data-stu-id="eb190-223">Property</span></span>|<span data-ttu-id="eb190-224">Impostazione</span><span class="sxs-lookup"><span data-stu-id="eb190-224">Setting</span></span>|
    |--------------|-------------|
    |<span data-ttu-id="eb190-225">**Nome**</span><span class="sxs-lookup"><span data-stu-id="eb190-225">**Name**</span></span>|`lblAlarm`|
    |<span data-ttu-id="eb190-226">**Text**</span><span class="sxs-lookup"><span data-stu-id="eb190-226">**Text**</span></span>|<span data-ttu-id="eb190-227">**Allarme!**</span><span class="sxs-lookup"><span data-stu-id="eb190-227">**Alarm!**</span></span>|
    |<span data-ttu-id="eb190-228">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="eb190-228">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="eb190-229">**Visible**</span><span class="sxs-lookup"><span data-stu-id="eb190-229">**Visible**</span></span>|`false`|

### <a name="add-the-alarm-functionality"></a><span data-ttu-id="eb190-230">Aggiungere la funzionalità di allarme</span><span class="sxs-lookup"><span data-stu-id="eb190-230">Add the Alarm Functionality</span></span>

<span data-ttu-id="eb190-231">Nelle procedure precedenti sono state aggiunte proprietà e un controllo in grado di abilitare la funzionalità di allarme nel controllo composito.</span><span class="sxs-lookup"><span data-stu-id="eb190-231">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="eb190-232">In questa procedura verrà aggiunto un codice che consente di confrontare l'ora corrente con l'ora dell'allarme e, se le ore risultano identiche, attivare un allarme lampeggiante.</span><span class="sxs-lookup"><span data-stu-id="eb190-232">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to flash an alarm.</span></span> <span data-ttu-id="eb190-233">Eseguendo l'override del metodo `timer1_Tick` di `ctlClock` e aggiungendovi ulteriore codice sarà possibile estendere le capacità di `ctlAlarmClock` e conservare allo stesso le funzionalità intrinseche di `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="eb190-233">By overriding the `timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>

#### <a name="to-override-the-timer1_tick-method-of-ctlclock"></a><span data-ttu-id="eb190-234">Per eseguire l'override del metodo Timer1_Tick di ctlClock</span><span class="sxs-lookup"><span data-stu-id="eb190-234">To override the timer1_Tick method of ctlClock</span></span>

1. <span data-ttu-id="eb190-235">Nell'**editor di codice**  individuare l'istruzione `private bool blnAlarmSet;`</span><span class="sxs-lookup"><span data-stu-id="eb190-235">In the **Code Editor**, locate the `private bool blnAlarmSet;` statement.</span></span> <span data-ttu-id="eb190-236">e aggiungere subito dopo la seguente istruzione.</span><span class="sxs-lookup"><span data-stu-id="eb190-236">Immediately beneath it, add the following statement.</span></span>

    ```csharp
    private bool blnColorTicker;
    ```

2. <span data-ttu-id="eb190-237">Nell'**editor di codice** individuare la parentesi graffa di chiusura (`})`) alla fine della classe.</span><span class="sxs-lookup"><span data-stu-id="eb190-237">In the **Code Editor**, locate the closing brace (`})` at the end of the class.</span></span> <span data-ttu-id="eb190-238">Aggiungere il seguente codice prima della parentesi graffa.</span><span class="sxs-lookup"><span data-stu-id="eb190-238">Just before the brace, add the following code.</span></span>

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

     <span data-ttu-id="eb190-239">Il codice appena aggiunto ha diverse funzioni.</span><span class="sxs-lookup"><span data-stu-id="eb190-239">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="eb190-240">Se si utilizza l'istruzione `override`, il controllo utilizzerà questo metodo anziché il metodo ereditato dal controllo di base.</span><span class="sxs-lookup"><span data-stu-id="eb190-240">The `override` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="eb190-241">Una volta chiamato, questo metodo chiamerà il metodo di cui esegue l'override utilizzando l'istruzione `base.timer1_Tick` e assicurando che tutte le funzionalità incorporate nel controllo originale vengano riprodotte in questo controllo.</span><span class="sxs-lookup"><span data-stu-id="eb190-241">When this method is called, it calls the method it overrides by invoking the `base.timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="eb190-242">Verrà quindi eseguito il codice aggiuntivo per incorporare la funzionalità di allarme.</span><span class="sxs-lookup"><span data-stu-id="eb190-242">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="eb190-243">Quando l'allarme viene attivato, verrà visualizzato un controllo label intermittente.</span><span class="sxs-lookup"><span data-stu-id="eb190-243">A flashing label control will appear when the alarm occurs.</span></span>

     <span data-ttu-id="eb190-244">Il controllo dell'allarme è quasi completo.</span><span class="sxs-lookup"><span data-stu-id="eb190-244">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="eb190-245">L'unica operazione rimasta è l'implementazione di un sistema di disattivazione.</span><span class="sxs-lookup"><span data-stu-id="eb190-245">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="eb190-246">A tal fine, è necessario aggiungere codice al metodo `lblAlarm_Click`.</span><span class="sxs-lookup"><span data-stu-id="eb190-246">To do this, you will add code to the `lblAlarm_Click` method.</span></span>

#### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="eb190-247">Per implementare il metodo di disattivazione</span><span class="sxs-lookup"><span data-stu-id="eb190-247">To implement the shutoff method</span></span>

1. <span data-ttu-id="eb190-248">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **ctlAlarmClock.cs**, quindi scegliere **Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="eb190-248">In **Solution Explorer**, right-click **ctlAlarmClock.cs**, and then click **View Designer**.</span></span>

     <span data-ttu-id="eb190-249">Viene aperta la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="eb190-249">The designer opens.</span></span>

2. <span data-ttu-id="eb190-250">Aggiungere un pulsante al controllo.</span><span class="sxs-lookup"><span data-stu-id="eb190-250">Add a button to the control.</span></span> <span data-ttu-id="eb190-251">Impostare le proprietà del pulsante come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="eb190-251">Set the properties of the button as follows.</span></span>

    |<span data-ttu-id="eb190-252">Proprietà</span><span class="sxs-lookup"><span data-stu-id="eb190-252">Property</span></span>|<span data-ttu-id="eb190-253">Valore</span><span class="sxs-lookup"><span data-stu-id="eb190-253">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="eb190-254">**Nome**</span><span class="sxs-lookup"><span data-stu-id="eb190-254">**Name**</span></span>|`btnAlarmOff`|
    |<span data-ttu-id="eb190-255">**Text**</span><span class="sxs-lookup"><span data-stu-id="eb190-255">**Text**</span></span>|<span data-ttu-id="eb190-256">**Disabilita allarme**</span><span class="sxs-lookup"><span data-stu-id="eb190-256">**Disable Alarm**</span></span>|

3. <span data-ttu-id="eb190-257">Nella finestra di progettazione fare doppio clic su **btnAlarmOff**.</span><span class="sxs-lookup"><span data-stu-id="eb190-257">In the designer, double-click **btnAlarmOff**.</span></span>

     <span data-ttu-id="eb190-258">Nell'**editor di codice** verrà visualizzata la riga `private void btnAlarmOff_Click`.</span><span class="sxs-lookup"><span data-stu-id="eb190-258">The **Code Editor** opens to the `private void btnAlarmOff_Click` line.</span></span>

4. <span data-ttu-id="eb190-259">Modificare il metodo in modo che risulti simile al seguente codice.</span><span class="sxs-lookup"><span data-stu-id="eb190-259">Modify this method so that it resembles the following code.</span></span>

    ```csharp
    private void btnAlarmOff_Click(object sender, System.EventArgs e)
    {
        // Turns off the alarm.
        AlarmSet = false;
        // Hides the flashing label.
        lblAlarm.Visible = false;
    }
    ```

5. <span data-ttu-id="eb190-260">Scegliere **Salva tutto** dal menu **File** per salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="eb190-260">On the **File** menu, click **Save All** to save the project.</span></span>

### <a name="use-the-inherited-control-on-a-form"></a><span data-ttu-id="eb190-261">Usare il controllo ereditato in un form</span><span class="sxs-lookup"><span data-stu-id="eb190-261">Use the Inherited Control on a Form</span></span>

<span data-ttu-id="eb190-262">È possibile testare il controllo ereditato nello stesso modo in cui è stato testato il controllo `ctlClock`della classe base: Premere **F5** per compilare il progetto ed eseguire il controllo in **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="eb190-262">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="eb190-263">Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di un](how-to-test-the-run-time-behavior-of-a-usercontrol.md)UserControl.</span><span class="sxs-lookup"><span data-stu-id="eb190-263">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

<span data-ttu-id="eb190-264">Per utilizzare il controllo è necessario inserirlo in un modulo.</span><span class="sxs-lookup"><span data-stu-id="eb190-264">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="eb190-265">Come i controlli compositi standard, i controlli compositi ereditati non possono essere autonomi e devono essere inclusi in un modulo o in un altro contenitore.</span><span class="sxs-lookup"><span data-stu-id="eb190-265">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="eb190-266">Poiché `ctlAlarmClock` include un maggior numero di funzionalità, per eseguire il test è necessario aggiungere del codice.</span><span class="sxs-lookup"><span data-stu-id="eb190-266">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="eb190-267">In questa procedura verrà scritto un semplice programma per la verifica delle funzionalità di `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="eb190-267">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="eb190-268">Verrà inoltre scritto il codice per impostare e visualizzare la proprietà `AlarmTime` di `ctlAlarmClock` e verrà eseguito il test delle funzionalità intrinseche del controllo.</span><span class="sxs-lookup"><span data-stu-id="eb190-268">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>

#### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="eb190-269">Per compilare e aggiungere il controllo a un modulo di test</span><span class="sxs-lookup"><span data-stu-id="eb190-269">To build and add your control to a test form</span></span>

1. <span data-ttu-id="eb190-270">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **ctlClockLib**e quindi scegliere **Compila**.</span><span class="sxs-lookup"><span data-stu-id="eb190-270">In **Solution Explorer**, right-click **ctlClockLib**, and then click **Build**.</span></span>

2. <span data-ttu-id="eb190-271">Aggiungere un nuovo progetto di **applicazione Windows** alla soluzione e denominarlo **test**.</span><span class="sxs-lookup"><span data-stu-id="eb190-271">Add a new **Windows Application** project to the solution, and name it **Test**.</span></span>

3. <span data-ttu-id="eb190-272">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nodo **riferimenti** per il progetto di test.</span><span class="sxs-lookup"><span data-stu-id="eb190-272">In **Solution Explorer**, right-click the **References** node for your test project.</span></span> <span data-ttu-id="eb190-273">Fare clic su **Aggiungi riferimento** per visualizzare la finestra di dialogo **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="eb190-273">Click **Add Reference** to display the **Add Reference** dialog box.</span></span> <span data-ttu-id="eb190-274">Scegliere la scheda **Progetti**.</span><span class="sxs-lookup"><span data-stu-id="eb190-274">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="eb190-275">Il progetto `ctlClockLib` verrà elencato in **Nome progetto**.</span><span class="sxs-lookup"><span data-stu-id="eb190-275">Your `ctlClockLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="eb190-276">Fare doppio clic sul progetto per cui si desidera aggiungere il riferimento al progetto di test.</span><span class="sxs-lookup"><span data-stu-id="eb190-276">Double-click the project to add the reference to the test project.</span></span>

4. <span data-ttu-id="eb190-277">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **test**, quindi scegliere **Compila**.</span><span class="sxs-lookup"><span data-stu-id="eb190-277">In **Solution Explorer**, right-click **Test**, and then click **Build**.</span></span>

5. <span data-ttu-id="eb190-278">Nella **Casella degli strumenti** espandere il nodo **Componenti ctlClockLib**.</span><span class="sxs-lookup"><span data-stu-id="eb190-278">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>

6. <span data-ttu-id="eb190-279">Fare doppio clic su **ctlAlarmClock** per aggiungere una copia di `ctlAlarmClock` al modulo.</span><span class="sxs-lookup"><span data-stu-id="eb190-279">Double-click **ctlAlarmClock** to add a copy of `ctlAlarmClock` to your form.</span></span>

7. <span data-ttu-id="eb190-280">Nella **casella degli strumenti**individuare e fare doppio clic su **DateTimePicker** per aggiungere <xref:System.Windows.Forms.DateTimePicker> un controllo al form, quindi aggiungere un <xref:System.Windows.Forms.Label> controllo facendo doppio clic su **etichetta**.</span><span class="sxs-lookup"><span data-stu-id="eb190-280">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>

8. <span data-ttu-id="eb190-281">Posizionare mediante il mouse i controlli in un punto del modulo di facile accesso.</span><span class="sxs-lookup"><span data-stu-id="eb190-281">Use the mouse to position the controls in a convenient place on the form.</span></span>

9. <span data-ttu-id="eb190-282">Impostare le proprietà dei controlli come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="eb190-282">Set the properties of these controls in the following manner.</span></span>

    |<span data-ttu-id="eb190-283">Control</span><span class="sxs-lookup"><span data-stu-id="eb190-283">Control</span></span>|<span data-ttu-id="eb190-284">Proprietà</span><span class="sxs-lookup"><span data-stu-id="eb190-284">Property</span></span>|<span data-ttu-id="eb190-285">Value</span><span class="sxs-lookup"><span data-stu-id="eb190-285">Value</span></span>|
    |-------------|--------------|-----------|
    |`label1`|<span data-ttu-id="eb190-286">**Text**</span><span class="sxs-lookup"><span data-stu-id="eb190-286">**Text**</span></span>|`(blank space)`|
    ||<span data-ttu-id="eb190-287">**Nome**</span><span class="sxs-lookup"><span data-stu-id="eb190-287">**Name**</span></span>|`lblTest`|
    |`dateTimePicker1`|<span data-ttu-id="eb190-288">**Nome**</span><span class="sxs-lookup"><span data-stu-id="eb190-288">**Name**</span></span>|`dtpTest`|
    ||<span data-ttu-id="eb190-289">**Format**</span><span class="sxs-lookup"><span data-stu-id="eb190-289">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|

10. <span data-ttu-id="eb190-290">Nella finestra di progettazione fare doppio clic su **dtpTest**.</span><span class="sxs-lookup"><span data-stu-id="eb190-290">In the designer, double-click **dtpTest**.</span></span>

     <span data-ttu-id="eb190-291">Nell'**Editor di codice** viene visualizzato `private void dtpTest_ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="eb190-291">The **Code Editor** opens to `private void dtpTest_ValueChanged`.</span></span>

11. <span data-ttu-id="eb190-292">Modificare il codice in modo che risulti simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="eb190-292">Modify the code so that it resembles the following.</span></span>

    ```csharp
    private void dtpTest_ValueChanged(object sender, System.EventArgs e)
    {
        ctlAlarmClock1.AlarmTime = dtpTest.Value;
        ctlAlarmClock1.AlarmSet = true;
        lblTest.Text = "Alarm Time is " +
            ctlAlarmClock1.AlarmTime.ToShortTimeString();
    }
    ```

12. <span data-ttu-id="eb190-293">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **test**, quindi scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="eb190-293">In **Solution Explorer**, right-click **Test**, and then click **Set as StartUp Project**.</span></span>

13. <span data-ttu-id="eb190-294">Scegliere **Avvia debug** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="eb190-294">On the **Debug** menu, click **Start Debugging**.</span></span>

     <span data-ttu-id="eb190-295">Verrà avviato il programma di test.</span><span class="sxs-lookup"><span data-stu-id="eb190-295">The test program starts.</span></span> <span data-ttu-id="eb190-296">Si noti che l'ora corrente viene aggiornata nel `ctlAlarmClock` controllo e che l'ora di inizio viene visualizzata <xref:System.Windows.Forms.DateTimePicker> nel controllo.</span><span class="sxs-lookup"><span data-stu-id="eb190-296">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>

14. <span data-ttu-id="eb190-297">Fare clic <xref:System.Windows.Forms.DateTimePicker> sul punto in cui vengono visualizzati i minuti dell'ora.</span><span class="sxs-lookup"><span data-stu-id="eb190-297">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>

15. <span data-ttu-id="eb190-298">Utilizzando la tastiera, impostare un valore per i minuti maggiore di un minuto rispetto all'ora corrente visualizzata da `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="eb190-298">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>

     <span data-ttu-id="eb190-299">L'ora per l'impostazione dell'allarme è visualizzata in `lblTest`.</span><span class="sxs-lookup"><span data-stu-id="eb190-299">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="eb190-300">Attendere che l'ora visualizzata raggiunga l'ora di impostazione dell'allarme.</span><span class="sxs-lookup"><span data-stu-id="eb190-300">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="eb190-301">Quando l'ora visualizzata raggiunge l'ora su cui è impostato l'allarme `lblAlarm` lampeggerà.</span><span class="sxs-lookup"><span data-stu-id="eb190-301">When the displayed time reaches the time to which the alarm is set, the `lblAlarm` will flash.</span></span>

16. <span data-ttu-id="eb190-302">Disattivare l'allarme facendo clic su `btnAlarmOff`.</span><span class="sxs-lookup"><span data-stu-id="eb190-302">Turn off the alarm by clicking `btnAlarmOff`.</span></span> <span data-ttu-id="eb190-303">A questo punto è possibile reimpostare l'allarme.</span><span class="sxs-lookup"><span data-stu-id="eb190-303">You may now reset the alarm.</span></span>

<span data-ttu-id="eb190-304">Questo articolo ha trattato diversi concetti chiave.</span><span class="sxs-lookup"><span data-stu-id="eb190-304">This article has covered a number of key concepts.</span></span> <span data-ttu-id="eb190-305">Si è appreso come creare un controllo composito combinando controlli e componenti in un contenitore controllo composito</span><span class="sxs-lookup"><span data-stu-id="eb190-305">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="eb190-306">e come aggiungere proprietà al controllo e scrivere il codice per l'implementazione di funzionalità personalizzate.</span><span class="sxs-lookup"><span data-stu-id="eb190-306">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="eb190-307">Nell'ultima sezione sono state illustrate l'estensione delle funzionalità di uno specifico controllo composito mediante ereditarietà e la modifica delle funzionalità dei metodi host mediante override.</span><span class="sxs-lookup"><span data-stu-id="eb190-307">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb190-308">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb190-308">See also</span></span>

- [<span data-ttu-id="eb190-309">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="eb190-309">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="eb190-310">Procedura: Visualizza un controllo nella finestra di dialogo Scegli elementi della casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="eb190-310">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="eb190-311">Procedura dettagliata: Eredità da un controllo Windows Forms con VisualC#</span><span class="sxs-lookup"><span data-stu-id="eb190-311">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
