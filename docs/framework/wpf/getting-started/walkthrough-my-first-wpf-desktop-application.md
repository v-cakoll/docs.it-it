---
title: Creare un'applicazione WPF in Visual Studio
ms.date: 04/12/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ceb4d79bb88e41e62f3ee136b6beb3324b3dbd7
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809716"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="86d2f-102">Procedura dettagliata: Prima applicazione desktop WPF</span><span class="sxs-lookup"><span data-stu-id="86d2f-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="86d2f-103">Questo articolo illustra come sviluppare un'applicazione Windows Presentation Foundation (WPF) semplice che include gli elementi che sono comuni alla maggior parte delle applicazioni WPF: markup Extensible Application Markup Language (XAML), codice-behind, definizioni delle applicazioni, i controlli, layout, associazione dati e stili.</span><span class="sxs-lookup"><span data-stu-id="86d2f-103">This article shows you how to develop a simple Windows Presentation Foundation (WPF) application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span>

<span data-ttu-id="86d2f-104">Questa procedura dettagliata include i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="86d2f-104">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="86d2f-105">Utilizzare XAML per progettare l'aspetto dell'interfaccia utente dell'applicazione (UI).</span><span class="sxs-lookup"><span data-stu-id="86d2f-105">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="86d2f-106">Scrivere codice per compilare il comportamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86d2f-106">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="86d2f-107">Creare una definizione di applicazione per gestire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86d2f-107">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="86d2f-108">Aggiungere controlli e creare il layout per comporre l'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86d2f-108">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="86d2f-109">Creare gli stili per un aspetto uniforme per interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86d2f-109">Create styles for a consistent appearance throughout an application's UI.</span></span>

- <span data-ttu-id="86d2f-110">Associare l'interfaccia utente ai dati sia popolare l'interfaccia utente da dati e mantenere i dati e dell'interfaccia utente sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="86d2f-110">Bind the UI to data to both populate the UI from data and keep the data and UI synchronized.</span></span>

<span data-ttu-id="86d2f-111">Al termine della procedura dettagliata, verrà creata un'applicazione Windows che consente agli utenti di visualizzare i report di spesa per gli utenti selezionati autonoma.</span><span class="sxs-lookup"><span data-stu-id="86d2f-111">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="86d2f-112">L'applicazione è composta da più pagine WPF ospitate in una finestra del browser stile.</span><span class="sxs-lookup"><span data-stu-id="86d2f-112">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="86d2f-113">Il codice di esempio che consente di compilare in questa procedura dettagliata è disponibile per Visual Basic e c# al [Introduzione alla compilazione di applicazioni WPF](http://go.microsoft.com/fwlink/?LinkID=160008).</span><span class="sxs-lookup"><span data-stu-id="86d2f-113">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Introduction to Building WPF Applications](http://go.microsoft.com/fwlink/?LinkID=160008).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="86d2f-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="86d2f-114">Prerequisites</span></span>

- <span data-ttu-id="86d2f-115">Visual Studio 2012 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="86d2f-115">Visual Studio 2012 or later</span></span>

<span data-ttu-id="86d2f-116">Per ulteriori informazioni sull'installazione della versione più recente di Visual Studio, vedere [installare Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="86d2f-116">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="86d2f-117">Creare il progetto di applicazione</span><span class="sxs-lookup"><span data-stu-id="86d2f-117">Create the application project</span></span>

<span data-ttu-id="86d2f-118">Il primo passaggio consiste nel creare l'infrastruttura dell'applicazione, che include una definizione di applicazione, due pagine e un'immagine.</span><span class="sxs-lookup"><span data-stu-id="86d2f-118">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="86d2f-119">Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual c# denominato **ExpenseIt**:</span><span class="sxs-lookup"><span data-stu-id="86d2f-119">Create a new WPF Application project in Visual Basic or Visual C# named **ExpenseIt**:</span></span>

   1. <span data-ttu-id="86d2f-120">Aprire Visual Studio e selezionare **File** > **nuovo** > **progetto**.</span><span class="sxs-lookup"><span data-stu-id="86d2f-120">Open Visual Studio and select **File** > **New** > **Project**.</span></span>

      <span data-ttu-id="86d2f-121">Il **nuovo progetto** verrà visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="86d2f-121">The **New Project** dialog opens.</span></span>

   2. <span data-ttu-id="86d2f-122">Sotto il **installati** categoria, espandere il **Visual c#** o **Visual Basic** nodo e quindi selezionare **Windows Desktop classico**.</span><span class="sxs-lookup"><span data-stu-id="86d2f-122">Under the **Installed** category, expand either the **Visual C#** or **Visual Basic** node, and then select **Windows Classic Desktop**.</span></span>

   3. <span data-ttu-id="86d2f-123">Selezionare il **applicazione WPF (.NET Framework)** modello.</span><span class="sxs-lookup"><span data-stu-id="86d2f-123">Select the **WPF App (.NET Framework)** template.</span></span> <span data-ttu-id="86d2f-124">Immettere il nome **ExpenseIt** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="86d2f-124">Enter the name **ExpenseIt** and then select **OK**.</span></span>

      ![Finestra di dialogo Nuovo progetto con app WPF selezionata](media/new-project-dialog.png)

      <span data-ttu-id="86d2f-126">Visual Studio crea il progetto e apre la finestra di progettazione per la finestra dell'applicazione predefinita denominata **MainWindow. XAML**.</span><span class="sxs-lookup"><span data-stu-id="86d2f-126">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="86d2f-127">Questa procedura dettagliata Usa il <xref:System.Windows.Controls.DataGrid> controllo che è disponibile in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="86d2f-127">This walkthrough uses the <xref:System.Windows.Controls.DataGrid> control that is available in the .NET Framework 4 and later.</span></span> <span data-ttu-id="86d2f-128">È possibile che il progetto è destinato a .NET Framework 4 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="86d2f-128">Be sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="86d2f-129">Per altre informazioni, vedere [Procedura: Destinare una versione di .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="86d2f-129">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>

