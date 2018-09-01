---
title: Raccogliere l'input penna nelle applicazioni WPF
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
ms.openlocfilehash: 25f9c0141a97d8e52e0883b14fd3e1f4574a05ea
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43394929"
---
# <a name="collect-ink"></a><span data-ttu-id="9f07d-102">Raccogliere l'input penna</span><span class="sxs-lookup"><span data-stu-id="9f07d-102">Collect Ink</span></span>

<span data-ttu-id="9f07d-103">La raccolta di input penna è una delle funzionalità principali della piattaforma [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md).</span><span class="sxs-lookup"><span data-stu-id="9f07d-103">The [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="9f07d-104">In questo argomento illustra i metodi per la raccolta dell'input penna in Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="9f07d-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9f07d-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9f07d-105">Prerequisites</span></span>

<span data-ttu-id="9f07d-106">Per usare gli esempi seguenti, è innanzitutto necessario installare Visual Studio e [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f07d-106">To use the following examples, you must first install Visual Studio and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="9f07d-107">È inoltre necessario comprendere come scrivere applicazioni per l'applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="9f07d-107">You should also understand how to write applications for the WPF.</span></span> <span data-ttu-id="9f07d-108">Per altre informazioni sulle operazioni iniziali con WPF, vedere [procedura dettagliata: prima applicazione desktop WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="9f07d-108">For more information about getting started with WPF, see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="use-the-inkcanvas-element"></a><span data-ttu-id="9f07d-109">Usare l'elemento InkCanvas</span><span class="sxs-lookup"><span data-stu-id="9f07d-109">Use the InkCanvas Element</span></span>

<span data-ttu-id="9f07d-110">Il <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> elemento fornisce il modo più semplice per raccogliere input penna in WPF.</span><span class="sxs-lookup"><span data-stu-id="9f07d-110">The <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> element provides the easiest way to collect ink in WPF.</span></span> <span data-ttu-id="9f07d-111">Usare un <xref:System.Windows.Controls.InkCanvas> elemento per ricevere e visualizzare input penna.</span><span class="sxs-lookup"><span data-stu-id="9f07d-111">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="9f07d-112">In genere, l'input penna viene effettuato tramite uno stilo che interagisce con un digitalizzatore per produrre i tratti.</span><span class="sxs-lookup"><span data-stu-id="9f07d-112">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="9f07d-113">È anche possibile usare un mouse al posto dello stilo.</span><span class="sxs-lookup"><span data-stu-id="9f07d-113">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="9f07d-114">I tratti creati sono rappresentati come <xref:System.Windows.Ink.Stroke> degli oggetti e che possono essere modificati sia a livello di codice che per l'utente di input.</span><span class="sxs-lookup"><span data-stu-id="9f07d-114">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="9f07d-115">Il <xref:System.Windows.Controls.InkCanvas> consente agli utenti di selezionare, modificare o eliminare un oggetto esistente <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="9f07d-115">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="9f07d-116">Tramite XAML, è possibile impostare la raccolta dell'input penna con la stessa facilità con cui si aggiunge un **InkCanvas** elemento alla struttura ad albero.</span><span class="sxs-lookup"><span data-stu-id="9f07d-116">By using XAML, you can set up ink collection as easily as adding an **InkCanvas** element to your tree.</span></span> <span data-ttu-id="9f07d-117">L'esempio seguente aggiunge un <xref:System.Windows.Controls.InkCanvas> a un progetto WPF predefiniti creato in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="9f07d-117">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default WPF project created in Visual Studio:</span></span>

[!code-xaml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

<span data-ttu-id="9f07d-118">Il **InkCanvas** elemento può anche contenere elementi figlio, rendendo possibile l'aggiunta di funzionalità di annotazione a penna a quasi tutti i tipi di elemento XAML.</span><span class="sxs-lookup"><span data-stu-id="9f07d-118">The **InkCanvas** element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="9f07d-119">Ad esempio, per aggiungere funzionalità di input penna a un elemento di testo, è sufficiente trasformarlo in un elemento figlio di un <xref:System.Windows.Controls.InkCanvas>:</span><span class="sxs-lookup"><span data-stu-id="9f07d-119">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>:</span></span>

[!code-xaml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

<span data-ttu-id="9f07d-120">Aggiunta del supporto per contrassegnare un'immagine con input penna è altrettanto semplice:</span><span class="sxs-lookup"><span data-stu-id="9f07d-120">Adding support for marking up an image with ink is just as easy:</span></span>

[!code-xaml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a><span data-ttu-id="9f07d-121">Modalità InkCollection</span><span class="sxs-lookup"><span data-stu-id="9f07d-121">InkCollection Modes</span></span>

<span data-ttu-id="9f07d-122">Il <xref:System.Windows.Controls.InkCanvas> offre il supporto per varie modalità di input tramite relativo <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="9f07d-122">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>

### <a name="manipulate-ink"></a><span data-ttu-id="9f07d-123">Modificare l'input penna</span><span class="sxs-lookup"><span data-stu-id="9f07d-123">Manipulate Ink</span></span>

<span data-ttu-id="9f07d-124">Il <xref:System.Windows.Controls.InkCanvas> fornisce il supporto per molte operazioni di modifica di input penna.</span><span class="sxs-lookup"><span data-stu-id="9f07d-124">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="9f07d-125">Ad esempio, <xref:System.Windows.Controls.InkCanvas> erase supporta back della penna e richiedere codice aggiuntivo non è necessario per aggiungere la funzionalità per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="9f07d-125">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase, and no additional code is needed to add the functionality to the element.</span></span>

#### <a name="selection"></a><span data-ttu-id="9f07d-126">Selection</span><span class="sxs-lookup"><span data-stu-id="9f07d-126">Selection</span></span>

<span data-ttu-id="9f07d-127">Impostazione della modalità di selezione è semplice come l'impostazione di <xref:System.Windows.Controls.InkCanvasEditingMode> proprietà **seleziona**.</span><span class="sxs-lookup"><span data-stu-id="9f07d-127">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span>

<span data-ttu-id="9f07d-128">Il codice seguente imposta la modalità di modifica in base al valore di un <xref:System.Windows.Forms.CheckBox>:</span><span class="sxs-lookup"><span data-stu-id="9f07d-128">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>

[!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a><span data-ttu-id="9f07d-129">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="9f07d-129">DrawingAttributes</span></span>

<span data-ttu-id="9f07d-130">Usare il <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> proprietà per modificare l'aspetto dei tratti input penna.</span><span class="sxs-lookup"><span data-stu-id="9f07d-130">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="9f07d-131">Ad esempio, il <xref:System.Windows.Ink.DrawingAttributes.Color%2A> appartenente <xref:System.Windows.Ink.DrawingAttributes> imposta il colore dell'oggetto sottoposto a rendering <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="9f07d-131">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="9f07d-132">Nell'esempio seguente modifica il colore dei tratti selezionati su rosso:</span><span class="sxs-lookup"><span data-stu-id="9f07d-132">The following example changes the color of the selected strokes to red:</span></span>

[!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a><span data-ttu-id="9f07d-133">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="9f07d-133">DefaultDrawingAttributes</span></span>

<span data-ttu-id="9f07d-134">Il <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proprietà offre l'accesso a proprietà quali l'altezza, larghezza e colore dei tratti da creare un <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="9f07d-134">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="9f07d-135">Dopo aver modificato il <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, tutti i futuri tratti immessi nel <xref:System.Windows.Controls.InkCanvas> vengono sottoposti a rendering con i nuovi valori di proprietà.</span><span class="sxs-lookup"><span data-stu-id="9f07d-135">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>

<span data-ttu-id="9f07d-136">Oltre a modificare la <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> nel file code-behind, è possibile usare la sintassi XAML per la specifica <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="9f07d-136">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span>

<span data-ttu-id="9f07d-137">L'esempio seguente viene illustrato come impostare il <xref:System.Windows.Ink.DrawingAttributes.Color%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="9f07d-137">The next example demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="9f07d-138">Per usare questo codice, creare un nuovo progetto WPF denominato "HelloInkCanvas" in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9f07d-138">To use this code, create a new WPF project called "HelloInkCanvas" in Visual Studio.</span></span> <span data-ttu-id="9f07d-139">Sostituire il codice nel *MainWindow. XAML* file con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="9f07d-139">Replace the code in the *MainWindow.xaml* file with the following code:</span></span>

[!code-xaml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

<span data-ttu-id="9f07d-140">Per il file code-behind, all'interno della classe MainWindow aggiungere quindi i gestori eventi dei pulsanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f07d-140">Next, add the following button event handlers to the code behind file, inside the MainWindow class:</span></span>

[!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

<span data-ttu-id="9f07d-141">Dopo aver copiato questo codice, premere **F5** in Visual Studio per eseguire il programma nel debugger.</span><span class="sxs-lookup"><span data-stu-id="9f07d-141">After copying this code, press **F5** in Visual Studio to run the program in the debugger.</span></span>

<span data-ttu-id="9f07d-142">Si noti che il <xref:System.Windows.Controls.StackPanel> colloca i pulsanti nella parte superiore del <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="9f07d-142">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="9f07d-143">Se si prova a input penna nella parte superiore dei pulsanti, il <xref:System.Windows.Controls.InkCanvas> raccoglie ed esegue il rendering dell'input penna dietro i pulsanti.</span><span class="sxs-lookup"><span data-stu-id="9f07d-143">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="9f07d-144">Infatti, i pulsanti sono elementi di pari livello del <xref:System.Windows.Controls.InkCanvas> e non elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="9f07d-144">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="9f07d-145">Il rendering dell'input penna viene eseguito dietro i pulsanti anche perché si trovano più in alto nel z order.</span><span class="sxs-lookup"><span data-stu-id="9f07d-145">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f07d-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f07d-146">See Also</span></span>

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>