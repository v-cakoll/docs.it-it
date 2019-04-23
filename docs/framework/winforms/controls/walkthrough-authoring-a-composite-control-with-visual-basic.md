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
ms.openlocfilehash: 6404e5933f886578b4ad8afd0d3da324541fc3f9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59299982"
---
# <a name="walkthrough-authoring-a-composite-control-with-visual-basic"></a><span data-ttu-id="188de-102">Procedura dettagliata: Creazione di un controllo composito con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="188de-102">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>
<span data-ttu-id="188de-103">I controlli compositi consentono di creare e riutilizzare interfacce grafiche personalizzate.</span><span class="sxs-lookup"><span data-stu-id="188de-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="188de-104">Un controllo composito è sostanzialmente un componente con rappresentazione visiva.</span><span class="sxs-lookup"><span data-stu-id="188de-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="188de-105">Può essere composto da uno o più controlli per Windows Forms, componenti o blocchi di codice in grado di estenderne le funzionalità convalidando l'input dell'utente, modificando le proprietà della visualizzazione o effettuando altre attività richieste dall'autore.</span><span class="sxs-lookup"><span data-stu-id="188de-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="188de-106">I controlli compositi possono essere inseriti in Windows Forms al pari degli altri controlli.</span><span class="sxs-lookup"><span data-stu-id="188de-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="188de-107">Nella prima parte di questa procedura verrà creato un controllo composito semplice denominato `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="188de-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="188de-108">Nella seconda parte, le funzionalità di `ctlClock` verranno estese mediante ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="188de-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="188de-109">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="188de-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="188de-110">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="188de-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="188de-111">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="188de-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="188de-112">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="188de-112">Creating the Project</span></span>  
 <span data-ttu-id="188de-113">Quando si crea un nuovo progetto è necessario specificarne il nome per impostare lo spazio dei nomi radice, il nome dell'assembly e il nome del progetto e assicurarsi che il componente predefinito sia inserito nello spazio dei nomi corretto.</span><span class="sxs-lookup"><span data-stu-id="188de-113">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>  
  
#### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="188de-114">Per creare la libreria di controlli ctlClockLib e il controllo ctlClock</span><span class="sxs-lookup"><span data-stu-id="188de-114">To create the ctlClockLib control library and the ctlClock control</span></span>  
  
1. <span data-ttu-id="188de-115">Scegliere **Nuovo** dal menu **File**, quindi selezionare **Progetto** per aprire la finestra di dialogo **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="188de-115">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2. <span data-ttu-id="188de-116">Nell'elenco dei progetti Visual Basic, selezionare la **libreria di controlli Windows** modello di progetto, digitare `ctlClockLib` nel **Name** casella e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="188de-116">From the list of Visual Basic projects, select the **Windows Control Library** project template, type `ctlClockLib` in the **Name** box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="188de-117">Per impostazione predefinita il nome del progetto, `ctlClockLib`, verrà assegnato anche allo spazio dei nomi radice.</span><span class="sxs-lookup"><span data-stu-id="188de-117">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="188de-118">Lo spazio dei nomi radice viene utilizzato per qualificare i nomi dei componenti dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="188de-118">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="188de-119">Se ad esempio due assembly forniscono componenti denominati `ctlClock`, sarà possibile specificare il componente `ctlClock` usando`ctlClockLib.ctlClock.`</span><span class="sxs-lookup"><span data-stu-id="188de-119">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>  
  
3. <span data-ttu-id="188de-120">In Esplora soluzioni fare clic con il pulsante destro del mouse su **UserControl1.vb**, quindi fare clic su **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="188de-120">In Solution Explorer, right-click **UserControl1.vb**, and then click **Rename**.</span></span> <span data-ttu-id="188de-121">Modificare il nome file in `ctlClock.vb`.</span><span class="sxs-lookup"><span data-stu-id="188de-121">Change the file name to `ctlClock.vb`.</span></span> <span data-ttu-id="188de-122">Scegliere il pulsante **Sì** quando richiesto per rinominare tutti i riferimenti all'elemento di codice "UserControl1".</span><span class="sxs-lookup"><span data-stu-id="188de-122">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="188de-123">Per impostazione predefinita, un controllo composito eredita il <xref:System.Windows.Forms.UserControl> classe fornita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="188de-123">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="188de-124">Il <xref:System.Windows.Forms.UserControl> classe fornisce le funzionalità richieste da tutti i controlli compositi e implementa proprietà e metodi standard.</span><span class="sxs-lookup"><span data-stu-id="188de-124">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>  
  
4. <span data-ttu-id="188de-125">Scegliere **Salva tutto** dal menu **File** per salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="188de-125">On the **File** menu, click **Save All** to save the project.</span></span>  
  
## <a name="adding-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="188de-126">Aggiunta di componenti e controlli Windows al controllo composito</span><span class="sxs-lookup"><span data-stu-id="188de-126">Adding Windows Controls and Components to the Composite Control</span></span>  
 <span data-ttu-id="188de-127">L'interfaccia visiva è parte integrante del controllo composito</span><span class="sxs-lookup"><span data-stu-id="188de-127">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="188de-128">e viene implementata mediante l'aggiunta di uno o più controlli Windows nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="188de-128">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="188de-129">Nella procedura riportata di seguito i controlli Windows verranno incorporati nel controllo composito e verrà scritto il codice per l'implementazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="188de-129">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>  
  
#### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="188de-130">Per aggiungere al controllo composito un oggetto Label e un oggetto Timer</span><span class="sxs-lookup"><span data-stu-id="188de-130">To add a Label and a Timer to your composite control</span></span>  
  
1. <span data-ttu-id="188de-131">In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlClock.vb**, quindi scegliere **Progettazione viste**.</span><span class="sxs-lookup"><span data-stu-id="188de-131">In Solution Explorer, right-click **ctlClock.vb**, and then click **View Designer**.</span></span>  
  
