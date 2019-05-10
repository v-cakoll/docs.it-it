---
title: Creare un'applicazione WPF in Visual Studio
ms.date: 03/20/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.custom: vs-dotnet
ms.openlocfilehash: 9d0abd18b2242ab21e8a915caac1ff9e3216acd0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617265"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="6104d-102">Procedura dettagliata: Compilare una prima applicazione desktop WPF</span><span class="sxs-lookup"><span data-stu-id="6104d-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="6104d-103">Questo articolo illustra come sviluppare un'applicazione desktop di Windows Presentation Foundation (WPF) che include gli elementi che sono comuni alla maggior parte delle applicazioni WPF: Extensible Application Markup Language (XAML) markup, code-behind, definizioni delle applicazioni, controlli, layout, associazione dati e stili.</span><span class="sxs-lookup"><span data-stu-id="6104d-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="6104d-104">Per sviluppare l'applicazione, si userà Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6104d-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="6104d-105">Questa procedura dettagliata include i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6104d-105">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="6104d-106">Usare XAML per progettare l'aspetto dell'interfaccia utente dell'applicazione (UI).</span><span class="sxs-lookup"><span data-stu-id="6104d-106">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="6104d-107">Scrivere codice per compilare un comportamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-107">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="6104d-108">Creare una definizione di applicazione per gestire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-108">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="6104d-109">Aggiungere controlli e creare il layout per comporre l'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-109">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="6104d-110">Creare stili per coerenza dell'aspetto dell'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-110">Create styles for a consistent appearance throughout the application's UI.</span></span>

- <span data-ttu-id="6104d-111">Associare l'interfaccia utente ai dati per popolare l'interfaccia utente dai dati e mantenere i dati e dell'interfaccia utente sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="6104d-111">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="6104d-112">Al termine della procedura dettagliata, verrà creata un'applicazione Windows che consente agli utenti di visualizzare rapporti spese per gli utenti selezionati autonoma.</span><span class="sxs-lookup"><span data-stu-id="6104d-112">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="6104d-113">L'applicazione è costituita da diverse pagine WPF ospitate in una finestra di tipo browser.</span><span class="sxs-lookup"><span data-stu-id="6104d-113">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="6104d-114">Il codice di esempio che viene usato per compilare questa procedura dettagliata è disponibile per entrambi Visual Basic e C# alla [codice di esempio di App WPF Walkthrough](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="6104d-114">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Walkthrough WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="6104d-115">È possibile attivare o disattivare il linguaggio del codice del codice di esempio tra C# e Visual Basic usando il **\< />** elenco a discesa in alto a destra di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="6104d-115">You can toggle the code language of the sample code between C# and Visual Basic by using the **\</>** drop-down on the upper right side of this article.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6104d-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6104d-116">Prerequisites</span></span>

- <span data-ttu-id="6104d-117">Visual Studio 2017 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="6104d-117">Visual Studio 2017 or later</span></span>

   <span data-ttu-id="6104d-118">Per altre informazioni sull'installazione della versione più recente di Visual Studio, vedere [installazione di Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="6104d-118">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span> <span data-ttu-id="6104d-119">Questo articolo Usa Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="6104d-119">This article uses Visual Studio 2019.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="6104d-120">Creare il progetto di applicazione</span><span class="sxs-lookup"><span data-stu-id="6104d-120">Create the application project</span></span>

