---
title: Creare la prima app WPF in Visual Studio 2019-.NET Framework
titleSuffix: ''
description: Sviluppare un'applicazione desktop Windows Presentation Foundation (WPF) che includa elementi comuni alla maggior parte delle applicazioni WPF.
ms.date: 09/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
ms.topic: tutorial
ms.custom: mvc,vs-dotnet
ms.openlocfilehash: c9af988bcf291325b11df4fd22827b47090c0b48
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853887"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a><span data-ttu-id="bc5d4-103">Esercitazione: creare la prima applicazione WPF in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="bc5d4-103">Tutorial: Create your first WPF application in Visual Studio 2019</span></span>

<span data-ttu-id="bc5d4-104">Questo articolo illustra come sviluppare un'applicazione desktop Windows Presentation Foundation (WPF) che include gli elementi comuni alla maggior parte delle applicazioni WPF: markup Extensible Application Markup Language (XAML), code-behind, definizioni delle applicazioni, controlli, layout, data binding e stili.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-104">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="bc5d4-105">Per sviluppare l'applicazione, si userà Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-105">To develop the application, you'll use Visual Studio.</span></span>

<span data-ttu-id="bc5d4-106">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-106">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="bc5d4-107">Creare un progetto WPF.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-107">Create a WPF project.</span></span>
> - <span data-ttu-id="bc5d4-108">Utilizzare XAML per progettare l'aspetto dell'interfaccia utente (UI) dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-108">Use XAML to design the appearance of the application's user interface (UI).</span></span>
> - <span data-ttu-id="bc5d4-109">Scrivere il codice per compilare il comportamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-109">Write code to build the application's behavior.</span></span>
> - <span data-ttu-id="bc5d4-110">Creare una definizione di applicazione per gestire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-110">Create an application definition to manage the application.</span></span>
> - <span data-ttu-id="bc5d4-111">Aggiungere i controlli e creare il layout per comporre l'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-111">Add controls and create the layout to compose the application UI.</span></span>
> - <span data-ttu-id="bc5d4-112">Creare stili per un aspetto coerente nell'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-112">Create styles for a consistent appearance throughout the application's UI.</span></span>
> - <span data-ttu-id="bc5d4-113">Associare l'interfaccia utente ai dati, sia per popolare l'interfaccia utente dai dati, sia per sincronizzare i dati e l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-113">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="bc5d4-114">Al termine dell'esercitazione, verrà creata un'applicazione Windows autonoma che consente agli utenti di visualizzare i report delle spese per le persone selezionate.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-114">By the end of the tutorial, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="bc5d4-115">L'applicazione è costituita da diverse pagine WPF ospitate in una finestra di tipo browser.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-115">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="bc5d4-116">Il codice di esempio usato in questa esercitazione è disponibile sia per Visual Basic che per C# nel [codice di esempio dell'app WPF dell'esercitazione](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="bc5d4-116">The sample code that is used in this tutorial is available for both Visual Basic and C# at [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="bc5d4-117">È possibile abilitare o disabilitare il linguaggio del codice di esempio tra C# e Visual Basic usando il selettore della lingua nella parte superiore di questa pagina.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-117">You can toggle the code language of the sample code between C# and Visual Basic by using the language selector on top of this page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bc5d4-118">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="bc5d4-118">Prerequisites</span></span>

- <span data-ttu-id="bc5d4-119">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro sviluppo di applicazioni **desktop .NET** installato.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-119">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET desktop development** workload installed.</span></span>

   <span data-ttu-id="bc5d4-120">Per ulteriori informazioni sull'installazione della versione più recente di Visual Studio, vedere [Install Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="bc5d4-120">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="bc5d4-121">Creare il progetto dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="bc5d4-121">Create the application project</span></span>