2. <span data-ttu-id="188de-132">Nella Casella degli strumenti espandere il nodo **Controlli comuni** e fare doppio clic su **Etichetta**.</span><span class="sxs-lookup"><span data-stu-id="188de-132">In the Toolbox, expand the **Common Controls** node, and then double-click **Label**.</span></span>  
  
     <span data-ttu-id="188de-133">Oggetto <xref:System.Windows.Forms.Label> controllo denominato `Label1` viene aggiunto al controllo nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="188de-133">A <xref:System.Windows.Forms.Label> control named `Label1` is added to your control on the designer surface.</span></span>  
  
3. <span data-ttu-id="188de-134">Nella finestra di progettazione fare clic su **Label1**.</span><span class="sxs-lookup"><span data-stu-id="188de-134">In the designer, click **Label1**.</span></span> <span data-ttu-id="188de-135">Nella finestra Proprietà impostare le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="188de-135">In the Properties window, set the following properties.</span></span>  
  
    |<span data-ttu-id="188de-136">Proprietà</span><span class="sxs-lookup"><span data-stu-id="188de-136">Property</span></span>|<span data-ttu-id="188de-137">Modificare in</span><span class="sxs-lookup"><span data-stu-id="188de-137">Change to</span></span>|  
    |--------------|---------------|  
    |<span data-ttu-id="188de-138">**Name**</span><span class="sxs-lookup"><span data-stu-id="188de-138">**Name**</span></span>|`lblDisplay`|  
    |<span data-ttu-id="188de-139">**per**</span><span class="sxs-lookup"><span data-stu-id="188de-139">**Text**</span></span>|`(blank space)`|  
    |<span data-ttu-id="188de-140">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="188de-140">**TextAlign**</span></span>|`MiddleCenter`|  
    |<span data-ttu-id="188de-141">**Font.Size**</span><span class="sxs-lookup"><span data-stu-id="188de-141">**Font.Size**</span></span>|`14`|  
  
4. <span data-ttu-id="188de-142">Nella **Casella degli strumenti** espandere il nodo **Componenti**, quindi fare doppio clic su **Timer**.</span><span class="sxs-lookup"><span data-stu-id="188de-142">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>  
  
     <span data-ttu-id="188de-143">Poiché un <xref:System.Windows.Forms.Timer> è un componente, non dispone di alcuna rappresentazione visiva in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="188de-143">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="188de-144">non verrà visualizzato insieme ai controlli nell'area di progettazione bensì in Progettazione componenti, una barra delle applicazioni disposta nella parte inferiore dell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="188de-144">Therefore, it does not appear with the controls on the designer surface, but rather in the Component Designer (a tray at the bottom of the designer surface).</span></span>  
  
5. <span data-ttu-id="188de-145">In Progettazione componenti fare clic su **Timer1**e quindi impostare il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà `1000` e il <xref:System.Windows.Forms.Timer.Enabled%2A> proprietà `True`.</span><span class="sxs-lookup"><span data-stu-id="188de-145">In the Component Designer, click **Timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `True`.</span></span>  
  
     <span data-ttu-id="188de-146">Il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà controlla la frequenza con cui scatta il componente timer.</span><span class="sxs-lookup"><span data-stu-id="188de-146">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the timer component ticks.</span></span> <span data-ttu-id="188de-147">Ogni volta che `Timer1` scatta, viene eseguito il codice nell'evento `Timer1_Tick`.</span><span class="sxs-lookup"><span data-stu-id="188de-147">Each time `Timer1` ticks, it runs the code in the `Timer1_Tick` event.</span></span> <span data-ttu-id="188de-148">L'intervallo rappresenta i millesimi di secondo che intercorrono tra uno scatto e l'altro.</span><span class="sxs-lookup"><span data-stu-id="188de-148">The interval represents the number of milliseconds between ticks.</span></span>  
  
6. <span data-ttu-id="188de-149">In Progettazione componenti fare doppio clic su **Timer1** per passare all'evento `Timer1_Tick` di `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="188de-149">In the Component Designer, double-click **Timer1** to go to the `Timer1_Tick` event for `ctlClock`.</span></span>  
  
