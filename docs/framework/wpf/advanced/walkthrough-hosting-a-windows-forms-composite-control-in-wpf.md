---
title: Ospitare un controllo Windows Forms composito in WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: 16c09b4bb393fa830412385b4b405dd1fae9878b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745002"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a><span data-ttu-id="e5e3e-102">Procedura dettagliata: hosting di controlli Windows Form compositi in WPF</span><span class="sxs-lookup"><span data-stu-id="e5e3e-102">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="e5e3e-103">fornisce un ambiente completo per la creazione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-103">provides a rich environment for creating applications.</span></span> <span data-ttu-id="e5e3e-104">Tuttavia, quando si ha un investimento sostanziale nel codice [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], può essere più efficace riutilizzare almeno parte del codice nell'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] anziché riscriverla da zero.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-104">However, when you have a substantial investment in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] code, it can be more effective to reuse at least some of that code in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application rather than to rewrite it from scratch.</span></span> <span data-ttu-id="e5e3e-105">Lo scenario più comune è quello in cui si dispone di controlli di Windows Forms esistenti.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-105">The most common scenario is when you have existing Windows Forms controls.</span></span> <span data-ttu-id="e5e3e-106">In alcuni casi, è possibile che non si abbia accesso al codice sorgente di questi controlli.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-106">In some cases, you might not even have access to the source code for these controls.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="e5e3e-107">fornisce una procedura semplice per l'hosting di tali controlli in un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5e3e-107">provides a straightforward procedure for hosting such controls in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="e5e3e-108">Ad esempio, è possibile usare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per la maggior parte della programmazione durante l'hosting dei controlli <xref:System.Windows.Forms.DataGridView> specializzati.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-108">For example, you can use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] for most of your programming while hosting your specialized <xref:System.Windows.Forms.DataGridView> controls.</span></span>  
  
 <span data-ttu-id="e5e3e-109">Questa procedura dettagliata illustra un'applicazione che ospita un controllo Windows Forms composito per eseguire l'immissione di dati in un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5e3e-109">This walkthrough steps you through an application that hosts a Windows Forms composite control to perform data entry in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="e5e3e-110">Il controllo composito è compresso in una DLL.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-110">The composite control is packaged in a DLL.</span></span> <span data-ttu-id="e5e3e-111">Questa procedura generale può essere estesa ad applicazioni e controlli più complessi.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-111">This general procedure can be extended to more complex applications and controls.</span></span> <span data-ttu-id="e5e3e-112">Questa procedura dettagliata è progettata per essere pressoché identica per quanto riguarda aspetto e funzionalità per [la procedura dettagliata: hosting di un controllo composito WPF in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e5e3e-112">This walkthrough is designed to be nearly identical in appearance and functionality to [Walkthrough: Hosting a WPF Composite Control in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).</span></span> <span data-ttu-id="e5e3e-113">La principale differenza è che lo scenario di hosting è invertito.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-113">The primary difference is that the hosting scenario is reversed.</span></span>  
  
 <span data-ttu-id="e5e3e-114">La procedura guidata è suddivisa in due sezioni.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-114">The walkthrough is divided into two sections.</span></span> <span data-ttu-id="e5e3e-115">Nella prima sezione viene brevemente descritta l'implementazione del controllo Windows Forms composito.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-115">The first section briefly describes the implementation of the Windows Forms composite control.</span></span> <span data-ttu-id="e5e3e-116">La seconda sezione illustra in dettaglio come ospitare il controllo composito in un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ricevere eventi dal controllo e accedere ad alcune delle proprietà del controllo.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-116">The second section discusses in detail how to host the composite control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, receive events from the control, and access some of the control's properties.</span></span>  
  
 <span data-ttu-id="e5e3e-117">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5e3e-117">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="e5e3e-118">Implementazione del controllo Windows Forms composito.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-118">Implementing the Windows Forms composite control.</span></span>  
  
- <span data-ttu-id="e5e3e-119">Implementazione dell'applicazione host WPF.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-119">Implementing the WPF host application.</span></span>  
  
 <span data-ttu-id="e5e3e-120">Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere la pagina relativa all' [hosting di un controllo Windows Forms composito in WPF di esempio](https://go.microsoft.com/fwlink/?LinkID=159999).</span><span class="sxs-lookup"><span data-stu-id="e5e3e-120">For a complete code listing of the tasks illustrated in this walkthrough, see [Hosting a Windows Forms Composite Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159999).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e5e3e-121">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e5e3e-121">Prerequisites</span></span>  