<span data-ttu-id="bc5d4-122">Il primo passaggio consiste nel creare l'infrastruttura dell'applicazione, che include una definizione dell'applicazione, due pagine e un'immagine.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-122">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="bc5d4-123">Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual C# denominato **`ExpenseIt`** :</span><span class="sxs-lookup"><span data-stu-id="bc5d4-123">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="bc5d4-124">Aprire Visual Studio e selezionare **Crea un nuovo progetto** **nel menu inizia** .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-124">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="bc5d4-125">Verrà visualizzata la finestra **di dialogo Crea un nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-125">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="bc5d4-126">Nell'elenco a discesa **lingua** selezionare **C#** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-126">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>

   3. <span data-ttu-id="bc5d4-127">Selezionare il modello **applicazione WPF (.NET Framework)** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-127">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span>

      ![Finestra di dialogo Crea nuovo progetto](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      <span data-ttu-id="bc5d4-129">Verrà visualizzata la finestra di dialogo **Configura nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-129">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="bc5d4-130">Immettere il nome del progetto **`ExpenseIt`** e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-130">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![Finestra di dialogo Configura nuovo progetto](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="bc5d4-132">Visual Studio crea il progetto e apre la finestra di progettazione per la finestra dell'applicazione predefinita denominata **MainWindow. XAML**.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-132">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="bc5d4-133">Aprire *Application. XAML* (Visual Basic) o *app. XAML* (C#).</span><span class="sxs-lookup"><span data-stu-id="bc5d4-133">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="bc5d4-134">Questo file XAML definisce un'applicazione WPF e tutte le risorse dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-134">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="bc5d4-135">Questo file viene usato anche per specificare l'interfaccia utente, in questo caso *MainWindow. XAML*, che mostra automaticamente all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-135">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="bc5d4-136">Il codice XAML dovrebbe essere simile al seguente in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-136">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="bc5d4-137">Analogamente a quanto riportato di seguito in C#:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-137">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="bc5d4-138">Aprire *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-138">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="bc5d4-139">Questo file XAML è la finestra principale dell'applicazione e visualizza il contenuto creato in pagine.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-139">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="bc5d4-140">La <xref:System.Windows.Window> classe definisce le proprietà di una finestra, ad esempio il titolo, le dimensioni o l'icona, e gestisce gli eventi, ad esempio la chiusura o il nascondiglio.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-140">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="bc5d4-141">Modificare l' <xref:System.Windows.Window> elemento in un oggetto <xref:System.Windows.Navigation.NavigationWindow> , come illustrato nel codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-141">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="bc5d4-142">Questa app passa a un contenuto diverso a seconda dell'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-142">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="bc5d4-143">Questo è il motivo per cui è <xref:System.Windows.Window> necessario modificare il principale in un <xref:System.Windows.Navigation.NavigationWindow> .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-143">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="bc5d4-144"><xref:System.Windows.Navigation.NavigationWindow>eredita tutte le proprietà di <xref:System.Windows.Window> .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-144"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="bc5d4-145">L' <xref:System.Windows.Navigation.NavigationWindow> elemento nel file XAML crea un'istanza della <xref:System.Windows.Navigation.NavigationWindow> classe.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-145">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="bc5d4-146">Per altre informazioni, vedere [Cenni preliminari sulla navigazione](../app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bc5d4-146">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="bc5d4-147">Rimuovere gli <xref:System.Windows.Controls.Grid> elementi tra i <xref:System.Windows.Navigation.NavigationWindow> tag.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-147">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="bc5d4-148">Modificare le proprietà seguenti nel codice XAML per l' <xref:System.Windows.Navigation.NavigationWindow> elemento:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-148">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="bc5d4-149">Impostare la <xref:System.Windows.Window.Title%2A> proprietà su " `ExpenseIt` ".</span><span class="sxs-lookup"><span data-stu-id="bc5d4-149">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="bc5d4-150">Impostare la <xref:System.Windows.FrameworkElement.Height%2A> proprietà su 350 pixel.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-150">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="bc5d4-151">Impostare la <xref:System.Windows.FrameworkElement.Width%2A> proprietà su 500 pixel.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-151">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="bc5d4-152">Il codice XAML dovrebbe essere simile al seguente per Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-152">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="bc5d4-153">E come il seguente per C#:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-153">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="bc5d4-154">Aprire *MainWindow. XAML. vb* o *MainWindow.XAML.cs*.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-154">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="bc5d4-155">Questo file è un file code-behind che contiene il codice per gestire gli eventi dichiarati in *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-155">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="bc5d4-156">Il file contiene una classe parziale per la finestra definita in XAML.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-156">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="bc5d4-157">Se si usa C#, modificare la `MainWindow` classe in modo che derivi da <xref:System.Windows.Navigation.NavigationWindow> .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-157">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="bc5d4-158">(In Visual Basic, questa operazione viene eseguita automaticamente quando si modifica la finestra in XAML.) Il codice C# dovrebbe ora essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-158">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="bc5d4-159">Aggiunta di file all'applicazione</span><span class="sxs-lookup"><span data-stu-id="bc5d4-159">Add files to the application</span></span>

<span data-ttu-id="bc5d4-160">In questa sezione si aggiungeranno due pagine e un'immagine all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-160">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="bc5d4-161">Aggiungere una nuova pagina al progetto e denominarla *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="bc5d4-161">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="bc5d4-162">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul **`ExpenseIt`** nodo del progetto e scegliere **Aggiungi**  >  **pagina**.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-162">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="bc5d4-163">Nella finestra di dialogo **Aggiungi nuovo elemento** , il modello **pagina (WPF)** è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-163">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="bc5d4-164">Immettere il nome **`ExpenseItHome`** e quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-164">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="bc5d4-165">Questa pagina è la prima pagina visualizzata all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-165">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="bc5d4-166">Verrà visualizzato un elenco di utenti da selezionare per visualizzare una nota spese per.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-166">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="bc5d4-167">Aprire *`ExpenseItHome.xaml`* .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-167">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="bc5d4-168">Impostare <xref:System.Windows.Controls.Page.Title%2A> su " `ExpenseIt - Home` ".</span><span class="sxs-lookup"><span data-stu-id="bc5d4-168">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="bc5d4-169">Impostare `DesignHeight` su 350 pixel e `DesignWidth` su 500 pixel.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-169">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="bc5d4-170">Il codice XAML ora viene visualizzato come segue per Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-170">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="bc5d4-171">E come il seguente per C#:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-171">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="bc5d4-172">Aprire *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-172">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="bc5d4-173">Aggiungere una <xref:System.Windows.Navigation.NavigationWindow.Source%2A> proprietà all' <xref:System.Windows.Navigation.NavigationWindow> elemento e impostarla su " `ExpenseItHome.xaml` ".</span><span class="sxs-lookup"><span data-stu-id="bc5d4-173">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="bc5d4-174">Questa impostazione *`ExpenseItHome.xaml`* è la prima pagina aperta all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-174">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span>

    <span data-ttu-id="bc5d4-175">XAML di esempio in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-175">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="bc5d4-176">E in C#:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-176">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="bc5d4-177">È anche possibile impostare la proprietà **source** nella categoria **varie** della finestra **proprietà** .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-177">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Proprietà di origine in Finestra Proprietà](./media/properties-source.png)

1. <span data-ttu-id="bc5d4-179">Aggiungere un'altra nuova pagina WPF al progetto e denominarla *ExpenseReportPage. XAML*::</span><span class="sxs-lookup"><span data-stu-id="bc5d4-179">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="bc5d4-180">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul **`ExpenseIt`** nodo del progetto e scegliere **Aggiungi**  >  **pagina**.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-180">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="bc5d4-181">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare il modello **pagina (WPF)** .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-181">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="bc5d4-182">Immettere il nome **ExpenseReportPage**e quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-182">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="bc5d4-183">Questa pagina visualizzerà la nota spese per la persona selezionata nella **`ExpenseItHome`** pagina.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-183">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="bc5d4-184">Aprire *ExpenseReportPage. XAML*.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-184">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="bc5d4-185">Impostare <xref:System.Windows.Controls.Page.Title%2A> su " `ExpenseIt - View Expense` ".</span><span class="sxs-lookup"><span data-stu-id="bc5d4-185">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="bc5d4-186">Impostare `DesignHeight` su 350 pixel e `DesignWidth` su 500 pixel.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-186">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="bc5d4-187">*ExpenseReportPage. XAML* ha ora un aspetto simile al seguente in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-187">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="bc5d4-188">Analogamente a quanto riportato di seguito in C#:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-188">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="bc5d4-189">Aprire *ExpenseItHome. XAML. vb* e *ExpenseReportPage. XAML. vb*o *ExpenseItHome.XAML.cs* e *ExpenseReportPage.XAML.cs*.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-189">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="bc5d4-190">Quando si crea un nuovo file di paging, Visual Studio crea automaticamente il file *code-behind* .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-190">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="bc5d4-191">Questi file code-behind gestiscono la logica per rispondere all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-191">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="bc5d4-192">Il codice dovrebbe essere simile al seguente per **`ExpenseItHome`** :</span><span class="sxs-lookup"><span data-stu-id="bc5d4-192">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="bc5d4-193">Come indicato di seguito per **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-193">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="bc5d4-194">Aggiungere un'immagine denominata *watermark.png* al progetto.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-194">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="bc5d4-195">È possibile creare un'immagine personalizzata, copiare il file dal codice di esempio o ottenerlo dal repository GitHub [Microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-195">You can create your own image, copy the file from the sample code, or get it from the [microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub repository.</span></span>

    1. <span data-ttu-id="bc5d4-196">Fare clic con il pulsante destro del mouse sul nodo del progetto e scegliere **Aggiungi**  >  **elemento esistente**oppure premere **MAIUSC** + **ALT** + **A**.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-196">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="bc5d4-197">Nella finestra di dialogo **Aggiungi elemento esistente** impostare filtro file su **tutti** i file o **file di immagine**, passare al file di immagine che si vuole usare e quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-197">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="bc5d4-198">Compilare ed eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="bc5d4-198">Build and run the application</span></span>

1. <span data-ttu-id="bc5d4-199">Per compilare ed eseguire l'applicazione, premere **F5** o scegliere **Avvia debug** dal menu **debug** .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-199">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="bc5d4-200">La figura seguente mostra l'applicazione con i <xref:System.Windows.Navigation.NavigationWindow> pulsanti:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-200">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![Applicazione dopo la compilazione e l'esecuzione.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="bc5d4-202">Chiudere l'applicazione per tornare a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-202">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="bc5d4-203">Creare il layout</span><span class="sxs-lookup"><span data-stu-id="bc5d4-203">Create the layout</span></span>

<span data-ttu-id="bc5d4-204">Il layout fornisce un modo ordinato per inserire gli elementi dell'interfaccia utente e gestisce anche le dimensioni e la posizione di tali elementi quando viene ridimensionata un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-204">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="bc5d4-205">In genere si crea un layout tramite uno dei controlli di layout seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-205">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="bc5d4-206"><xref:System.Windows.Controls.Canvas>: Definisce un'area all'interno della quale è possibile posizionare in modo esplicito gli elementi figlio usando le coordinate relative all'area Canvas.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-206"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="bc5d4-207"><xref:System.Windows.Controls.DockPanel>: Definisce un'area in cui è possibile disporre gli elementi figlio in senso orizzontale o verticale, in relazione l'uno con l'altro.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-207"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="bc5d4-208"><xref:System.Windows.Controls.Grid>: Definisce un'area griglia flessibile costituita da righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-208"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="bc5d4-209"><xref:System.Windows.Controls.StackPanel>: Dispone gli elementi figlio in una sola riga che può essere orientata orizzontalmente o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-209"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="bc5d4-210"><xref:System.Windows.Controls.VirtualizingStackPanel>: Dispone e virtualizza il contenuto su una sola riga orientata orizzontalmente o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-210"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="bc5d4-211"><xref:System.Windows.Controls.WrapPanel>-Posiziona gli elementi figlio in sequenza da sinistra a destra, suddividendo il contenuto nella riga successiva al bordo della casella contenitore.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-211"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="bc5d4-212">L'ordinamento successivo avviene in sequenza dall'alto verso il basso o da destra a sinistra, a seconda del valore della proprietà Orientation.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-212">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="bc5d4-213">Ognuno di questi controlli di layout supporta un particolare tipo di layout per i relativi elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-213">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="bc5d4-214">`ExpenseIt`le pagine possono essere ridimensionate e ogni pagina contiene elementi disposti orizzontalmente e verticalmente insieme ad altri elementi.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-214">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="bc5d4-215">In questo esempio, <xref:System.Windows.Controls.Grid> viene utilizzato come elemento layout per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-215">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="bc5d4-216">Per altre informazioni sugli <xref:System.Windows.Controls.Panel> elementi, vedere [Cenni preliminari sui pannelli](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bc5d4-216">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="bc5d4-217">Per ulteriori informazioni sul layout, vedere [layout](../advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="bc5d4-217">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="bc5d4-218">In questa sezione viene creata una tabella a colonna singola con tre righe e un margine di 10 pixel aggiungendo definizioni di colonna e di riga a <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`* .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-218">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="bc5d4-219">In *`ExpenseItHome.xaml`* impostare la <xref:System.Windows.FrameworkElement.Margin%2A> proprietà dell'elemento su <xref:System.Windows.Controls.Grid> "10, 0, 10, 10", che corrisponde ai margini sinistro, superiore, destro e inferiore:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-219">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="bc5d4-220">È inoltre possibile impostare i valori dei **margini** nella finestra **Proprietà** , sotto la categoria **layout** :</span><span class="sxs-lookup"><span data-stu-id="bc5d4-220">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Valori dei margini in Finestra Proprietà](./media/properties-margin.png)

2. <span data-ttu-id="bc5d4-222">Aggiungere il seguente codice XAML tra i <xref:System.Windows.Controls.Grid> tag per creare le definizioni di riga e di colonna:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-222">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="bc5d4-223">Il <xref:System.Windows.Controls.RowDefinition.Height%2A> di due righe è impostato su <xref:System.Windows.GridLength.Auto%2A> , il che significa che le righe vengono ridimensionate in base al contenuto delle righe.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-223">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="bc5d4-224">Il valore predefinito <xref:System.Windows.Controls.RowDefinition.Height%2A> è il <xref:System.Windows.GridUnitType.Star> dimensionamento, che indica che l'altezza della riga è una proporzione ponderata dello spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-224">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="bc5d4-225">Se, ad esempio, due righe hanno un valore <xref:System.Windows.Controls.RowDefinition.Height%2A> di "\*", ognuna ha un'altezza pari alla metà dello spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-225">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="bc5d4-226">Il <xref:System.Windows.Controls.Grid> dovrebbe ora contenere il seguente codice XAML:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-226">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="bc5d4-227">Aggiungere controlli</span><span class="sxs-lookup"><span data-stu-id="bc5d4-227">Add controls</span></span>

<span data-ttu-id="bc5d4-228">In questa sezione verrà aggiornata l'interfaccia utente di home page per visualizzare un elenco di persone, in cui è possibile selezionare una persona per visualizzare la nota spese.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-228">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="bc5d4-229">I controlli sono oggetti dell'interfaccia utente che consentono agli utenti di interagire con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-229">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="bc5d4-230">Per altre informazioni, vedere [Controlli](../controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="bc5d4-230">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="bc5d4-231">Per creare questa interfaccia utente, aggiungere gli elementi seguenti a *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="bc5d4-231">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="bc5d4-232"><xref:System.Windows.Controls.ListBox>(Per l'elenco di persone).</span><span class="sxs-lookup"><span data-stu-id="bc5d4-232">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="bc5d4-233">Oggetto <xref:System.Windows.Controls.Label> (per l'intestazione dell'elenco).</span><span class="sxs-lookup"><span data-stu-id="bc5d4-233">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="bc5d4-234"><xref:System.Windows.Controls.Button>(Per fare clic per visualizzare la nota spese per la persona selezionata nell'elenco).</span><span class="sxs-lookup"><span data-stu-id="bc5d4-234">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="bc5d4-235">Ogni controllo è posizionato in una riga di impostando <xref:System.Windows.Controls.Grid> la <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> proprietà associata.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-235">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="bc5d4-236">Per ulteriori informazioni sulle proprietà associate, vedere [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bc5d4-236">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="bc5d4-237">In *`ExpenseItHome.xaml`* aggiungere il codice XAML seguente tra i <xref:System.Windows.Controls.Grid> Tag:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-237">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="bc5d4-238">È anche possibile creare i controlli trascinandoli dalla finestra **casella degli strumenti** nella finestra di progettazione e quindi impostarne le proprietà nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-238">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="bc5d4-239">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-239">Build and run the application.</span></span>

    <span data-ttu-id="bc5d4-240">Nella figura seguente sono illustrati i controlli creati:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-240">The following illustration shows the controls you created:</span></span>

![Schermata di esempio ExpenseIt che visualizza un elenco di nomi](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="bc5d4-242">Aggiungere un'immagine e un titolo</span><span class="sxs-lookup"><span data-stu-id="bc5d4-242">Add an image and a title</span></span>

<span data-ttu-id="bc5d4-243">In questa sezione si aggiornerà l'interfaccia utente di home page con un'immagine e un titolo della pagina.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-243">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="bc5d4-244">In *`ExpenseItHome.xaml`* aggiungere un'altra colonna a <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con un valore fisso <xref:System.Windows.Controls.ColumnDefinition.Width%2A> di 230 pixel:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-244">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewColumn)]

2. <span data-ttu-id="bc5d4-245">Aggiungere un'altra riga a <xref:System.Windows.Controls.Grid.RowDefinitions%2A> , per un totale di quattro righe:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-245">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewRows)]

3. <span data-ttu-id="bc5d4-246">Spostare i controlli nella seconda colonna impostando la <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> proprietà su 1 in ognuno dei tre controlli (bordo, casella di riepilogo e pulsante).</span><span class="sxs-lookup"><span data-stu-id="bc5d4-246">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="bc5d4-247">Spostare ogni controllo verso il basso di una riga incrementando il <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> valore di 1 per ognuno dei tre controlli (bordo, casella di riepilogo e pulsante) e per l'elemento Border.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-247">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="bc5d4-248">Il codice XAML per i tre controlli ha ora un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-248">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="bc5d4-249">Impostare la <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> proprietà sul file di immagine *watermark.png* , aggiungendo il codice XAML seguente in qualsiasi punto tra i `<Grid>` `</Grid>` tag e:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-249">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="bc5d4-250">Prima dell' <xref:System.Windows.Controls.Border> elemento, aggiungere un oggetto <xref:System.Windows.Controls.Label> con il contenuto "View Expense Report".</span><span class="sxs-lookup"><span data-stu-id="bc5d4-250">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="bc5d4-251">Questa etichetta è il titolo della pagina.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-251">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="bc5d4-252">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-252">Build and run the application.</span></span>

<span data-ttu-id="bc5d4-253">La figura seguente mostra i risultati di quanto appena aggiunto:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-253">The following illustration shows the results of what you just added:</span></span>

![Schermata di esempio di ExpenseIt che mostra la nuova immagine di sfondo e titolo della pagina](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="bc5d4-255">Aggiungere codice per gestire gli eventi</span><span class="sxs-lookup"><span data-stu-id="bc5d4-255">Add code to handle events</span></span>

1. <span data-ttu-id="bc5d4-256">In *`ExpenseItHome.xaml`* aggiungere un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi all' <xref:System.Windows.Controls.Button> elemento.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-256">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="bc5d4-257">Per altre informazioni, vedere [procedura: creare un gestore eventi semplice](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="bc5d4-257">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="bc5d4-258">Aprire *`ExpenseItHome.xaml.vb`* o *`ExpenseItHome.xaml.cs`* .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-258">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="bc5d4-259">Aggiungere il codice seguente alla `ExpenseItHome` classe per aggiungere un gestore dell'evento click del pulsante.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-259">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="bc5d4-260">Il gestore eventi apre la pagina **ExpenseReportPage** .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-260">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="bc5d4-261">Creare l'interfaccia utente per ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="bc5d4-261">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="bc5d4-262">*ExpenseReportPage. XAML* Visualizza la nota spese per la persona selezionata nella **`ExpenseItHome`** pagina.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-262">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="bc5d4-263">In questa sezione verrà creata l'interfaccia utente per **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-263">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="bc5d4-264">Verranno inoltre aggiunti i colori di sfondo e riempimento ai vari elementi dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-264">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="bc5d4-265">Aprire *ExpenseReportPage. XAML*.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-265">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="bc5d4-266">Aggiungere il codice XAML seguente tra i <xref:System.Windows.Controls.Grid> Tag:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-266">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="bc5d4-267">Questa interfaccia utente è simile a *`ExpenseItHome.xaml`* , ad eccezione del fatto che i dati del report vengono visualizzati in un oggetto <xref:System.Windows.Controls.DataGrid> .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-267">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="bc5d4-268">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-268">Build and run the application.</span></span>

4. <span data-ttu-id="bc5d4-269">Selezionare il pulsante **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-269">Select the **View** button.</span></span>

    <span data-ttu-id="bc5d4-270">Viene visualizzata la pagina della nota spese.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-270">The expense report page appears.</span></span> <span data-ttu-id="bc5d4-271">Si noti anche che il pulsante di spostamento indietro è abilitato.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-271">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="bc5d4-272">La figura seguente Mostra gli elementi dell'interfaccia utente aggiunti a *ExpenseReportPage. XAML*.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-272">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Schermata di esempio ExpenseIt che mostra l'interfaccia utente appena creata per il ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="bc5d4-274">Controlli di stile</span><span class="sxs-lookup"><span data-stu-id="bc5d4-274">Style controls</span></span>

<span data-ttu-id="bc5d4-275">L'aspetto dei vari elementi è spesso lo stesso per tutti gli elementi dello stesso tipo in un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-275">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="bc5d4-276">L'interfaccia utente usa gli [stili](../../../desktop-wpf/fundamentals/styles-templates-overview.md) per rendere i riutilizzabili in più elementi.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-276">UI uses [styles](../../../desktop-wpf/fundamentals/styles-templates-overview.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="bc5d4-277">La riutilizzabilità degli stili consente di semplificare la creazione e la gestione di XAML.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-277">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="bc5d4-278">In questa sezione vengono sostituiti con gli stili gli attributi per elemento definiti nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-278">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="bc5d4-279">Aprire *Application. XAML* o *app. XAML*.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-279">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="bc5d4-280">Aggiungere il codice XAML seguente tra i <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Tag:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-280">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="bc5d4-281">Questo codice XAML aggiunge gli stili seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-281">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="bc5d4-282">`headerTextStyle`: per formattare il titolo della pagina <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-282">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="bc5d4-283">`labelStyle`: per formattare i controlli <xref:System.Windows.Controls.Label> .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-283">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="bc5d4-284">`columnHeaderStyle`: per formattare <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-284">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="bc5d4-285">`listHeaderStyle`: per formattare i controlli <xref:System.Windows.Controls.Border> dell'intestazione dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-285">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="bc5d4-286">`listHeaderTextStyle`: Per formattare l'intestazione dell'elenco <xref:System.Windows.Controls.Label> .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-286">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="bc5d4-287">`buttonStyle`: Per formattare l'oggetto <xref:System.Windows.Controls.Button> in `ExpenseItHome.xaml` .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-287">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="bc5d4-288">Si noti che gli stili sono risorse e elementi figlio dell' <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> elemento Property.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-288">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="bc5d4-289">In questa posizione, gli stili vengono applicati a tutti gli elementi di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-289">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="bc5d4-290">Per un esempio dell'uso delle risorse in un'app .NET, vedere [usare le risorse dell'applicazione](../advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="bc5d4-290">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="bc5d4-291">In *`ExpenseItHome.xaml`* sostituire tutti gli elementi tra gli <xref:System.Windows.Controls.Grid> elementi con il codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-291">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="bc5d4-292">Le proprietà come <xref:System.Windows.VerticalAlignment> e <xref:System.Windows.Media.FontFamily> che definiscono l'aspetto di ciascun controllo vengono rimosse e sostituite mediante l'applicazione degli stili.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-292">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="bc5d4-293">Ad esempio, l'oggetto `headerTextStyle` viene applicato a "View Expense Report" <xref:System.Windows.Controls.Label> .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-293">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="bc5d4-294">Aprire *ExpenseReportPage. XAML*.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-294">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="bc5d4-295">Sostituire tutti gli <xref:System.Windows.Controls.Grid> elementi con il codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-295">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="bc5d4-296">Questo codice XAML aggiunge stili agli <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.Border> elementi e.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-296">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="bc5d4-297">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-297">Build and run the application.</span></span> <span data-ttu-id="bc5d4-298">L'aspetto della finestra è identico a quello precedente.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-298">The window appearance is the same as previously.</span></span>

    ![Schermata di esempio ExpenseIt con lo stesso aspetto dell'ultima sezione.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="bc5d4-300">Chiudere l'applicazione per tornare a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-300">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="bc5d4-301">Associare dati a un controllo</span><span class="sxs-lookup"><span data-stu-id="bc5d4-301">Bind data to a control</span></span>

<span data-ttu-id="bc5d4-302">In questa sezione verranno creati i dati XML associati a vari controlli.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-302">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="bc5d4-303">In *`ExpenseItHome.xaml`* , dopo l' <xref:System.Windows.Controls.Grid> elemento Opening, aggiungere il seguente codice XAML per creare un oggetto <xref:System.Windows.Data.XmlDataProvider> che contiene i dati per ogni persona:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-303">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="bc5d4-304">I dati vengono creati come <xref:System.Windows.Controls.Grid> risorsa.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-304">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="bc5d4-305">Normalmente questi dati vengono caricati come file, ma per semplicità i dati vengono aggiunti inline.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-305">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="bc5d4-306">Nell' `<Grid.Resources>` elemento aggiungere l' `<xref:System.Windows.DataTemplate>` elemento seguente, che definisce come visualizzare i dati in <xref:System.Windows.Controls.ListBox> , dopo l' `<XmlDataProvider>` elemento:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-306">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="bc5d4-307">Per ulteriori informazioni sui modelli di dati, vedere [Cenni preliminari](../data/data-templating-overview.md)sui modelli di dati.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-307">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="bc5d4-308">Sostituire il file esistente <xref:System.Windows.Controls.ListBox> con il codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-308">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="bc5d4-309">Questo codice XAML associa la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà di <xref:System.Windows.Controls.ListBox> all'origine dati e applica il modello di dati come <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-309">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="bc5d4-310">Connettere i dati ai controlli</span><span class="sxs-lookup"><span data-stu-id="bc5d4-310">Connect data to controls</span></span>

<span data-ttu-id="bc5d4-311">Successivamente, verrà aggiunto il codice per recuperare il nome selezionato nella **`ExpenseItHome`** pagina e passarlo al costruttore di **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-311">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="bc5d4-312">**ExpenseReportPage** imposta il contesto dei dati con l'elemento passato, ovvero l'associazione tra i controlli definiti in *ExpenseReportPage. XAML* .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-312">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="bc5d4-313">Aprire *ExpenseReportPage. XAML. vb* o *ExpenseReportPage.XAML.cs*.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-313">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="bc5d4-314">Aggiungere un costruttore che accetti un oggetto, in modo da poter passare i dati della nota spese della persona selezionata.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-314">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="bc5d4-315">Aprire *`ExpenseItHome.xaml.vb`* o *`ExpenseItHome.xaml.cs`* .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-315">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="bc5d4-316">Modificare il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi per chiamare il nuovo costruttore passando i dati della nota spese della persona selezionata.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-316">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="bc5d4-317">Applicare uno stile ai dati con i modelli di dati</span><span class="sxs-lookup"><span data-stu-id="bc5d4-317">Style data with data templates</span></span>

<span data-ttu-id="bc5d4-318">In questa sezione verrà aggiornata l'interfaccia utente per ogni elemento negli elenchi associati a dati utilizzando i modelli di dati.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-318">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="bc5d4-319">Aprire *ExpenseReportPage. XAML*.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-319">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="bc5d4-320">Associare il contenuto degli elementi "Name" e "Department" <xref:System.Windows.Controls.Label> alla proprietà dell'origine dati appropriata.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-320">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="bc5d4-321">Per ulteriori informazioni su data binding, vedere [Cenni preliminari sul data binding](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bc5d4-321">For more information about data binding, see [Data binding overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="bc5d4-322">Dopo l' <xref:System.Windows.Controls.Grid> elemento Opening, aggiungere i modelli di dati seguenti, che definiscono come visualizzare i dati della nota spese:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-322">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="bc5d4-323">Sostituire gli <xref:System.Windows.Controls.DataGridTextColumn> elementi con <xref:System.Windows.Controls.DataGridTemplateColumn> sotto l' <xref:System.Windows.Controls.DataGrid> elemento e applicarvi i modelli.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-323">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="bc5d4-324">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-324">Build and run the application.</span></span>

6. <span data-ttu-id="bc5d4-325">Selezionare una persona e quindi fare clic sul pulsante **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="bc5d4-325">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="bc5d4-326">Nella figura seguente sono illustrate entrambe le pagine dell' `ExpenseIt` applicazione con i controlli, il layout, gli stili, data binding e i modelli di dati applicati:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-326">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Entrambe le pagine dell'app che mostrano l'elenco dei nomi e una nota spese.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="bc5d4-328">Questo esempio illustra una funzionalità specifica di WPF e non segue tutte le procedure consigliate per elementi come sicurezza, localizzazione e accessibilità.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-328">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="bc5d4-329">Per una copertura completa delle procedure consigliate per lo sviluppo di applicazioni .NET e WPF, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-329">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="bc5d4-330">Accessibilità</span><span class="sxs-lookup"><span data-stu-id="bc5d4-330">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
> - [<span data-ttu-id="bc5d4-331">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="bc5d4-331">Security</span></span>](../security-wpf.md)
> - [<span data-ttu-id="bc5d4-332">Globalizzazione e localizzazione WPF</span><span class="sxs-lookup"><span data-stu-id="bc5d4-332">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
> - [<span data-ttu-id="bc5d4-333">Prestazioni di WPF</span><span class="sxs-lookup"><span data-stu-id="bc5d4-333">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="bc5d4-334">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="bc5d4-334">Next steps</span></span>

<span data-ttu-id="bc5d4-335">In questa procedura dettagliata sono state illustrate alcune tecniche per la creazione di un'interfaccia utente con Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="bc5d4-335">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="bc5d4-336">A questo punto si dovrebbe avere una conoscenza di base dei blocchi predefiniti di un'app .NET associata a dati.</span><span class="sxs-lookup"><span data-stu-id="bc5d4-336">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="bc5d4-337">Per altre informazioni sull'architettura WPF e i modelli di programmazione, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-337">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="bc5d4-338">Architettura WPF</span><span class="sxs-lookup"><span data-stu-id="bc5d4-338">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="bc5d4-339">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="bc5d4-339">XAML overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="bc5d4-340">Panoramica delle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="bc5d4-340">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="bc5d4-341">Layout</span><span class="sxs-lookup"><span data-stu-id="bc5d4-341">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="bc5d4-342">Per altre informazioni sulla creazione di applicazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc5d4-342">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="bc5d4-343">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="bc5d4-343">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="bc5d4-344">Controlli</span><span class="sxs-lookup"><span data-stu-id="bc5d4-344">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="bc5d4-345">Panoramica del data binding</span><span class="sxs-lookup"><span data-stu-id="bc5d4-345">Data binding overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="bc5d4-346">Elementi grafici e multimediali</span><span class="sxs-lookup"><span data-stu-id="bc5d4-346">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="bc5d4-347">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="bc5d4-347">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="bc5d4-348">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc5d4-348">See also</span></span>

- [<span data-ttu-id="bc5d4-349">Cenni preliminari sui pannelli</span><span class="sxs-lookup"><span data-stu-id="bc5d4-349">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="bc5d4-350">Panoramica sui modelli di dati</span><span class="sxs-lookup"><span data-stu-id="bc5d4-350">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="bc5d4-351">Creare un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="bc5d4-351">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="bc5d4-352">Stili e modelli</span><span class="sxs-lookup"><span data-stu-id="bc5d4-352">Styles and templates</span></span>](../controls/styles-and-templates.md)
