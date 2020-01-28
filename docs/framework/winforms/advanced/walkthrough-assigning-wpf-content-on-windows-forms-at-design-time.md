---
title: Selezionare i controlli WPF per Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 19f1dfec282b025f5a1fa367ec5fa9a52472c691
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746807"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="453ea-102">Procedura dettagliata: assegnare contenuto WPF in Windows Forms in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="453ea-102">Walkthrough: Assign WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="453ea-103">Questo articolo illustra come selezionare i tipi di controllo Windows Presentation Foundation (WPF) che si desidera visualizzare nel form.</span><span class="sxs-lookup"><span data-stu-id="453ea-103">This article show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="453ea-104">È possibile selezionare qualsiasi tipo di controllo WPF incluso nel progetto.</span><span class="sxs-lookup"><span data-stu-id="453ea-104">You can select any WPF control types that are included in your project.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="453ea-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="453ea-105">Prerequisites</span></span>

<span data-ttu-id="453ea-106">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="453ea-106">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="453ea-107">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="453ea-107">Create the project</span></span>

<span data-ttu-id="453ea-108">Aprire Visual Studio e creare un nuovo progetto di applicazione Windows Forms in Visual Basic o C# in un oggetto visivo denominato `SelectingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="453ea-108">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="453ea-109">Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="453ea-109">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="453ea-110">Creare i tipi di controllo WPF</span><span class="sxs-lookup"><span data-stu-id="453ea-110">Create the WPF control types</span></span>

<span data-ttu-id="453ea-111">Dopo avere aggiunto i tipi di controllo WPF al progetto, è possibile includerli in controlli <xref:System.Windows.Forms.Integration.ElementHost> diversi.</span><span class="sxs-lookup"><span data-stu-id="453ea-111">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>

1. <span data-ttu-id="453ea-112">Aggiungere un nuovo progetto WPF <xref:System.Windows.Controls.UserControl> alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="453ea-112">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="453ea-113">Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="453ea-113">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="453ea-114">Per ulteriori informazioni, vedere [procedura dettagliata: creazione di nuovi contenuti WPF in Windows Forms in fase di progettazione](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="453ea-114">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="453ea-115">In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="453ea-115">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="453ea-116">Nella finestra **Proprietà** impostare il valore delle proprietà <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> su **200**.</span><span class="sxs-lookup"><span data-stu-id="453ea-116">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="453ea-117">Aggiungere un controllo <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> al <xref:System.Windows.Controls.UserControl> e impostare il valore della proprietà <xref:System.Windows.Controls.TextBox.Text%2A> su **contenuto ospitato**.</span><span class="sxs-lookup"><span data-stu-id="453ea-117">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

5. <span data-ttu-id="453ea-118">Aggiungere un secondo controllo WPF <xref:System.Windows.Controls.UserControl> al progetto.</span><span class="sxs-lookup"><span data-stu-id="453ea-118">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="453ea-119">Usare il nome predefinito per il tipo di controllo, `UserControl2.xaml`.</span><span class="sxs-lookup"><span data-stu-id="453ea-119">Use the default name for the control type, `UserControl2.xaml`.</span></span>

6. <span data-ttu-id="453ea-120">Nella finestra **Proprietà** impostare il valore delle proprietà <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> su **200**.</span><span class="sxs-lookup"><span data-stu-id="453ea-120">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

7. <span data-ttu-id="453ea-121">Aggiungere un controllo <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> al <xref:System.Windows.Controls.UserControl> e impostare il valore della proprietà <xref:System.Windows.Controls.TextBox.Text%2A> su **contenuto ospitato 2**.</span><span class="sxs-lookup"><span data-stu-id="453ea-121">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="453ea-122">In generale, è opportuno ospitare contenuto WPF più sofisticato.</span><span class="sxs-lookup"><span data-stu-id="453ea-122">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="453ea-123">Il controllo <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> è qui usato a solo a titolo esemplificativo.</span><span class="sxs-lookup"><span data-stu-id="453ea-123">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

8. <span data-ttu-id="453ea-124">Compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="453ea-124">Build the project.</span></span>

## <a name="select-wpf-controls"></a><span data-ttu-id="453ea-125">Selezionare i controlli WPF</span><span class="sxs-lookup"><span data-stu-id="453ea-125">Select WPF controls</span></span>

<span data-ttu-id="453ea-126">È possibile assegnare contenuto WPF diverso a un controllo <xref:System.Windows.Forms.Integration.ElementHost> che include già contenuto.</span><span class="sxs-lookup"><span data-stu-id="453ea-126">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>

1. <span data-ttu-id="453ea-127">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="453ea-127">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="453ea-128">Nella **casella degli strumenti**fare doppio clic su `UserControl1` per creare un'istanza di `UserControl1` nel form.</span><span class="sxs-lookup"><span data-stu-id="453ea-128">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="453ea-129">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="453ea-129">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

3. <span data-ttu-id="453ea-130">Nel pannello smart tag per `elementHost1`aprire l'elenco a discesa **selezione contenuto ospitato** .</span><span class="sxs-lookup"><span data-stu-id="453ea-130">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>

4. <span data-ttu-id="453ea-131">Nella casella di riepilogo a discesa selezionare **UserControl2** .</span><span class="sxs-lookup"><span data-stu-id="453ea-131">Select **UserControl2** from the drop-down list box.</span></span>

   <span data-ttu-id="453ea-132">Il controllo `elementHost1` include ora un'istanza del tipo `UserControl2`.</span><span class="sxs-lookup"><span data-stu-id="453ea-132">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>

5. <span data-ttu-id="453ea-133">Nella finestra **Proprietà** verificare che la proprietà <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> sia impostata su **UserControl2**.</span><span class="sxs-lookup"><span data-stu-id="453ea-133">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>

6. <span data-ttu-id="453ea-134">Dalla **casella degli strumenti**, nel gruppo **interoperabilità WPF** trascinare un controllo <xref:System.Windows.Forms.Integration.ElementHost> nel form.</span><span class="sxs-lookup"><span data-stu-id="453ea-134">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>

   <span data-ttu-id="453ea-135">Il nome predefinito del nuovo controllo è `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="453ea-135">The default name for the new control is `elementHost2`.</span></span>

7. <span data-ttu-id="453ea-136">Nel pannello smart tag per `elementHost2`aprire l'elenco a discesa **selezione contenuto ospitato** .</span><span class="sxs-lookup"><span data-stu-id="453ea-136">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>

8. <span data-ttu-id="453ea-137">Selezionare **UserControl1** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="453ea-137">Select **UserControl1** from the drop-down list.</span></span>

9. <span data-ttu-id="453ea-138">Il controllo `elementHost2` include ora un'istanza del tipo `UserControl1`.</span><span class="sxs-lookup"><span data-stu-id="453ea-138">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>

## <a name="see-also"></a><span data-ttu-id="453ea-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="453ea-139">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="453ea-140">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="453ea-140">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="453ea-141">Uso di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="453ea-141">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="453ea-142">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="453ea-142">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