<span data-ttu-id="6104d-121">Il primo passaggio consiste nel creare l'infrastruttura dell'applicazione, che include una definizione di applicazione, due pagine e un'immagine.</span><span class="sxs-lookup"><span data-stu-id="6104d-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="6104d-122">Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual c# denominato **`ExpenseIt`**:</span><span class="sxs-lookup"><span data-stu-id="6104d-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="6104d-123">Aprire Visual Studio e selezionare **File** > **New** > **progetto**.</span><span class="sxs-lookup"><span data-stu-id="6104d-123">Open Visual Studio and select **File** > **New** > **Project**.</span></span>

      <span data-ttu-id="6104d-124">Il **creare un nuovo progetto** verrà visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="6104d-124">The **Create a new project** dialog opens.</span></span>

      ![Creare una finestra di dialogo Nuovo progetto](./media/gettingstartedfigure0a.png)

   2. <span data-ttu-id="6104d-126">Nel **Language** elenco a discesa, selezionare **C#** oppure **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="6104d-126">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>

   3. <span data-ttu-id="6104d-127">Selezionare il **App WPF (.NET Framework)** modello e quindi selezionare **successivo**.</span><span class="sxs-lookup"><span data-stu-id="6104d-127">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
    
   4. <span data-ttu-id="6104d-128">Selezionare **creare un nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="6104d-128">Select **Create a new project**.</span></span>

      <span data-ttu-id="6104d-129">Il **configurare un nuovo progetto** verrà visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="6104d-129">The **Configure a new project** dialog opens.</span></span>

      ![Configurare una finestra di dialogo Nuovo progetto](./media/gettingstartedfigure0c.png)

   5. <span data-ttu-id="6104d-131">Immettere il nome del progetto **`ExpenseIt`** e quindi selezionare **Create**.</span><span class="sxs-lookup"><span data-stu-id="6104d-131">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      <span data-ttu-id="6104d-132">Visual Studio crea il progetto e apre la finestra di progettazione per la finestra dell'applicazione predefinita denominata **MainWindow. XAML**.</span><span class="sxs-lookup"><span data-stu-id="6104d-132">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="6104d-133">Aprire *Application. XAML* (Visual Basic) o *app* (c#).</span><span class="sxs-lookup"><span data-stu-id="6104d-133">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="6104d-134">Questo file XAML definisce un'applicazione WPF e tutte le risorse dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-134">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="6104d-135">È anche usare questo file per specificare l'interfaccia utente, in questo caso *MainWindow. XAML*, visualizzato automaticamente all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-135">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="6104d-136">il XAML dovrebbe essere simile al seguente in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="6104d-136">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="6104d-137">E come il seguente in C#:</span><span class="sxs-lookup"><span data-stu-id="6104d-137">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="6104d-138">Aprire *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="6104d-138">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="6104d-139">Questo file XAML è la finestra principale dell'applicazione e visualizza il contenuto creato nelle pagine.</span><span class="sxs-lookup"><span data-stu-id="6104d-139">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="6104d-140">Il <xref:System.Windows.Window> classe definisce le proprietà di una finestra, ad esempio titolo, dimensione o icona e gestisce gli eventi, ad esempio la chiusura o nascondere.</span><span class="sxs-lookup"><span data-stu-id="6104d-140">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="6104d-141">Modifica il <xref:System.Windows.Window> elemento da un <xref:System.Windows.Navigation.NavigationWindow>, come illustrato in XAML i seguenti:</span><span class="sxs-lookup"><span data-stu-id="6104d-141">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="6104d-142">Questa app consente di passare a contenuto diverso a seconda di input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6104d-142">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="6104d-143">Questo è il motivo principale <xref:System.Windows.Window> deve essere modificato in un <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="6104d-143">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="6104d-144"><xref:System.Windows.Navigation.NavigationWindow> eredita tutte le proprietà di <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="6104d-144"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="6104d-145">Il <xref:System.Windows.Navigation.NavigationWindow> elemento nel file XAML crea un'istanza di <xref:System.Windows.Navigation.NavigationWindow> classe.</span><span class="sxs-lookup"><span data-stu-id="6104d-145">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="6104d-146">Per altre informazioni, vedere [Cenni preliminari sulla navigazione](../app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6104d-146">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="6104d-147">Rimuovere il <xref:System.Windows.Controls.Grid> degli elementi da tra il <xref:System.Windows.Navigation.NavigationWindow> tag.</span><span class="sxs-lookup"><span data-stu-id="6104d-147">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="6104d-148">Modificare le proprietà seguenti nel codice XAML per il <xref:System.Windows.Navigation.NavigationWindow> elemento:</span><span class="sxs-lookup"><span data-stu-id="6104d-148">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="6104d-149">Impostare il <xref:System.Windows.Window.Title%2A> proprietà su "`ExpenseIt`".</span><span class="sxs-lookup"><span data-stu-id="6104d-149">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="6104d-150">Impostare il <xref:System.Windows.FrameworkElement.Height%2A> proprietà su 350 pixel.</span><span class="sxs-lookup"><span data-stu-id="6104d-150">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="6104d-151">Impostare il <xref:System.Windows.FrameworkElement.Width%2A> proprietà su 500 pixel.</span><span class="sxs-lookup"><span data-stu-id="6104d-151">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="6104d-152">il XAML dovrebbe essere simile al seguente per Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="6104d-152">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="6104d-153">E simili al seguente per C#:</span><span class="sxs-lookup"><span data-stu-id="6104d-153">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="6104d-154">Aprire *XAML. vb* oppure *MainWindow.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="6104d-154">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="6104d-155">Questo file è un file code-behind che contiene il codice per gestire gli eventi dichiarati nelle *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="6104d-155">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="6104d-156">Il file contiene una classe parziale per la finestra definita in XAML.</span><span class="sxs-lookup"><span data-stu-id="6104d-156">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="6104d-157">Se si usa C#, modificare il `MainWindow` classe derivandola da <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="6104d-157">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="6104d-158">(In Visual Basic, ciò avviene automaticamente quando si modifica la finestra in XAML.) Il C# codice dovrebbe ora essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="6104d-158">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="6104d-159">Aggiungere i file all'applicazione</span><span class="sxs-lookup"><span data-stu-id="6104d-159">Add files to the application</span></span>