2. <span data-ttu-id="86d2f-130">Aprire *Application. XAML* (Visual Basic) o *app* (c#).</span><span class="sxs-lookup"><span data-stu-id="86d2f-130">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="86d2f-131">Questo file XAML definisce un'applicazione WPF e tutte le risorse dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86d2f-131">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="86d2f-132">Utilizzare questo file per specificare l'interfaccia utente che visualizza automaticamente quando l'avvio dell'applicazione; In questo caso *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-132">You also use this file to specify the UI that automatically shows when the application starts; in this case, *MainWindow.xaml*.</span></span>

    <span data-ttu-id="86d2f-133">In Visual Basic, il codice XAML dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="86d2f-133">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="86d2f-134">Oppure l'aspetto seguente in C#:</span><span class="sxs-lookup"><span data-stu-id="86d2f-134">Or like this in C#:</span></span>

    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="86d2f-135">Aprire *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-135">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="86d2f-136">Questo file XAML è la finestra principale dell'applicazione e visualizza il contenuto creato nelle pagine.</span><span class="sxs-lookup"><span data-stu-id="86d2f-136">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="86d2f-137">La <xref:System.Windows.Window> classe definisce le proprietà di una finestra, ad esempio titolo, dimensioni o sull'icona e gestisce gli eventi, ad esempio la chiusura o disattivazione della visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="86d2f-137">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="86d2f-138">Modifica il <xref:System.Windows.Window> elemento da un <xref:System.Windows.Navigation.NavigationWindow>, come illustrato nel codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="86d2f-138">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="86d2f-139">Questa app passa a un contenuto diverso a seconda di input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="86d2f-139">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="86d2f-140">Questo è il motivo principale <xref:System.Windows.Window> deve essere modificato in un <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="86d2f-140">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="86d2f-141"><xref:System.Windows.Navigation.NavigationWindow> eredita tutte le proprietà di <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="86d2f-141"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="86d2f-142">Il <xref:System.Windows.Navigation.NavigationWindow> elemento nel file XAML crea un'istanza di <xref:System.Windows.Navigation.NavigationWindow> classe.</span><span class="sxs-lookup"><span data-stu-id="86d2f-142">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="86d2f-143">Per altre informazioni, vedere [Panoramica di navigazione](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="86d2f-143">For more information, see [Navigation overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="86d2f-144">Modificare le proprietà seguenti nel <xref:System.Windows.Navigation.NavigationWindow> elemento:</span><span class="sxs-lookup"><span data-stu-id="86d2f-144">Change the following properties on the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="86d2f-145">Impostare il <xref:System.Windows.Window.Title%2A> proprietà su "ExpenseIt".</span><span class="sxs-lookup"><span data-stu-id="86d2f-145">Set the <xref:System.Windows.Window.Title%2A> property to "ExpenseIt".</span></span>

    - <span data-ttu-id="86d2f-146">Impostare il <xref:System.Windows.FrameworkElement.Width%2A> proprietà su 500 pixel.</span><span class="sxs-lookup"><span data-stu-id="86d2f-146">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    - <span data-ttu-id="86d2f-147">Impostare il <xref:System.Windows.FrameworkElement.Height%2A> proprietà 350 pixel.</span><span class="sxs-lookup"><span data-stu-id="86d2f-147">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="86d2f-148">Rimuovere il <xref:System.Windows.Controls.Grid> elementi tra il <xref:System.Windows.Navigation.NavigationWindow> tag.</span><span class="sxs-lookup"><span data-stu-id="86d2f-148">Remove the <xref:System.Windows.Controls.Grid> elements between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

    <span data-ttu-id="86d2f-149">In Visual Basic, il codice XAML dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="86d2f-149">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="86d2f-150">Oppure l'aspetto seguente in C#:</span><span class="sxs-lookup"><span data-stu-id="86d2f-150">Or like this in C#:</span></span>

    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

6. <span data-ttu-id="86d2f-151">Aprire *. Xaml. vb* oppure *MainWindow.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-151">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="86d2f-152">Questo file è un file code-behind che contiene il codice per gestire gli eventi dichiarati nelle *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-152">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="86d2f-153">Il file contiene una classe parziale per la finestra definita in XAML.</span><span class="sxs-lookup"><span data-stu-id="86d2f-153">This file contains a partial class for the window defined in XAML.</span></span>

7. <span data-ttu-id="86d2f-154">Se si utilizza c#, modificare il `MainWindow` classe deriva da <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="86d2f-154">If you are using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="86d2f-155">(In Visual Basic, ciò avviene automaticamente quando si modifica la finestra in XAML)</span><span class="sxs-lookup"><span data-stu-id="86d2f-155">(In Visual Basic, this happens automatically when you change the window in XAML.)</span></span>

   <span data-ttu-id="86d2f-156">Il codice dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="86d2f-156">Your code should look like this:</span></span>

   [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
   [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]

   > [!TIP]
   > <span data-ttu-id="86d2f-157">È possibile attivare o disattivare il linguaggio del codice del codice di esempio tra linguaggi c# e Visual Basic nel **Language** elenco a discesa in alto a destra di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="86d2f-157">You can toggle the code language of the sample code between C# and Visual Basic in the **Language** drop-down on the upper right side of this article.</span></span>

## <a name="add-files-to-the-application"></a><span data-ttu-id="86d2f-158">Aggiungere i file all'applicazione</span><span class="sxs-lookup"><span data-stu-id="86d2f-158">Add files to the application</span></span>

<span data-ttu-id="86d2f-159">In questa sezione si aggiungeranno due pagine e un'immagine all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86d2f-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="86d2f-160">Aggiungere una nuova pagina WPF al progetto e denominarlo *ExpenseItHome. XAML*:</span><span class="sxs-lookup"><span data-stu-id="86d2f-160">Add a new WPF page to the project, and name it *ExpenseItHome.xaml*:</span></span>

   1. <span data-ttu-id="86d2f-161">In **Esplora soluzioni**, fare clic sui **ExpenseIt** nodo del progetto e scegliere **Aggiungi** > **pagina**.</span><span class="sxs-lookup"><span data-stu-id="86d2f-161">In **Solution Explorer**, right-click on the **ExpenseIt** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="86d2f-162">Nel **Aggiungi nuovo elemento** finestra di dialogo, la **pagina (WPF)** il modello è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="86d2f-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="86d2f-163">Immettere il nome **ExpenseItHome**, quindi selezionare **Add**.</span><span class="sxs-lookup"><span data-stu-id="86d2f-163">Enter the name **ExpenseItHome**, and then select **Add**.</span></span>

    <span data-ttu-id="86d2f-164">Questa pagina è la prima pagina che viene visualizzata quando viene avviata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86d2f-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="86d2f-165">Verrà visualizzato un elenco di utenti di selezionare questa opzione, per visualizzare una nota spese per.</span><span class="sxs-lookup"><span data-stu-id="86d2f-165">It will show a list of people to select from, to show an expense report for.</span></span>

2. <span data-ttu-id="86d2f-166">Aprire *ExpenseItHome.xaml*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-166">Open *ExpenseItHome.xaml*.</span></span>

3. <span data-ttu-id="86d2f-167">Impostare il <xref:System.Windows.Controls.Page.Title%2A> su "ExpenseIt - Home".</span><span class="sxs-lookup"><span data-stu-id="86d2f-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "ExpenseIt - Home".</span></span>

    <span data-ttu-id="86d2f-168">In Visual Basic, il codice XAML dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="86d2f-168">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="86d2f-169">Oppure l'aspetto seguente in C#:</span><span class="sxs-lookup"><span data-stu-id="86d2f-169">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

4. <span data-ttu-id="86d2f-170">Aprire *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-170">Open *MainWindow.xaml*.</span></span>

5. <span data-ttu-id="86d2f-171">Impostare il <xref:System.Windows.Navigation.NavigationWindow.Source%2A> proprietà il <xref:System.Windows.Navigation.NavigationWindow> a "ExpenseItHome. xaml".</span><span class="sxs-lookup"><span data-stu-id="86d2f-171">Set the <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property on the <xref:System.Windows.Navigation.NavigationWindow> to "ExpenseItHome.xaml".</span></span>

    <span data-ttu-id="86d2f-172">*ExpenseItHome.xaml* viene impostata come la prima pagina aperta all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86d2f-172">This sets *ExpenseItHome.xaml* to be the first page opened when the application starts.</span></span> <span data-ttu-id="86d2f-173">In Visual Basic, il codice XAML dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="86d2f-173">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="86d2f-174">Oppure l'aspetto seguente in C#:</span><span class="sxs-lookup"><span data-stu-id="86d2f-174">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="86d2f-175">È inoltre possibile impostare il **origine** proprietà il **varie** categoria del **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="86d2f-175">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Proprietà di origine nella finestra proprietà](media/properties-source.png)

6. <span data-ttu-id="86d2f-177">Aggiungere una nuova pagina WPF al progetto e denominarlo *ExpenseReportPage*::</span><span class="sxs-lookup"><span data-stu-id="86d2f-177">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="86d2f-178">In **Esplora soluzioni**, fare clic sui **ExpenseIt** nodo del progetto e scegliere **Aggiungi** > **pagina**.</span><span class="sxs-lookup"><span data-stu-id="86d2f-178">In **Solution Explorer**, right-click on the **ExpenseIt** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="86d2f-179">Nel **Aggiungi nuovo elemento** finestra di dialogo, la **pagina (WPF)** il modello è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="86d2f-179">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="86d2f-180">Immettere il nome **ExpenseReportPage**, quindi selezionare **Add**.</span><span class="sxs-lookup"><span data-stu-id="86d2f-180">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="86d2f-181">Questa pagina visualizzerà la nota spese per la persona a cui viene selezionata per il **ExpenseItHome** pagina.</span><span class="sxs-lookup"><span data-stu-id="86d2f-181">This page will show the expense report for the person that is selected on the **ExpenseItHome** page.</span></span>

7. <span data-ttu-id="86d2f-182">Aprire *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-182">Open *ExpenseReportPage.xaml*.</span></span>

8. <span data-ttu-id="86d2f-183">Impostare il <xref:System.Windows.Controls.Page.Title%2A> su "ExpenseIt - View Expense".</span><span class="sxs-lookup"><span data-stu-id="86d2f-183">Set the <xref:System.Windows.Controls.Page.Title%2A> to "ExpenseIt - View Expense".</span></span>

    <span data-ttu-id="86d2f-184">In Visual Basic, il codice XAML dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="86d2f-184">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="86d2f-185">Oppure l'aspetto seguente in C#:</span><span class="sxs-lookup"><span data-stu-id="86d2f-185">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

9. <span data-ttu-id="86d2f-186">Aprire *ExpenseItHome.xaml.vb* e *ExpenseReportPage.xaml.vb*, o *ExpenseItHome.xaml.cs* e *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-186">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="86d2f-187">Quando si crea un nuovo file di paging, Visual Studio crea automaticamente un *codice* file.</span><span class="sxs-lookup"><span data-stu-id="86d2f-187">When you create a new Page file, Visual Studio automatically creates a *code-behind* file.</span></span> <span data-ttu-id="86d2f-188">Questi file code-behind gestiscono la logica per rispondere all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="86d2f-188">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="86d2f-189">Il codice dovrebbe essere simile alla seguente per **ExpenseItHome**:</span><span class="sxs-lookup"><span data-stu-id="86d2f-189">Your code should look like this for **ExpenseItHome**:</span></span>

    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="86d2f-190">Oppure per **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="86d2f-190">And like this for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

10. <span data-ttu-id="86d2f-191">Aggiungere un'immagine denominata *watermark* al progetto.</span><span class="sxs-lookup"><span data-stu-id="86d2f-191">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="86d2f-192">È possibile creare un'immagine personalizzata, copiare il file il codice di esempio o ottenerlo [qui](https://github.com/dotnet/docs/blob/master/docs/framework/wpf/getting-started/media/watermark.png).</span><span class="sxs-lookup"><span data-stu-id="86d2f-192">You can create your own image, copy the file from the sample code, or get it [here](https://github.com/dotnet/docs/blob/master/docs/framework/wpf/getting-started/media/watermark.png).</span></span>

   1. <span data-ttu-id="86d2f-193">Fare clic sul nodo del progetto e selezionare **Add** > **elemento esistente**, oppure premere **MAIUSC**+**Alt** + **A**.</span><span class="sxs-lookup"><span data-stu-id="86d2f-193">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

   2. <span data-ttu-id="86d2f-194">Nel **Aggiungi elemento esistente** finestra di dialogo, selezionare il file di immagine si desidera utilizzare e quindi selezionare **Add**.</span><span class="sxs-lookup"><span data-stu-id="86d2f-194">In the **Add Existing Item** dialog, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="86d2f-195">Compilazione ed esecuzione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="86d2f-195">Build and run the application</span></span>

1. <span data-ttu-id="86d2f-196">Per compilare ed eseguire l'applicazione, premere **F5** oppure selezionare **Avvia debug** dal **Debug** menu.</span><span class="sxs-lookup"><span data-stu-id="86d2f-196">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="86d2f-197">Nella figura seguente viene illustrata l'applicazione con il <xref:System.Windows.Navigation.NavigationWindow> pulsanti:</span><span class="sxs-lookup"><span data-stu-id="86d2f-197">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![Schermata dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png)

2. <span data-ttu-id="86d2f-199">Chiudere l'applicazione per tornare a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="86d2f-199">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="86d2f-200">Creare il layout</span><span class="sxs-lookup"><span data-stu-id="86d2f-200">Create the layout</span></span>

<span data-ttu-id="86d2f-201">Layout fornisce un modo ordinato per posizionare elementi dell'interfaccia utente e di gestione le dimensioni e la posizione di tali elementi durante il ridimensionamento di un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="86d2f-201">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="86d2f-202">In genere si crea un layout tramite uno dei controlli di layout seguenti:</span><span class="sxs-lookup"><span data-stu-id="86d2f-202">You typically create a layout with one of the following layout controls:</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.VirtualizingStackPanel>
- <xref:System.Windows.Controls.WrapPanel>

<span data-ttu-id="86d2f-203">Ognuno di questi controlli di layout supporta un tipo speciale di layout per i relativi elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="86d2f-203">Each of these layout controls supports a special type of layout for its child elements.</span></span> <span data-ttu-id="86d2f-204">È possibile ridimensionare le pagine ExpenseIt e ogni pagina contiene elementi disposti in orizzontale e in verticale accanto ad altri elementi.</span><span class="sxs-lookup"><span data-stu-id="86d2f-204">ExpenseIt pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="86d2f-205">Di conseguenza, il <xref:System.Windows.Controls.Grid> è l'elemento di layout ideale per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86d2f-205">Consequently, the <xref:System.Windows.Controls.Grid> is the ideal layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="86d2f-206">Per ulteriori informazioni <xref:System.Windows.Controls.Panel> elementi, vedere [Panoramica pannelli](../../../../docs/framework/wpf/controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="86d2f-206">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span> <span data-ttu-id="86d2f-207">Per ulteriori informazioni sul layout, vedere [Layout](../../../../docs/framework/wpf/advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="86d2f-207">For more information about layout, see [Layout](../../../../docs/framework/wpf/advanced/layout.md).</span></span>

<span data-ttu-id="86d2f-208">Nella sezione crei una tabella a colonna singola con tre righe e un margine di 10 pixel mediante l'aggiunta di definizioni di colonna e riga per il <xref:System.Windows.Controls.Grid> in *ExpenseItHome. XAML*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-208">In the section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *ExpenseItHome.xaml*.</span></span>

1. <span data-ttu-id="86d2f-209">Aprire *ExpenseItHome.xaml*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-209">Open *ExpenseItHome.xaml*.</span></span>

2. <span data-ttu-id="86d2f-210">Impostare il <xref:System.Windows.FrameworkElement.Margin%2A> proprietà il <xref:System.Windows.Controls.Grid> elemento "10,0,10,10", che corrispondono ai margini sinistro, superiore, destro e inferiore:</span><span class="sxs-lookup"><span data-stu-id="86d2f-210">Set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="86d2f-211">È inoltre possibile impostare il **margine** valori il **proprietà** finestra, sotto il **Layout** categoria:</span><span class="sxs-lookup"><span data-stu-id="86d2f-211">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Valori dei margini nella finestra proprietà](media/properties-margin.png)

3. <span data-ttu-id="86d2f-213">Aggiungere il codice XAML seguente tra i <xref:System.Windows.Controls.Grid> tag per creare le definizioni di riga e colonna:</span><span class="sxs-lookup"><span data-stu-id="86d2f-213">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="86d2f-214">Il <xref:System.Windows.Controls.RowDefinition.Height%2A> di due righe è impostato su <xref:System.Windows.GridLength.Auto%2A>, vale a dire che le righe vengono ridimensionate i basare il contenuto nelle righe.</span><span class="sxs-lookup"><span data-stu-id="86d2f-214">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized base on the content in the rows.</span></span> <span data-ttu-id="86d2f-215">Il valore predefinito <xref:System.Windows.Controls.RowDefinition.Height%2A> è <xref:System.Windows.GridUnitType.Star> ridimensionamento, che significa che l'altezza della riga è una proporzione ponderata dello spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="86d2f-215">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="86d2f-216">Se, ad esempio due righe hanno un <xref:System.Windows.Controls.RowDefinition.Height%2A> di "\*", ognuna di esse presenta un'altezza pari alla metà dello spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="86d2f-216">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="86d2f-217">Il <xref:System.Windows.Controls.Grid> dovrebbe essere simile al codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="86d2f-217">Your <xref:System.Windows.Controls.Grid> should now look like the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="86d2f-218">Aggiunta di controlli</span><span class="sxs-lookup"><span data-stu-id="86d2f-218">Add controls</span></span>

<span data-ttu-id="86d2f-219">In questa sezione si aggiornerà la home page dell'interfaccia utente per visualizzare un elenco di persone che un utente può selezionare per mostrare la nota spese per.</span><span class="sxs-lookup"><span data-stu-id="86d2f-219">In this section, you'll update the home page UI to show a list of people that a user can select from to show the expense report for.</span></span> <span data-ttu-id="86d2f-220">I controlli sono oggetti dell'interfaccia utente che consentono agli utenti di interagire con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86d2f-220">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="86d2f-221">Per altre informazioni, vedere [Controlli](../../../../docs/framework/wpf/controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="86d2f-221">For more information, see [Controls](../../../../docs/framework/wpf/controls/index.md).</span></span>

<span data-ttu-id="86d2f-222">Per creare questa interfaccia utente, aggiungerai gli elementi seguenti per *ExpenseItHome. XAML*:</span><span class="sxs-lookup"><span data-stu-id="86d2f-222">To create this UI, you'll add the following elements to *ExpenseItHome.xaml*:</span></span>

- <span data-ttu-id="86d2f-223"><xref:System.Windows.Controls.ListBox> (per un elenco di persone).</span><span class="sxs-lookup"><span data-stu-id="86d2f-223"><xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="86d2f-224"><xref:System.Windows.Controls.Label> (per l'intestazione dell'elenco).</span><span class="sxs-lookup"><span data-stu-id="86d2f-224"><xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="86d2f-225"><xref:System.Windows.Controls.Button> (possibile fare clic per visualizzare la nota spese per la persona che sia selezionata nell'elenco).</span><span class="sxs-lookup"><span data-stu-id="86d2f-225"><xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="86d2f-226">Ogni controllo viene posizionato in una riga del <xref:System.Windows.Controls.Grid> impostando il <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> proprietà associata.</span><span class="sxs-lookup"><span data-stu-id="86d2f-226">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="86d2f-227">Per ulteriori informazioni sulle proprietà associate, vedere [collegato Cenni preliminari sulle proprietà](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="86d2f-227">For more information about attached properties, see [Attached Properties Overview](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="86d2f-228">Aprire *ExpenseItHome.xaml*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-228">Open *ExpenseItHome.xaml*.</span></span>

2. <span data-ttu-id="86d2f-229">Aggiungere il seguente codice XAML in un punto compreso tra il <xref:System.Windows.Controls.Grid> tag:</span><span class="sxs-lookup"><span data-stu-id="86d2f-229">Add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="86d2f-230">È anche possibile creare i controlli trascinandole dal **casella degli strumenti** nella finestra di progettazione e quindi impostando le proprietà nella finestra di **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="86d2f-230">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

3. <span data-ttu-id="86d2f-231">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86d2f-231">Build and run the application.</span></span>

<span data-ttu-id="86d2f-232">La figura seguente mostra i controlli che appena creato:</span><span class="sxs-lookup"><span data-stu-id="86d2f-232">The following illustration shows the controls you just created:</span></span>

![Schermata dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="86d2f-234">Aggiungere un'immagine e un titolo</span><span class="sxs-lookup"><span data-stu-id="86d2f-234">Add an image and a title</span></span>

<span data-ttu-id="86d2f-235">In questa sezione, si verrà aggiornata l'interfaccia utente della home page con un'immagine e un titolo della pagina.</span><span class="sxs-lookup"><span data-stu-id="86d2f-235">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="86d2f-236">Aprire *ExpenseItHome.xaml*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-236">Open *ExpenseItHome.xaml*.</span></span>

2. <span data-ttu-id="86d2f-237">Aggiungere un'altra colonna per il <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con fissa <xref:System.Windows.Controls.ColumnDefinition.Width%2A> di 230 pixel:</span><span class="sxs-lookup"><span data-stu-id="86d2f-237">Add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]

3. <span data-ttu-id="86d2f-238">Aggiungere un'altra riga per il <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, per un totale di quattro righe:</span><span class="sxs-lookup"><span data-stu-id="86d2f-238">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]

4. <span data-ttu-id="86d2f-239">Spostare i controlli nella seconda colonna impostando il <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> proprietà su 1 in ognuno dei tre controlli (bordo, casella di riepilogo e pulsante).</span><span class="sxs-lookup"><span data-stu-id="86d2f-239">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

5. <span data-ttu-id="86d2f-240">Spostare ogni controllo verso il basso una riga, incrementando il relativo <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> valore di 1.</span><span class="sxs-lookup"><span data-stu-id="86d2f-240">Move each control down a row, by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1.</span></span>

   <span data-ttu-id="86d2f-241">Il codice XAML per i tre controlli avrà ora un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="86d2f-241">The XAML for the three controls now looks like this:</span></span>

    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

6. <span data-ttu-id="86d2f-242">Impostare il <xref:System.Windows.Controls.Panel.Background%2A> del <xref:System.Windows.Controls.Grid> sia il *watermark* file di immagine, aggiungendo il seguente codice XAML in un punto compreso tra il `<Grid>` e `<\/Grid>` tag:</span><span class="sxs-lookup"><span data-stu-id="86d2f-242">Set the <xref:System.Windows.Controls.Panel.Background%2A> of the <xref:System.Windows.Controls.Grid> to be the *watermark.png* image file, by adding the following XAML somewhere between the `<Grid>` and `<\/Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

7. <span data-ttu-id="86d2f-243">Prima di <xref:System.Windows.Controls.Border> elemento, aggiungere un <xref:System.Windows.Controls.Label> con il contenuto "View Expense Report".</span><span class="sxs-lookup"><span data-stu-id="86d2f-243">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="86d2f-244">Questo è il titolo della pagina.</span><span class="sxs-lookup"><span data-stu-id="86d2f-244">This is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

8. <span data-ttu-id="86d2f-245">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86d2f-245">Build and run the application.</span></span>

<span data-ttu-id="86d2f-246">La figura seguente mostra i risultati di ciò che appena aggiunto:</span><span class="sxs-lookup"><span data-stu-id="86d2f-246">The following illustration shows the results of what you just added:</span></span>

![Schermata dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="86d2f-248">Aggiungere il codice per gestire gli eventi</span><span class="sxs-lookup"><span data-stu-id="86d2f-248">Add code to handle events</span></span>

1. <span data-ttu-id="86d2f-249">Aprire *ExpenseItHome.xaml*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-249">Open *ExpenseItHome.xaml*.</span></span>

2. <span data-ttu-id="86d2f-250">Aggiungere un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi per il <xref:System.Windows.Controls.Button> elemento.</span><span class="sxs-lookup"><span data-stu-id="86d2f-250">Add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="86d2f-251">Per altre informazioni, vedere [procedura: creare un gestore di evento semplice](http://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480).</span><span class="sxs-lookup"><span data-stu-id="86d2f-251">For more information, see [How to: Create a simple event handler](http://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480).</span></span>

    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

3. <span data-ttu-id="86d2f-252">Aprire *ExpenseItHome.xaml.vb* o *ExpenseItHome.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-252">Open *ExpenseItHome.xaml.vb* or *ExpenseItHome.xaml.cs*.</span></span>

4. <span data-ttu-id="86d2f-253">Aggiungere il codice seguente per il `ExpenseItHome` classe per aggiungere un pulsante gestore dell'evento click.</span><span class="sxs-lookup"><span data-stu-id="86d2f-253">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="86d2f-254">Il gestore eventi apre il **ExpenseReportPage** pagina.</span><span class="sxs-lookup"><span data-stu-id="86d2f-254">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="86d2f-255">Creare l'interfaccia utente per ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="86d2f-255">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="86d2f-256">*ExpenseReportPage* Visualizza la nota spese per la persona che viene selezionata per il **ExpenseItHome** pagina.</span><span class="sxs-lookup"><span data-stu-id="86d2f-256">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **ExpenseItHome** page.</span></span> <span data-ttu-id="86d2f-257">In questa sezione, che consentono controlli di creare l'interfaccia utente per **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="86d2f-257">In this section, you'll controls and create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="86d2f-258">Aggiungerai anche in background e colori di riempimento ai vari elementi dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="86d2f-258">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="86d2f-259">Aprire *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-259">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="86d2f-260">Aggiungere il codice XAML seguente tra i <xref:System.Windows.Controls.Grid> tag:</span><span class="sxs-lookup"><span data-stu-id="86d2f-260">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="86d2f-261">Questa interfaccia è simile a *ExpenseItHome. XAML*, ma i dati del report viene visualizzati un <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="86d2f-261">This UI is similar to *ExpenseItHome.xaml*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="86d2f-262">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86d2f-262">Build and run the application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="86d2f-263">Se si verifica un errore di <xref:System.Windows.Controls.DataGrid> non è stato trovato o non esiste, verificare che il progetto è destinato a .NET Framework 4 o versione successivo.</span><span class="sxs-lookup"><span data-stu-id="86d2f-263">If you get an error that the <xref:System.Windows.Controls.DataGrid> was not found or does not exist, make sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="86d2f-264">Per altre informazioni, vedere [Procedura: Destinare una versione di .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="86d2f-264">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>

4. <span data-ttu-id="86d2f-265">Selezionare il **vista** pulsante.</span><span class="sxs-lookup"><span data-stu-id="86d2f-265">Select the **View** button.</span></span>

    <span data-ttu-id="86d2f-266">Viene visualizzata la pagina della nota spese.</span><span class="sxs-lookup"><span data-stu-id="86d2f-266">The expense report page appears.</span></span> <span data-ttu-id="86d2f-267">Si noti inoltre che il pulsante di navigazione all'indietro è abilitato.</span><span class="sxs-lookup"><span data-stu-id="86d2f-267">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="86d2f-268">La figura seguente mostra gli elementi dell'interfaccia utente aggiunti alla *ExpenseReportPage*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-268">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Schermata dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png)

## <a name="style-controls"></a><span data-ttu-id="86d2f-270">Controlli in stile</span><span class="sxs-lookup"><span data-stu-id="86d2f-270">Style controls</span></span>

<span data-ttu-id="86d2f-271">L'aspetto dei diversi elementi è spesso lo stesso per tutti gli elementi dello stesso tipo in un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="86d2f-271">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="86d2f-272">Interfaccia utente vengono usati [stili](../../../../docs/framework/wpf/controls/styling-and-templating.md) per rendere riutilizzabile l'aspetto degli elementi.</span><span class="sxs-lookup"><span data-stu-id="86d2f-272">UI uses [styles](../../../../docs/framework/wpf/controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="86d2f-273">La possibilità di riutilizzo consente di semplificare la gestione e la creazione di XAML.</span><span class="sxs-lookup"><span data-stu-id="86d2f-273">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="86d2f-274">In questa sezione vengono sostituiti con gli stili gli attributi per elemento definiti nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="86d2f-274">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="86d2f-275">Aprire *Application. XAML* oppure *app*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-275">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="86d2f-276">Aggiungere il codice XAML seguente tra i <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tag:</span><span class="sxs-lookup"><span data-stu-id="86d2f-276">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="86d2f-277">Questo codice XAML aggiunge gli stili seguenti:</span><span class="sxs-lookup"><span data-stu-id="86d2f-277">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="86d2f-278">`headerTextStyle`: per formattare il titolo della pagina <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="86d2f-278">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="86d2f-279">`labelStyle`: per formattare i controlli <xref:System.Windows.Controls.Label> .</span><span class="sxs-lookup"><span data-stu-id="86d2f-279">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="86d2f-280">`columnHeaderStyle`: per formattare <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="86d2f-280">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="86d2f-281">`listHeaderStyle`: per formattare i controlli <xref:System.Windows.Controls.Border> dell'intestazione dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="86d2f-281">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="86d2f-282">`listHeaderTextStyle`: Per formattare l'intestazione dell'elenco <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="86d2f-282">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="86d2f-283">`buttonStyle`: Per formattare il <xref:System.Windows.Controls.Button> in ExpenseItHome. Xaml.</span><span class="sxs-lookup"><span data-stu-id="86d2f-283">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on ExpenseItHome.xaml.</span></span>

    <span data-ttu-id="86d2f-284">Si noti che gli stili sono risorse e i relativi elementi figlio di <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> elemento proprietà.</span><span class="sxs-lookup"><span data-stu-id="86d2f-284">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="86d2f-285">In questa posizione, gli stili vengono applicati a tutti gli elementi di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86d2f-285">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="86d2f-286">Per un esempio di utilizzo delle risorse in un'applicazione .NET Framework, vedere [le risorse dell'applicazione di utilizzare](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="86d2f-286">For an example of using resources in a .NET Framework application, see [Use Application Resources](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="86d2f-287">Aprire *ExpenseItHome.xaml*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-287">Open *ExpenseItHome.xaml*.</span></span>

4. <span data-ttu-id="86d2f-288">Sostituire tutto il contenuto tra il <xref:System.Windows.Controls.Grid> gli elementi con il codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="86d2f-288">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="86d2f-289">Le proprietà come <xref:System.Windows.VerticalAlignment> e <xref:System.Windows.Media.FontFamily> che definiscono l'aspetto di ciascun controllo vengono rimosse e sostituite mediante l'applicazione degli stili.</span><span class="sxs-lookup"><span data-stu-id="86d2f-289">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="86d2f-290">Ad esempio, il `headerTextStyle` viene applicato a "View Expense Report" <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="86d2f-290">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

5. <span data-ttu-id="86d2f-291">Aprire *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-291">Open *ExpenseReportPage.xaml*.</span></span>

6. <span data-ttu-id="86d2f-292">Sostituire tutto il contenuto tra il <xref:System.Windows.Controls.Grid> gli elementi con il codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="86d2f-292">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="86d2f-293">Vengono aggiunti gli stili agli elementi <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="86d2f-293">This adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="86d2f-294">Associare dati a un controllo</span><span class="sxs-lookup"><span data-stu-id="86d2f-294">Bind data to a control</span></span>

<span data-ttu-id="86d2f-295">In questa sezione, si creeranno i dati XML sono associati a vari controlli.</span><span class="sxs-lookup"><span data-stu-id="86d2f-295">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="86d2f-296">Aprire *ExpenseItHome.xaml*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-296">Open *ExpenseItHome.xaml*.</span></span>

2. <span data-ttu-id="86d2f-297">Dopo l'apertura <xref:System.Windows.Controls.Grid> elemento, aggiungere il codice XAML seguente per creare un <xref:System.Windows.Data.XmlDataProvider> che contiene i dati per ogni persona:</span><span class="sxs-lookup"><span data-stu-id="86d2f-297">After the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    <span data-ttu-id="86d2f-298">I dati vengono creati come un <xref:System.Windows.Controls.Grid> risorse.</span><span class="sxs-lookup"><span data-stu-id="86d2f-298">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="86d2f-299">In genere questi dati vengono caricati sotto forma di file, ma in questo caso, per semplicità, verranno aggiunti inline.</span><span class="sxs-lookup"><span data-stu-id="86d2f-299">Normally this would be loaded as a file, but for simplicity the data is added inline.</span></span>

3. <span data-ttu-id="86d2f-300">All'interno di `<Grid.Resources>` elemento, aggiungere quanto segue <xref:System.Windows.DataTemplate>, che definisce come visualizzare i dati nel <xref:System.Windows.Controls.ListBox>:</span><span class="sxs-lookup"><span data-stu-id="86d2f-300">Within the `<Grid.Resources>` element, add the following <xref:System.Windows.DataTemplate>, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>:</span></span>

    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    <span data-ttu-id="86d2f-301">Per ulteriori informazioni sui modelli di dati, vedere [panoramica dei modelli di dati](../../../../docs/framework/wpf/data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="86d2f-301">For more information about data templates, see [Data templating overview](../../../../docs/framework/wpf/data/data-templating-overview.md).</span></span>

4. <span data-ttu-id="86d2f-302">Sostituire <xref:System.Windows.Controls.ListBox> con il codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="86d2f-302">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="86d2f-303">Questo codice XAML associa il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà del <xref:System.Windows.Controls.ListBox> all'origine dati e applica il modello di dati come il <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="86d2f-303">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="86d2f-304">Connettere i dati ai controlli</span><span class="sxs-lookup"><span data-stu-id="86d2f-304">Connect data to controls</span></span>

<span data-ttu-id="86d2f-305">Successivamente, verrà aggiunto il codice per recuperare il nome che viene selezionato per il **ExpenseItHome** pagina e passarlo al costruttore della **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="86d2f-305">Next, you'll add code to retrieve the name that's selected on the **ExpenseItHome** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="86d2f-306">**ExpenseReportPage** imposta il contesto dati con l'elemento passato, ovvero i controlli definiti in *ExpenseReportPage* associare.</span><span class="sxs-lookup"><span data-stu-id="86d2f-306">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="86d2f-307">Aprire *ExpenseReportPage.xaml.vb* o *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-307">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="86d2f-308">Aggiungere un costruttore che accetti un oggetto, in modo da poter passare i dati della nota spese della persona selezionata.</span><span class="sxs-lookup"><span data-stu-id="86d2f-308">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="86d2f-309">Aprire *ExpenseItHome.xaml.vb* o *ExpenseItHome.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-309">Open *ExpenseItHome.xaml.vb* or *ExpenseItHome.xaml.cs*.</span></span>

4. <span data-ttu-id="86d2f-310">Modifica il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi per chiamare il nuovo costruttore passando i dati della nota spese della persona selezionata.</span><span class="sxs-lookup"><span data-stu-id="86d2f-310">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="86d2f-311">Dati di tipo con i modelli di dati</span><span class="sxs-lookup"><span data-stu-id="86d2f-311">Style data with data templates</span></span>

<span data-ttu-id="86d2f-312">In questa sezione si aggiornerà l'interfaccia utente per ogni articolo negli elenchi di associazione a dati mediante i modelli di dati.</span><span class="sxs-lookup"><span data-stu-id="86d2f-312">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="86d2f-313">Aprire *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="86d2f-313">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="86d2f-314">Associare il contenuto di "Nome" e "Department" <xref:System.Windows.Controls.Label> proprietà source elementi per i dati appropriati.</span><span class="sxs-lookup"><span data-stu-id="86d2f-314">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="86d2f-315">Per ulteriori informazioni sull'associazione dati, vedere [Panoramica sul Data binding](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="86d2f-315">For more information about data binding, see [Data binding overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="86d2f-316">Dopo l'apertura <xref:System.Windows.Controls.Grid> elemento, aggiungere i seguenti modelli di dati, che consentono di definire come visualizzare i dati della nota spese:</span><span class="sxs-lookup"><span data-stu-id="86d2f-316">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="86d2f-317">Applicare i modelli per il <xref:System.Windows.Controls.DataGrid> colonne che visualizzano i costi per i dati del report.</span><span class="sxs-lookup"><span data-stu-id="86d2f-317">Apply the templates to the <xref:System.Windows.Controls.DataGrid> columns that display the expense report data.</span></span>

    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="86d2f-318">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86d2f-318">Build and run the application.</span></span>

6. <span data-ttu-id="86d2f-319">Selezionare una persona, quindi selezionare il **vista** pulsante.</span><span class="sxs-lookup"><span data-stu-id="86d2f-319">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="86d2f-320">La figura seguente mostra le due pagine dell'applicazione ExpenseIt con i controlli, layout, stili, associazione dati e modelli di dati applicati:</span><span class="sxs-lookup"><span data-stu-id="86d2f-320">The following illustration shows both pages of the ExpenseIt application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Schermate dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png)

> [!NOTE]
> <span data-ttu-id="86d2f-322">Questo esempio viene illustrata una funzionalità specifica di WPF e non è conforme a tutte le procedure consigliate per elementi quali sicurezza, localizzazione e accessibilità.</span><span class="sxs-lookup"><span data-stu-id="86d2f-322">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="86d2f-323">Per informazioni complete di WPF e .NET Framework applicazione sviluppo consigliate, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="86d2f-323">For comprehensive coverage of WPF and the .NET Framework application development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="86d2f-324">Accessibilità</span><span class="sxs-lookup"><span data-stu-id="86d2f-324">Accessibility</span></span>](../../../../docs/framework/ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="86d2f-325">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="86d2f-325">Security</span></span>](../../../../docs/framework/wpf/security-wpf.md)
>
> - [<span data-ttu-id="86d2f-326">Globalizzazione e localizzazione WPF</span><span class="sxs-lookup"><span data-stu-id="86d2f-326">WPF globalization and localization</span></span>](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="86d2f-327">Delle prestazioni WPF</span><span class="sxs-lookup"><span data-stu-id="86d2f-327">WPF performance</span></span>](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="86d2f-328">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="86d2f-328">Next steps</span></span>

<span data-ttu-id="86d2f-329">In questa procedura dettagliata è stato diverse tecniche per la creazione di un'interfaccia utente mediante Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="86d2f-329">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="86d2f-330">È stata acquisita una conoscenza di base dei componenti fondamentali di un'applicazione .NET Framework associato a dati.</span><span class="sxs-lookup"><span data-stu-id="86d2f-330">You should now have a basic understanding of the building blocks of a data-bound, .NET Framework application.</span></span> <span data-ttu-id="86d2f-331">Per altre informazioni sull'architettura WPF e i modelli di programmazione, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="86d2f-331">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="86d2f-332">Architettura WPF</span><span class="sxs-lookup"><span data-stu-id="86d2f-332">WPF architecture</span></span>](../../../../docs/framework/wpf/advanced/wpf-architecture.md)
- [<span data-ttu-id="86d2f-333">Panoramica di XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="86d2f-333">XAML overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="86d2f-334">Cenni preliminari sulle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="86d2f-334">Dependency properties overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [<span data-ttu-id="86d2f-335">Layout</span><span class="sxs-lookup"><span data-stu-id="86d2f-335">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)

<span data-ttu-id="86d2f-336">Per altre informazioni sulla creazione di applicazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="86d2f-336">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="86d2f-337">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="86d2f-337">Application development</span></span>](../../../../docs/framework/wpf/app-development/index.md)
- [<span data-ttu-id="86d2f-338">Controlli</span><span class="sxs-lookup"><span data-stu-id="86d2f-338">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)
- [<span data-ttu-id="86d2f-339">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="86d2f-339">Data binding overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="86d2f-340">Grafica e multimedia</span><span class="sxs-lookup"><span data-stu-id="86d2f-340">Graphics and multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
- [<span data-ttu-id="86d2f-341">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="86d2f-341">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="86d2f-342">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86d2f-342">See also</span></span>

- [<span data-ttu-id="86d2f-343">Panoramica di pannelli</span><span class="sxs-lookup"><span data-stu-id="86d2f-343">Panels overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
- [<span data-ttu-id="86d2f-344">Panoramica del modello di dati</span><span class="sxs-lookup"><span data-stu-id="86d2f-344">Data templating overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)
- [<span data-ttu-id="86d2f-345">Compilare un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="86d2f-345">Build a WPF application</span></span>](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="86d2f-346">Stili e modelli</span><span class="sxs-lookup"><span data-stu-id="86d2f-346">Styles and templates</span></span>](../../../../docs/framework/wpf/controls/styles-and-templates.md)
