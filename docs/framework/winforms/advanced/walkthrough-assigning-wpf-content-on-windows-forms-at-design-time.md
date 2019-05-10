---
title: 'Procedura dettagliata: Assegnazione del contenuto WPF in Windows Form in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
ms.openlocfilehash: 09427bfc836f40ca9c7aa76f4904bfe7083bf8dc
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211230"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="43197-102">Procedura dettagliata: Assegnare contenuto WPF in Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="43197-102">Walkthrough: Assign WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="43197-103">Questa procedura dettagliata illustra come selezionare i tipi di controllo Windows Presentation Foundation (WPF) da visualizzare nel form.</span><span class="sxs-lookup"><span data-stu-id="43197-103">This walkthrough show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="43197-104">È possibile selezionare qualsiasi tipo di controllo WPF incluso nel progetto.</span><span class="sxs-lookup"><span data-stu-id="43197-104">You can select any WPF control types which are included in your project.</span></span>

<span data-ttu-id="43197-105">Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="43197-105">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="43197-106">Creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="43197-106">Create the project.</span></span>

- <span data-ttu-id="43197-107">Creare i tipi di controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="43197-107">Create the WPF control types.</span></span>

- <span data-ttu-id="43197-108">Selezionare i controlli WPF.</span><span class="sxs-lookup"><span data-stu-id="43197-108">Select WPF controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="43197-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="43197-109">Prerequisites</span></span>

<span data-ttu-id="43197-110">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="43197-110">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="43197-111">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="43197-111">Create the project</span></span>

<span data-ttu-id="43197-112">Aprire Visual Studio e creare un nuovo progetto Windows Forms Application in Visual Basic o l'oggetto visivo C# denominato `SelectingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="43197-112">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="43197-113">Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="43197-113">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="43197-114">Creare i tipi di controllo WPF</span><span class="sxs-lookup"><span data-stu-id="43197-114">Create the WPF control types</span></span>

<span data-ttu-id="43197-115">Dopo avere aggiunto i tipi di controllo WPF al progetto, è possibile includerli in controlli <xref:System.Windows.Forms.Integration.ElementHost> diversi.</span><span class="sxs-lookup"><span data-stu-id="43197-115">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>

## <a name="create-wpf-control-types"></a><span data-ttu-id="43197-116">Creare tipi di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="43197-116">Create WPF control types</span></span>

1. <span data-ttu-id="43197-117">Aggiungere un nuovo progetto WPF <xref:System.Windows.Controls.UserControl> alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="43197-117">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="43197-118">Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="43197-118">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="43197-119">Per altre informazioni, vedere [Procedura dettagliata: Creare nuovo contenuto WPF in Windows Form in fase di progettazione](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="43197-119">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="43197-120">In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="43197-120">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="43197-121">Per altre informazioni, vedere [Procedura: Selezionare e spostare gli elementi nell'area di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="43197-121">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="43197-122">Nel **le proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà da `200`.</span><span class="sxs-lookup"><span data-stu-id="43197-122">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

4. <span data-ttu-id="43197-123">Aggiungere un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> il controllo al <xref:System.Windows.Controls.UserControl> e impostare il valore della <xref:System.Windows.Controls.TextBox.Text%2A> proprietà **contenuto ospitato**.</span><span class="sxs-lookup"><span data-stu-id="43197-123">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

5. <span data-ttu-id="43197-124">Aggiungere un secondo controllo WPF <xref:System.Windows.Controls.UserControl> al progetto.</span><span class="sxs-lookup"><span data-stu-id="43197-124">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="43197-125">Usare il nome predefinito per il tipo di controllo, `UserControl2.xaml`.</span><span class="sxs-lookup"><span data-stu-id="43197-125">Use the default name for the control type, `UserControl2.xaml`.</span></span>

6. <span data-ttu-id="43197-126">Nel **le proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà da `200`.</span><span class="sxs-lookup"><span data-stu-id="43197-126">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

7. <span data-ttu-id="43197-127">Aggiungere un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> il controllo al <xref:System.Windows.Controls.UserControl> e impostare il valore della <xref:System.Windows.Controls.TextBox.Text%2A> proprietà **Hosted Content 2**.</span><span class="sxs-lookup"><span data-stu-id="43197-127">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>

 <span data-ttu-id="43197-128">**Nota** In generale, è opportuno ospitare contenuto WPF più sofisticato.</span><span class="sxs-lookup"><span data-stu-id="43197-128">**Note** In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="43197-129">Il controllo <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> è qui usato a solo a titolo esemplificativo.</span><span class="sxs-lookup"><span data-stu-id="43197-129">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

1. <span data-ttu-id="43197-130">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="43197-130">Build the project.</span></span>

## <a name="select-wpf-controls"></a><span data-ttu-id="43197-131">Selezionare i controlli WPF</span><span class="sxs-lookup"><span data-stu-id="43197-131">Select WPF controls</span></span>

<span data-ttu-id="43197-132">È possibile assegnare contenuto WPF diverso a un controllo <xref:System.Windows.Forms.Integration.ElementHost> che include già contenuto.</span><span class="sxs-lookup"><span data-stu-id="43197-132">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>

1. <span data-ttu-id="43197-133">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="43197-133">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="43197-134">Nel **casella degli strumenti**, fare doppio clic su `UserControl1` per creare un'istanza di `UserControl1` nel form.</span><span class="sxs-lookup"><span data-stu-id="43197-134">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

     <span data-ttu-id="43197-135">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="43197-135">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

3. <span data-ttu-id="43197-136">Nel pannello smart tag per `elementHost1`, aprire il **selezione contenuto ospitato** elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="43197-136">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>

4. <span data-ttu-id="43197-137">Selezionare **UserControl2** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="43197-137">Select **UserControl2** from the drop-down list box.</span></span>

     <span data-ttu-id="43197-138">Il controllo `elementHost1` include ora un'istanza del tipo `UserControl2`.</span><span class="sxs-lookup"><span data-stu-id="43197-138">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>

5. <span data-ttu-id="43197-139">Nel **delle proprietà** finestra, verificare che il <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> è impostata su **UserControl2**.</span><span class="sxs-lookup"><span data-stu-id="43197-139">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>

6. <span data-ttu-id="43197-140">Dal **casella degli strumenti**, nella **interoperabilità WPF** gruppo, trascinare un <xref:System.Windows.Forms.Integration.ElementHost> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="43197-140">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>

     <span data-ttu-id="43197-141">Il nome predefinito del nuovo controllo è `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="43197-141">The default name for the new control is `elementHost2`.</span></span>

7. <span data-ttu-id="43197-142">Nel pannello smart tag per `elementHost2`, aprire il **selezione contenuto ospitato** elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="43197-142">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>

8. <span data-ttu-id="43197-143">Selezionare **UserControl1** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="43197-143">Select **UserControl1** from the drop-down list.</span></span>

9. <span data-ttu-id="43197-144">Il controllo `elementHost2` include ora un'istanza del tipo `UserControl1`.</span><span class="sxs-lookup"><span data-stu-id="43197-144">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>

## <a name="see-also"></a><span data-ttu-id="43197-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43197-145">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="43197-146">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="43197-146">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="43197-147">Uso di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="43197-147">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="43197-148">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="43197-148">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