7. <span data-ttu-id="188de-150">Modificare il codice in modo che risulti simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="188de-150">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="188de-151">Assicurarsi di cambiare il modificatore di accesso da `Private` a `Protected`.</span><span class="sxs-lookup"><span data-stu-id="188de-151">Be sure to change the access modifier from `Private` to `Protected`.</span></span>  
  
    ```vb  
    Protected Sub Timer1_Tick(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles Timer1.Tick  
        ' Causes the label to display the current time.    
        lblDisplay.Text = Format(Now, "hh:mm:ss")  
    End Sub  
    ```  
  
     <span data-ttu-id="188de-152">Questo codice determinerà la visualizzazione dell'ora corrente in `lblDisplay`.</span><span class="sxs-lookup"><span data-stu-id="188de-152">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="188de-153">Poiché l'intervallo di `Timer1` è stato impostato su `1000`, l'evento verrà generato ogni mille millesimi di secondo, aggiornando quindi l'ora corrente ogni secondo.</span><span class="sxs-lookup"><span data-stu-id="188de-153">Because the interval of `Timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>  
  
8. <span data-ttu-id="188de-154">Modificare il metodo in modo che sia sottoponibile a override.</span><span class="sxs-lookup"><span data-stu-id="188de-154">Modify the method to be overridable.</span></span> <span data-ttu-id="188de-155">Per ulteriori informazioni, vedere la sezione "Eredità da un controllo utente" riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="188de-155">For more information, see the "Inheriting from a User Control" section below.</span></span>  
  
    ```vb  
    Protected Overridable Sub Timer1_Tick(ByVal sender As Object, ByVal _  
        e As System.EventArgs) Handles Timer1.Tick  
    ```  
  
9. <span data-ttu-id="188de-156">Scegliere **Salva tutto** dal menu **File** per salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="188de-156">On the **File** menu, click **Save All** to save the project.</span></span>  
  
## <a name="adding-properties-to-the-composite-control"></a><span data-ttu-id="188de-157">Aggiunta di proprietà al controllo composito</span><span class="sxs-lookup"><span data-stu-id="188de-157">Adding Properties to the Composite Control</span></span>  
 <span data-ttu-id="188de-158">Il controllo orologio ora incapsula un' <xref:System.Windows.Forms.Label> controllo e un <xref:System.Windows.Forms.Timer> componente, ognuno con un proprio set di proprietà intrinseche.</span><span class="sxs-lookup"><span data-stu-id="188de-158">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="188de-159">Benché le singole proprietà di questi controlli non siano accessibili ai futuri utenti del controllo, è possibile creare ed esporre proprietà personalizzate scrivendo i blocchi di codice appropriati.</span><span class="sxs-lookup"><span data-stu-id="188de-159">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="188de-160">Nella procedura riportata di seguito verrà illustrato come aggiungere al controllo proprietà che consentono all'utente di modificare il colore dello sfondo e del testo.</span><span class="sxs-lookup"><span data-stu-id="188de-160">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>  
  
#### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="188de-161">Per aggiungere una proprietà al controllo composito</span><span class="sxs-lookup"><span data-stu-id="188de-161">To add a property to your composite control</span></span>  
  
1. <span data-ttu-id="188de-162">In Esplora soluzioni fare clic con il pulsante destro del mouse su c**tlClock.vb**, quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="188de-162">In Solution Explorer, right-click **ctlClock.vb**, and then click **View Code**.</span></span>  
  
     <span data-ttu-id="188de-163">Verrà visualizzato l'editor del codice per il controllo.</span><span class="sxs-lookup"><span data-stu-id="188de-163">The Code Editor for your control opens.</span></span>  
  
2. <span data-ttu-id="188de-164">Individuare l'istruzione `Public Class ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="188de-164">Locate the `Public Class ctlClock` statement.</span></span> <span data-ttu-id="188de-165">Sotto tale riga, aggiungere il seguente codice.</span><span class="sxs-lookup"><span data-stu-id="188de-165">Beneath it, type the following code.</span></span>  
  
    ```vb  
    Private colFColor as Color  
    Private colBColor as Color  
    ```  
  
     <span data-ttu-id="188de-166">Queste istruzioni consentono di creare le variabili private da utilizzare per la memorizzazione dei valori delle proprietà che verranno create.</span><span class="sxs-lookup"><span data-stu-id="188de-166">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>  
  