<span data-ttu-id="e5e3e-122">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-122">You need Visual Studio to complete this walkthrough.</span></span>
  
## <a name="implementing-the-windows-forms-composite-control"></a><span data-ttu-id="e5e3e-123">Implementazione del controllo Windows Forms composito</span><span class="sxs-lookup"><span data-stu-id="e5e3e-123">Implementing the Windows Forms Composite Control</span></span>  
 <span data-ttu-id="e5e3e-124">Il Windows Forms controllo composito usato in questo esempio è un semplice form di immissione dati.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-124">The Windows Forms composite control used in this example is a simple data-entry form.</span></span> <span data-ttu-id="e5e3e-125">Questo form accetta nome e indirizzo dell'utente e quindi usa un evento personalizzato per restituire le informazioni all'host.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-125">This form takes the user's name and address and then uses a custom event to return that information to the host.</span></span> <span data-ttu-id="e5e3e-126">La figura seguente mostra il controllo sottoposto a rendering.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-126">The following illustration shows the rendered control.</span></span>  

 <span data-ttu-id="e5e3e-127">Nell'immagine seguente viene illustrato un controllo Windows Forms composito:</span><span class="sxs-lookup"><span data-stu-id="e5e3e-127">The following image shows a Windows Forms composite control:</span></span>  

 ![Screenshot che mostra un semplice controllo Windows Forms.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-forms-control.gif)  
  
### <a name="creating-the-project"></a><span data-ttu-id="e5e3e-129">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="e5e3e-129">Creating the Project</span></span>  
 <span data-ttu-id="e5e3e-130">Per avviare il progetto:</span><span class="sxs-lookup"><span data-stu-id="e5e3e-130">To start the project:</span></span>  
  
1. <span data-ttu-id="e5e3e-131">Avviare Visual Studio e aprire la finestra di dialogo **nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="e5e3e-131">Launch Visual Studio, and open the **New Project** dialog box.</span></span>  
  
2. <span data-ttu-id="e5e3e-132">Nella categoria finestra selezionare il modello **libreria di controlli Windows Forms** .</span><span class="sxs-lookup"><span data-stu-id="e5e3e-132">In the Window category, select the **Windows Forms Control Library** template.</span></span>  
  
3. <span data-ttu-id="e5e3e-133">Assegnare il nome `MyControls` al nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-133">Name the new project `MyControls`.</span></span>  
  
4. <span data-ttu-id="e5e3e-134">Per il percorso specificare una cartella di primo livello con un nome appropriato, ad esempio `WpfHostingWindowsFormsControl`.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-134">For the location, specify a conveniently named top-level folder, such as `WpfHostingWindowsFormsControl`.</span></span> <span data-ttu-id="e5e3e-135">Successivamente, si immetterà l'applicazione host in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-135">Later, you will put the host application in this folder.</span></span>  
  
5. <span data-ttu-id="e5e3e-136">Fare clic su **OK** per creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-136">Click **OK** to create the project.</span></span> <span data-ttu-id="e5e3e-137">Il progetto predefinito contiene un singolo controllo denominato `UserControl1`.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-137">The default project contains a single control named `UserControl1`.</span></span>  
  
