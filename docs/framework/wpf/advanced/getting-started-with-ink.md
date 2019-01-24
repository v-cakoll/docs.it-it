---
title: Creare un oggetto InkCanvas in un'app WPF in Visual Studio
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: eaaa8ad5273331941bc6915231460100e8ac24b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646240"
---
# <a name="get-started-with-ink-in-wpf"></a><span data-ttu-id="fdfef-102">Introduzione a input penna in WPF</span><span class="sxs-lookup"><span data-stu-id="fdfef-102">Get Started with Ink in WPF</span></span>

<span data-ttu-id="fdfef-103">Windows Presentation Foundation (WPF) è una funzionalità di input penna che rende più semplice incorporare input penna digitale nella tua app.</span><span class="sxs-lookup"><span data-stu-id="fdfef-103">Windows Presentation Foundation (WPF) has an ink feature that makes it easy to incorporate digital ink into your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fdfef-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="fdfef-104">Prerequisites</span></span>

<span data-ttu-id="fdfef-105">Per usare gli esempi seguenti, innanzitutto [installa Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="fdfef-105">To use the following examples, first [install Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span></span> <span data-ttu-id="fdfef-106">È anche utile per sapere come scrivere le app WPF di base.</span><span class="sxs-lookup"><span data-stu-id="fdfef-106">It also helps to know how to write basic WPF apps.</span></span> <span data-ttu-id="fdfef-107">Per informazioni sulla Guida introduttiva a WPF, vedere [procedura dettagliata: Prima applicazione desktop WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="fdfef-107">For help getting started with WPF, see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="quick-start"></a><span data-ttu-id="fdfef-108">Guida introduttiva</span><span class="sxs-lookup"><span data-stu-id="fdfef-108">Quick Start</span></span>

<span data-ttu-id="fdfef-109">In questa sezione consente di scrivere una semplice applicazione WPF che consente di raccogliere input penna.</span><span class="sxs-lookup"><span data-stu-id="fdfef-109">This section helps you write a simple WPF application that collects ink.</span></span>

### <a name="got-ink"></a><span data-ttu-id="fdfef-110">Ricevuto input penna?</span><span class="sxs-lookup"><span data-stu-id="fdfef-110">Got Ink?</span></span>

<span data-ttu-id="fdfef-111">Per creare un'app WPF che supporta l'input penna:</span><span class="sxs-lookup"><span data-stu-id="fdfef-111">To create a WPF app that supports ink:</span></span>

1. <span data-ttu-id="fdfef-112">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fdfef-112">Open Visual Studio.</span></span>

2. <span data-ttu-id="fdfef-113">Creare una nuova **App WPF**.</span><span class="sxs-lookup"><span data-stu-id="fdfef-113">Create a new **WPF App**.</span></span>

   <span data-ttu-id="fdfef-114">Nel **nuovo progetto** finestra di dialogo espandere il **installato** > **Visual c#** oppure **Visual Basic**  >   **Windows Desktop** categoria.</span><span class="sxs-lookup"><span data-stu-id="fdfef-114">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="fdfef-115">Selezionare quindi il **App WPF (.NET Framework)** modello di app.</span><span class="sxs-lookup"><span data-stu-id="fdfef-115">Then, select the **WPF App (.NET Framework)** app template.</span></span> <span data-ttu-id="fdfef-116">Immettere un nome e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="fdfef-116">Enter a name, and then select **OK**.</span></span>

   <span data-ttu-id="fdfef-117">Visual Studio crea il progetto, e *MainWindow. XAML* nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="fdfef-117">Visual Studio creates the project, and *MainWindow.xaml* opens in the designer.</span></span>

3. <span data-ttu-id="fdfef-118">Tipo di `<InkCanvas/>` tra il `<Grid>` tag.</span><span class="sxs-lookup"><span data-stu-id="fdfef-118">Type `<InkCanvas/>` between the `<Grid>` tags.</span></span>

   ![Finestra di progettazione XAML con tag InkCanvas](media/getting-started-with-ink/inkcanvas-xaml.png)

4. <span data-ttu-id="fdfef-120">Premere **F5** per avviare l'applicazione nel debugger.</span><span class="sxs-lookup"><span data-stu-id="fdfef-120">Press **F5** to launch your application in the debugger.</span></span>

5. <span data-ttu-id="fdfef-121">Tramite uno stilo o un mouse, scrivere **HelloWorld** nella finestra.</span><span class="sxs-lookup"><span data-stu-id="fdfef-121">Using a stylus or mouse, write **hello world** in the window.</span></span>

<span data-ttu-id="fdfef-122">L'equivalente dell'input penna di un'applicazione "hello world" con solo 12 tasti scritto!</span><span class="sxs-lookup"><span data-stu-id="fdfef-122">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>

### <a name="spice-up-your-app"></a><span data-ttu-id="fdfef-123">Migliorare le prestazioni dell'App</span><span class="sxs-lookup"><span data-stu-id="fdfef-123">Spice Up Your App</span></span>

<span data-ttu-id="fdfef-124">È possibile sfruttare i vantaggi di alcune funzionalità di WPF.</span><span class="sxs-lookup"><span data-stu-id="fdfef-124">Let’s take advantage of some features of the WPF.</span></span> <span data-ttu-id="fdfef-125">Sostituire tutto il contenuto tra l'apertura e chiusura \<finestra > tag con il markup seguente:</span><span class="sxs-lookup"><span data-stu-id="fdfef-125">Replace everything between the opening and closing \<Window> tags with the following markup:</span></span>

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

<span data-ttu-id="fdfef-126">Questo XAML crea uno sfondo pennello sfumato nella superficie dell'input penna.</span><span class="sxs-lookup"><span data-stu-id="fdfef-126">This XAML creates a gradient brush background on your inking surface.</span></span>

![Colori sfumati in input penna di surface in app WPF](media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a><span data-ttu-id="fdfef-128">Aggiungere il codice dietro il XAML</span><span class="sxs-lookup"><span data-stu-id="fdfef-128">Add Some Code Behind the XAML</span></span>

<span data-ttu-id="fdfef-129">Mentre XAML è molto semplice progettare l'interfaccia utente, tutte le applicazioni del mondo reale deve aggiungere il codice per gestire gli eventi.</span><span class="sxs-lookup"><span data-stu-id="fdfef-129">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="fdfef-130">Ecco un esempio semplice che viene ingrandita sull'input penna in risposta al pulsante destro del mouse.</span><span class="sxs-lookup"><span data-stu-id="fdfef-130">Here is a simple example that zooms in on the ink in response to a right-click from a mouse.</span></span>

1. <span data-ttu-id="fdfef-131">Impostare il `MouseRightButtonUp` gestore nel XAML:</span><span class="sxs-lookup"><span data-stu-id="fdfef-131">Set the `MouseRightButtonUp` handler in your XAML:</span></span>

   [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. <span data-ttu-id="fdfef-132">Nelle **Esplora soluzioni**espandere MainWindow. XAML e aprire il file code-behind (MainWindow.xaml.cs o XAML. vb).</span><span class="sxs-lookup"><span data-stu-id="fdfef-132">In **Solution Explorer**, expand MainWindow.xaml and open the code-behind file (MainWindow.xaml.cs or MainWindow.xaml.vb).</span></span> <span data-ttu-id="fdfef-133">Aggiungere il codice del gestore eventi seguente:</span><span class="sxs-lookup"><span data-stu-id="fdfef-133">Add the following event handler code:</span></span>

   [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. <span data-ttu-id="fdfef-134">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fdfef-134">Run the application.</span></span> <span data-ttu-id="fdfef-135">Aggiungere alcuni input penna, quindi fare clic con il mouse o eseguire un equivalente premere e tenere con uno stilo.</span><span class="sxs-lookup"><span data-stu-id="fdfef-135">Add some ink, and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>

   <span data-ttu-id="fdfef-136">La visualizzazione viene ingrandita ogni volta che si fa clic con il pulsante destro del mouse.</span><span class="sxs-lookup"><span data-stu-id="fdfef-136">The display zooms in each time you click with the right mouse button.</span></span>

### <a name="use-procedural-code-instead-of-xaml"></a><span data-ttu-id="fdfef-137">Usare codice procedurale anziché XAML</span><span class="sxs-lookup"><span data-stu-id="fdfef-137">Use Procedural Code Instead of XAML</span></span>

<span data-ttu-id="fdfef-138">Tutte le funzionalità WPF è possibile accedere dal codice procedurale.</span><span class="sxs-lookup"><span data-stu-id="fdfef-138">You can access all WPF features from procedural code.</span></span> <span data-ttu-id="fdfef-139">Seguire questi passaggi per creare un'applicazione "Hello dell'input penna World" per WPF che non utilizza affatto qualsiasi XAML.</span><span class="sxs-lookup"><span data-stu-id="fdfef-139">Follow these steps to create a "Hello Ink World" application for WPF that doesn’t use any XAML at all.</span></span>

1. <span data-ttu-id="fdfef-140">Creare un nuovo progetto applicazione console in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fdfef-140">Create a new console application project in Visual Studio.</span></span>

   <span data-ttu-id="fdfef-141">Nel **nuovo progetto** finestra di dialogo espandere il **installato** > **Visual c#** oppure **Visual Basic**  >   **Windows Desktop** categoria.</span><span class="sxs-lookup"><span data-stu-id="fdfef-141">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="fdfef-142">Selezionare quindi il **App Console (.NET Framework)** modello di app.</span><span class="sxs-lookup"><span data-stu-id="fdfef-142">Then, select the **Console App (.NET Framework)** app template.</span></span> <span data-ttu-id="fdfef-143">Immettere un nome e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="fdfef-143">Enter a name, and then select **OK**.</span></span>

1. <span data-ttu-id="fdfef-144">Incollare il codice seguente nel file Program.cs o Program. vb:</span><span class="sxs-lookup"><span data-stu-id="fdfef-144">Paste the following code into the Program.cs or Program.vb file:</span></span>

   [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. <span data-ttu-id="fdfef-145">Aggiungere riferimenti agli assembly PresentationCore, PresentationFramework e WindowsBase facendo clic su **riferimenti** nelle **Esplora soluzioni** e scegliendo **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="fdfef-145">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies by right-clicking on **References** in **Solution Explorer** and choosing **Add Reference**.</span></span>

   ![Gestione di riferimenti che mostra PresentationCore e PresentationFramework](media/getting-started-with-ink/references.png)

1. <span data-ttu-id="fdfef-147">Compilare l'applicazione premendo **F5**.</span><span class="sxs-lookup"><span data-stu-id="fdfef-147">Build the application by pressing **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="fdfef-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdfef-148">See also</span></span>

- [<span data-ttu-id="fdfef-149">Input penna</span><span class="sxs-lookup"><span data-stu-id="fdfef-149">Digital Ink</span></span>](../../../../docs/framework/wpf/advanced/digital-ink.md)
- [<span data-ttu-id="fdfef-150">Raccolta di input penna</span><span class="sxs-lookup"><span data-stu-id="fdfef-150">Collecting Ink</span></span>](../../../../docs/framework/wpf/advanced/collecting-ink.md)
- [<span data-ttu-id="fdfef-151">Riconoscimento della grafia</span><span class="sxs-lookup"><span data-stu-id="fdfef-151">Handwriting Recognition</span></span>](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)
- [<span data-ttu-id="fdfef-152">Archiviazione dell'input penna</span><span class="sxs-lookup"><span data-stu-id="fdfef-152">Storing Ink</span></span>](../../../../docs/framework/wpf/advanced/storing-ink.md)