3. <span data-ttu-id="188de-167">Sotto le dichiarazioni delle variabili del passaggio 2 inserire il seguente codice.</span><span class="sxs-lookup"><span data-stu-id="188de-167">Insert the following code beneath the variable declarations from step 2.</span></span>  
  
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
  
     <span data-ttu-id="188de-168">Nel codice riportato in precedenza vengono create due proprietà personalizzate, `ClockForeColor` e `ClockBackColor`, disponibili agli utenti successivi del controllo mediante l'utilizzo dell'istruzione `Property`.</span><span class="sxs-lookup"><span data-stu-id="188de-168">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control by invoking the `Property` statement.</span></span> <span data-ttu-id="188de-169">Le istruzioni `Get` e `Set` consentono di archiviare e recuperare il valore della proprietà e di inserire il codice per implementare le funzionalità appropriate per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="188de-169">The `Get` and `Set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>  
  
4. <span data-ttu-id="188de-170">Scegliere **Salva tutto** dal menu **File** per salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="188de-170">On the **File** menu, click **Save All** to save the project.</span></span>  
  
## <a name="testing-the-control"></a><span data-ttu-id="188de-171">Test del controllo</span><span class="sxs-lookup"><span data-stu-id="188de-171">Testing the Control</span></span>  
 <span data-ttu-id="188de-172">I controlli non sono progetti autonomi e devono pertanto essere inseriti in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="188de-172">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="188de-173">Eseguire il test del comportamento del controllo in fase di esecuzione e sperimentare le proprietà con **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="188de-173">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="188de-174">Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="188de-174">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
#### <a name="to-test-your-control"></a><span data-ttu-id="188de-175">Per eseguire il test del controllo</span><span class="sxs-lookup"><span data-stu-id="188de-175">To test your control</span></span>  
  
1. <span data-ttu-id="188de-176">Per compilare il progetto ed eseguire il controllo in **UserControl Test Container**, premere F5.</span><span class="sxs-lookup"><span data-stu-id="188de-176">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>  
  
2. <span data-ttu-id="188de-177">Nella griglia della proprietà di Test Container, selezionare la proprietà `ClockBackColor`, quindi fare clic sulla freccia a discesa per visualizzare la tavolozza dei colori.</span><span class="sxs-lookup"><span data-stu-id="188de-177">In the test container's property grid, select the `ClockBackColor` property, and then click the drop-down arrow to display the color palette.</span></span>  
  
3. <span data-ttu-id="188de-178">Scegliere un colore facendovi clic sopra.</span><span class="sxs-lookup"><span data-stu-id="188de-178">Choose a color by clicking it.</span></span>  
  
     <span data-ttu-id="188de-179">Il colore di sfondo del controllo cambierà in base al colore selezionato.</span><span class="sxs-lookup"><span data-stu-id="188de-179">The background color of your control changes to the color you selected.</span></span>  
  
4. <span data-ttu-id="188de-180">Usare una sequenza di eventi simile per verificare il corretto funzionamento della proprietà `ClockForeColor`.</span><span class="sxs-lookup"><span data-stu-id="188de-180">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>  
  
5. <span data-ttu-id="188de-181">Per chiudere la finestra **UserControl Test Container**, scegliere **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="188de-181">Click **Close** to close the **UserControl Test Container**.</span></span>  
  
     <span data-ttu-id="188de-182">In questa sezione e in quelle precedenti è stato illustrato come combinare componenti e controlli Windows con codici e package per aggiungere funzionalità personalizzate al modulo di un controllo composito.</span><span class="sxs-lookup"><span data-stu-id="188de-182">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="188de-183">Si è inoltre appreso come esporre le proprietà del controllo composito e come eseguire il test del controllo dopo averlo completato.</span><span class="sxs-lookup"><span data-stu-id="188de-183">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="188de-184">Nella sezione successiva verranno fornite informazioni sulla modalità di creazione di un controllo composito ereditato utilizzando `ctlClock` come base.</span><span class="sxs-lookup"><span data-stu-id="188de-184">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>  
  
## <a name="inheriting-from-a-composite-control"></a><span data-ttu-id="188de-185">Eredità da un controllo composito</span><span class="sxs-lookup"><span data-stu-id="188de-185">Inheriting from a Composite Control</span></span>  
 <span data-ttu-id="188de-186">Nelle sezioni precedenti si è appreso come combinare controlli, componenti e codice Windows in controlli compositi riutilizzabili.</span><span class="sxs-lookup"><span data-stu-id="188de-186">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="188de-187">Il controllo composito può ora essere usato come base per la compilazione di altri controlli.</span><span class="sxs-lookup"><span data-stu-id="188de-187">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="188de-188">Il processo di derivazione di una classe da una classe di base è detto *ereditarietà*.</span><span class="sxs-lookup"><span data-stu-id="188de-188">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="188de-189">In questa sezione verrà creato un controllo composito denominato `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="188de-189">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="188de-190">Il controllo verrà derivato dal relativo controllo padre, in questo caso `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="188de-190">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="188de-191">Verrà spiegato come estendere le funzionalità di `ctlClock` mediante l'override dei metodi padre e l'aggiunta di nuovi metodi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="188de-191">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>  
  
 <span data-ttu-id="188de-192">Per creare un controllo ereditato, è innanzitutto necessario derivare il controllo dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="188de-192">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="188de-193">Questa operazione consente di creare un nuovo controllo, con le stesse proprietà, metodi e caratteristiche grafiche del controllo padre, che può essere anche utilizzato come base per l'aggiunta di una funzionalità nuova o modificata.</span><span class="sxs-lookup"><span data-stu-id="188de-193">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>  
  
#### <a name="to-create-the-inherited-control"></a><span data-ttu-id="188de-194">Per creare il controllo ereditato</span><span class="sxs-lookup"><span data-stu-id="188de-194">To create the inherited control</span></span>  
  
1. <span data-ttu-id="188de-195">In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlClockLib**, scegliere **Aggiungi**, quindi **Controllo utente**.</span><span class="sxs-lookup"><span data-stu-id="188de-195">In Solution Explorer, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>  
  
     <span data-ttu-id="188de-196">Viene aperta la finestra di dialogo **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="188de-196">The **Add New Item** dialog box opens.</span></span>  
  
2. <span data-ttu-id="188de-197">Selezionare il modello **Controllo utente ereditato**.</span><span class="sxs-lookup"><span data-stu-id="188de-197">Select the **Inherited User Control** template.</span></span>  
  
3. <span data-ttu-id="188de-198">Nella casella **Nome** digitare `ctlAlarmClock.vb` e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="188de-198">In the **Name** box, type `ctlAlarmClock.vb`, and then click **Add**.</span></span>  
  
     <span data-ttu-id="188de-199">Viene visualizzata la finestra di dialogo **Selezione ereditarietà**.</span><span class="sxs-lookup"><span data-stu-id="188de-199">The **Inheritance Picker** dialog box appears.</span></span>  
  
4. <span data-ttu-id="188de-200">In **Nome componente** fare doppio clic su **ctlClock**.</span><span class="sxs-lookup"><span data-stu-id="188de-200">Under **Component Name**, double-click **ctlClock**.</span></span>  
  
5. <span data-ttu-id="188de-201">In Esplora soluzioni scorrere i progetti correnti.</span><span class="sxs-lookup"><span data-stu-id="188de-201">In Solution Explorer, browse through the current projects.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="188de-202">Nel progetto corrente è stato aggiunto il file denominato **ctlAlarmClock.vb**.</span><span class="sxs-lookup"><span data-stu-id="188de-202">A file called **ctlAlarmClock.vb** has been added to the current project.</span></span>  
  
### <a name="adding-the-alarm-properties"></a><span data-ttu-id="188de-203">Aggiunta delle proprietà per l'allarme</span><span class="sxs-lookup"><span data-stu-id="188de-203">Adding the Alarm Properties</span></span>  
 <span data-ttu-id="188de-204">Le modalità di aggiunta delle proprietà a un controllo ereditato sono analoghe a quelle utilizzate per i controlli compositi.</span><span class="sxs-lookup"><span data-stu-id="188de-204">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="188de-205">Mediante la sintassi di dichiarazione delle proprietà si aggiungeranno ora al controllo due proprietà: `AlarmTime`, in cui viene memorizzato il valore della data e dell'ora in cui l'allarme deve essere disattivato, e `AlarmSet`, che indica se l'allarme è impostato o meno.</span><span class="sxs-lookup"><span data-stu-id="188de-205">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>  
  
##### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="188de-206">Per aggiungere proprietà al controllo composito</span><span class="sxs-lookup"><span data-stu-id="188de-206">To add properties to your composite control</span></span>  
  
1. <span data-ttu-id="188de-207">In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlAlarmClock**, quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="188de-207">In Solution Explorer, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>  
  
2. <span data-ttu-id="188de-208">Individuare la dichiarazione di classe per il controllo ctlAlarmClock, visualizzato come `Public Class ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="188de-208">Locate the class declaration for the ctlAlarmClock control, which appears as `Public Class ctlAlarmClock`.</span></span>  <span data-ttu-id="188de-209">Inserire il codice seguente nella dichiarazione di classe.</span><span class="sxs-lookup"><span data-stu-id="188de-209">In the class declaration, insert the following code.</span></span>  
  
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
  