6. <span data-ttu-id="e5e3e-138">In Esplora soluzioni rinominare `UserControl1` `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-138">In Solution Explorer, rename `UserControl1` to `MyControl1`.</span></span>  
  
 <span data-ttu-id="e5e3e-139">Il progetto dovrebbe includere riferimenti alle DLL di sistema seguenti.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-139">Your project should have references to the following system DLLs.</span></span> <span data-ttu-id="e5e3e-140">Se alcune di queste DLL non sono incluse per impostazione predefinita, aggiungerle al progetto.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-140">If any of these DLLs are not included by default, add them to the project.</span></span>  
  
- <span data-ttu-id="e5e3e-141">System</span><span class="sxs-lookup"><span data-stu-id="e5e3e-141">System</span></span>  
  
- <span data-ttu-id="e5e3e-142">System.Data</span><span class="sxs-lookup"><span data-stu-id="e5e3e-142">System.Data</span></span>  
  
- <span data-ttu-id="e5e3e-143">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="e5e3e-143">System.Drawing</span></span>  
  
- <span data-ttu-id="e5e3e-144">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="e5e3e-144">System.Windows.Forms</span></span>  
  
- <span data-ttu-id="e5e3e-145">System.Xml</span><span class="sxs-lookup"><span data-stu-id="e5e3e-145">System.Xml</span></span>  
  
### <a name="adding-controls-to-the-form"></a><span data-ttu-id="e5e3e-146">Aggiunta di controlli al form</span><span class="sxs-lookup"><span data-stu-id="e5e3e-146">Adding Controls to the Form</span></span>  
 <span data-ttu-id="e5e3e-147">Per aggiungere controlli al form:</span><span class="sxs-lookup"><span data-stu-id="e5e3e-147">To add controls to the form:</span></span>  
  
- <span data-ttu-id="e5e3e-148">Aprire `MyControl1` nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-148">Open `MyControl1` in the designer.</span></span>  
  
 <span data-ttu-id="e5e3e-149">Aggiungere cinque controlli <xref:System.Windows.Forms.Label> e i controlli <xref:System.Windows.Forms.TextBox> corrispondenti, ridimensionati e disposti come sono nell'illustrazione precedente, nel form.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-149">Add five <xref:System.Windows.Forms.Label> controls and their corresponding <xref:System.Windows.Forms.TextBox> controls, sized and arranged as they are in the preceding illustration, on the form.</span></span> <span data-ttu-id="e5e3e-150">Nell'esempio, i controlli <xref:System.Windows.Forms.TextBox> sono denominati:</span><span class="sxs-lookup"><span data-stu-id="e5e3e-150">In the example, the <xref:System.Windows.Forms.TextBox> controls are named:</span></span>  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 <span data-ttu-id="e5e3e-151">Aggiungere due controlli <xref:System.Windows.Forms.Button> con etichetta **OK** e **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-151">Add two <xref:System.Windows.Forms.Button> controls labeled **OK** and **Cancel**.</span></span> <span data-ttu-id="e5e3e-152">Nell'esempio i nomi dei pulsanti sono `btnOK` e `btnCancel`rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-152">In the example, the button names are `btnOK` and `btnCancel`, respectively.</span></span>  
  
### <a name="implementing-the-supporting-code"></a><span data-ttu-id="e5e3e-153">Implementazione del codice di supporto</span><span class="sxs-lookup"><span data-stu-id="e5e3e-153">Implementing the Supporting Code</span></span>  
 <span data-ttu-id="e5e3e-154">Aprire il form nella visualizzazione codice.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-154">Open the form in code view.</span></span> <span data-ttu-id="e5e3e-155">Il controllo restituisce i dati raccolti al relativo host generando l'evento `OnButtonClick` personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-155">The control returns the collected data to its host by raising the custom `OnButtonClick` event.</span></span> <span data-ttu-id="e5e3e-156">I dati sono contenuti nell'oggetto argomento dell'evento.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-156">The data is contained in the event argument object.</span></span> <span data-ttu-id="e5e3e-157">Il codice seguente mostra la dichiarazione di evento e delegato.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-157">The following code shows the event and delegate declaration.</span></span>  
  
 <span data-ttu-id="e5e3e-158">Aggiungere il codice seguente alla classe `MyControl1` .</span><span class="sxs-lookup"><span data-stu-id="e5e3e-158">Add the following code to the `MyControl1` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 <span data-ttu-id="e5e3e-159">La classe `MyControlEventArgs` contiene le informazioni da restituire all'host.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-159">The `MyControlEventArgs` class contains the information to be returned to the host.</span></span>

 <span data-ttu-id="e5e3e-160">Aggiungere la classe seguente al form.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-160">Add the following class to the form.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 <span data-ttu-id="e5e3e-161">Quando l'utente fa clic sul pulsante **OK** o **Annulla** , i gestori eventi <xref:System.Windows.Forms.Control.Click> creano un oggetto `MyControlEventArgs` che contiene i dati e genera l'evento di `OnButtonClick`.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-161">When the user clicks the **OK** or **Cancel** button, the <xref:System.Windows.Forms.Control.Click> event handlers create a `MyControlEventArgs` object that contains the data and raises the `OnButtonClick` event.</span></span> <span data-ttu-id="e5e3e-162">L'unica differenza tra i due gestori è la proprietà `IsOK` dell'argomento dell'evento.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-162">The only difference between the two handlers is the event argument's `IsOK` property.</span></span> <span data-ttu-id="e5e3e-163">Questa proprietà consente all'host di determinare su quale pulsante è stato fatto clic.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-163">This property enables the host to determine which button was clicked.</span></span> <span data-ttu-id="e5e3e-164">È impostato su `true` per il pulsante **OK** e `false` per il pulsante **Annulla** .</span><span class="sxs-lookup"><span data-stu-id="e5e3e-164">It is set to `true` for the **OK** button, and `false` for the **Cancel** button.</span></span> <span data-ttu-id="e5e3e-165">Il codice seguente illustra i gestori dei due pulsanti.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-165">The following code shows the two button handlers.</span></span>

 <span data-ttu-id="e5e3e-166">Aggiungere il codice seguente alla classe `MyControl1` .</span><span class="sxs-lookup"><span data-stu-id="e5e3e-166">Add the following code to the `MyControl1` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a><span data-ttu-id="e5e3e-167">Assegnazione di un nome sicuro all'assembly e compilazione dell'assembly</span><span class="sxs-lookup"><span data-stu-id="e5e3e-167">Giving the Assembly a Strong Name and Building the Assembly</span></span>
 <span data-ttu-id="e5e3e-168">Per fare in modo che a questo assembly venga fatto riferimento da un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è necessario che disponga di un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-168">For this assembly to be referenced by a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, it must have a strong name.</span></span> <span data-ttu-id="e5e3e-169">Per creare un nome sicuro, creare un file di chiave con sn. exe e aggiungerlo al progetto.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-169">To create a strong name, create a key file with Sn.exe and add it to your project.</span></span>

1. <span data-ttu-id="e5e3e-170">Aprire il prompt dei comandi di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-170">Open a Visual Studio command prompt.</span></span> <span data-ttu-id="e5e3e-171">A tale scopo, fare clic sul menu **Start** , quindi selezionare **tutti i programmi/Microsoft Visual Studio 2010/strumenti di Visual Studio/prompt dei comandi di Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-171">To do so, click the **Start** menu, and then select **All Programs/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio Command Prompt**.</span></span> <span data-ttu-id="e5e3e-172">Verrà avviata una finestra della console con variabili di ambiente personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-172">This launches a console window with customized environment variables.</span></span>

2. <span data-ttu-id="e5e3e-173">Al prompt dei comandi usare il comando `cd` per passare alla cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-173">At the command prompt, use the `cd` command to go to your project folder.</span></span>

3. <span data-ttu-id="e5e3e-174">Generare un file di chiave denominato MyControls.snk eseguendo il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-174">Generate a key file named MyControls.snk by running the following command.</span></span>

    ```console
    Sn.exe -k MyControls.snk
    ```

4. <span data-ttu-id="e5e3e-175">Per includere il file di chiave nel progetto, fare clic con il pulsante destro del mouse sul nome del progetto in Esplora soluzioni e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-175">To include the key file in your project, right-click the project name in Solution Explorer and then click **Properties**.</span></span> <span data-ttu-id="e5e3e-176">In Creazione progetti fare clic sulla scheda **firma** , selezionare la casella di controllo **Firma assembly** e quindi passare al file di chiave.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-176">In the Project Designer, click the **Signing** tab, select the **Sign the assembly** check box and then browse to your key file.</span></span>

5. <span data-ttu-id="e5e3e-177">Compila la soluzione.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-177">Build the solution.</span></span> <span data-ttu-id="e5e3e-178">La compilazione genererà una DLL denominata MyControls.dll.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-178">The build will produce a DLL named MyControls.dll.</span></span>

## <a name="implementing-the-wpf-host-application"></a><span data-ttu-id="e5e3e-179">Implementazione dell'applicazione host WPF</span><span class="sxs-lookup"><span data-stu-id="e5e3e-179">Implementing the WPF Host Application</span></span>
 <span data-ttu-id="e5e3e-180">L'applicazione host [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa il controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> per ospitare `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-180">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] host application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control to host `MyControl1`.</span></span> <span data-ttu-id="e5e3e-181">L'applicazione gestisce l'evento `OnButtonClick` per ricevere i dati dal controllo.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-181">The application handles the `OnButtonClick` event to receive the data from the control.</span></span> <span data-ttu-id="e5e3e-182">Dispone inoltre di una raccolta di pulsanti di opzione che consentono di modificare alcune delle proprietà del controllo dall'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5e3e-182">It also has a collection of option buttons that enable you to change some of the control's properties from the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="e5e3e-183">La figura seguente illustra l'applicazione finita.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-183">The following illustration shows the finished application.</span></span>

