---
title: Risoluzione dei problemi relativi alla modifica di controlli e componenti
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting components
- troubleshooting controls [Windows Forms]
- controls [Windows Forms], troubleshooting
- components [Windows Forms], troubleshooting
- Windows Forms controls, debugging
ms.assetid: e9c8c099-2271-4737-882f-50f336c7a55e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2e0b98107ac5f43c80aad6cb5ea61e6f4e1e28d3
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015704"
---
# <a name="troubleshoot-control-and-component-authoring"></a><span data-ttu-id="26c88-102">Risolvere i problemi relativi alla creazione di controlli e componenti</span><span class="sxs-lookup"><span data-stu-id="26c88-102">Troubleshoot Control and Component Authoring</span></span>

<span data-ttu-id="26c88-103">In questo argomento vengono elencati i seguenti problemi comuni che si verificano durante lo sviluppo di componenti e controlli:</span><span class="sxs-lookup"><span data-stu-id="26c88-103">This topic lists the following common problems that arise when developing components and controls:</span></span>

- <span data-ttu-id="26c88-104">Impossibile aggiungere un controllo alla casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="26c88-104">Cannot Add Control to Toolbox</span></span>

- <span data-ttu-id="26c88-105">Impossibile eseguire il debug del componente o controllo utente di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26c88-105">Cannot Debug the Windows Forms User Control or Component</span></span>

- <span data-ttu-id="26c88-106">L'evento viene generato due volte nel componente o controllo ereditato</span><span class="sxs-lookup"><span data-stu-id="26c88-106">Event Is Raised Twice in Inherited Control or Component</span></span>

- <span data-ttu-id="26c88-107">Errore in fase di progettazione: "Impossibile creare il componente '*nome componente*'"</span><span class="sxs-lookup"><span data-stu-id="26c88-107">Design-Time Error: "Failed to Create Component '*Component Name*'"</span></span>

- <span data-ttu-id="26c88-108">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="26c88-108">STAThreadAttribute</span></span>

- <span data-ttu-id="26c88-109">L'icona del componente non appare nella casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="26c88-109">Component Icon Does Not Appear in Toolbox</span></span>

## <a name="cannot-add-control-to-toolbox"></a><span data-ttu-id="26c88-110">Impossibile aggiungere un controllo alla casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="26c88-110">Cannot Add Control to Toolbox</span></span>

<span data-ttu-id="26c88-111">Se si vuole aggiungere un controllo personalizzato creato in un altro progetto o un controllo di terze parti alla **casella degli strumenti**, è necessario farlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="26c88-111">If you want to add a custom control that you created in another project or a third-party control to the **Toolbox**, you must do so manually.</span></span> <span data-ttu-id="26c88-112">Se il progetto corrente include il controllo o il componente, deve automaticamente apparire nella **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="26c88-112">If the current project contains your control or component, it should appear in the **Toolbox** automatically.</span></span> <span data-ttu-id="26c88-113">Per altre informazioni, vedere [Procedura dettagliata: Popolamento automatico della casella degli strumenti con](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)componenti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="26c88-113">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

### <a name="to-add-a-control-to-the-toolbox"></a><span data-ttu-id="26c88-114">Per aggiungere un controllo alla casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="26c88-114">To add a control to the Toolbox</span></span>

1. <span data-ttu-id="26c88-115">Fare clic con il pulsante destro del mouse nella **casella degli strumenti** e selezionare **Scegli elementi** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="26c88-115">Right-click the **Toolbox** and from the shortcut menu, select **Choose Items**.</span></span>

2. <span data-ttu-id="26c88-116">Nella finestra di dialogo **Scegli elementi della Casella degli strumenti** aggiungere il componente:</span><span class="sxs-lookup"><span data-stu-id="26c88-116">In the **Choose Toolbox Items** dialog box, add the component:</span></span>

    - <span data-ttu-id="26c88-117">per aggiungere un componente o un controllo di .NET Framework, fare clic sulla scheda **Componenti di .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="26c88-117">If you want to add a .NET Framework component or control, click the **.NET Framework Components** tab.</span></span>

         <span data-ttu-id="26c88-118">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="26c88-118">– or –</span></span>

    - <span data-ttu-id="26c88-119">per aggiungere un componente COM o un controllo ActiveX, fare clic sulla scheda **Componenti COM**.</span><span class="sxs-lookup"><span data-stu-id="26c88-119">If you want to add a COM component or ActiveX control, click the **COM Components** tab.</span></span>

3. <span data-ttu-id="26c88-120">Se il controllo è indicato nella finestra di dialogo, verificare se è selezionato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="26c88-120">If your control is listed in the dialog box, confirm it is selected, and then click **OK**.</span></span>

     <span data-ttu-id="26c88-121">Il controllo viene aggiunto alla **della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="26c88-121">The control is added to the **Toolbox**.</span></span>