<span data-ttu-id="6104d-160">In questa sezione si aggiungeranno due pagine e un'immagine all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-160">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="6104d-161">Aggiungere una nuova pagina al progetto e denominarlo *`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="6104d-161">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="6104d-162">Nelle **Esplora soluzioni**, fare clic sul **`ExpenseIt`** nodo del progetto e scegliere **Add** > **pagina**.</span><span class="sxs-lookup"><span data-stu-id="6104d-162">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="6104d-163">Nel **Aggiungi nuovo elemento** finestra di dialogo, il **pagina (WPF)** modello è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="6104d-163">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="6104d-164">Immettere il nome **`ExpenseItHome`**, quindi selezionare **Add**.</span><span class="sxs-lookup"><span data-stu-id="6104d-164">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="6104d-165">Questa pagina è la prima pagina visualizzata quando viene avviata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-165">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="6104d-166">Mostrerà un elenco di utenti di selezionare, per visualizzare una nota spese per.</span><span class="sxs-lookup"><span data-stu-id="6104d-166">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="6104d-167">Aprire *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="6104d-167">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="6104d-168">Impostare il <xref:System.Windows.Controls.Page.Title%2A> a "`ExpenseIt - Home`".</span><span class="sxs-lookup"><span data-stu-id="6104d-168">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="6104d-169">Impostare il `DesignHeight` e `DesignWidth` valori degli elementi di 300 pixel.</span><span class="sxs-lookup"><span data-stu-id="6104d-169">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="6104d-170">il XAML ora viene visualizzata come indicato di seguito per Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="6104d-170">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="6104d-171">E simili al seguente per C#:</span><span class="sxs-lookup"><span data-stu-id="6104d-171">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="6104d-172">Aprire *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="6104d-172">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="6104d-173">Aggiungere un <xref:System.Windows.Navigation.NavigationWindow.Source%2A> proprietà per il <xref:System.Windows.Navigation.NavigationWindow> elemento e impostarla su "`ExpenseItHome.xaml`".</span><span class="sxs-lookup"><span data-stu-id="6104d-173">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="6104d-174">Questo imposta *`ExpenseItHome.xaml`* prima pagina aperta all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-174">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="6104d-175">Esempio di XAML in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="6104d-175">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="6104d-176">E nel linguaggio C#:</span><span class="sxs-lookup"><span data-stu-id="6104d-176">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="6104d-177">È anche possibile impostare il **origine** proprietà nel **varie** categoria del **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="6104d-177">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Proprietà di origine nella finestra proprietà](./media/properties-source.png)

1. <span data-ttu-id="6104d-179">Aggiungere un'altra nuova pagina WPF al progetto e denominarlo *ExpenseReportPage. XAML*::</span><span class="sxs-lookup"><span data-stu-id="6104d-179">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="6104d-180">Nelle **Esplora soluzioni**, fare clic sul **`ExpenseIt`** nodo del progetto e scegliere **Add** > **pagina**.</span><span class="sxs-lookup"><span data-stu-id="6104d-180">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="6104d-181">Nel **Aggiungi nuovo elemento** finestra di dialogo, seleziona la **pagina (WPF)** modello.</span><span class="sxs-lookup"><span data-stu-id="6104d-181">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="6104d-182">Immettere il nome **ExpenseReportPage**, quindi selezionare **Add**.</span><span class="sxs-lookup"><span data-stu-id="6104d-182">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="6104d-183">Questa pagina visualizzerà la nota spese della persona selezionata nella **`ExpenseItHome`** pagina.</span><span class="sxs-lookup"><span data-stu-id="6104d-183">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="6104d-184">Aprire *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="6104d-184">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="6104d-185">Impostare il <xref:System.Windows.Controls.Page.Title%2A> a "`ExpenseIt - View Expense`".</span><span class="sxs-lookup"><span data-stu-id="6104d-185">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="6104d-186">Impostare il `DesignHeight` e `DesignWidth` valori degli elementi di 300 pixel.</span><span class="sxs-lookup"><span data-stu-id="6104d-186">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="6104d-187">*ExpenseReportPage. XAML* ora ha un aspetto analogo al seguente in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="6104d-187">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="6104d-188">E come il seguente in C#:</span><span class="sxs-lookup"><span data-stu-id="6104d-188">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="6104d-189">Aprire *ExpenseItHome* e *ExpenseReportPage*, o *ExpenseItHome.xaml.cs* e *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="6104d-189">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="6104d-190">Quando si crea un nuovo file di paging, Visual Studio crea automaticamente relativi *code-behind* file.</span><span class="sxs-lookup"><span data-stu-id="6104d-190">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="6104d-191">Questi file code-behind gestiscono la logica per rispondere all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6104d-191">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="6104d-192">Il codice dovrebbe essere simile al seguente per **`ExpenseItHome`**:</span><span class="sxs-lookup"><span data-stu-id="6104d-192">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="6104d-193">E simili al seguente per **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="6104d-193">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="6104d-194">Aggiungere un'immagine denominata *watermark. PNG* al progetto.</span><span class="sxs-lookup"><span data-stu-id="6104d-194">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="6104d-195">È possibile creare un'immagine, copiare il file dal codice di esempio o ottenerlo [qui](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="6104d-195">You can create your own image, copy the file from the sample code, or get it [here](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>

    1. <span data-ttu-id="6104d-196">Fare doppio clic sul nodo del progetto e selezionare **Add** > **elemento esistente**, oppure premere **MAIUSC**+**Alt** + **Oggetto**.</span><span class="sxs-lookup"><span data-stu-id="6104d-196">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="6104d-197">Nel **Aggiungi elemento esistente** finestra di dialogo impostare il filtro del file a uno **tutti i file** o **i file di immagine**, selezionare il file di immagine si vuole usare e quindi selezionare **Add** .</span><span class="sxs-lookup"><span data-stu-id="6104d-197">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="6104d-198">Compilazione ed esecuzione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="6104d-198">Build and run the application</span></span>