<span data-ttu-id="e5e3e-184">Nell'immagine seguente viene illustrata l'applicazione completa, incluso il controllo incorporato nell'applicazione WPF:</span><span class="sxs-lookup"><span data-stu-id="e5e3e-184">The following image shows the complete application, including the control embedded in the WPF application:</span></span>

 ![Screenshot che mostra un controllo incorporato in una pagina WPF.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a><span data-ttu-id="e5e3e-186">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="e5e3e-186">Creating the Project</span></span>
 <span data-ttu-id="e5e3e-187">Per avviare il progetto:</span><span class="sxs-lookup"><span data-stu-id="e5e3e-187">To start the project:</span></span>

1. <span data-ttu-id="e5e3e-188">Aprire Visual Studio e selezionare **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-188">Open Visual Studio, and select **New Project**.</span></span>

2. <span data-ttu-id="e5e3e-189">Nella categoria finestra selezionare il modello **applicazione WPF** .</span><span class="sxs-lookup"><span data-stu-id="e5e3e-189">In the Window category, select the **WPF Application** template.</span></span>

3. <span data-ttu-id="e5e3e-190">Assegnare il nome `WpfHost` al nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-190">Name the new project `WpfHost`.</span></span>

4. <span data-ttu-id="e5e3e-191">Come percorso, specificare la stessa cartella di livello superiore che contiene il progetto MyControls.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-191">For the location, specify the same top-level folder that contains the MyControls project.</span></span>

5. <span data-ttu-id="e5e3e-192">Fare clic su **OK** per creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-192">Click **OK** to create the project.</span></span>

 <span data-ttu-id="e5e3e-193">È anche necessario aggiungere riferimenti alla DLL che contiene `MyControl1` e altri assembly.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-193">You also need to add references to the DLL that contains `MyControl1` and other assemblies.</span></span>

1. <span data-ttu-id="e5e3e-194">Fare clic con il pulsante destro del mouse sul nome del progetto in Esplora soluzioni e scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-194">Right-click the project name in Solution Explorer and select **Add Reference**.</span></span>

2. <span data-ttu-id="e5e3e-195">Fare clic sulla scheda **Sfoglia** e selezionare la cartella che contiene i controlli. dll.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-195">Click the **Browse** tab, and browse to the folder that contains MyControls.dll.</span></span> <span data-ttu-id="e5e3e-196">In questa procedura dettagliata la cartella è MyControls\bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-196">For this walkthrough, this folder is MyControls\bin\Debug.</span></span>

3. <span data-ttu-id="e5e3e-197">Selezionare controllo. dll e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-197">Select MyControls.dll, and then click **OK**.</span></span>

4. <span data-ttu-id="e5e3e-198">Aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration. dll.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-198">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

### <a name="implementing-the-basic-layout"></a><span data-ttu-id="e5e3e-199">Implementazione del layout di base</span><span class="sxs-lookup"><span data-stu-id="e5e3e-199">Implementing the Basic Layout</span></span>
 <span data-ttu-id="e5e3e-200">Il [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dell'applicazione host viene implementato nel file MainWindow. XAML.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-200">The [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] of the host application is implemented in MainWindow.xaml.</span></span> <span data-ttu-id="e5e3e-201">Questo file contiene [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup che definisce il layout e ospita il controllo Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-201">This file contains [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup that defines the layout, and hosts the Windows Forms control.</span></span> <span data-ttu-id="e5e3e-202">L'applicazione è suddivisa in tre aree:</span><span class="sxs-lookup"><span data-stu-id="e5e3e-202">The application is divided into three regions:</span></span>

- <span data-ttu-id="e5e3e-203">Il pannello **Proprietà controllo** , che contiene una raccolta di pulsanti di opzione che è possibile utilizzare per modificare varie proprietà del controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-203">The **Control Properties** panel, which contains a collection of option buttons that you can use to modify various properties of the hosted control.</span></span>

- <span data-ttu-id="e5e3e-204">**Dati dal pannello di controllo** , che contiene diversi elementi <xref:System.Windows.Controls.TextBlock> che visualizzano i dati restituiti dal controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-204">The **Data from Control** panel, which contains several <xref:System.Windows.Controls.TextBlock> elements that display the data returned from the hosted control.</span></span>

- <span data-ttu-id="e5e3e-205">Il controllo ospitato stesso.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-205">The hosted control itself.</span></span>

 <span data-ttu-id="e5e3e-206">Il layout di base è illustrato nel codice XAML seguente.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-206">The basic layout is shown in the following XAML.</span></span> <span data-ttu-id="e5e3e-207">Il markup necessario per ospitare `MyControl1` viene omesso da questo esempio, ma verrà discusso più avanti.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-207">The markup that is needed to host `MyControl1` is omitted from this example, but will be discussed later.</span></span>

 <span data-ttu-id="e5e3e-208">Sostituire il codice XAML in MainWindow.xaml con il seguente.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-208">Replace the XAML in MainWindow.xaml with the following.</span></span> <span data-ttu-id="e5e3e-209">Se si utilizza Visual Basic, impostare la classe su `x:Class="MainWindow"`.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-209">If you are using Visual Basic, change the class to `x:Class="MainWindow"`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 <span data-ttu-id="e5e3e-210">Il primo elemento <xref:System.Windows.Controls.StackPanel> contiene diversi set di controlli <xref:System.Windows.Controls.RadioButton> che consentono di modificare diverse proprietà predefinite del controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-210">The first <xref:System.Windows.Controls.StackPanel> element contains several sets of <xref:System.Windows.Controls.RadioButton> controls that enable you to modify various default properties of the hosted control.</span></span> <span data-ttu-id="e5e3e-211">Seguito da un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> che ospita `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-211">That is followed by a <xref:System.Windows.Forms.Integration.WindowsFormsHost> element, which hosts `MyControl1`.</span></span> <span data-ttu-id="e5e3e-212">L'elemento <xref:System.Windows.Controls.StackPanel> finale contiene diversi elementi <xref:System.Windows.Controls.TextBlock> che visualizzano i dati restituiti dal controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-212">The final <xref:System.Windows.Controls.StackPanel> element contains several <xref:System.Windows.Controls.TextBlock> elements that display the data that is returned by the hosted control.</span></span> <span data-ttu-id="e5e3e-213">L'ordinamento degli elementi e le impostazioni degli attributi <xref:System.Windows.Controls.DockPanel.Dock%2A> e <xref:System.Windows.FrameworkElement.Height%2A> incorporano il controllo ospitato nella finestra senza gap o distorsione.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-213">The ordering of the elements and the <xref:System.Windows.Controls.DockPanel.Dock%2A> and <xref:System.Windows.FrameworkElement.Height%2A> attribute settings embed the hosted control into the window with no gaps or distortion.</span></span>

#### <a name="hosting-the-control"></a><span data-ttu-id="e5e3e-214">Hosting del controllo</span><span class="sxs-lookup"><span data-stu-id="e5e3e-214">Hosting the Control</span></span>
 <span data-ttu-id="e5e3e-215">La versione modificata seguente del codice XAML precedente è incentrata sugli elementi necessari per ospitare `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-215">The following edited version of the previous XAML focuses on the elements that are needed to host `MyControl1`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 <span data-ttu-id="e5e3e-216">L'attributo di mapping dello spazio dei nomi `xmlns` crea un riferimento allo spazio dei nomi `MyControls` che contiene il controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-216">The `xmlns` namespace mapping attribute creates a reference to the `MyControls` namespace that contains the hosted control.</span></span> <span data-ttu-id="e5e3e-217">Questo mapping consente di rappresentare `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] `<mcl:MyControl1>`.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-217">This mapping enables you to represent `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] as `<mcl:MyControl1>`.</span></span>

 <span data-ttu-id="e5e3e-218">Due elementi nel codice XAML gestiscono l'hosting:</span><span class="sxs-lookup"><span data-stu-id="e5e3e-218">Two elements in the XAML handle the hosting:</span></span>

- <span data-ttu-id="e5e3e-219">`WindowsFormsHost` rappresenta l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> che consente di ospitare un controllo Windows Forms in un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5e3e-219">`WindowsFormsHost` represents the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element that enables you to host a Windows Forms control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

- <span data-ttu-id="e5e3e-220">`mcl:MyControl1`, che rappresenta `MyControl1`, viene aggiunto alla raccolta figlio dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-220">`mcl:MyControl1`, which represents `MyControl1`, is added to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child collection.</span></span> <span data-ttu-id="e5e3e-221">Di conseguenza, viene eseguito il rendering di questo controllo Windows Forms come parte della finestra di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ed è possibile comunicare con il controllo dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-221">As a result, this Windows Forms control is rendered as part of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] window, and you can communicate with the control from the application.</span></span>