4. <span data-ttu-id="26c88-122">Se il controllo non è indicato nella finestra di dialogo, eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="26c88-122">If your control is not listed in the dialog box, do the following:</span></span>

    1. <span data-ttu-id="26c88-123">Fare clic sul pulsante **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="26c88-123">Click the **Browse** button.</span></span>

    2. <span data-ttu-id="26c88-124">Passare alla cartella che contiene il file DLL in cui si trova il controllo.</span><span class="sxs-lookup"><span data-stu-id="26c88-124">Browse to the folder that contains the .dll file that contains your control.</span></span>

    3. <span data-ttu-id="26c88-125">Selezionare il file DLL e fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="26c88-125">Select the .dll file and click **Open**.</span></span>

         <span data-ttu-id="26c88-126">Il controllo viene visualizzato nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="26c88-126">Your control appears in the dialog box.</span></span>

    4. <span data-ttu-id="26c88-127">Verificare se il controllo è selezionato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="26c88-127">Confirm that your control is selected, and then click **OK**.</span></span>

         <span data-ttu-id="26c88-128">Il controllo viene aggiunto alla **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="26c88-128">Your control is added to the **Toolbox**.</span></span>

## <a name="cannot-debug-the-windows-forms-user-control-or-component"></a><span data-ttu-id="26c88-129">Impossibile eseguire il debug del componente o controllo utente di Windows Form</span><span class="sxs-lookup"><span data-stu-id="26c88-129">Cannot Debug the Windows Forms User Control or Component</span></span>

<span data-ttu-id="26c88-130">Se il controllo deriva dalla <xref:System.Windows.Forms.UserControl> classe, è possibile eseguire il debug del comportamento in fase di esecuzione con il contenitore di test.</span><span class="sxs-lookup"><span data-stu-id="26c88-130">If your control derives from the <xref:System.Windows.Forms.UserControl> class, you can debug its run-time behavior with the test container.</span></span> <span data-ttu-id="26c88-131">Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di un](how-to-test-the-run-time-behavior-of-a-usercontrol.md)UserControl.</span><span class="sxs-lookup"><span data-stu-id="26c88-131">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

<span data-ttu-id="26c88-132">Altri componenti e controlli personalizzati non sono progetti autonomi.</span><span class="sxs-lookup"><span data-stu-id="26c88-132">Other custom controls and components are not stand-alone projects.</span></span> <span data-ttu-id="26c88-133">Devono essere ospitati da un'applicazione, ad esempio un progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="26c88-133">They must be hosted by an application such as a Windows Forms project.</span></span> <span data-ttu-id="26c88-134">Per eseguire il debug di un controllo o un componente, è necessario aggiungerlo a un progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="26c88-134">To debug a control or component, you must add it to a Windows Forms project.</span></span>

### <a name="to-debug-a-control-or-component"></a><span data-ttu-id="26c88-135">Per eseguire il debug di un controllo o componente</span><span class="sxs-lookup"><span data-stu-id="26c88-135">To debug a control or component</span></span>

1. <span data-ttu-id="26c88-136">Scegliere **Compila soluzione** dal menu **Compila** per creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="26c88-136">From the **Build** menu, click **Build Solution** to build your solution.</span></span>

2. <span data-ttu-id="26c88-137">Scegliere **Aggiungi** dal menu **File**, quindi selezionare **Nuovo progetto** per aggiungere un progetto di test all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26c88-137">From the **File** menu, choose **Add**, and then **New Project** to add a test project to your application.</span></span>

3. <span data-ttu-id="26c88-138">Nella finestra di dialogo **Aggiungi nuovo progetto** scegliere **Applicazione Windows** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="26c88-138">In the **Add New Project** dialog box choose **Windows Application** for the type of project.</span></span>

4. <span data-ttu-id="26c88-139">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Riferimenti** per il nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="26c88-139">In **Solution Explorer**, right-click the **References** node for the new project.</span></span> <span data-ttu-id="26c88-140">Nel menu di scelta rapida fare clic su **Aggiungi riferimento** per aggiungere un riferimento al progetto contenente il controllo o il componente.</span><span class="sxs-lookup"><span data-stu-id="26c88-140">On the shortcut menu, click **Add Reference** to add a reference to the project containing the control or component.</span></span>

5. <span data-ttu-id="26c88-141">Creare un'istanza del controllo o componente nel progetto di test.</span><span class="sxs-lookup"><span data-stu-id="26c88-141">Create an instance of your control or component in the test project.</span></span> <span data-ttu-id="26c88-142">Se il componente si trova nella **casella degli strumenti**, è possibile trascinarlo nell'area di progettazione oppure creare l'istanza a livello di codice, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="26c88-142">If your component is in the **Toolbox**, you can drag it to your designer surface, or you can create the instance programmatically, as shown in the following code example.</span></span>

    ```vb
    Dim Component1 As New MyNeatComponent()
    ```

    ```csharp
    MyNeatComponent Component1 = new MyNeatComponent();
    ```

   <span data-ttu-id="26c88-143">È ora possibile eseguire il debug del controllo o del componente come di consueto.</span><span class="sxs-lookup"><span data-stu-id="26c88-143">You can now debug your control or component as usual.</span></span>