### <a name="adding-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="188de-210">Aggiunta del controllo all'interfaccia grafica</span><span class="sxs-lookup"><span data-stu-id="188de-210">Adding to the Graphical Interface of the Control</span></span>  
 <span data-ttu-id="188de-211">Il controllo ereditato presenta un'interfaccia grafica identica a quella del controllo dal quale eredita</span><span class="sxs-lookup"><span data-stu-id="188de-211">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="188de-212">e possiede gli stessi controlli costitutivi del controllo padre, ma le proprietà dei controlli costitutivi non sono disponibili, a meno che non siano state specificamente esposte.</span><span class="sxs-lookup"><span data-stu-id="188de-212">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="188de-213">Analogamente a qualsiasi altro controllo composito, è possibile aggiungere elementi all'interfaccia grafica di un controllo composito ereditato, utilizzando la medesima procedura.</span><span class="sxs-lookup"><span data-stu-id="188de-213">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="188de-214">In questo esempio verrà utilizzato un controllo label per aggiungere un effetto intermittente all'interfaccia grafica del controllo quando l'allarme suona.</span><span class="sxs-lookup"><span data-stu-id="188de-214">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>  
  
##### <a name="to-add-the-label-control"></a><span data-ttu-id="188de-215">Per aggiungere il controllo label</span><span class="sxs-lookup"><span data-stu-id="188de-215">To add the label control</span></span>  
  