### <a name="implementing-the-code-behind-file"></a><span data-ttu-id="e5e3e-222">Implementazione del file code-behind</span><span class="sxs-lookup"><span data-stu-id="e5e3e-222">Implementing the Code-Behind File</span></span>
 <span data-ttu-id="e5e3e-223">Il file code-behind, MainWindow. XAML. vb o MainWindow.xaml.cs, contiene il codice procedurale che implementa la funzionalità della [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] descritta nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-223">The code-behind file, MainWindow.xaml.vb or MainWindow.xaml.cs, contains the procedural code that implements the functionality of the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] discussed in the preceding section.</span></span> <span data-ttu-id="e5e3e-224">Le attività principali sono:</span><span class="sxs-lookup"><span data-stu-id="e5e3e-224">The primary tasks are:</span></span>

- <span data-ttu-id="e5e3e-225">Associazione di un gestore eventi all'evento `OnButtonClick` di `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-225">Attaching an event handler to `MyControl1`'s `OnButtonClick` event.</span></span>

- <span data-ttu-id="e5e3e-226">Modifica di diverse proprietà di `MyControl1`, in base alla modalità di impostazione della raccolta di pulsanti di opzione.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-226">Modifying various properties of `MyControl1`, based on how the collection of option buttons are set.</span></span>

