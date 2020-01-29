---
title: Creare InkCanvas in Visual Studio
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: b8087d6db04f7024b9ee48f28002bee04045a14b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737884"
---
# <a name="get-started-with-ink-in-wpf"></a><span data-ttu-id="dbc78-102">Introduzione a input penna in WPF</span><span class="sxs-lookup"><span data-stu-id="dbc78-102">Get Started with Ink in WPF</span></span>

<span data-ttu-id="dbc78-103">Windows Presentation Foundation (WPF) dispone di una funzionalità di input penna che semplifica l'incorporamento dell'input penna digitale nell'app.</span><span class="sxs-lookup"><span data-stu-id="dbc78-103">Windows Presentation Foundation (WPF) has an ink feature that makes it easy to incorporate digital ink into your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dbc78-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="dbc78-104">Prerequisites</span></span>

<span data-ttu-id="dbc78-105">Per usare gli esempi seguenti, installare innanzitutto [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="dbc78-105">To use the following examples, first install [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span></span> <span data-ttu-id="dbc78-106">Consente inoltre di comprendere come scrivere app WPF di base.</span><span class="sxs-lookup"><span data-stu-id="dbc78-106">It also helps to know how to write basic WPF apps.</span></span> <span data-ttu-id="dbc78-107">Per informazioni introduttive su WPF, vedere [procedura dettagliata: applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="dbc78-107">For help getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="quick-start"></a><span data-ttu-id="dbc78-108">Guida introduttiva a</span><span class="sxs-lookup"><span data-stu-id="dbc78-108">Quick Start</span></span>

<span data-ttu-id="dbc78-109">Questa sezione consente di scrivere una semplice applicazione WPF che raccoglie input penna.</span><span class="sxs-lookup"><span data-stu-id="dbc78-109">This section helps you write a simple WPF application that collects ink.</span></span>

### <a name="got-ink"></a><span data-ttu-id="dbc78-110">Hai un input penna?</span><span class="sxs-lookup"><span data-stu-id="dbc78-110">Got Ink?</span></span>

<span data-ttu-id="dbc78-111">Per creare un'applicazione WPF che supporti l'input penna:</span><span class="sxs-lookup"><span data-stu-id="dbc78-111">To create a WPF app that supports ink:</span></span>

1. <span data-ttu-id="dbc78-112">Apri Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dbc78-112">Open Visual Studio.</span></span>

2. <span data-ttu-id="dbc78-113">Creare una nuova **app WPF**.</span><span class="sxs-lookup"><span data-stu-id="dbc78-113">Create a new **WPF App**.</span></span>

   <span data-ttu-id="dbc78-114">Nella finestra di dialogo **nuovo progetto** espandere la categoria **installato** > **Visual C#**  o **Visual Basic** > desktop di **Windows** .</span><span class="sxs-lookup"><span data-stu-id="dbc78-114">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="dbc78-115">Quindi, selezionare il modello app **WPF (.NET Framework)** .</span><span class="sxs-lookup"><span data-stu-id="dbc78-115">Then, select the **WPF App (.NET Framework)** app template.</span></span> <span data-ttu-id="dbc78-116">Immettere un nome e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbc78-116">Enter a name, and then select **OK**.</span></span>

   <span data-ttu-id="dbc78-117">Visual Studio crea il progetto e *MainWindow. XAML* si apre nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="dbc78-117">Visual Studio creates the project, and *MainWindow.xaml* opens in the designer.</span></span>

3. <span data-ttu-id="dbc78-118">Digitare `<InkCanvas/>` tra i tag di `<Grid>`.</span><span class="sxs-lookup"><span data-stu-id="dbc78-118">Type `<InkCanvas/>` between the `<Grid>` tags.</span></span>

   ![Finestra di progettazione XAML con tag InkCanvas](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. <span data-ttu-id="dbc78-120">Premere **F5** per avviare l'applicazione nel debugger.</span><span class="sxs-lookup"><span data-stu-id="dbc78-120">Press **F5** to launch your application in the debugger.</span></span>

5. <span data-ttu-id="dbc78-121">Usando uno stilo o un mouse, scrivere **Hello World** nella finestra.</span><span class="sxs-lookup"><span data-stu-id="dbc78-121">Using a stylus or mouse, write **hello world** in the window.</span></span>

<span data-ttu-id="dbc78-122">Hai scritto l'equivalente dell'input penna di un'applicazione "Hello World" con solo 12 sequenze di tasti.</span><span class="sxs-lookup"><span data-stu-id="dbc78-122">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>

### <a name="spice-up-your-app"></a><span data-ttu-id="dbc78-123">Ravviva la tua app</span><span class="sxs-lookup"><span data-stu-id="dbc78-123">Spice Up Your App</span></span>

<span data-ttu-id="dbc78-124">È ora opportuno usufruire di alcune funzionalità di WPF.</span><span class="sxs-lookup"><span data-stu-id="dbc78-124">Let’s take advantage of some features of the WPF.</span></span> <span data-ttu-id="dbc78-125">Sostituire tutti gli elementi tra la finestra di \<di apertura e di chiusura > Tag con il markup seguente:</span><span class="sxs-lookup"><span data-stu-id="dbc78-125">Replace everything between the opening and closing \<Window> tags with the following markup:</span></span>

```xaml
<Page>
  <InkCanvas Name="myInkCanvas" MouseRightButtonUp="RightMouseUpHandler">
    <InkCanvas.Background>
      <LinearGradientBrush>
        <GradientStop Color="Yellow" Offset="0.0" />
          <GradientStop Color="Blue" Offset="0.5" />
            <GradientStop Color="HotPink" Offset="1.0" />
              </LinearGradientBrush>
    </InkCanvas.Background>
  </InkCanvas>
</Page>
```

<span data-ttu-id="dbc78-126">Questo codice XAML crea uno sfondo del pennello sfumatura sull'area di Inking.</span><span class="sxs-lookup"><span data-stu-id="dbc78-126">This XAML creates a gradient brush background on your inking surface.</span></span>

![Colori sfumatura sull'area Inking nell'app WPF](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a><span data-ttu-id="dbc78-128">Aggiungere codice sottostante a XAML</span><span class="sxs-lookup"><span data-stu-id="dbc78-128">Add Some Code Behind the XAML</span></span>

<span data-ttu-id="dbc78-129">Mentre XAML rende molto semplice progettare l'interfaccia utente, qualsiasi applicazione reale deve aggiungere codice per gestire gli eventi.</span><span class="sxs-lookup"><span data-stu-id="dbc78-129">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="dbc78-130">Ecco un semplice esempio che esegue lo zoom avanti sull'input penna in risposta a un clic con il pulsante destro del mouse.</span><span class="sxs-lookup"><span data-stu-id="dbc78-130">Here is a simple example that zooms in on the ink in response to a right-click from a mouse.</span></span>

1. <span data-ttu-id="dbc78-131">Impostare il gestore `MouseRightButtonUp` in XAML:</span><span class="sxs-lookup"><span data-stu-id="dbc78-131">Set the `MouseRightButtonUp` handler in your XAML:</span></span>

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. <span data-ttu-id="dbc78-132">In **Esplora soluzioni**espandere MainWindow. XAML e aprire il file code-behind (MainWindow.XAML.cs o MainWindow. XAML. vb).</span><span class="sxs-lookup"><span data-stu-id="dbc78-132">In **Solution Explorer**, expand MainWindow.xaml and open the code-behind file (MainWindow.xaml.cs or MainWindow.xaml.vb).</span></span> <span data-ttu-id="dbc78-133">Aggiungere il seguente codice del gestore eventi:</span><span class="sxs-lookup"><span data-stu-id="dbc78-133">Add the following event handler code:</span></span>

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. <span data-ttu-id="dbc78-134">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dbc78-134">Run the application.</span></span> <span data-ttu-id="dbc78-135">Aggiungere un input penna, quindi fare clic con il pulsante destro del mouse con il mouse o eseguire un valore equivalente a premere e tenere premuto uno stilo.</span><span class="sxs-lookup"><span data-stu-id="dbc78-135">Add some ink, and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>

   <span data-ttu-id="dbc78-136">La visualizzazione viene ingrandita ogni volta che si fa clic con il pulsante destro del mouse.</span><span class="sxs-lookup"><span data-stu-id="dbc78-136">The display zooms in each time you click with the right mouse button.</span></span>

### <a name="use-procedural-code-instead-of-xaml"></a><span data-ttu-id="dbc78-137">Usa codice procedurale anziché XAML</span><span class="sxs-lookup"><span data-stu-id="dbc78-137">Use Procedural Code Instead of XAML</span></span>

<span data-ttu-id="dbc78-138">È possibile accedere a tutte le funzionalità WPF dal codice procedurale.</span><span class="sxs-lookup"><span data-stu-id="dbc78-138">You can access all WPF features from procedural code.</span></span> <span data-ttu-id="dbc78-139">Seguire questa procedura per creare un'applicazione "Hello Ink World" per WPF che non usa alcun codice XAML.</span><span class="sxs-lookup"><span data-stu-id="dbc78-139">Follow these steps to create a "Hello Ink World" application for WPF that doesn’t use any XAML at all.</span></span>

1. <span data-ttu-id="dbc78-140">Creare un nuovo progetto di applicazione console in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dbc78-140">Create a new console application project in Visual Studio.</span></span>

   <span data-ttu-id="dbc78-141">Nella finestra di dialogo **nuovo progetto** espandere la categoria **installato** > **Visual C#**  o **Visual Basic** > desktop di **Windows** .</span><span class="sxs-lookup"><span data-stu-id="dbc78-141">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="dbc78-142">Quindi, selezionare il modello app **Console (.NET Framework)** .</span><span class="sxs-lookup"><span data-stu-id="dbc78-142">Then, select the **Console App (.NET Framework)** app template.</span></span> <span data-ttu-id="dbc78-143">Immettere un nome e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbc78-143">Enter a name, and then select **OK**.</span></span>

1. <span data-ttu-id="dbc78-144">Incollare il codice seguente nel file Program.cs o Program. vb:</span><span class="sxs-lookup"><span data-stu-id="dbc78-144">Paste the following code into the Program.cs or Program.vb file:</span></span>

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. <span data-ttu-id="dbc78-145">Aggiungere riferimenti agli assembly PresentationCore, PresentationFramework e WindowsBase facendo clic con il pulsante destro del mouse su **riferimenti** in **Esplora soluzioni** e scegliendo **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="dbc78-145">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies by right-clicking on **References** in **Solution Explorer** and choosing **Add Reference**.</span></span>

   ![Gestione riferimenti che mostra PresentationCore e PresentationFramework](./media/getting-started-with-ink/reference-manager-presentationcore-presentationframework.png)

1. <span data-ttu-id="dbc78-147">Compilare l'applicazione premendo **F5**.</span><span class="sxs-lookup"><span data-stu-id="dbc78-147">Build the application by pressing **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="dbc78-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbc78-148">See also</span></span>

- [<span data-ttu-id="dbc78-149">Input penna</span><span class="sxs-lookup"><span data-stu-id="dbc78-149">Digital Ink</span></span>](digital-ink.md)
- [<span data-ttu-id="dbc78-150">Raccolta di input penna</span><span class="sxs-lookup"><span data-stu-id="dbc78-150">Collecting Ink</span></span>](collecting-ink.md)
- [<span data-ttu-id="dbc78-151">Riconoscimento della grafia</span><span class="sxs-lookup"><span data-stu-id="dbc78-151">Handwriting Recognition</span></span>](handwriting-recognition.md)
- [<span data-ttu-id="dbc78-152">Archiviazione dell'input penna</span><span class="sxs-lookup"><span data-stu-id="dbc78-152">Storing Ink</span></span>](storing-ink.md)