1. <span data-ttu-id="6104d-199">Per compilare ed eseguire l'applicazione, premere **F5** oppure selezionare **Avvia debug** dal **Debug** menu.</span><span class="sxs-lookup"><span data-stu-id="6104d-199">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="6104d-200">La figura seguente mostra l'applicazione con il <xref:System.Windows.Navigation.NavigationWindow> pulsanti:</span><span class="sxs-lookup"><span data-stu-id="6104d-200">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![Schermata dell'esempio ExpenseIt](./media/gettingstartedfigure1.png)

2. <span data-ttu-id="6104d-202">Chiudere l'applicazione per tornare a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6104d-202">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="6104d-203">Creare il layout</span><span class="sxs-lookup"><span data-stu-id="6104d-203">Create the layout</span></span>

<span data-ttu-id="6104d-204">Layout consente di posizionare gli elementi dell'interfaccia utente in modo ordinato e di gestione le dimensioni e posizione degli elementi durante il ridimensionamento di un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="6104d-204">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="6104d-205">In genere si crea un layout tramite uno dei controlli di layout seguenti:</span><span class="sxs-lookup"><span data-stu-id="6104d-205">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="6104d-206"><xref:System.Windows.Controls.Canvas> -Definisce un'area all'interno del quale è possibile posizionare in modo esplicito elementi figlio tramite coordinate relative rispetto all'area di disegno.</span><span class="sxs-lookup"><span data-stu-id="6104d-206"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="6104d-207"><xref:System.Windows.Controls.DockPanel> -Definisce un'area in cui è possibile disporre elementi figlio orizzontalmente o verticalmente, uno rispetto a altro.</span><span class="sxs-lookup"><span data-stu-id="6104d-207"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="6104d-208"><xref:System.Windows.Controls.Grid> -Definisce un'area griglia flessibile costituita da righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="6104d-208"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="6104d-209"><xref:System.Windows.Controls.StackPanel> -Dispone gli elementi figlio in una singola riga che può essere orientata orizzontalmente o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="6104d-209"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="6104d-210"><xref:System.Windows.Controls.VirtualizingStackPanel> -Dispone e virtualizza il contenuto in una sola riga che può essere orientata orizzontalmente o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="6104d-210"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="6104d-211"><xref:System.Windows.Controls.WrapPanel> -Posiziona gli elementi figlio in sequenza da sinistra a destra, contenuto di rilievo alla riga successiva sul bordo della casella contenitore.</span><span class="sxs-lookup"><span data-stu-id="6104d-211"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="6104d-212">Ordinamento successivo procede in sequenza dall'alto verso il basso o da destra a sinistra, a seconda del valore della proprietà Orientation.</span><span class="sxs-lookup"><span data-stu-id="6104d-212">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="6104d-213">Ognuno di questi controlli di layout supporta un determinato tipo di layout per i relativi elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="6104d-213">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="6104d-214">`ExpenseIt` è possono ridimensionare le pagine e ogni pagina contiene elementi disposti orizzontalmente e verticalmente insieme ad altri elementi.</span><span class="sxs-lookup"><span data-stu-id="6104d-214">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="6104d-215">In questo esempio, il <xref:System.Windows.Controls.Grid> viene usato come elemento di layout per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-215">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="6104d-216">Per altre informazioni sulle <xref:System.Windows.Controls.Panel> elementi, vedere [Cenni preliminari su pannelli](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6104d-216">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="6104d-217">Per altre informazioni sul layout, vedere [Layout](../advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="6104d-217">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="6104d-218">In questa sezione è creare una tabella a colonna singola con tre righe e un margine di 10 pixel tramite l'aggiunta di definizioni di colonna e riga per il <xref:System.Windows.Controls.Grid> nelle *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="6104d-218">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="6104d-219">Nel *`ExpenseItHome.xaml`*, impostare il <xref:System.Windows.FrameworkElement.Margin%2A> proprietà di <xref:System.Windows.Controls.Grid> elemento "10,0,10,10", che corrispondono ai margini sinistro, superiore, destro e inferiore:</span><span class="sxs-lookup"><span data-stu-id="6104d-219">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="6104d-220">È anche possibile impostare il **margine** i valori del **proprietà** finestra, sotto il **Layout** categoria:</span><span class="sxs-lookup"><span data-stu-id="6104d-220">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Valori dei margini nella finestra proprietà](./media/properties-margin.png)