- <span data-ttu-id="e5e3e-227">Visualizzare i dati raccolti dal controllo.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-227">Displaying the data collected by the control.</span></span>

#### <a name="initializing-the-application"></a><span data-ttu-id="e5e3e-228">Inizializzazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="e5e3e-228">Initializing the Application</span></span>
 <span data-ttu-id="e5e3e-229">Il codice di inizializzazione è contenuto in un gestore eventi per l'evento <xref:System.Windows.FrameworkElement.Loaded> della finestra e connette un gestore eventi all'evento `OnButtonClick` del controllo.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-229">The initialization code is contained in an event handler for the window's <xref:System.Windows.FrameworkElement.Loaded> event and attaches an event handler to the control's `OnButtonClick` event.</span></span>

 <span data-ttu-id="e5e3e-230">In MainWindow. XAML. vb o MainWindow.xaml.cs aggiungere il codice seguente alla classe `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-230">In MainWindow.xaml.vb or MainWindow.xaml.cs, add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 <span data-ttu-id="e5e3e-231">Poiché la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] descritta in precedenza ha aggiunto `MyControl1` alla raccolta di elementi figlio dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, è possibile eseguire il cast del <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> per ottenere il riferimento a `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-231">Because the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] discussed previously added `MyControl1` to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child element collection, you can cast the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> to get the reference to `MyControl1`.</span></span> <span data-ttu-id="e5e3e-232">È quindi possibile utilizzare tale riferimento per alleghi un gestore eventi a `OnButtonClick`.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-232">You can then use that reference to attach an event handler to `OnButtonClick`.</span></span>

 <span data-ttu-id="e5e3e-233">Oltre a fornire un riferimento al controllo stesso, <xref:System.Windows.Forms.Integration.WindowsFormsHost> espone alcune proprietà del controllo, che è possibile modificare dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-233">In addition to providing a reference to the control itself, <xref:System.Windows.Forms.Integration.WindowsFormsHost> exposes a number of the control's properties, which you can manipulate from the application.</span></span> <span data-ttu-id="e5e3e-234">Il codice di inizializzazione assegna tali valori a variabili globali private per l'uso successivo nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-234">The initialization code assigns those values to private global variables for later use in the application.</span></span>

 <span data-ttu-id="e5e3e-235">Per poter accedere facilmente ai tipi nella DLL `MyControls`, aggiungere la `Imports` o l'istruzione `using` seguente all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-235">So that you can easily access the types in the `MyControls` DLL, add the following `Imports` or `using` statement to the top of the file.</span></span>

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a><span data-ttu-id="e5e3e-236">Gestione dell'evento OnButtonClick</span><span class="sxs-lookup"><span data-stu-id="e5e3e-236">Handling the OnButtonClick Event</span></span>
 <span data-ttu-id="e5e3e-237">`MyControl1` genera l'evento `OnButtonClick` quando l'utente fa clic su uno dei pulsanti del controllo.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-237">`MyControl1` raises the `OnButtonClick` event when the user clicks either of the control's buttons.</span></span>

 <span data-ttu-id="e5e3e-238">Aggiungere il codice seguente alla classe `MainWindow` .</span><span class="sxs-lookup"><span data-stu-id="e5e3e-238">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 <span data-ttu-id="e5e3e-239">I dati nelle caselle di testo vengono compressi nell'oggetto `MyControlEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-239">The data in the text boxes is packed into the `MyControlEventArgs` object.</span></span> <span data-ttu-id="e5e3e-240">Se l'utente fa clic sul pulsante **OK** , il gestore dell'evento estrae i dati e li Visualizza nel pannello riportato di seguito `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-240">If the user clicks the **OK** button, the event handler extracts the data and displays it in the panel below `MyControl1`.</span></span>

