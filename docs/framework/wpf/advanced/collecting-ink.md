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
ms.openlocfilehash: 0d0796eae469f8a40e01e3de02c00149eb3f00c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051273"
---
# <a name="collect-ink"></a><span data-ttu-id="873f4-102">Raccogliere l'input penna</span><span class="sxs-lookup"><span data-stu-id="873f4-102">Collect Ink</span></span>

<span data-ttu-id="873f4-103">La raccolta di input penna è una delle funzionalità principali della piattaforma [Windows Presentation Foundation](../index.md).</span><span class="sxs-lookup"><span data-stu-id="873f4-103">The [Windows Presentation Foundation](../index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="873f4-104">In questo argomento illustra i metodi per la raccolta dell'input penna in Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="873f4-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="873f4-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="873f4-105">Prerequisites</span></span>

<span data-ttu-id="873f4-106">Per usare gli esempi seguenti, è innanzitutto necessario installare Visual Studio e [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="873f4-106">To use the following examples, you must first install Visual Studio and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="873f4-107">È inoltre necessario comprendere come scrivere applicazioni per l'applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="873f4-107">You should also understand how to write applications for the WPF.</span></span> <span data-ttu-id="873f4-108">Per altre informazioni sulle operazioni iniziali con WPF, vedere [procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="873f4-108">For more information about getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="use-the-inkcanvas-element"></a><span data-ttu-id="873f4-109">Usare l'elemento InkCanvas</span><span class="sxs-lookup"><span data-stu-id="873f4-109">Use the InkCanvas Element</span></span>

<span data-ttu-id="873f4-110">Il <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> elemento fornisce il modo più semplice per raccogliere input penna in WPF.</span><span class="sxs-lookup"><span data-stu-id="873f4-110">The <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> element provides the easiest way to collect ink in WPF.</span></span> <span data-ttu-id="873f4-111">Usare un <xref:System.Windows.Controls.InkCanvas> elemento per ricevere e visualizzare input penna.</span><span class="sxs-lookup"><span data-stu-id="873f4-111">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="873f4-112">In genere, l'input penna viene effettuato tramite uno stilo che interagisce con un digitalizzatore per produrre i tratti.</span><span class="sxs-lookup"><span data-stu-id="873f4-112">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="873f4-113">È anche possibile usare un mouse al posto dello stilo.</span><span class="sxs-lookup"><span data-stu-id="873f4-113">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="873f4-114">I tratti creati sono rappresentati come <xref:System.Windows.Ink.Stroke> degli oggetti e che possono essere modificati sia a livello di codice che per l'utente di input.</span><span class="sxs-lookup"><span data-stu-id="873f4-114">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="873f4-115">Il <xref:System.Windows.Controls.InkCanvas> consente agli utenti di selezionare, modificare o eliminare un oggetto esistente <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="873f4-115">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="873f4-116">Tramite XAML, è possibile impostare la raccolta dell'input penna con la stessa facilità con cui si aggiunge un **InkCanvas** elemento alla struttura ad albero.</span><span class="sxs-lookup"><span data-stu-id="873f4-116">By using XAML, you can set up ink collection as easily as adding an **InkCanvas** element to your tree.</span></span> <span data-ttu-id="873f4-117">L'esempio seguente aggiunge un <xref:System.Windows.Controls.InkCanvas> a un progetto WPF predefiniti creato in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="873f4-117">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default WPF project created in Visual Studio:</span></span>

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

<span data-ttu-id="873f4-118">Il **InkCanvas** elemento può anche contenere elementi figlio, rendendo possibile l'aggiunta di funzionalità di annotazione a penna a quasi tutti i tipi di elemento XAML.</span><span class="sxs-lookup"><span data-stu-id="873f4-118">The **InkCanvas** element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="873f4-119">Ad esempio, per aggiungere funzionalità di input penna a un elemento di testo, è sufficiente trasformarlo in un elemento figlio di un <xref:System.Windows.Controls.InkCanvas>:</span><span class="sxs-lookup"><span data-stu-id="873f4-119">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>:</span></span>

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

<span data-ttu-id="873f4-120">Aggiunta del supporto per contrassegnare un'immagine con input penna è altrettanto semplice:</span><span class="sxs-lookup"><span data-stu-id="873f4-120">Adding support for marking up an image with ink is just as easy:</span></span>

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a><span data-ttu-id="873f4-121">Modalità InkCollection</span><span class="sxs-lookup"><span data-stu-id="873f4-121">InkCollection Modes</span></span>

<span data-ttu-id="873f4-122">Il <xref:System.Windows.Controls.InkCanvas> offre il supporto per varie modalità di input tramite relativo <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="873f4-122">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>

### <a name="manipulate-ink"></a><span data-ttu-id="873f4-123">Modificare l'input penna</span><span class="sxs-lookup"><span data-stu-id="873f4-123">Manipulate Ink</span></span>

<span data-ttu-id="873f4-124">Il <xref:System.Windows.Controls.InkCanvas> fornisce il supporto per molte operazioni di modifica di input penna.</span><span class="sxs-lookup"><span data-stu-id="873f4-124">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="873f4-125">Ad esempio, <xref:System.Windows.Controls.InkCanvas> erase supporta back della penna e richiedere codice aggiuntivo non è necessario per aggiungere la funzionalità per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="873f4-125">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase, and no additional code is needed to add the functionality to the element.</span></span>

#### <a name="selection"></a><span data-ttu-id="873f4-126">Selection</span><span class="sxs-lookup"><span data-stu-id="873f4-126">Selection</span></span>

<span data-ttu-id="873f4-127">Impostazione della modalità di selezione è semplice come l'impostazione di <xref:System.Windows.Controls.InkCanvasEditingMode> proprietà **seleziona**.</span><span class="sxs-lookup"><span data-stu-id="873f4-127">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span>

<span data-ttu-id="873f4-128">Il codice seguente imposta la modalità di modifica in base al valore di un <xref:System.Windows.Forms.CheckBox>:</span><span class="sxs-lookup"><span data-stu-id="873f4-128">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a><span data-ttu-id="873f4-129">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="873f4-129">DrawingAttributes</span></span>

<span data-ttu-id="873f4-130">Usare il <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> proprietà per modificare l'aspetto dei tratti input penna.</span><span class="sxs-lookup"><span data-stu-id="873f4-130">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="873f4-131">Ad esempio, il <xref:System.Windows.Ink.DrawingAttributes.Color%2A> appartenente <xref:System.Windows.Ink.DrawingAttributes> imposta il colore dell'oggetto sottoposto a rendering <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="873f4-131">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="873f4-132">Nell'esempio seguente modifica il colore dei tratti selezionati su rosso:</span><span class="sxs-lookup"><span data-stu-id="873f4-132">The following example changes the color of the selected strokes to red:</span></span>

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a><span data-ttu-id="873f4-133">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="873f4-133">DefaultDrawingAttributes</span></span>

<span data-ttu-id="873f4-134">Il <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proprietà offre l'accesso a proprietà quali l'altezza, larghezza e colore dei tratti da creare un <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="873f4-134">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="873f4-135">Dopo aver modificato il <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, tutti i futuri tratti immessi nel <xref:System.Windows.Controls.InkCanvas> vengono sottoposti a rendering con i nuovi valori di proprietà.</span><span class="sxs-lookup"><span data-stu-id="873f4-135">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>

<span data-ttu-id="873f4-136">Oltre a modificare la <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> nel file code-behind, è possibile usare la sintassi XAML per la specifica <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="873f4-136">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span>

<span data-ttu-id="873f4-137">L'esempio seguente viene illustrato come impostare il <xref:System.Windows.Ink.DrawingAttributes.Color%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="873f4-137">The next example demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="873f4-138">Per usare questo codice, creare un nuovo progetto WPF denominato "HelloInkCanvas" in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="873f4-138">To use this code, create a new WPF project called "HelloInkCanvas" in Visual Studio.</span></span> <span data-ttu-id="873f4-139">Sostituire il codice nel *MainWindow. XAML* file con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="873f4-139">Replace the code in the *MainWindow.xaml* file with the following code:</span></span>

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

<span data-ttu-id="873f4-140">Per il file code-behind, all'interno della classe MainWindow aggiungere quindi i gestori eventi dei pulsanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="873f4-140">Next, add the following button event handlers to the code behind file, inside the MainWindow class:</span></span>

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

<span data-ttu-id="873f4-141">Dopo aver copiato questo codice, premere **F5** in Visual Studio per eseguire il programma nel debugger.</span><span class="sxs-lookup"><span data-stu-id="873f4-141">After copying this code, press **F5** in Visual Studio to run the program in the debugger.</span></span>

<span data-ttu-id="873f4-142">Si noti che il <xref:System.Windows.Controls.StackPanel> colloca i pulsanti nella parte superiore del <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="873f4-142">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="873f4-143">Se si prova a input penna nella parte superiore dei pulsanti, il <xref:System.Windows.Controls.InkCanvas> raccoglie ed esegue il rendering dell'input penna dietro i pulsanti.</span><span class="sxs-lookup"><span data-stu-id="873f4-143">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="873f4-144">Infatti, i pulsanti sono elementi di pari livello del <xref:System.Windows.Controls.InkCanvas> e non elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="873f4-144">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="873f4-145">Il rendering dell'input penna viene eseguito dietro i pulsanti anche perché si trovano più in alto nel z order.</span><span class="sxs-lookup"><span data-stu-id="873f4-145">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>

## <a name="see-also"></a><span data-ttu-id="873f4-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="873f4-146">See also</span></span>

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>