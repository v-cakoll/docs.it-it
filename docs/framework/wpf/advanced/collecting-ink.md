---
title: Raccogli input penna digitale
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
ms.openlocfilehash: 813a5313a6fbf83c36cdbed1f64ce69a217ad788
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747034"
---
# <a name="collect-ink"></a><span data-ttu-id="d8493-102">Raccogli input penna</span><span class="sxs-lookup"><span data-stu-id="d8493-102">Collect Ink</span></span>

<span data-ttu-id="d8493-103">La raccolta di input penna è una delle funzionalità principali della piattaforma [Windows Presentation Foundation](../index.md).</span><span class="sxs-lookup"><span data-stu-id="d8493-103">The [Windows Presentation Foundation](../index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="d8493-104">In questo argomento vengono illustrati i metodi per la raccolta di input penna in Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="d8493-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d8493-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d8493-105">Prerequisites</span></span>

<span data-ttu-id="d8493-106">Per usare gli esempi seguenti, è necessario innanzitutto installare Visual Studio e il Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="d8493-106">To use the following examples, you must first install Visual Studio and the Windows SDK.</span></span> <span data-ttu-id="d8493-107">È inoltre necessario comprendere come scrivere applicazioni per WPF.</span><span class="sxs-lookup"><span data-stu-id="d8493-107">You should also understand how to write applications for the WPF.</span></span> <span data-ttu-id="d8493-108">Per ulteriori informazioni su come iniziare a usare WPF, vedere [procedura dettagliata: applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="d8493-108">For more information about getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="use-the-inkcanvas-element"></a><span data-ttu-id="d8493-109">Usare l'elemento InkCanvas</span><span class="sxs-lookup"><span data-stu-id="d8493-109">Use the InkCanvas Element</span></span>

<span data-ttu-id="d8493-110">L'elemento <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> rappresenta il modo più semplice per raccogliere input penna in WPF.</span><span class="sxs-lookup"><span data-stu-id="d8493-110">The <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> element provides the easiest way to collect ink in WPF.</span></span> <span data-ttu-id="d8493-111">Usare un elemento <xref:System.Windows.Controls.InkCanvas> per ricevere e visualizzare input penna.</span><span class="sxs-lookup"><span data-stu-id="d8493-111">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="d8493-112">In genere, l'input penna viene effettuato tramite uno stilo che interagisce con un digitalizzatore per produrre i tratti.</span><span class="sxs-lookup"><span data-stu-id="d8493-112">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="d8493-113">È anche possibile usare un mouse al posto dello stilo.</span><span class="sxs-lookup"><span data-stu-id="d8493-113">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="d8493-114">I tratti creati sono rappresentati come oggetti <xref:System.Windows.Ink.Stroke> e possono essere modificati sia a livello di codice sia in base all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d8493-114">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="d8493-115">Il <xref:System.Windows.Controls.InkCanvas> consente agli utenti di selezionare, modificare o eliminare un <xref:System.Windows.Ink.Stroke>esistente.</span><span class="sxs-lookup"><span data-stu-id="d8493-115">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="d8493-116">Usando XAML, è possibile configurare la raccolta di input penna con la stessa facilità con cui si aggiunge un elemento **InkCanvas** all'albero.</span><span class="sxs-lookup"><span data-stu-id="d8493-116">By using XAML, you can set up ink collection as easily as adding an **InkCanvas** element to your tree.</span></span> <span data-ttu-id="d8493-117">Nell'esempio seguente viene aggiunto un <xref:System.Windows.Controls.InkCanvas> a un progetto WPF predefinito creato in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="d8493-117">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default WPF project created in Visual Studio:</span></span>

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

<span data-ttu-id="d8493-118">L'elemento **InkCanvas** può inoltre contenere elementi figlio, rendendo possibile l'aggiunta di funzionalità di annotazione Ink a quasi tutti i tipi di elementi XAML.</span><span class="sxs-lookup"><span data-stu-id="d8493-118">The **InkCanvas** element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="d8493-119">Ad esempio, per aggiungere le funzionalità di Inking a un elemento di testo, è sufficiente renderlo figlio di un <xref:System.Windows.Controls.InkCanvas>:</span><span class="sxs-lookup"><span data-stu-id="d8493-119">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>:</span></span>

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

<span data-ttu-id="d8493-120">L'aggiunta del supporto per contrassegnare un'immagine con input penna è semplice:</span><span class="sxs-lookup"><span data-stu-id="d8493-120">Adding support for marking up an image with ink is just as easy:</span></span>

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a><span data-ttu-id="d8493-121">Modalità InkCollection</span><span class="sxs-lookup"><span data-stu-id="d8493-121">InkCollection Modes</span></span>

<span data-ttu-id="d8493-122">Il <xref:System.Windows.Controls.InkCanvas> fornisce supporto per varie modalità di input tramite la relativa proprietà <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8493-122">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>

### <a name="manipulate-ink"></a><span data-ttu-id="d8493-123">Modificare l'input penna</span><span class="sxs-lookup"><span data-stu-id="d8493-123">Manipulate Ink</span></span>

<span data-ttu-id="d8493-124">Il <xref:System.Windows.Controls.InkCanvas> fornisce il supporto per molte operazioni di modifica dell'input penna.</span><span class="sxs-lookup"><span data-stu-id="d8493-124">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="d8493-125">Ad esempio, <xref:System.Windows.Controls.InkCanvas> supporta la cancellazione della penna indietro e non è necessario alcun codice aggiuntivo per aggiungere la funzionalità all'elemento.</span><span class="sxs-lookup"><span data-stu-id="d8493-125">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase, and no additional code is needed to add the functionality to the element.</span></span>

#### <a name="selection"></a><span data-ttu-id="d8493-126">Selezione</span><span class="sxs-lookup"><span data-stu-id="d8493-126">Selection</span></span>

<span data-ttu-id="d8493-127">Per impostare la modalità di selezione è sufficiente impostare la proprietà <xref:System.Windows.Controls.InkCanvasEditingMode> su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="d8493-127">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span>

<span data-ttu-id="d8493-128">Il codice seguente imposta la modalità di modifica in base al valore di un <xref:System.Windows.Forms.CheckBox>:</span><span class="sxs-lookup"><span data-stu-id="d8493-128">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a><span data-ttu-id="d8493-129">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="d8493-129">DrawingAttributes</span></span>

<span data-ttu-id="d8493-130">Utilizzare la proprietà <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> per modificare l'aspetto dei tratti di input penna.</span><span class="sxs-lookup"><span data-stu-id="d8493-130">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="d8493-131">Ad esempio, il membro <xref:System.Windows.Ink.DrawingAttributes.Color%2A> di <xref:System.Windows.Ink.DrawingAttributes> imposta il colore del <xref:System.Windows.Ink.Stroke>sottoposto a rendering.</span><span class="sxs-lookup"><span data-stu-id="d8493-131">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="d8493-132">Nell'esempio seguente il colore dei tratti selezionati viene modificato in rosso:</span><span class="sxs-lookup"><span data-stu-id="d8493-132">The following example changes the color of the selected strokes to red:</span></span>

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a><span data-ttu-id="d8493-133">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="d8493-133">DefaultDrawingAttributes</span></span>

<span data-ttu-id="d8493-134">La proprietà <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> fornisce l'accesso a proprietà quali l'altezza, la larghezza e il colore dei tratti da creare in una <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="d8493-134">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="d8493-135">Una volta modificato il <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, viene eseguito il rendering di tutti i tratti successivi immessi nel <xref:System.Windows.Controls.InkCanvas> con i nuovi valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="d8493-135">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>

<span data-ttu-id="d8493-136">Oltre a modificare il <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> nel file code-behind, è possibile utilizzare la sintassi XAML per specificare <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="d8493-136">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span>

<span data-ttu-id="d8493-137">Nell'esempio seguente viene illustrato come impostare la proprietà <xref:System.Windows.Ink.DrawingAttributes.Color%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8493-137">The next example demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="d8493-138">Per usare questo codice, creare un nuovo progetto WPF denominato "HelloInkCanvas" in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d8493-138">To use this code, create a new WPF project called "HelloInkCanvas" in Visual Studio.</span></span> <span data-ttu-id="d8493-139">Sostituire il codice nel file *MainWindow. XAML* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d8493-139">Replace the code in the *MainWindow.xaml* file with the following code:</span></span>

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

<span data-ttu-id="d8493-140">Successivamente, aggiungere i gestori eventi del pulsante seguenti al file code-behind, all'interno della classe MainWindow:</span><span class="sxs-lookup"><span data-stu-id="d8493-140">Next, add the following button event handlers to the code behind file, inside the MainWindow class:</span></span>

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

<span data-ttu-id="d8493-141">Dopo aver copiato il codice, premere **F5** in Visual Studio per eseguire il programma nel debugger.</span><span class="sxs-lookup"><span data-stu-id="d8493-141">After copying this code, press **F5** in Visual Studio to run the program in the debugger.</span></span>

<span data-ttu-id="d8493-142">Si noti come il <xref:System.Windows.Controls.StackPanel> posiziona i pulsanti sulla parte superiore del <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="d8493-142">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="d8493-143">Se si tenta di eseguire l'input penna sulla parte superiore dei pulsanti, il <xref:System.Windows.Controls.InkCanvas> raccoglie ed esegue il rendering dell'input penna dietro i pulsanti.</span><span class="sxs-lookup"><span data-stu-id="d8493-143">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="d8493-144">Il motivo è che i pulsanti sono elementi di pari livello del <xref:System.Windows.Controls.InkCanvas> anziché degli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="d8493-144">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="d8493-145">Il rendering dell'input penna viene eseguito dietro i pulsanti anche perché si trovano più in alto nel z order.</span><span class="sxs-lookup"><span data-stu-id="d8493-145">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8493-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8493-146">See also</span></span>

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>