1. <span data-ttu-id="188de-216">In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlAlarmClock** e scegliere **Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="188de-216">In Solution Explorer, right-click **ctlAlarmClock**, and click **View Designer**.</span></span>  
  
     <span data-ttu-id="188de-217">Nella finestra principale viene aperta la finestra di progettazione per `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="188de-217">The designer for `ctlAlarmClock` opens in the main window.</span></span>  
  
2. <span data-ttu-id="188de-218">Fare clic su `lblDisplay` (parte visualizzata del controllo) e osservare la finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="188de-218">Click `lblDisplay` (the display portion of the control), and view the Properties window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="188de-219">Tutte le proprietà sono presenti ma inattive, ossia visualizzate in grigio.</span><span class="sxs-lookup"><span data-stu-id="188de-219">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="188de-220">Ciò indica che le proprietà sono native di `lblDisplay` e non è possibile accedervi né modificarle nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="188de-220">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="188de-221">Per impostazione predefinita i controlli contenuti in un controllo composito sono `Private` e le relative proprietà non sono accessibili.</span><span class="sxs-lookup"><span data-stu-id="188de-221">By default, controls contained in a composite control are `Private`, and their properties are not accessible by any means.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="188de-222">Se si desidera che gli utenti successivi del controllo composito abbiano accesso ai relativi controlli interni, dichiararli come `Public` o `Protected`.</span><span class="sxs-lookup"><span data-stu-id="188de-222">If you want subsequent users of your composite control to have access to its internal controls, declare them as `Public` or `Protected`.</span></span> <span data-ttu-id="188de-223">Sarà così possibile impostare e modificare le proprietà dei controlli contenuti nel controllo composito mediante il codice appropriato.</span><span class="sxs-lookup"><span data-stu-id="188de-223">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>  
  
3. <span data-ttu-id="188de-224">Aggiungere un <xref:System.Windows.Forms.Label> controllo al controllo composito.</span><span class="sxs-lookup"><span data-stu-id="188de-224">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>  
  
4. <span data-ttu-id="188de-225">Usando il mouse, trascinare il <xref:System.Windows.Forms.Label> controllo immediatamente di sotto della visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="188de-225">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="188de-226">Nella finestra Proprietà impostare le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="188de-226">In the Properties window, set the following properties.</span></span>  
  
    |<span data-ttu-id="188de-227">Proprietà</span><span class="sxs-lookup"><span data-stu-id="188de-227">Property</span></span>|<span data-ttu-id="188de-228">Impostazione</span><span class="sxs-lookup"><span data-stu-id="188de-228">Setting</span></span>|  
    |--------------|-------------|  
    |<span data-ttu-id="188de-229">**Name**</span><span class="sxs-lookup"><span data-stu-id="188de-229">**Name**</span></span>|`lblAlarm`|  
    |<span data-ttu-id="188de-230">**per**</span><span class="sxs-lookup"><span data-stu-id="188de-230">**Text**</span></span>|<span data-ttu-id="188de-231">**Allarme!**</span><span class="sxs-lookup"><span data-stu-id="188de-231">**Alarm!**</span></span>|  
    |<span data-ttu-id="188de-232">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="188de-232">**TextAlign**</span></span>|`MiddleCenter`|  
    |<span data-ttu-id="188de-233">**Visible**</span><span class="sxs-lookup"><span data-stu-id="188de-233">**Visible**</span></span>|`False`|  
  
### <a name="adding-the-alarm-functionality"></a><span data-ttu-id="188de-234">Aggiunta della funzionalità di allarme</span><span class="sxs-lookup"><span data-stu-id="188de-234">Adding the Alarm Functionality</span></span>  
 <span data-ttu-id="188de-235">Nelle procedure precedenti sono state aggiunte proprietà e un controllo in grado di abilitare la funzionalità di allarme nel controllo composito.</span><span class="sxs-lookup"><span data-stu-id="188de-235">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="188de-236">In questa procedura verrà aggiunto un codice che consente di confrontare l'ora corrente con l'ora dell'allarme e, se le ore risultano identiche, attivare un allarme sonoro e lampeggiante.</span><span class="sxs-lookup"><span data-stu-id="188de-236">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to sound and flash an alarm.</span></span> <span data-ttu-id="188de-237">Eseguendo l'override del metodo `Timer1_Tick` di `ctlClock` e aggiungendovi ulteriore codice sarà possibile estendere le capacità di `ctlAlarmClock` e conservare allo stesso le funzionalità intrinseche di `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="188de-237">By overriding the `Timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>  
  
##### <a name="to-override-the-timer1tick-method-of-ctlclock"></a><span data-ttu-id="188de-238">Per eseguire l'override del metodo Timer1_Tick di ctlClock</span><span class="sxs-lookup"><span data-stu-id="188de-238">To override the Timer1_Tick method of ctlClock</span></span>  
  
1. <span data-ttu-id="188de-239">In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlAlarmClock.vb**, quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="188de-239">In Solution Explorer, right-click **ctlAlarmClock.vb**, and then click **View Code**.</span></span>  
  
2. <span data-ttu-id="188de-240">Individuare l'istruzione `Private blnAlarmSet As Boolean`.</span><span class="sxs-lookup"><span data-stu-id="188de-240">Locate the `Private blnAlarmSet As Boolean` statement.</span></span> <span data-ttu-id="188de-241">e aggiungere subito dopo la seguente istruzione.</span><span class="sxs-lookup"><span data-stu-id="188de-241">Immediately beneath it, add the following statement.</span></span>  
  
    ```vb  
    Dim blnColorTicker as Boolean  
    ```  
  
3. <span data-ttu-id="188de-242">Individuare l'istruzione `End Class` nella parte inferiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="188de-242">Locate the `End Class` statement at the bottom of the page.</span></span> <span data-ttu-id="188de-243">Prima dell'istruzione `End Class` aggiungere il seguente codice.</span><span class="sxs-lookup"><span data-stu-id="188de-243">Just before the `End Class` statement, add the following code.</span></span>  
  
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
  
     <span data-ttu-id="188de-244">Il codice appena aggiunto ha diverse funzioni.</span><span class="sxs-lookup"><span data-stu-id="188de-244">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="188de-245">Se si utilizza l'istruzione `Overrides`, il controllo utilizzerà questo metodo anziché il metodo ereditato dal controllo di base.</span><span class="sxs-lookup"><span data-stu-id="188de-245">The `Overrides` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="188de-246">Una volta chiamato, questo metodo chiamerà il metodo di cui esegue l'override utilizzando l'istruzione `MyBase.Timer1_Tick` e assicurando che tutte le funzionalità incorporate nel controllo originale vengano riprodotte in questo controllo.</span><span class="sxs-lookup"><span data-stu-id="188de-246">When this method is called, it calls the method it overrides by invoking the `MyBase.Timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="188de-247">Verrà quindi eseguito il codice aggiuntivo per incorporare la funzionalità di allarme.</span><span class="sxs-lookup"><span data-stu-id="188de-247">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="188de-248">Quando l'allarme viene attivato, viene visualizzato un controllo etichetta lampeggiante e viene emesso un segnale acustico.</span><span class="sxs-lookup"><span data-stu-id="188de-248">A flashing label control will appear when the alarm occurs, and an audible beep will be heard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="188de-249">Poiché si esegue l'override di un gestore eventi ereditato, non è necessario specificare l'evento tramite la parola chiave `Handles`.</span><span class="sxs-lookup"><span data-stu-id="188de-249">Because you are overriding an inherited event handler, you do not have to specify the event with the `Handles` keyword.</span></span> <span data-ttu-id="188de-250">L'evento risulta già associato.</span><span class="sxs-lookup"><span data-stu-id="188de-250">The event is already hooked up.</span></span> <span data-ttu-id="188de-251">L'override riguarda l'implementazione del gestore.</span><span class="sxs-lookup"><span data-stu-id="188de-251">All you are overriding is the implementation of the handler.</span></span>  
  
     <span data-ttu-id="188de-252">Il controllo dell'allarme è quasi completo.</span><span class="sxs-lookup"><span data-stu-id="188de-252">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="188de-253">L'unica operazione rimasta è l'implementazione di un sistema di disattivazione.</span><span class="sxs-lookup"><span data-stu-id="188de-253">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="188de-254">A tal fine, è necessario aggiungere codice al metodo `lblAlarm_Click`.</span><span class="sxs-lookup"><span data-stu-id="188de-254">To do this, you will add code to the `lblAlarm_Click` method.</span></span>  
  
##### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="188de-255">Per implementare il metodo di disattivazione</span><span class="sxs-lookup"><span data-stu-id="188de-255">To implement the shutoff method</span></span>  
  
1. <span data-ttu-id="188de-256">In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlAlarmClock.vb**, quindi scegliere **Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="188de-256">In Solution Explorer, right-click **ctlAlarmClock.vb**, and then click **View Designer**.</span></span>  
  
2. <span data-ttu-id="188de-257">Nella finestra di progettazione fare doppio clic sul controllo **lblAlarm**.</span><span class="sxs-lookup"><span data-stu-id="188de-257">In the designer, double-click **lblAlarm**.</span></span> <span data-ttu-id="188de-258">Nell'**editor di codice** verrà visualizzata la riga `Private Sub lblAlarm_Click`.</span><span class="sxs-lookup"><span data-stu-id="188de-258">The **Code Editor** opens to the `Private Sub lblAlarm_Click` line.</span></span>  
  
3. <span data-ttu-id="188de-259">Modificare il metodo in modo che risulti simile al seguente codice.</span><span class="sxs-lookup"><span data-stu-id="188de-259">Modify this method so that it resembles the following code.</span></span>  
  
    ```vb  
    Private Sub lblAlarm_Click(ByVal sender As Object, ByVal e As _  
     System.EventArgs) Handles lblAlarm.Click  
        ' Turns off the alarm.  
        AlarmSet = False  
        ' Hides the flashing label.  
        lblAlarm.Visible = False  
    End Sub  
    ```  
  
