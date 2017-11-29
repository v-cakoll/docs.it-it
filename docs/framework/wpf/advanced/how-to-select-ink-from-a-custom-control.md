---
title: 'Procedura: selezionare l''input penna da un controllo personalizzato'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dd9693209cc35ecd3c0473133b7c21639a239ff5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-select-ink-from-a-custom-control"></a><span data-ttu-id="98bcf-102">Procedura: selezionare l'input penna da un controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="98bcf-102">How to: Select Ink from a Custom Control</span></span>
<span data-ttu-id="98bcf-103">Aggiungendo un <xref:System.Windows.Ink.IncrementalLassoHitTester> al controllo personalizzato, è possibile abilitare il controllo in modo che un utente può selezionare input penna con lo strumento, analogamente al modo in cui il <xref:System.Windows.Controls.InkCanvas> seleziona input penna con un lazo.</span><span class="sxs-lookup"><span data-stu-id="98bcf-103">By adding an <xref:System.Windows.Ink.IncrementalLassoHitTester> to your custom control, you can enable your control so that a user can select ink with a lasso tool, similar to the way the <xref:System.Windows.Controls.InkCanvas> selects ink with a lasso.</span></span>  
  
 <span data-ttu-id="98bcf-104">In questo esempio si presuppone che si ha familiarità con la creazione di un controllo personalizzato abilitato input penna.</span><span class="sxs-lookup"><span data-stu-id="98bcf-104">This example assumes you are familiar with creating an ink-enabled custom control.</span></span>  <span data-ttu-id="98bcf-105">Per creare un controllo personalizzato che accetta l'input penna, vedere [la creazione di un controllo di Input penna](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).</span><span class="sxs-lookup"><span data-stu-id="98bcf-105">To create a custom control that accepts ink input, see [Creating an Ink Input Control](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98bcf-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="98bcf-106">Example</span></span>  
 <span data-ttu-id="98bcf-107">Quando l'utente utilizza lo strumento lazo, il <xref:System.Windows.Ink.IncrementalLassoHitTester> consente di stimare quali tratti sarà all'interno dei confini del lazo lazo al termine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="98bcf-107">When the user draws a lasso, the <xref:System.Windows.Ink.IncrementalLassoHitTester> predicts which strokes will be within the lasso path's boundaries after the user completes the lasso.</span></span>  <span data-ttu-id="98bcf-108">I tratti che sono determinati all'interno dei confini del lazo possono essere considerati come selezionato.</span><span class="sxs-lookup"><span data-stu-id="98bcf-108">Strokes that are determined to be within the lasso path's boundaries can be thought of as being selected.</span></span>  <span data-ttu-id="98bcf-109">Tratti selezionati possono anche essere deselezionati.</span><span class="sxs-lookup"><span data-stu-id="98bcf-109">Selected strokes can also become unselected.</span></span>  <span data-ttu-id="98bcf-110">Se l'utente cambia direzione mentre lazo, ad esempio il <xref:System.Windows.Ink.IncrementalLassoHitTester> deselezione di alcuni tratti.</span><span class="sxs-lookup"><span data-stu-id="98bcf-110">For example, if the user reverses direction while drawing the lasso, the <xref:System.Windows.Ink.IncrementalLassoHitTester> may unselect some strokes.</span></span>  
  
 <span data-ttu-id="98bcf-111">Il <xref:System.Windows.Ink.IncrementalLassoHitTester> genera il <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> evento, che consente di rispondere mentre l'utente è lazo un controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="98bcf-111">The <xref:System.Windows.Ink.IncrementalLassoHitTester> raises the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event, which enables your custom control to respond while the user is drawing the lasso.</span></span>  <span data-ttu-id="98bcf-112">Ad esempio, è possibile modificare l'aspetto dei tratti come utente selezionati e deselezionati.</span><span class="sxs-lookup"><span data-stu-id="98bcf-112">For example, you can change the appearance of strokes as the user selects and unselects them.</span></span>  
  