2. <span data-ttu-id="6104d-222">Aggiungere il seguente XAML tra i <xref:System.Windows.Controls.Grid> tag per creare le definizioni di riga e colonna:</span><span class="sxs-lookup"><span data-stu-id="6104d-222">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="6104d-223">Il <xref:System.Windows.Controls.RowDefinition.Height%2A> di due righe è impostata su <xref:System.Windows.GridLength.Auto%2A>, il che significa che le righe vengono ridimensionate in base al contenuto delle righe.</span><span class="sxs-lookup"><span data-stu-id="6104d-223">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="6104d-224">Il valore predefinito <xref:System.Windows.Controls.RowDefinition.Height%2A> è <xref:System.Windows.GridUnitType.Star> determinazione della dimensione, ciò significa che l'altezza della riga è una proporzione ponderata dello spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="6104d-224">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="6104d-225">Se, ad esempio due righe hanno un <xref:System.Windows.Controls.RowDefinition.Height%2A> di "\*", ognuno ha un'altezza pari alla metà dello spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="6104d-225">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="6104d-226">Il <xref:System.Windows.Controls.Grid> dovrebbe ora contenere il seguente XAML:</span><span class="sxs-lookup"><span data-stu-id="6104d-226">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="6104d-227">Aggiungere controlli</span><span class="sxs-lookup"><span data-stu-id="6104d-227">Add controls</span></span>