4. <span data-ttu-id="188de-260">Scegliere **Salva tutto** dal menu **File** per salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="188de-260">On the **File** menu, click **Save All** to save the project.</span></span>  
  
### <a name="using-the-inherited-control-on-a-form"></a><span data-ttu-id="188de-261">Utilizzo del controllo ereditato in un modulo</span><span class="sxs-lookup"><span data-stu-id="188de-261">Using the Inherited Control on a Form</span></span>  
 <span data-ttu-id="188de-262">È possibile testare il controllo ereditato esattamente come si esegue il controllo di classe di base, `ctlClock`: Per compilare il progetto ed eseguire il controllo in **UserControl Test Container**, premere F5.</span><span class="sxs-lookup"><span data-stu-id="188de-262">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="188de-263">Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="188de-263">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
 <span data-ttu-id="188de-264">Per utilizzare il controllo è necessario inserirlo in un modulo.</span><span class="sxs-lookup"><span data-stu-id="188de-264">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="188de-265">Come i controlli compositi standard, i controlli compositi ereditati non possono essere autonomi e devono essere inclusi in un modulo o in un altro contenitore.</span><span class="sxs-lookup"><span data-stu-id="188de-265">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="188de-266">Poiché `ctlAlarmClock` include un maggior numero di funzionalità, per eseguire il test è necessario aggiungere del codice.</span><span class="sxs-lookup"><span data-stu-id="188de-266">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="188de-267">In questa procedura verrà scritto un semplice programma per la verifica delle funzionalità di `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="188de-267">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="188de-268">Verrà inoltre scritto il codice per impostare e visualizzare la proprietà `AlarmTime` di `ctlAlarmClock` e verrà eseguito il test delle funzionalità intrinseche del controllo.</span><span class="sxs-lookup"><span data-stu-id="188de-268">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>  
  
##### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="188de-269">Per compilare e aggiungere il controllo a un modulo di test</span><span class="sxs-lookup"><span data-stu-id="188de-269">To build and add your control to a test form</span></span>  
  
1. <span data-ttu-id="188de-270">In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlClockLib**, quindi scegliere **Compila**.</span><span class="sxs-lookup"><span data-stu-id="188de-270">In Solution Explorer, right-click **ctlClockLib**, and then click **Build**.</span></span>  
  
2. <span data-ttu-id="188de-271">Scegliere **Aggiungi** dal menu **File**e quindi fare clic su **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="188de-271">On the **File** menu, point to **Add**, and then click **New Project**.</span></span>  
  
3. <span data-ttu-id="188de-272">Aggiungere un nuovo progetto **Applicazione Windows** alla soluzione e denominarlo `Test`.</span><span class="sxs-lookup"><span data-stu-id="188de-272">Add a new **Windows Application** project to the solution, and name it `Test`.</span></span>  
  
     <span data-ttu-id="188de-273">Il progetto **Test** verrà aggiunto a Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="188de-273">The **Test** project is added to Solution Explorer.</span></span>  
  
4. <span data-ttu-id="188de-274">In Esplora soluzioni fare clic con il pulsante destro del mouse sul nodo di progetto `Test`, quindi scegliere **Aggiungi riferimento** per visualizzare la finestra di dialogo **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="188de-274">In Solution Explorer, right-click the `Test` project node, and then click **Add Reference** to display the **Add Reference** dialog box.</span></span>  
  
5. <span data-ttu-id="188de-275">Scegliere la scheda **Progetti**.</span><span class="sxs-lookup"><span data-stu-id="188de-275">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="188de-276">Il progetto **ctlClockLib** verrà elencato in **Nome progetto**.</span><span class="sxs-lookup"><span data-stu-id="188de-276">The project **ctlClockLib** will be listed under **Project Name**.</span></span> <span data-ttu-id="188de-277">Fare doppio clic su **ctlClockLib** per aggiungere il riferimento al progetto di test.</span><span class="sxs-lookup"><span data-stu-id="188de-277">Double-click **ctlClockLib** to add the reference to the test project.</span></span>  
  
6. <span data-ttu-id="188de-278">In Esplora soluzioni fare clic con il pulsante destro del mouse su **Test**, quindi scegliere **Compila**.</span><span class="sxs-lookup"><span data-stu-id="188de-278">In Solution Explorer, right-click **Test**, and then click **Build**.</span></span>  
  
7. <span data-ttu-id="188de-279">Nella **Casella degli strumenti** espandere il nodo **Componenti ctlClockLib**.</span><span class="sxs-lookup"><span data-stu-id="188de-279">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>  
  
8. <span data-ttu-id="188de-280">Fare doppio clic su **ctlAlarmClock** per aggiungere un'istanza di `ctlAlarmClock` al modulo.</span><span class="sxs-lookup"><span data-stu-id="188de-280">Double-click **ctlAlarmClock** to add an instance of `ctlAlarmClock` to your form.</span></span>  
  
9. <span data-ttu-id="188de-281">Nel **casella degli strumenti**individuare e fare doppio clic su **DateTimePicker** per aggiungere un <xref:System.Windows.Forms.DateTimePicker> controllo al form e quindi aggiungere un <xref:System.Windows.Forms.Label> facendo doppio clic sui **etichetta**.</span><span class="sxs-lookup"><span data-stu-id="188de-281">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>  
  
10. <span data-ttu-id="188de-282">Posizionare mediante il mouse i controlli in un punto del modulo di facile accesso.</span><span class="sxs-lookup"><span data-stu-id="188de-282">Use the mouse to position the controls in a convenient place on the form.</span></span>  
  
11. <span data-ttu-id="188de-283">Impostare le proprietà dei controlli come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="188de-283">Set the properties of these controls in the following manner.</span></span>  
  
    |<span data-ttu-id="188de-284">Control</span><span class="sxs-lookup"><span data-stu-id="188de-284">Control</span></span>|<span data-ttu-id="188de-285">Proprietà</span><span class="sxs-lookup"><span data-stu-id="188de-285">Property</span></span>|<span data-ttu-id="188de-286">Value</span><span class="sxs-lookup"><span data-stu-id="188de-286">Value</span></span>|  
    |-------------|--------------|-----------|  
    |`label1`|<span data-ttu-id="188de-287">**per**</span><span class="sxs-lookup"><span data-stu-id="188de-287">**Text**</span></span>|`(blank space)`|  
    ||<span data-ttu-id="188de-288">**Name**</span><span class="sxs-lookup"><span data-stu-id="188de-288">**Name**</span></span>|`lblTest`|  
    |`dateTimePicker1`|<span data-ttu-id="188de-289">**Name**</span><span class="sxs-lookup"><span data-stu-id="188de-289">**Name**</span></span>|`dtpTest`|  
    ||<span data-ttu-id="188de-290">**Format**</span><span class="sxs-lookup"><span data-stu-id="188de-290">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|  
  
12. <span data-ttu-id="188de-291">Nella finestra di progettazione fare doppio clic su **dtpTest**.</span><span class="sxs-lookup"><span data-stu-id="188de-291">In the designer, double-click **dtpTest**.</span></span>  
  
     <span data-ttu-id="188de-292">Nell'**Editor di codice** viene visualizzato `Private Sub dtpTest_ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="188de-292">The **Code Editor** opens to `Private Sub dtpTest_ValueChanged`.</span></span>  
  