<span data-ttu-id="26c88-144">Per ulteriori informazioni sul debug, vedere [debug in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) e [procedura dettagliata: Debug di controlli di Windows Forms personalizzati in](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="26c88-144">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) and [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>

## <a name="event-is-raised-twice-in-inherited-control-or-component"></a><span data-ttu-id="26c88-145">L'evento viene generato due volte nel componente o controllo ereditato</span><span class="sxs-lookup"><span data-stu-id="26c88-145">Event Is Raised Twice in Inherited Control or Component</span></span>

<span data-ttu-id="26c88-146">Ciò è probabilmente dovuto a una clausola `Handles` duplicata.</span><span class="sxs-lookup"><span data-stu-id="26c88-146">This is likely due to a duplicated `Handles` clause.</span></span> <span data-ttu-id="26c88-147">Per altre informazioni, vedere [Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="26c88-147">For more information, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>

## <a name="design-time-error-failed-to-create-component-component-name"></a><span data-ttu-id="26c88-148">Errore in fase di progettazione: "Impossibile creare il componente ' nome componente '"</span><span class="sxs-lookup"><span data-stu-id="26c88-148">Design-Time Error: "Failed to Create Component 'Component Name'"</span></span>

<span data-ttu-id="26c88-149">Il componente o il controllo deve fornire un costruttore senza parametri senza parametri.</span><span class="sxs-lookup"><span data-stu-id="26c88-149">Your component or control must provide a parameterless constructor with no parameters.</span></span> <span data-ttu-id="26c88-150">Quando l'ambiente di progettazione crea un'istanza del componente o controllo, non tenta di definire parametri per gli overload del costruttore che accettano tali parametri.</span><span class="sxs-lookup"><span data-stu-id="26c88-150">When the design environment creates an instance of your component or control, it does not attempt to provide any parameters to constructor overloads that take parameters.</span></span>

## <a name="stathreadattribute"></a><span data-ttu-id="26c88-151">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="26c88-151">STAThreadAttribute</span></span>

<span data-ttu-id="26c88-152"><xref:System.STAThreadAttribute> Informa il Common Language Runtime (CLR) che Windows Forms utilizza il modello di Apartment a thread singolo.</span><span class="sxs-lookup"><span data-stu-id="26c88-152">The <xref:System.STAThreadAttribute> informs the common language runtime (CLR) that Windows Forms uses the single-threaded apartment model.</span></span> <span data-ttu-id="26c88-153">È possibile riscontrare un comportamento imprevisto se non si applica questo attributo al metodo `Main` dell'applicazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="26c88-153">You may notice unintended behavior if you do not apply this attribute to your Windows Forms application's `Main` method.</span></span> <span data-ttu-id="26c88-154">Ad esempio, le immagini di sfondo potrebbero non essere visualizzate <xref:System.Windows.Forms.ListView>per i controlli come.</span><span class="sxs-lookup"><span data-stu-id="26c88-154">For example, background images may not appear for controls like <xref:System.Windows.Forms.ListView>.</span></span> <span data-ttu-id="26c88-155">Alcuni controlli possono inoltre richiedere questo attributo per il funzionamento corretto del completamento automatico e del trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="26c88-155">Some controls may also require this attribute for correct AutoComplete and drag-and-drop behavior.</span></span>

## <a name="component-icon-does-not-appear-in-toolbox"></a><span data-ttu-id="26c88-156">L'icona del componente non appare nella casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="26c88-156">Component Icon Does Not Appear in Toolbox</span></span>

<span data-ttu-id="26c88-157">Quando si utilizza <xref:System.Drawing.ToolboxBitmapAttribute> per associare un'icona al componente personalizzato, la bitmap non viene visualizzata nella casella degli strumenti per i componenti generati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="26c88-157">When you use <xref:System.Drawing.ToolboxBitmapAttribute> to associate an icon with your custom component, the bitmap does not appear in the Toolbox for autogenerated components.</span></span> <span data-ttu-id="26c88-158">Per visualizzare la bitmap, ricaricare il controllo usando la finestra di dialogo **Scegli elementi della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="26c88-158">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="26c88-159">Per altre informazioni, vedere [Procedura: Specificare una bitmap della casella degli strumenti](how-to-provide-a-toolbox-bitmap-for-a-control.md)per un controllo.</span><span class="sxs-lookup"><span data-stu-id="26c88-159">For more information, see [How to: Provide a Toolbox Bitmap for a Control](how-to-provide-a-toolbox-bitmap-for-a-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="26c88-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26c88-160">See also</span></span>

- [<span data-ttu-id="26c88-161">Sviluppo di controlli Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="26c88-161">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="26c88-162">Procedura dettagliata: Popolamento automatico della casella degli strumenti con componenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="26c88-162">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="26c88-163">Procedura: Testare il comportamento in fase di esecuzione di un UserControl</span><span class="sxs-lookup"><span data-stu-id="26c88-163">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [<span data-ttu-id="26c88-164">Procedura dettagliata: Debug di controlli di Windows Form personalizzati in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="26c88-164">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)