<span data-ttu-id="6104d-228">In questa sezione, si aggiornerà la home page dell'interfaccia utente per visualizzare un elenco di persone, in cui si seleziona una persona per visualizzare la nota spese.</span><span class="sxs-lookup"><span data-stu-id="6104d-228">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="6104d-229">I controlli sono oggetti dell'interfaccia utente che consentono agli utenti di interagire con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-229">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="6104d-230">Per altre informazioni, vedere [Controlli](../controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="6104d-230">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="6104d-231">Per creare questa interfaccia utente, è necessario aggiungere gli elementi seguenti alla *`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="6104d-231">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="6104d-232">Oggetto <xref:System.Windows.Controls.ListBox> (per l'elenco di persone).</span><span class="sxs-lookup"><span data-stu-id="6104d-232">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="6104d-233">Oggetto <xref:System.Windows.Controls.Label> (per l'intestazione dell'elenco).</span><span class="sxs-lookup"><span data-stu-id="6104d-233">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="6104d-234">Oggetto <xref:System.Windows.Controls.Button> (deve fare clic per visualizzare la nota spese della persona selezionata nell'elenco).</span><span class="sxs-lookup"><span data-stu-id="6104d-234">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="6104d-235">Ogni controllo viene inserito in una riga della <xref:System.Windows.Controls.Grid> impostando la <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> proprietà associata.</span><span class="sxs-lookup"><span data-stu-id="6104d-235">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="6104d-236">Per altre informazioni sulle proprietà associate, vedere [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6104d-236">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="6104d-237">Nelle *`ExpenseItHome.xaml`*, aggiungere il seguente XAML in una posizione tra le <xref:System.Windows.Controls.Grid> tag:</span><span class="sxs-lookup"><span data-stu-id="6104d-237">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="6104d-238">È anche possibile creare i controlli trascinandoli dal **casella degli strumenti** alla finestra di progettazione e quindi impostando le proprietà nella finestra di **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="6104d-238">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="6104d-239">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-239">Build and run the application.</span></span>

    <span data-ttu-id="6104d-240">La figura seguente mostra i controlli che è stato creato:</span><span class="sxs-lookup"><span data-stu-id="6104d-240">The following illustration shows the controls you created:</span></span>

    ![Schermata dell'esempio ExpenseIt](./media/gettingstartedfigure2.png)

3. <span data-ttu-id="6104d-242">Chiudere l'applicazione per tornare a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6104d-242">Close the application to return to Visual Studio.</span></span>

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="6104d-243">Aggiungere un'immagine e un titolo</span><span class="sxs-lookup"><span data-stu-id="6104d-243">Add an image and a title</span></span>

<span data-ttu-id="6104d-244">In questa sezione, si verrà aggiornata la home page dell'interfaccia utente con un'immagine e un titolo della pagina.</span><span class="sxs-lookup"><span data-stu-id="6104d-244">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="6104d-245">Nelle *`ExpenseItHome.xaml`*, aggiungere un'altra colonna per il <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con fisse <xref:System.Windows.Controls.ColumnDefinition.Width%2A> di 230 pixel:</span><span class="sxs-lookup"><span data-stu-id="6104d-245">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="6104d-246">Aggiungere un'altra riga per il <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, per un totale di quattro righe:</span><span class="sxs-lookup"><span data-stu-id="6104d-246">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="6104d-247">Spostare i controlli nella seconda colonna impostando il <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> proprietà su 1 in ognuno dei tre controlli (bordo, ListBox e pulsante).</span><span class="sxs-lookup"><span data-stu-id="6104d-247">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="6104d-248">Spostare ogni controllo verso il basso una riga incrementando il relativo <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> valore di 1 per ognuno dei tre controlli (bordo, ListBox e pulsante) e per l'elemento Border.</span><span class="sxs-lookup"><span data-stu-id="6104d-248">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="6104d-249">il XAML per i tre controlli ora simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="6104d-249">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="6104d-250">Impostare il <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> proprietà per il *watermark. PNG* file di immagine, aggiungendo il seguente XAML in un punto qualsiasi tra il `<Grid>` e `</Grid>` tag:</span><span class="sxs-lookup"><span data-stu-id="6104d-250">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="6104d-251">Prima di <xref:System.Windows.Controls.Border> elemento, aggiungere un <xref:System.Windows.Controls.Label> con il contenuto "View Expense Report".</span><span class="sxs-lookup"><span data-stu-id="6104d-251">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="6104d-252">Questa etichetta è il titolo della pagina.</span><span class="sxs-lookup"><span data-stu-id="6104d-252">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="6104d-253">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-253">Build and run the application.</span></span>

<span data-ttu-id="6104d-254">La figura seguente mostra i risultati di ciò che appena aggiunto:</span><span class="sxs-lookup"><span data-stu-id="6104d-254">The following illustration shows the results of what you just added:</span></span>

![Schermata dell'esempio ExpenseIt](./media/gettingstartedfigure3.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="6104d-256">Aggiungere il codice per gestire gli eventi</span><span class="sxs-lookup"><span data-stu-id="6104d-256">Add code to handle events</span></span>

1. <span data-ttu-id="6104d-257">Nelle *`ExpenseItHome.xaml`*, aggiungere un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore dell'evento per il <xref:System.Windows.Controls.Button> elemento.</span><span class="sxs-lookup"><span data-stu-id="6104d-257">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="6104d-258">Per altre informazioni, vedere [Procedura: Creare un gestore eventi semplice](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="6104d-258">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="6104d-259">Aprire *`ExpenseItHome.xaml.vb`* oppure *`ExpenseItHome.xaml.cs`*.</span><span class="sxs-lookup"><span data-stu-id="6104d-259">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="6104d-260">Aggiungere il codice seguente per il `ExpenseItHome` classe per aggiungere un pulsante gestore dell'evento click.</span><span class="sxs-lookup"><span data-stu-id="6104d-260">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="6104d-261">Il gestore eventi apre la **ExpenseReportPage** pagina.</span><span class="sxs-lookup"><span data-stu-id="6104d-261">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="6104d-262">Creare l'interfaccia utente per ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="6104d-262">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="6104d-263">*ExpenseReportPage. XAML* consente di visualizzare la nota spese della persona selezionata nella **`ExpenseItHome`** pagina.</span><span class="sxs-lookup"><span data-stu-id="6104d-263">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="6104d-264">In questa sezione si creerà l'interfaccia utente per **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="6104d-264">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="6104d-265">Verrà inoltre aggiunto sfondo e colori di riempimento ai vari elementi dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="6104d-265">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="6104d-266">Aprire *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="6104d-266">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="6104d-267">Aggiungere il seguente XAML tra i <xref:System.Windows.Controls.Grid> tag:</span><span class="sxs-lookup"><span data-stu-id="6104d-267">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="6104d-268">Questa interfaccia utente è simile a *`ExpenseItHome.xaml`*, tranne i dati del report viene visualizzati un <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="6104d-268">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="6104d-269">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-269">Build and run the application.</span></span>

4. <span data-ttu-id="6104d-270">Selezionare il **vista** pulsante.</span><span class="sxs-lookup"><span data-stu-id="6104d-270">Select the **View** button.</span></span>

    <span data-ttu-id="6104d-271">Viene visualizzata la pagina della nota spese.</span><span class="sxs-lookup"><span data-stu-id="6104d-271">The expense report page appears.</span></span> <span data-ttu-id="6104d-272">Si noti inoltre che il pulsante di navigazione indietro è abilitato.</span><span class="sxs-lookup"><span data-stu-id="6104d-272">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="6104d-273">La figura seguente mostra gli elementi dell'interfaccia utente aggiunti alla *ExpenseReportPage. XAML*.</span><span class="sxs-lookup"><span data-stu-id="6104d-273">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Schermata dell'esempio ExpenseIt](./media/gettingstartedfigure4.png)

## <a name="style-controls"></a><span data-ttu-id="6104d-275">Controlli in stile</span><span class="sxs-lookup"><span data-stu-id="6104d-275">Style controls</span></span>

<span data-ttu-id="6104d-276">L'aspetto dei diversi elementi spesso è lo stesso per tutti gli elementi dello stesso tipo in un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="6104d-276">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="6104d-277">Interfaccia utente usa [stili](../controls/styling-and-templating.md) per rendere l'aspetto riutilizzabile tra più elementi.</span><span class="sxs-lookup"><span data-stu-id="6104d-277">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="6104d-278">La possibilità di riutilizzo consente di semplificare la gestione e la creazione di XAML.</span><span class="sxs-lookup"><span data-stu-id="6104d-278">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="6104d-279">In questa sezione vengono sostituiti con gli stili gli attributi per elemento definiti nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="6104d-279">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="6104d-280">Aprire *Application. XAML* oppure *app*.</span><span class="sxs-lookup"><span data-stu-id="6104d-280">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="6104d-281">Aggiungere il seguente XAML tra i <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tag:</span><span class="sxs-lookup"><span data-stu-id="6104d-281">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="6104d-282">Questo codice XAML aggiunge gli stili seguenti:</span><span class="sxs-lookup"><span data-stu-id="6104d-282">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="6104d-283">`headerTextStyle`: Per formattare il titolo della pagina <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="6104d-283">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="6104d-284">`labelStyle`: Per formattare il <xref:System.Windows.Controls.Label> controlli.</span><span class="sxs-lookup"><span data-stu-id="6104d-284">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="6104d-285">`columnHeaderStyle`: Per formattare il <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="6104d-285">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="6104d-286">`listHeaderStyle`: Per formattare l'intestazione dell'elenco <xref:System.Windows.Controls.Border> controlli.</span><span class="sxs-lookup"><span data-stu-id="6104d-286">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="6104d-287">`listHeaderTextStyle`: Per formattare l'intestazione dell'elenco <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="6104d-287">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="6104d-288">`buttonStyle`: Per formattare il <xref:System.Windows.Controls.Button> su `ExpenseItHome.xaml`.</span><span class="sxs-lookup"><span data-stu-id="6104d-288">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="6104d-289">Si noti che gli stili sono risorse ed elementi figlio del <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property (elemento).</span><span class="sxs-lookup"><span data-stu-id="6104d-289">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="6104d-290">In questa posizione, gli stili vengono applicati a tutti gli elementi di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-290">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="6104d-291">Per un esempio di utilizzo delle risorse in un'app .NET, vedere [le risorse dell'applicazione usare](../advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="6104d-291">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="6104d-292">Nelle *`ExpenseItHome.xaml`*, sostituire tutto il contenuto tra il <xref:System.Windows.Controls.Grid> gli elementi con il XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="6104d-292">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="6104d-293">Le proprietà come <xref:System.Windows.VerticalAlignment> e <xref:System.Windows.Media.FontFamily> che definiscono l'aspetto di ciascun controllo vengono rimosse e sostituite mediante l'applicazione degli stili.</span><span class="sxs-lookup"><span data-stu-id="6104d-293">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="6104d-294">Ad esempio, il `headerTextStyle` viene applicato a "View Expense Report" <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="6104d-294">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="6104d-295">Aprire *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="6104d-295">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="6104d-296">Sostituire tutto il contenuto tra il <xref:System.Windows.Controls.Grid> gli elementi con il XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="6104d-296">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="6104d-297">Questo XAML aggiunge gli stili per il <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.Border> elementi.</span><span class="sxs-lookup"><span data-stu-id="6104d-297">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="6104d-298">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-298">Build and run the application.</span></span> <span data-ttu-id="6104d-299">L'aspetto delle finestre è uguale come in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6104d-299">The window appearance is the same as previously.</span></span>

    ![Schermata dell'esempio ExpenseIt](./media/gettingstartedfigure4.png)

7. <span data-ttu-id="6104d-301">Chiudere l'applicazione per tornare a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6104d-301">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="6104d-302">Associare dati a un controllo</span><span class="sxs-lookup"><span data-stu-id="6104d-302">Bind data to a control</span></span>

<span data-ttu-id="6104d-303">In questa sezione si creerà i dati XML che sono associati a vari controlli.</span><span class="sxs-lookup"><span data-stu-id="6104d-303">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="6104d-304">Nelle *`ExpenseItHome.xaml`*, dopo l'apertura <xref:System.Windows.Controls.Grid> elemento, aggiungere il seguente XAML per creare un <xref:System.Windows.Data.XmlDataProvider> che contiene i dati per ogni persona:</span><span class="sxs-lookup"><span data-stu-id="6104d-304">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="6104d-305">I dati vengono creati come una <xref:System.Windows.Controls.Grid> risorsa.</span><span class="sxs-lookup"><span data-stu-id="6104d-305">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="6104d-306">In genere questi dati verranno caricati come file, ma per semplicità i dati verranno aggiunti inline.</span><span class="sxs-lookup"><span data-stu-id="6104d-306">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="6104d-307">All'interno di `<Grid.Resources>` elemento, aggiungere quanto segue `<xref:System.Windows.DataTemplate>` elemento che definisce come visualizzare i dati nel <xref:System.Windows.Controls.ListBox>, dopo il `<XmlDataProvider>` elemento:</span><span class="sxs-lookup"><span data-stu-id="6104d-307">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="6104d-308">Per altre informazioni sui modelli di dati, vedere [Cenni preliminari sui modelli di dati](../data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6104d-308">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="6104d-309">Sostituire il <xref:System.Windows.Controls.ListBox> con il XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="6104d-309">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="6104d-310">Questo XAML associa il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà del <xref:System.Windows.Controls.ListBox> all'origine dati e applica il modello di dati come il <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="6104d-310">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="6104d-311">Connetti i dati a controlli</span><span class="sxs-lookup"><span data-stu-id="6104d-311">Connect data to controls</span></span>

<span data-ttu-id="6104d-312">Successivamente, si aggiungerà codice per recuperare il nome selezionato sul **`ExpenseItHome`** pagina e passarlo al costruttore della **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="6104d-312">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="6104d-313">**ExpenseReportPage** imposta il contesto dei dati con l'elemento passato, ovvero i controlli definiti in *ExpenseReportPage. XAML* associarsi.</span><span class="sxs-lookup"><span data-stu-id="6104d-313">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="6104d-314">Aprire *ExpenseReportPage.xaml.vb* o *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="6104d-314">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="6104d-315">Aggiungere un costruttore che accetti un oggetto, in modo da poter passare i dati della nota spese della persona selezionata.</span><span class="sxs-lookup"><span data-stu-id="6104d-315">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="6104d-316">Aprire *`ExpenseItHome.xaml.vb`* oppure *`ExpenseItHome.xaml.cs`*.</span><span class="sxs-lookup"><span data-stu-id="6104d-316">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="6104d-317">Modifica il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi per chiamare il nuovo costruttore che passa i dati della nota spese della persona selezionata.</span><span class="sxs-lookup"><span data-stu-id="6104d-317">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="6104d-318">Dati di tipo con i modelli di dati</span><span class="sxs-lookup"><span data-stu-id="6104d-318">Style data with data templates</span></span>

<span data-ttu-id="6104d-319">In questa sezione, si aggiornerà l'interfaccia utente per ogni elemento negli elenchi associati a dati con i modelli di dati.</span><span class="sxs-lookup"><span data-stu-id="6104d-319">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="6104d-320">Aprire *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="6104d-320">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="6104d-321">Associare il contenuto del "Name" e "Department" <xref:System.Windows.Controls.Label> proprietà dell'origine elementi per i dati appropriati.</span><span class="sxs-lookup"><span data-stu-id="6104d-321">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="6104d-322">Per altre informazioni sul data binding, vedere [Panoramica sul Data binding](../data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6104d-322">For more information about data binding, see [Data binding overview](../data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="6104d-323">Dopo l'apertura <xref:System.Windows.Controls.Grid> elemento, aggiungere i seguenti modelli di dati, che definiscono la modalità visualizzare i dati della nota spese:</span><span class="sxs-lookup"><span data-stu-id="6104d-323">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="6104d-324">Sostituire il <xref:System.Windows.Controls.DataGridTextColumn> elementi con <xref:System.Windows.Controls.DataGridTemplateColumn> sotto il <xref:System.Windows.Controls.DataGrid> elemento e applica i modelli a essi.</span><span class="sxs-lookup"><span data-stu-id="6104d-324">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="6104d-325">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6104d-325">Build and run the application.</span></span>

6. <span data-ttu-id="6104d-326">Selezionare una persona e quindi selezionare il **vista** pulsante.</span><span class="sxs-lookup"><span data-stu-id="6104d-326">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="6104d-327">Nella figura seguente mostra le due pagine del `ExpenseIt` applicazione controlli, layout, stili, associazione dati e modelli di dati applicati:</span><span class="sxs-lookup"><span data-stu-id="6104d-327">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Schermate dell'esempio ExpenseIt](./media/gettingstartedfigure5.png)

> [!NOTE]
> <span data-ttu-id="6104d-329">Questo esempio illustra una funzionalità specifica di WPF e non segue tutte le procedure consigliate per aspetti quali sicurezza, localizzazione e accessibilità.</span><span class="sxs-lookup"><span data-stu-id="6104d-329">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="6104d-330">Per una descrizione completa di WPF e le procedure guidate di sviluppo .NET di app, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6104d-330">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="6104d-331">Accessibilità</span><span class="sxs-lookup"><span data-stu-id="6104d-331">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="6104d-332">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6104d-332">Security</span></span>](../security-wpf.md)
>
> - [<span data-ttu-id="6104d-333">Globalizzazione e localizzazione WPF</span><span class="sxs-lookup"><span data-stu-id="6104d-333">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="6104d-334">Prestazioni WPF</span><span class="sxs-lookup"><span data-stu-id="6104d-334">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="6104d-335">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6104d-335">Next steps</span></span>

<span data-ttu-id="6104d-336">In questa procedura dettagliata si è appreso diverse tecniche per la creazione di un'interfaccia utente mediante Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="6104d-336">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="6104d-337">È stata acquisita una conoscenza di base dei blocchi predefiniti di un'app .NET con associazione a dati.</span><span class="sxs-lookup"><span data-stu-id="6104d-337">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="6104d-338">Per altre informazioni sull'architettura WPF e i modelli di programmazione, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6104d-338">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="6104d-339">Architettura WPF</span><span class="sxs-lookup"><span data-stu-id="6104d-339">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="6104d-340">Panoramica di XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="6104d-340">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="6104d-341">Cenni preliminari sulle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="6104d-341">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="6104d-342">Layout</span><span class="sxs-lookup"><span data-stu-id="6104d-342">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="6104d-343">Per altre informazioni sulla creazione di applicazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6104d-343">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="6104d-344">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="6104d-344">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="6104d-345">Controlli</span><span class="sxs-lookup"><span data-stu-id="6104d-345">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="6104d-346">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="6104d-346">Data binding overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="6104d-347">Grafica e funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="6104d-347">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="6104d-348">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="6104d-348">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="6104d-349">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6104d-349">See also</span></span>

- [<span data-ttu-id="6104d-350">Panoramica di pannelli</span><span class="sxs-lookup"><span data-stu-id="6104d-350">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="6104d-351">Cenni preliminari sui modelli di dati</span><span class="sxs-lookup"><span data-stu-id="6104d-351">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="6104d-352">Compilare un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="6104d-352">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="6104d-353">Stili e modelli</span><span class="sxs-lookup"><span data-stu-id="6104d-353">Styles and templates</span></span>](../controls/styles-and-templates.md)