13. <span data-ttu-id="188de-293">Modificare il codice in modo che risulti simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="188de-293">Modify the code so that it resembles the following.</span></span>  
  
    ```vb  
    Private Sub dtpTest_ValueChanged(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles dtpTest.ValueChanged  
        ctlAlarmClock1.AlarmTime = dtpTest.Value  
        ctlAlarmClock1.AlarmSet = True  
        lblTest.Text = "Alarm Time is " & Format(ctlAlarmClock1.AlarmTime, _  
            "hh:mm")  
    End Sub  
    ```  
  
14. <span data-ttu-id="188de-294">In Esplora soluzioni fare clic con il pulsante destro del mouse su **Test** e scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="188de-294">In Solution Explorer, right-click **Test**, and then click **Set as StartUp Project**.</span></span>  
  
15. <span data-ttu-id="188de-295">Scegliere **Avvia debug** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="188de-295">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="188de-296">Verrà avviato il programma di test.</span><span class="sxs-lookup"><span data-stu-id="188de-296">The test program starts.</span></span> <span data-ttu-id="188de-297">Si noti che l'ora corrente viene aggiornata nel `ctlAlarmClock` controllo e l'ora di inizio viene visualizzato nei <xref:System.Windows.Forms.DateTimePicker> controllo.</span><span class="sxs-lookup"><span data-stu-id="188de-297">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>  
  
16. <span data-ttu-id="188de-298">Fare clic su di <xref:System.Windows.Forms.DateTimePicker> vengono visualizzati i minuti dell'ora.</span><span class="sxs-lookup"><span data-stu-id="188de-298">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>  
  
17. <span data-ttu-id="188de-299">Utilizzando la tastiera, impostare un valore per i minuti maggiore di un minuto rispetto all'ora corrente visualizzata da `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="188de-299">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>  
  
     <span data-ttu-id="188de-300">L'ora per l'impostazione dell'allarme è visualizzata in `lblTest`.</span><span class="sxs-lookup"><span data-stu-id="188de-300">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="188de-301">Attendere che l'ora visualizzata raggiunga l'ora di impostazione dell'allarme.</span><span class="sxs-lookup"><span data-stu-id="188de-301">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="188de-302">Quando l'ora visualizzata raggiunge l'ora su cui è impostato l'allarme, verrà emesso un segnale acustico e `lblAlarm` lampeggerà.</span><span class="sxs-lookup"><span data-stu-id="188de-302">When the displayed time reaches the time to which the alarm is set, the beep will sound and `lblAlarm` will flash.</span></span>  
  
18. <span data-ttu-id="188de-303">Disattivare l'allarme facendo clic su `lblAlarm`.</span><span class="sxs-lookup"><span data-stu-id="188de-303">Turn off the alarm by clicking `lblAlarm`.</span></span> <span data-ttu-id="188de-304">A questo punto è possibile reimpostare l'allarme.</span><span class="sxs-lookup"><span data-stu-id="188de-304">You may now reset the alarm.</span></span>  
  
     <span data-ttu-id="188de-305">In questa procedura dettagliata sono stati trattati diversi concetti chiave.</span><span class="sxs-lookup"><span data-stu-id="188de-305">This walkthrough has covered a number of key concepts.</span></span> <span data-ttu-id="188de-306">Si è appreso come creare un controllo composito combinando controlli e componenti in un contenitore controllo composito</span><span class="sxs-lookup"><span data-stu-id="188de-306">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="188de-307">e come aggiungere proprietà al controllo e scrivere il codice per l'implementazione di funzionalità personalizzate.</span><span class="sxs-lookup"><span data-stu-id="188de-307">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="188de-308">Nell'ultima sezione sono state illustrate l'estensione delle funzionalità di uno specifico controllo composito mediante ereditarietà e la modifica delle funzionalità dei metodi host mediante override.</span><span class="sxs-lookup"><span data-stu-id="188de-308">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="188de-309">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="188de-309">See also</span></span>

- [<span data-ttu-id="188de-310">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="188de-310">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="188de-311">Procedura: Modificare controlli compositi</span><span class="sxs-lookup"><span data-stu-id="188de-311">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="188de-312">Procedura: Visualizzare un controllo nella finestra di dialogo elementi della casella degli strumenti scegliere</span><span class="sxs-lookup"><span data-stu-id="188de-312">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