## <a name="managing-the-ink-mode"></a><span data-ttu-id="98bcf-113">Gestione della modalità di input penna</span><span class="sxs-lookup"><span data-stu-id="98bcf-113">Managing the Ink Mode</span></span>  
 <span data-ttu-id="98bcf-114">È utile per l'utente se il lazo sia diverso rispetto all'input penna sul controllo.</span><span class="sxs-lookup"><span data-stu-id="98bcf-114">It is helpful to the user if the lasso appears differently than the ink on your control.</span></span> <span data-ttu-id="98bcf-115">A tale scopo, il controllo personalizzato deve tenere traccia di se l'utente è la scrittura o la selezione di input penna.</span><span class="sxs-lookup"><span data-stu-id="98bcf-115">To accomplish this, your custom control must keep track of whether the user is writing or selecting ink.</span></span> <span data-ttu-id="98bcf-116">Il modo più semplice per eseguire questa operazione consiste nel dichiarare un'enumerazione con due valori: una per indicare che l'utente scrive input penna e uno per indicare che l'utente seleziona l'input penna.</span><span class="sxs-lookup"><span data-stu-id="98bcf-116">The easiest way to do this is to declare an enumeration with two values: one to indicate that the user is writing ink and one to indicate that the user is selecting ink.</span></span>  
  
 [!code-csharp[HowToSelectInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 <span data-ttu-id="98bcf-117">Successivamente, aggiungere due <xref:System.Windows.Ink.DrawingAttributes> alla classe: utilizzare quando l'utente scrive input penna, uno da utilizzare quando l'utente seleziona l'input penna.</span><span class="sxs-lookup"><span data-stu-id="98bcf-117">Next, add two <xref:System.Windows.Ink.DrawingAttributes> to the class: one to use when the user writes ink, one to use when the user selects ink.</span></span>  <span data-ttu-id="98bcf-118">Nel costruttore, inizializzare il <xref:System.Windows.Ink.DrawingAttributes> e collegare entrambi <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> eventi al gestore dell'evento stesso.</span><span class="sxs-lookup"><span data-stu-id="98bcf-118">In the constructor, initialize the <xref:System.Windows.Ink.DrawingAttributes> and attach both <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> events to the same event handler.</span></span> <span data-ttu-id="98bcf-119">Impostare quindi la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> proprietà del <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> all'input penna <xref:System.Windows.Ink.DrawingAttributes>.</span><span class="sxs-lookup"><span data-stu-id="98bcf-119">Then set the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> property of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the ink <xref:System.Windows.Ink.DrawingAttributes>.</span></span>  
  
 [!code-csharp[HowToSelectInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 <span data-ttu-id="98bcf-120">Aggiungere una proprietà che espone la modalità di selezione.</span><span class="sxs-lookup"><span data-stu-id="98bcf-120">Add a property that exposes the selection mode.</span></span> <span data-ttu-id="98bcf-121">Quando l'utente modifica la modalità di selezione, impostare il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> proprietà del <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> appropriati <xref:System.Windows.Ink.DrawingAttributes> dell'oggetto e quindi ricollegare il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> proprietà per il <xref:System.Windows.Controls.InkPresenter>.</span><span class="sxs-lookup"><span data-stu-id="98bcf-121">When the user changes the selection mode, set the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> property of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the appropriate <xref:System.Windows.Ink.DrawingAttributes> object and then reattach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> Property to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[HowToSelectInk#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 <span data-ttu-id="98bcf-122">Esporre il <xref:System.Windows.Ink.DrawingAttributes> come proprietà affinché le applicazioni possono determinare l'aspetto dei tratti input penna e selezione.</span><span class="sxs-lookup"><span data-stu-id="98bcf-122">Expose the <xref:System.Windows.Ink.DrawingAttributes> as properties so applications can determine the appearance of the ink strokes and selection strokes.</span></span>  
  
 [!code-csharp[HowToSelectInk#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 <span data-ttu-id="98bcf-123">Quando una proprietà di un <xref:System.Windows.Ink.DrawingAttributes> oggetto viene modificato, il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> devono essere ricollegate al <xref:System.Windows.Controls.InkPresenter>.</span><span class="sxs-lookup"><span data-stu-id="98bcf-123">When a property of a <xref:System.Windows.Ink.DrawingAttributes> object changes, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> must be reattached to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  <span data-ttu-id="98bcf-124">Nel gestore eventi per il <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> evento, ricollegare il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> per il <xref:System.Windows.Controls.InkPresenter>.</span><span class="sxs-lookup"><span data-stu-id="98bcf-124">In the event handler for the <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> event, reattach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[HowToSelectInk#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a><span data-ttu-id="98bcf-125">Utilizzo di IncrementalLassoHitTester</span><span class="sxs-lookup"><span data-stu-id="98bcf-125">Using the IncrementalLassoHitTester</span></span>  
 <span data-ttu-id="98bcf-126">Creare e inizializzare un <xref:System.Windows.Ink.StrokeCollection> che contiene i tratti selezionati.</span><span class="sxs-lookup"><span data-stu-id="98bcf-126">Create and initialize a <xref:System.Windows.Ink.StrokeCollection> that contains the selected strokes.</span></span>  
  
 [!code-csharp[HowToSelectInk#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 <span data-ttu-id="98bcf-127">Quando l'utente inizia a disegnare un tratto, input penna o lazo, deselezionare tutte le tracce selezionate.</span><span class="sxs-lookup"><span data-stu-id="98bcf-127">When the user starts to draw a stroke, either ink or the lasso, unselect any selected strokes.</span></span> <span data-ttu-id="98bcf-128">Se l'utente disegna un lazo, creare un <xref:System.Windows.Ink.IncrementalLassoHitTester> chiamando <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, sottoscrivere il <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> evento e chiamare <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>.</span><span class="sxs-lookup"><span data-stu-id="98bcf-128">Then, if the user is drawing a lasso, create an <xref:System.Windows.Ink.IncrementalLassoHitTester> by calling <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, subscribe to the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event, and call <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>.</span></span> <span data-ttu-id="98bcf-129">Questo codice può essere un metodo separato e chiamata dal <xref:System.Windows.UIElement.OnStylusDown%2A> e <xref:System.Windows.UIElement.OnMouseDown%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="98bcf-129">This code can be a separate method and called from the <xref:System.Windows.UIElement.OnStylusDown%2A> and <xref:System.Windows.UIElement.OnMouseDown%2A> methods.</span></span>  
  
 [!code-csharp[HowToSelectInk#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 <span data-ttu-id="98bcf-130">Aggiungere i punti dello stilo per il <xref:System.Windows.Ink.IncrementalLassoHitTester> mentre l'utente disegna il lazo.</span><span class="sxs-lookup"><span data-stu-id="98bcf-130">Add the stylus points to the <xref:System.Windows.Ink.IncrementalLassoHitTester> while the user draws the lasso.</span></span>  <span data-ttu-id="98bcf-131">Chiamare il metodo seguente dal <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, e <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="98bcf-131">Call the following method from the <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, and <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> methods.</span></span>  
  
 [!code-csharp[HowToSelectInk#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 <span data-ttu-id="98bcf-132">Gestire il <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> rispondere quando l'utente seleziona e deseleziona tratti dell'evento.</span><span class="sxs-lookup"><span data-stu-id="98bcf-132">Handle the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> event to respond when the user selects and unselects strokes.</span></span>  <span data-ttu-id="98bcf-133">Il <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> classe dispone di <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> e <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> proprietà che recuperano i tratti che sono state selezionate e deselezionate, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="98bcf-133">The <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> class has the <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> and <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> properties that get the strokes that were selected and unselected, respectively.</span></span>  
  
 [!code-csharp[HowToSelectInk#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 <span data-ttu-id="98bcf-134">Quando l'utente termina di lazo, annullare la sottoscrizione di <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> eventi e chiamate <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.</span><span class="sxs-lookup"><span data-stu-id="98bcf-134">When the user finishes drawing the lasso, unsubscribe from the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event and call <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.</span></span>  
  
 [!code-csharp[HowToSelectInk#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a><span data-ttu-id="98bcf-135">Inserire tutti insieme.</span><span class="sxs-lookup"><span data-stu-id="98bcf-135">Putting it All Together.</span></span>  
 <span data-ttu-id="98bcf-136">Nell'esempio seguente è un controllo personalizzato che consente all'utente di selezionare input penna con un lazo.</span><span class="sxs-lookup"><span data-stu-id="98bcf-136">The following example is a custom control that enables a user to select ink with a lasso.</span></span>  
  
 [!code-csharp[HowToSelectInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="98bcf-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98bcf-137">See Also</span></span>  
 <xref:System.Windows.Ink.IncrementalLassoHitTester>  
 <xref:System.Windows.Ink.StrokeCollection>  
 <xref:System.Windows.Input.StylusPointCollection>  
 [<span data-ttu-id="98bcf-138">Creazione di un controllo di input penna</span><span class="sxs-lookup"><span data-stu-id="98bcf-138">Creating an Ink Input Control</span></span>](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)