#### <a name="modifying-the-controls-properties"></a><span data-ttu-id="e5e3e-241">Modifica delle proprietà del controllo</span><span class="sxs-lookup"><span data-stu-id="e5e3e-241">Modifying the Control’s Properties</span></span>
 <span data-ttu-id="e5e3e-242">L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> espone diverse proprietà predefinite del controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-242">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element exposes several of the hosted control's default properties.</span></span> <span data-ttu-id="e5e3e-243">Di conseguenza, è possibile modificare l'aspetto del controllo in modo che corrisponda maggiormente allo stile dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-243">As a result, you can change the appearance of the control to match the style of your application more closely.</span></span> <span data-ttu-id="e5e3e-244">Gli insiemi di pulsanti di opzione nel pannello di sinistra consentono all'utente di modificare varie proprietà di colore e tipo di carattere.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-244">The sets of option buttons in the left panel enable the user to modify several color and font properties.</span></span> <span data-ttu-id="e5e3e-245">Ogni set di pulsanti dispone di un gestore per l'evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, che rileva le selezioni dei pulsanti di opzione dell'utente e modifica la proprietà corrispondente nel controllo.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-245">Each set of buttons has a handler for the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which detects the user's option button selections and changes the corresponding property on the control.</span></span>

 <span data-ttu-id="e5e3e-246">Aggiungere il codice seguente alla classe `MainWindow` .</span><span class="sxs-lookup"><span data-stu-id="e5e3e-246">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 <span data-ttu-id="e5e3e-247">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-247">Build and run the application.</span></span> <span data-ttu-id="e5e3e-248">Aggiungere testo nel controllo Windows Forms composito, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-248">Add some text in the Windows Forms composite control and then click **OK**.</span></span> <span data-ttu-id="e5e3e-249">Il testo viene visualizzato nelle etichette.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-249">The text appears in the labels.</span></span> <span data-ttu-id="e5e3e-250">Fare clic sui vari pulsanti di opzione per vedere l'effetto sul controllo.</span><span class="sxs-lookup"><span data-stu-id="e5e3e-250">Click the different radio buttons to see the effect on the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5e3e-251">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5e3e-251">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="e5e3e-252">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e5e3e-252">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="e5e3e-253">Procedura dettagliata: hosting di controlli Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="e5e3e-253">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="e5e3e-254">Procedura dettaglia: hosting di un controllo WPF composito in Windows Form</span><span class="sxs-lookup"><span data-stu-id="e5e3e-254">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
