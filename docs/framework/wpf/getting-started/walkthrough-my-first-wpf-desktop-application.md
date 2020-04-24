---
title: Creare la prima app WPF in Visual Studio 2019 - .NET Framework
titleSuffix: ''
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
ms.openlocfilehash: 9381873faa8cca1accf95d823f5183a218d28813
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646421"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a><span data-ttu-id="5e8de-102">Esercitazione: Creare la prima applicazione WPF in Visual Studio 2019Tutorial: Create your first WPF application in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="5e8de-102">Tutorial: Create your first WPF application in Visual Studio 2019</span></span>

<span data-ttu-id="5e8de-103">In questo articolo viene illustrato come sviluppare un'applicazione desktop Windows Presentation Foundation (WPF) che include gli elementi comuni alla maggior parte delle applicazioni WPFWPF: markup XAML (Extensible Application Markup Language), code-behind, definizioni di applicazioni, controlli, layout, associazione dati e stili.</span><span class="sxs-lookup"><span data-stu-id="5e8de-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="5e8de-104">Per sviluppare l'applicazione, si userà Visual Studio.To develop the application, you'll use Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5e8de-104">To develop the application, you'll use Visual Studio.</span></span>

<span data-ttu-id="5e8de-105">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="5e8de-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="5e8de-106">Creare un progetto WPF.</span><span class="sxs-lookup"><span data-stu-id="5e8de-106">Create a WPF project.</span></span>
> - <span data-ttu-id="5e8de-107">Usa XAML per progettare l'aspetto dell'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-107">Use XAML to design the appearance of the application's user interface (UI).</span></span>
> - <span data-ttu-id="5e8de-108">Scrivere codice per compilare il comportamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-108">Write code to build the application's behavior.</span></span>
> - <span data-ttu-id="5e8de-109">Creare una definizione di applicazione per gestire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-109">Create an application definition to manage the application.</span></span>
> - <span data-ttu-id="5e8de-110">Aggiungere controlli e creare il layout per comporre l'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-110">Add controls and create the layout to compose the application UI.</span></span>
> - <span data-ttu-id="5e8de-111">Creare stili per un aspetto coerente in tutta l'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-111">Create styles for a consistent appearance throughout the application's UI.</span></span>
> - <span data-ttu-id="5e8de-112">Associare l'interfaccia utente ai dati, sia per popolare l'interfaccia utente dai dati che per mantenere sincronizzati i dati e l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5e8de-112">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="5e8de-113">Alla fine dell'esercitazione, avrai creato un'applicazione Windows autonoma che consente agli utenti di visualizzare le note spese per persone selezionate.</span><span class="sxs-lookup"><span data-stu-id="5e8de-113">By the end of the tutorial, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="5e8de-114">L'applicazione è composta da diverse pagine WPF ospitate in una finestra di tipo browser.</span><span class="sxs-lookup"><span data-stu-id="5e8de-114">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="5e8de-115">Il codice di esempio utilizzato in questa esercitazione è disponibile sia per Visual Basic che per C, in [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="5e8de-115">The sample code that is used in this tutorial is available for both Visual Basic and C# at [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="5e8de-116">È possibile attivare o disattivare il linguaggio di codice del codice di esempio tra C ' e Visual Basic utilizzando il selettore del linguaggio nella parte superiore di questa pagina.</span><span class="sxs-lookup"><span data-stu-id="5e8de-116">You can toggle the code language of the sample code between C# and Visual Basic by using the language selector on top of this page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5e8de-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5e8de-117">Prerequisites</span></span>

- <span data-ttu-id="5e8de-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro di **sviluppo desktop .NET** installato.</span><span class="sxs-lookup"><span data-stu-id="5e8de-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET desktop development** workload installed.</span></span>

   <span data-ttu-id="5e8de-119">Per ulteriori informazioni sull'installazione della versione più recente di Visual Studio, vedere [Installare Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="5e8de-119">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="5e8de-120">Creare il progetto di applicazioneCreate the application project</span><span class="sxs-lookup"><span data-stu-id="5e8de-120">Create the application project</span></span>

<span data-ttu-id="5e8de-121">Il primo passaggio consiste nel creare l'infrastruttura dell'applicazione, che include una definizione di applicazione, due pagine e un'immagine.</span><span class="sxs-lookup"><span data-stu-id="5e8de-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="5e8de-122">Creare un nuovo progetto di applicazione WPF **`ExpenseIt`** in Visual Basic o Visual C, denominato :</span><span class="sxs-lookup"><span data-stu-id="5e8de-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="5e8de-123">Aprire Visual Studio e selezionare **Crea un nuovo progetto** nel menu Inizia.Open Visual Studio and select Create a new project under the Get **started** menu.</span><span class="sxs-lookup"><span data-stu-id="5e8de-123">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="5e8de-124">Viene visualizzata la finestra di dialogo **Crea un nuovo progetto.**</span><span class="sxs-lookup"><span data-stu-id="5e8de-124">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="5e8de-125">Nell'elenco a discesa **Linguaggio,** selezionare **C '** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="5e8de-125">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>

   3. <span data-ttu-id="5e8de-126">Selezionare il modello **App WPF (.NET Framework)** e quindi **scegliere Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5e8de-126">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span>

      ![Finestra di dialogo Crea un nuovo progetto](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      <span data-ttu-id="5e8de-128">Viene visualizzata la finestra di dialogo **Configura il nuovo progetto.**</span><span class="sxs-lookup"><span data-stu-id="5e8de-128">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="5e8de-129">Immettere il **`ExpenseIt`** nome del progetto e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="5e8de-129">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![Finestra di dialogo Configura un nuovo progetto](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="5e8de-131">Visual Studio crea il progetto e apre la finestra di progettazione per la finestra dell'applicazione predefinita **denominata MainWindow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="5e8de-131">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="5e8de-132">Aprire *Application.xaml* (Visual Basic) o *App.xaml* (C' ).</span><span class="sxs-lookup"><span data-stu-id="5e8de-132">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="5e8de-133">Questo file XAML definisce un'applicazione WPF e tutte le risorse dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-133">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="5e8de-134">Questo file viene utilizzato anche per specificare l'interfaccia utente, in questo caso *MainWindow.xaml*, che viene visualizzata automaticamente all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-134">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="5e8de-135">Il codice XAML dovrebbe essere simile al seguente in Visual Basic:Your XAML should look like the following in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="5e8de-135">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="5e8de-136">E come il seguente in C :</span><span class="sxs-lookup"><span data-stu-id="5e8de-136">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="5e8de-137">Aprire *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="5e8de-137">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="5e8de-138">Questo file XAML è la finestra principale dell'applicazione e visualizza il contenuto creato nelle pagine.</span><span class="sxs-lookup"><span data-stu-id="5e8de-138">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="5e8de-139">La <xref:System.Windows.Window> classe definisce le proprietà di una finestra, ad esempio il titolo, le dimensioni o l'icona, e gestisce gli eventi, ad esempio la chiusura o l'occultamento.</span><span class="sxs-lookup"><span data-stu-id="5e8de-139">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="5e8de-140">Modificare <xref:System.Windows.Window> l'elemento <xref:System.Windows.Navigation.NavigationWindow>in un oggetto , come illustrato nel codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="5e8de-140">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="5e8de-141">Questa app passa a contenuti diversi a seconda dell'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5e8de-141">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="5e8de-142">Questo è il <xref:System.Windows.Window> motivo per <xref:System.Windows.Navigation.NavigationWindow>cui il principale deve essere cambiato in un .</span><span class="sxs-lookup"><span data-stu-id="5e8de-142">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="5e8de-143"><xref:System.Windows.Navigation.NavigationWindow>eredita tutte le <xref:System.Windows.Window>proprietà di .</span><span class="sxs-lookup"><span data-stu-id="5e8de-143"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="5e8de-144">L'elemento <xref:System.Windows.Navigation.NavigationWindow> nel file XAML crea <xref:System.Windows.Navigation.NavigationWindow> un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="5e8de-144">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="5e8de-145">Per ulteriori informazioni, consultate [Panoramica della navigazione.](../app-development/navigation-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5e8de-145">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="5e8de-146">Rimuovere <xref:System.Windows.Controls.Grid> gli elementi <xref:System.Windows.Navigation.NavigationWindow> tra i tag.</span><span class="sxs-lookup"><span data-stu-id="5e8de-146">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="5e8de-147">Modificare le proprietà seguenti nel <xref:System.Windows.Navigation.NavigationWindow> codice XAML per l'elemento:</span><span class="sxs-lookup"><span data-stu-id="5e8de-147">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="5e8de-148">Impostare <xref:System.Windows.Window.Title%2A> la`ExpenseIt`proprietà su " ".</span><span class="sxs-lookup"><span data-stu-id="5e8de-148">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="5e8de-149">Impostare <xref:System.Windows.FrameworkElement.Height%2A> la proprietà su 350 pixel.</span><span class="sxs-lookup"><span data-stu-id="5e8de-149">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="5e8de-150">Impostare <xref:System.Windows.FrameworkElement.Width%2A> la proprietà su 500 pixel.</span><span class="sxs-lookup"><span data-stu-id="5e8de-150">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="5e8de-151">Il codice XAML dovrebbe essere simile al seguente per Visual Basic:Your XAML should look like the following for Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="5e8de-151">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="5e8de-152">E come il seguente per il linguaggio C:</span><span class="sxs-lookup"><span data-stu-id="5e8de-152">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="5e8de-153">Aprire *MainWindow.xaml.vb* o *MainWindow.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="5e8de-153">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="5e8de-154">Questo file è un file code-behind che contiene il codice per gestire gli eventi dichiarati in *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="5e8de-154">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="5e8de-155">Il file contiene una classe parziale per la finestra definita in XAML.</span><span class="sxs-lookup"><span data-stu-id="5e8de-155">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="5e8de-156">Se si utilizza C, modificare `MainWindow` la classe <xref:System.Windows.Navigation.NavigationWindow>in modo che derivi da .</span><span class="sxs-lookup"><span data-stu-id="5e8de-156">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="5e8de-157">(In Visual Basic, questo accade automaticamente quando si modifica la finestra in XAML.) Il codice di C'è ora simile al seguente:Your C's code should now look like this:</span><span class="sxs-lookup"><span data-stu-id="5e8de-157">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="5e8de-158">Aggiungere file all'applicazione</span><span class="sxs-lookup"><span data-stu-id="5e8de-158">Add files to the application</span></span>

<span data-ttu-id="5e8de-159">In questa sezione si aggiungeranno due pagine e un'immagine all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="5e8de-160">Aggiungere una nuova pagina al progetto *`ExpenseItHome.xaml`* e denominarla:</span><span class="sxs-lookup"><span data-stu-id="5e8de-160">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="5e8de-161">In **Esplora soluzioni**fare **`ExpenseIt`** clic con il pulsante destro del mouse sul nodo del progetto e **scegliere Aggiungi** > **pagina**.</span><span class="sxs-lookup"><span data-stu-id="5e8de-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="5e8de-162">Nella finestra di dialogo **Aggiungi nuovo elemento,** il modello **Pagina (WPF)** è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="5e8de-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="5e8de-163">Immettere **`ExpenseItHome`** il nome , quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5e8de-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="5e8de-164">Questa pagina è la prima pagina visualizzata all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="5e8de-165">Verrà visualizzato un elenco di persone tra cui scegliere, per cui visualizzare una nota spese.</span><span class="sxs-lookup"><span data-stu-id="5e8de-165">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="5e8de-166">Aperto *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="5e8de-166">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="5e8de-167">Impostare <xref:System.Windows.Controls.Page.Title%2A> il`ExpenseIt - Home`su " ".</span><span class="sxs-lookup"><span data-stu-id="5e8de-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="5e8de-168">Impostare `DesignHeight` il valore di `DesignWidth` 350 pixel e 500 pixel.</span><span class="sxs-lookup"><span data-stu-id="5e8de-168">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="5e8de-169">Il codice XAML viene ora visualizzato come segue per Visual Basic:The XAML now appears as follows for Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="5e8de-169">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="5e8de-170">E come il seguente per il linguaggio C:</span><span class="sxs-lookup"><span data-stu-id="5e8de-170">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="5e8de-171">Aprire *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="5e8de-171">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="5e8de-172">Aggiungere <xref:System.Windows.Navigation.NavigationWindow.Source%2A> una proprietà <xref:System.Windows.Navigation.NavigationWindow> all'elemento e`ExpenseItHome.xaml`impostarla su " ".</span><span class="sxs-lookup"><span data-stu-id="5e8de-172">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="5e8de-173">Questo *`ExpenseItHome.xaml`* imposta per essere la prima pagina aperta all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-173">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span>

    <span data-ttu-id="5e8de-174">XAML di esempio in Visual Basic:Example XAML in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="5e8de-174">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="5e8de-175">E in C:</span><span class="sxs-lookup"><span data-stu-id="5e8de-175">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="5e8de-176">È inoltre possibile impostare la proprietà **Source** nella categoria **Varie** della finestra **Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="5e8de-176">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Proprietà Source nella finestra Proprietà](./media/properties-source.png)

1. <span data-ttu-id="5e8de-178">Aggiungere un'altra nuova pagina WPF al progetto e denominarla *ExpenseReportPage.xaml*::</span><span class="sxs-lookup"><span data-stu-id="5e8de-178">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="5e8de-179">In **Esplora soluzioni**fare **`ExpenseIt`** clic con il pulsante destro del mouse sul nodo del progetto e **scegliere Aggiungi** > **pagina**.</span><span class="sxs-lookup"><span data-stu-id="5e8de-179">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="5e8de-180">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare il modello Pagina **(WPF).**</span><span class="sxs-lookup"><span data-stu-id="5e8de-180">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="5e8de-181">Immettere il nome **ExpenseReportPage**, quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5e8de-181">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="5e8de-182">In questa pagina verrà visualizzata la nota **`ExpenseItHome`** spese per la persona selezionata nella pagina.</span><span class="sxs-lookup"><span data-stu-id="5e8de-182">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="5e8de-183">Aprire *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="5e8de-183">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="5e8de-184">Impostare <xref:System.Windows.Controls.Page.Title%2A> il`ExpenseIt - View Expense`su " ".</span><span class="sxs-lookup"><span data-stu-id="5e8de-184">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="5e8de-185">Impostare `DesignHeight` il valore di `DesignWidth` 350 pixel e 500 pixel.</span><span class="sxs-lookup"><span data-stu-id="5e8de-185">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="5e8de-186">*ExpenseReportPage.xaml* è ora simile al seguente in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="5e8de-186">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="5e8de-187">E come il seguente in C :</span><span class="sxs-lookup"><span data-stu-id="5e8de-187">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="5e8de-188">Aprire *ExpenseItHome.xaml.vb* e *ExpenseReportPage.xaml.vb*oppure *ExpenseItHome.xaml.cs* e *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="5e8de-188">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="5e8de-189">Quando si crea un nuovo file di paging, Visual Studio crea automaticamente il relativo file *code-behind.*</span><span class="sxs-lookup"><span data-stu-id="5e8de-189">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="5e8de-190">Questi file code-behind gestiscono la logica per rispondere all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5e8de-190">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="5e8de-191">Il codice dovrebbe essere **`ExpenseItHome`** simile al seguente per :</span><span class="sxs-lookup"><span data-stu-id="5e8de-191">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="5e8de-192">E come il seguente per **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="5e8de-192">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="5e8de-193">Aggiungere un'immagine denominata *watermark.png* al progetto.</span><span class="sxs-lookup"><span data-stu-id="5e8de-193">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="5e8de-194">È possibile creare un'immagine personalizzata, copiare il file dal codice di esempio o ottenerlo dal repository GitHub [di microsoft/WPF-Samples.You](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) can create your own image, copy the file from the sample code, or get it from the microsoft/WPF-Samples GitHub repository.</span><span class="sxs-lookup"><span data-stu-id="5e8de-194">You can create your own image, copy the file from the sample code, or get it from the [microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub repository.</span></span>

    1. <span data-ttu-id="5e8de-195">Fare clic con il pulsante destro del mouse sul nodo del progetto e selezionare **Aggiungi** > **elemento esistente**oppure premere**ALT**+**A** **.**+</span><span class="sxs-lookup"><span data-stu-id="5e8de-195">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="5e8de-196">Nella finestra di dialogo **Aggiungi elemento esistente** impostare il filtro di file su Tutti i **file** o **File di immagine**, individuare il file di immagine che si desidera utilizzare e quindi scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5e8de-196">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="5e8de-197">Compilare ed eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="5e8de-197">Build and run the application</span></span>

1. <span data-ttu-id="5e8de-198">Per compilare ed eseguire l'applicazione, premere **F5** o scegliere **Avvia debug** dal menu **Debug** .</span><span class="sxs-lookup"><span data-stu-id="5e8de-198">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="5e8de-199">La figura seguente mostra <xref:System.Windows.Navigation.NavigationWindow> l'applicazione con i pulsanti:</span><span class="sxs-lookup"><span data-stu-id="5e8de-199">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![L'applicazione dopo averla compilata ed eseguita.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="5e8de-201">Chiudere l'applicazione per tornare a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5e8de-201">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="5e8de-202">Creare il layout</span><span class="sxs-lookup"><span data-stu-id="5e8de-202">Create the layout</span></span>

<span data-ttu-id="5e8de-203">Layout fornisce un modo ordinato per posizionare gli elementi dell'interfaccia utente e gestisce anche le dimensioni e la posizione di tali elementi quando un'interfaccia utente viene ridimensionata.</span><span class="sxs-lookup"><span data-stu-id="5e8de-203">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="5e8de-204">In genere si crea un layout tramite uno dei controlli di layout seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e8de-204">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="5e8de-205"><xref:System.Windows.Controls.Canvas>- Definisce un'area all'interno della quale è possibile posizionare in modo esplicito gli elementi figlio utilizzando coordinate relative all'area di disegno.</span><span class="sxs-lookup"><span data-stu-id="5e8de-205"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="5e8de-206"><xref:System.Windows.Controls.DockPanel>- Definisce un'area in cui è possibile disporre gli elementi figlio orizzontalmente o verticalmente, uno rispetto all'altro.</span><span class="sxs-lookup"><span data-stu-id="5e8de-206"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="5e8de-207"><xref:System.Windows.Controls.Grid>- Definisce un'area della griglia flessibile costituita da colonne e righe.</span><span class="sxs-lookup"><span data-stu-id="5e8de-207"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="5e8de-208"><xref:System.Windows.Controls.StackPanel>- Dispone gli elementi figlio in un'unica riga che può essere orientata orizzontalmente o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="5e8de-208"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="5e8de-209"><xref:System.Windows.Controls.VirtualizingStackPanel>- Dispone e virtualizza il contenuto su una singola riga orientata orizzontalmente o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="5e8de-209"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="5e8de-210"><xref:System.Windows.Controls.WrapPanel>- Posiziona gli elementi figlio in posizione sequenziale da sinistra a destra, suddividendo il contenuto alla riga successiva sul bordo della casella contenitore.</span><span class="sxs-lookup"><span data-stu-id="5e8de-210"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="5e8de-211">L'ordinamento successivo viene eseguito in sequenza dall'alto verso il basso o da destra a sinistra, a seconda del valore della proprietà Orientation.</span><span class="sxs-lookup"><span data-stu-id="5e8de-211">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="5e8de-212">Ognuno di questi controlli di layout supporta un particolare tipo di layout per i relativi elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="5e8de-212">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="5e8de-213">`ExpenseIt`le pagine possono essere ridimensionate e ogni pagina contiene elementi disposti orizzontalmente e verticalmente insieme ad altri elementi.</span><span class="sxs-lookup"><span data-stu-id="5e8de-213">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="5e8de-214">In questo esempio, l'oggetto <xref:System.Windows.Controls.Grid> viene utilizzato come elemento di layout per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-214">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="5e8de-215">Per ulteriori <xref:System.Windows.Controls.Panel> informazioni sugli elementi, consultate [Panoramica dei pannelli.](../controls/panels-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5e8de-215">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="5e8de-216">Per ulteriori informazioni sul layout, consultate [Layout.](../advanced/layout.md)</span><span class="sxs-lookup"><span data-stu-id="5e8de-216">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="5e8de-217">In questa sezione viene creata una tabella a colonna singola con tre righe e un <xref:System.Windows.Controls.Grid> *`ExpenseItHome.xaml`* margine di 10 pixel aggiungendo definizioni di colonna e riga alla .</span><span class="sxs-lookup"><span data-stu-id="5e8de-217">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="5e8de-218">In *`ExpenseItHome.xaml`*, <xref:System.Windows.FrameworkElement.Margin%2A> impostare <xref:System.Windows.Controls.Grid> la proprietà dell'elemento su "10,0,10,10", che corrisponde ai margini sinistro, superiore, destro e inferiore:</span><span class="sxs-lookup"><span data-stu-id="5e8de-218">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="5e8de-219">È inoltre possibile impostare i valori **Margine** nella finestra **Proprietà,** nella categoria **Layout:**</span><span class="sxs-lookup"><span data-stu-id="5e8de-219">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Valori di margine nella finestra Proprietà](./media/properties-margin.png)

2. <span data-ttu-id="5e8de-221">Aggiungere il codice <xref:System.Windows.Controls.Grid> XAML seguente tra i tag per creare le definizioni di riga e colonna:</span><span class="sxs-lookup"><span data-stu-id="5e8de-221">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="5e8de-222">L'oggetto <xref:System.Windows.Controls.RowDefinition.Height%2A> di due <xref:System.Windows.GridLength.Auto%2A>righe è impostato su , il che significa che le righe vengono ridimensionate in base al contenuto delle righe.</span><span class="sxs-lookup"><span data-stu-id="5e8de-222">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="5e8de-223">L'impostazione predefinita <xref:System.Windows.Controls.RowDefinition.Height%2A> è <xref:System.Windows.GridUnitType.Star> il ridimensionamento, il che significa che l'altezza della riga è una proporzione ponderata dello spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="5e8de-223">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="5e8de-224">Ad esempio, se due <xref:System.Windows.Controls.RowDefinition.Height%2A> righe hanno ciascuna un dici, ognuna di esse ha un'altezza pari alla metà dello spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="5e8de-224">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="5e8de-225">Il <xref:System.Windows.Controls.Grid> codice XAML dovrebbe ora contenere il codice XAML seguente:Your should now contain the following XAML:</span><span class="sxs-lookup"><span data-stu-id="5e8de-225">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="5e8de-226">Aggiungere controlli</span><span class="sxs-lookup"><span data-stu-id="5e8de-226">Add controls</span></span>

<span data-ttu-id="5e8de-227">In questa sezione si aggiornerà l'interfaccia utente della home page per visualizzare un elenco di persone, in cui è possibile selezionare una persona per visualizzare la nota spese.</span><span class="sxs-lookup"><span data-stu-id="5e8de-227">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="5e8de-228">I controlli sono oggetti dell'interfaccia utente che consentono agli utenti di interagire con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-228">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="5e8de-229">Per altre informazioni, vedere [Controlli](../controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="5e8de-229">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="5e8de-230">Per creare questa interfaccia utente, si *`ExpenseItHome.xaml`* aggiungeranno i seguenti elementi a:</span><span class="sxs-lookup"><span data-stu-id="5e8de-230">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="5e8de-231">A <xref:System.Windows.Controls.ListBox> (per l'elenco delle persone).</span><span class="sxs-lookup"><span data-stu-id="5e8de-231">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="5e8de-232">A <xref:System.Windows.Controls.Label> (per l'intestazione dell'elenco).</span><span class="sxs-lookup"><span data-stu-id="5e8de-232">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="5e8de-233">A <xref:System.Windows.Controls.Button> (per visualizzare la nota spese per la persona selezionata nell'elenco).</span><span class="sxs-lookup"><span data-stu-id="5e8de-233">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="5e8de-234">Ogni controllo viene inserito <xref:System.Windows.Controls.Grid> in una <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> riga dell'oggetto impostando la proprietà associata.</span><span class="sxs-lookup"><span data-stu-id="5e8de-234">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="5e8de-235">Per ulteriori informazioni sulle proprietà associate, vedere [Cenni preliminari](../advanced/attached-properties-overview.md)sulle proprietà associate .</span><span class="sxs-lookup"><span data-stu-id="5e8de-235">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="5e8de-236">In *`ExpenseItHome.xaml`*, aggiungi il codice <xref:System.Windows.Controls.Grid> XAML seguente tra i tag:</span><span class="sxs-lookup"><span data-stu-id="5e8de-236">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="5e8de-237">È inoltre possibile creare i controlli trascinandoli dalla finestra **Casella degli strumenti** nella finestra di progettazione e impostandone le proprietà nella finestra **Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="5e8de-237">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="5e8de-238">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-238">Build and run the application.</span></span>

    <span data-ttu-id="5e8de-239">Nella figura seguente vengono illustrati i controlli creati:</span><span class="sxs-lookup"><span data-stu-id="5e8de-239">The following illustration shows the controls you created:</span></span>

![Schermata di esempio ExpenseIt che visualizza un elenco di nomi](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="5e8de-241">Aggiungere un'immagine e un titolo</span><span class="sxs-lookup"><span data-stu-id="5e8de-241">Add an image and a title</span></span>

<span data-ttu-id="5e8de-242">In questa sezione aggiornerai l'interfaccia utente della home page con un'immagine e un titolo di pagina.</span><span class="sxs-lookup"><span data-stu-id="5e8de-242">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="5e8de-243">In *`ExpenseItHome.xaml`*, aggiungere un'altra colonna al <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con un fisso <xref:System.Windows.Controls.ColumnDefinition.Width%2A> di 230 pixel:</span><span class="sxs-lookup"><span data-stu-id="5e8de-243">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewColumn)]

2. <span data-ttu-id="5e8de-244">Aggiungere un'altra <xref:System.Windows.Controls.Grid.RowDefinitions%2A>riga a , per un totale di quattro righe:</span><span class="sxs-lookup"><span data-stu-id="5e8de-244">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewRows)]

3. <span data-ttu-id="5e8de-245">Spostare i controlli nella seconda <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> colonna impostando la proprietà su 1 in ognuno dei tre controlli (Border, ListBox e Button).</span><span class="sxs-lookup"><span data-stu-id="5e8de-245">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="5e8de-246">Spostare ogni controllo verso il <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> basso di una riga incrementandone il valore di 1 per ognuno dei tre controlli (Border, ListBox e Button) e per l'elemento Border.</span><span class="sxs-lookup"><span data-stu-id="5e8de-246">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="5e8de-247">Il codice XAML per i tre controlli è ora simile al seguente:The XAML for the three controls now looks like the following:</span><span class="sxs-lookup"><span data-stu-id="5e8de-247">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="5e8de-248">Impostare <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> la proprietà sul file di immagine *watermark.png,* aggiungendo il codice XAML seguente in qualsiasi punto tra i `<Grid>` tag e `</Grid>` :</span><span class="sxs-lookup"><span data-stu-id="5e8de-248">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="5e8de-249">Prima <xref:System.Windows.Controls.Border> dell'elemento, <xref:System.Windows.Controls.Label> aggiungere a con il contenuto "Visualizza nota spese".</span><span class="sxs-lookup"><span data-stu-id="5e8de-249">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="5e8de-250">Questa etichetta è il titolo della pagina.</span><span class="sxs-lookup"><span data-stu-id="5e8de-250">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="5e8de-251">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-251">Build and run the application.</span></span>

<span data-ttu-id="5e8de-252">La figura seguente mostra i risultati di ciò che è stato appena aggiunto:</span><span class="sxs-lookup"><span data-stu-id="5e8de-252">The following illustration shows the results of what you just added:</span></span>

![Schermata di esempio ExpenseIt che mostra lo sfondo della nuova immagine e il titolo della pagina](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="5e8de-254">Aggiungere codice per gestire gli eventiAdd code to handle events</span><span class="sxs-lookup"><span data-stu-id="5e8de-254">Add code to handle events</span></span>

1. <span data-ttu-id="5e8de-255">In *`ExpenseItHome.xaml`*, <xref:System.Windows.Controls.Primitives.ButtonBase.Click> aggiungere un <xref:System.Windows.Controls.Button> gestore eventi all'elemento.</span><span class="sxs-lookup"><span data-stu-id="5e8de-255">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="5e8de-256">Per ulteriori informazioni, vedere [Procedura: creare un gestore eventi semplice.](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5e8de-256">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="5e8de-257">Aperto *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* o .</span><span class="sxs-lookup"><span data-stu-id="5e8de-257">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="5e8de-258">Aggiungere il codice `ExpenseItHome` seguente alla classe per aggiungere un gestore dell'evento Click del pulsante.</span><span class="sxs-lookup"><span data-stu-id="5e8de-258">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="5e8de-259">Il gestore eventi apre la pagina **ExpenseReportPage.**</span><span class="sxs-lookup"><span data-stu-id="5e8de-259">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="5e8de-260">Creare l'interfaccia utente per ExpenseReportPageCreate the UI for ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="5e8de-260">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="5e8de-261">*ExpenseReportPage.xaml* visualizza la nota spese per la **`ExpenseItHome`** persona selezionata nella pagina.</span><span class="sxs-lookup"><span data-stu-id="5e8de-261">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="5e8de-262">In questa sezione verrà creata l'interfaccia utente per **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="5e8de-262">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="5e8de-263">Potrai anche aggiungere colori di sfondo e riempimento ai vari elementi dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5e8de-263">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="5e8de-264">Aprire *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="5e8de-264">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="5e8de-265">Aggiungere il codice <xref:System.Windows.Controls.Grid> XAML seguente tra i tag:</span><span class="sxs-lookup"><span data-stu-id="5e8de-265">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="5e8de-266">Questa interfaccia utente *`ExpenseItHome.xaml`* è simile a , ad <xref:System.Windows.Controls.DataGrid>eccezione del fatto che i dati del report vengono visualizzati in un oggetto .</span><span class="sxs-lookup"><span data-stu-id="5e8de-266">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="5e8de-267">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-267">Build and run the application.</span></span>

4. <span data-ttu-id="5e8de-268">Selezionare il pulsante **Visualizza.**</span><span class="sxs-lookup"><span data-stu-id="5e8de-268">Select the **View** button.</span></span>

    <span data-ttu-id="5e8de-269">Viene visualizzata la pagina della nota spese.</span><span class="sxs-lookup"><span data-stu-id="5e8de-269">The expense report page appears.</span></span> <span data-ttu-id="5e8de-270">Si noti inoltre che il pulsante di spostamento indietro è abilitato.</span><span class="sxs-lookup"><span data-stu-id="5e8de-270">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="5e8de-271">Nella figura seguente vengono illustrati gli elementi dell'interfaccia utente aggiunti a *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="5e8de-271">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![ExpenseIt sample screenshot showing the UI just created for the ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="5e8de-273">Controlli di stile</span><span class="sxs-lookup"><span data-stu-id="5e8de-273">Style controls</span></span>

<span data-ttu-id="5e8de-274">L'aspetto di vari elementi è spesso lo stesso per tutti gli elementi dello stesso tipo in un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5e8de-274">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="5e8de-275">L'interfaccia utente usa [gli stili](../../../desktop-wpf/fundamentals/styles-templates-overview.md) per rendere gli aspetti riutilizzabili su più elementi.</span><span class="sxs-lookup"><span data-stu-id="5e8de-275">UI uses [styles](../../../desktop-wpf/fundamentals/styles-templates-overview.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="5e8de-276">La riusabilità degli stili consente di semplificare la creazione e la gestione di XAML.</span><span class="sxs-lookup"><span data-stu-id="5e8de-276">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="5e8de-277">In questa sezione vengono sostituiti con gli stili gli attributi per elemento definiti nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="5e8de-277">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="5e8de-278">Aprire *Application.xaml* o *App.xaml*.</span><span class="sxs-lookup"><span data-stu-id="5e8de-278">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="5e8de-279">Aggiungere il codice <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> XAML seguente tra i tag:</span><span class="sxs-lookup"><span data-stu-id="5e8de-279">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="5e8de-280">Questo codice XAML aggiunge gli stili seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e8de-280">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="5e8de-281">`headerTextStyle`: per formattare il titolo della pagina <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="5e8de-281">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="5e8de-282">`labelStyle`: per formattare i controlli <xref:System.Windows.Controls.Label> .</span><span class="sxs-lookup"><span data-stu-id="5e8de-282">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="5e8de-283">`columnHeaderStyle`: per formattare <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="5e8de-283">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="5e8de-284">`listHeaderStyle`: per formattare i controlli <xref:System.Windows.Controls.Border> dell'intestazione dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5e8de-284">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="5e8de-285">`listHeaderTextStyle`: per formattare <xref:System.Windows.Controls.Label>l'intestazione dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5e8de-285">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="5e8de-286">`buttonStyle`: per <xref:System.Windows.Controls.Button> formattare `ExpenseItHome.xaml`l'oggetto .</span><span class="sxs-lookup"><span data-stu-id="5e8de-286">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="5e8de-287">Si noti che gli stili <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> sono risorse e elementi figlio dell'elemento proprietà.</span><span class="sxs-lookup"><span data-stu-id="5e8de-287">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="5e8de-288">In questa posizione, gli stili vengono applicati a tutti gli elementi di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-288">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="5e8de-289">Per un esempio di utilizzo delle risorse in un'app .NET, vedere [Usare le risorse dell'applicazione.](../advanced/how-to-use-application-resources.md)</span><span class="sxs-lookup"><span data-stu-id="5e8de-289">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="5e8de-290">In *`ExpenseItHome.xaml`*, sostituisci <xref:System.Windows.Controls.Grid> tutti gli elementi tra gli elementi con il codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="5e8de-290">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="5e8de-291">Le proprietà come <xref:System.Windows.VerticalAlignment> e <xref:System.Windows.Media.FontFamily> che definiscono l'aspetto di ciascun controllo vengono rimosse e sostituite mediante l'applicazione degli stili.</span><span class="sxs-lookup"><span data-stu-id="5e8de-291">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="5e8de-292">Ad esempio, `headerTextStyle` l'oggetto viene applicato <xref:System.Windows.Controls.Label>alla cartella "Visualizza nota spese".</span><span class="sxs-lookup"><span data-stu-id="5e8de-292">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="5e8de-293">Aprire *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="5e8de-293">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="5e8de-294">Sostituisci tutti <xref:System.Windows.Controls.Grid> gli elementi tra gli elementi con il codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="5e8de-294">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="5e8de-295">Questo codice XAML <xref:System.Windows.Controls.Label> aggiunge <xref:System.Windows.Controls.Border> stili agli elementi e .</span><span class="sxs-lookup"><span data-stu-id="5e8de-295">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="5e8de-296">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-296">Build and run the application.</span></span> <span data-ttu-id="5e8de-297">L'aspetto della finestra è lo stesso di prima.</span><span class="sxs-lookup"><span data-stu-id="5e8de-297">The window appearance is the same as previously.</span></span>

    ![Schermata di esempio ExpenseIt con lo stesso aspetto dell'ultima sezione.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="5e8de-299">Chiudere l'applicazione per tornare a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5e8de-299">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="5e8de-300">Associare dati a un controlloBind data to a control</span><span class="sxs-lookup"><span data-stu-id="5e8de-300">Bind data to a control</span></span>

<span data-ttu-id="5e8de-301">In questa sezione verranno creati i dati XML associati a vari controlli.</span><span class="sxs-lookup"><span data-stu-id="5e8de-301">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="5e8de-302">In *`ExpenseItHome.xaml`*, dopo <xref:System.Windows.Controls.Grid> l'elemento di apertura, <xref:System.Windows.Data.XmlDataProvider> aggiungere il codice XAML seguente per creare un oggetto che contiene i dati per ogni persona:</span><span class="sxs-lookup"><span data-stu-id="5e8de-302">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="5e8de-303">I dati vengono <xref:System.Windows.Controls.Grid> creati come risorsa.</span><span class="sxs-lookup"><span data-stu-id="5e8de-303">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="5e8de-304">Normalmente questi dati verrebbero caricati come file, ma per semplicità i dati vengono aggiunti inline.</span><span class="sxs-lookup"><span data-stu-id="5e8de-304">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="5e8de-305">All'interno `<Grid.Resources>` dell'elemento, aggiungere il `<xref:System.Windows.DataTemplate>` seguente elemento, che <xref:System.Windows.Controls.ListBox>definisce `<XmlDataProvider>` come visualizzare i dati in , dopo l'elemento:</span><span class="sxs-lookup"><span data-stu-id="5e8de-305">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="5e8de-306">Per ulteriori informazioni sui modelli di dati, vedere [Panoramica](../data/data-templating-overview.md)dei modelli di dati .</span><span class="sxs-lookup"><span data-stu-id="5e8de-306">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="5e8de-307">Sostituire l'esistente <xref:System.Windows.Controls.ListBox> con il codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="5e8de-307">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="5e8de-308">Questo codice XAML <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> associa <xref:System.Windows.Controls.ListBox> la proprietà dell'oggetto all'origine <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>dati e applica il modello di dati come metodo .</span><span class="sxs-lookup"><span data-stu-id="5e8de-308">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="5e8de-309">Connettere i dati ai controlli</span><span class="sxs-lookup"><span data-stu-id="5e8de-309">Connect data to controls</span></span>

<span data-ttu-id="5e8de-310">Successivamente, si aggiungerà il codice per recuperare il **`ExpenseItHome`** nome selezionato nella pagina e passarlo al costruttore di **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="5e8de-310">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="5e8de-311">**ExpenseReportPage** imposta il contesto dati con l'elemento passato, ovvero a cosa si associano i controlli definiti in *ExpenseReportPage.xaml.*</span><span class="sxs-lookup"><span data-stu-id="5e8de-311">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="5e8de-312">Aprire *ExpenseReportPage.xaml.vb* o *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="5e8de-312">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="5e8de-313">Aggiungere un costruttore che accetti un oggetto, in modo da poter passare i dati della nota spese della persona selezionata.</span><span class="sxs-lookup"><span data-stu-id="5e8de-313">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="5e8de-314">Aperto *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* o .</span><span class="sxs-lookup"><span data-stu-id="5e8de-314">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="5e8de-315">Modificare <xref:System.Windows.Controls.Primitives.ButtonBase.Click> il gestore eventi per chiamare il nuovo costruttore passando i dati della nota spese della persona selezionata.</span><span class="sxs-lookup"><span data-stu-id="5e8de-315">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="5e8de-316">Applicare stili ai dati con i modelli di dati</span><span class="sxs-lookup"><span data-stu-id="5e8de-316">Style data with data templates</span></span>

<span data-ttu-id="5e8de-317">In questa sezione si aggiornerà l'interfaccia utente per ogni elemento negli elenchi con associazione a dati usando i modelli di dati.</span><span class="sxs-lookup"><span data-stu-id="5e8de-317">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="5e8de-318">Aprire *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="5e8de-318">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="5e8de-319">Associare il contenuto degli elementi "Name" e "Department" <xref:System.Windows.Controls.Label> alla proprietà dell'origine dati appropriata.</span><span class="sxs-lookup"><span data-stu-id="5e8de-319">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="5e8de-320">Per ulteriori informazioni sull'associazione dati, vedere [Panoramica dell'associazione dati](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5e8de-320">For more information about data binding, see [Data binding overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="5e8de-321">Dopo l'elemento di apertura, <xref:System.Windows.Controls.Grid> aggiungere i modelli di dati seguenti, che definiscono come visualizzare i dati della nota spese:</span><span class="sxs-lookup"><span data-stu-id="5e8de-321">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="5e8de-322">Sostituire <xref:System.Windows.Controls.DataGridTextColumn> gli <xref:System.Windows.Controls.DataGridTemplateColumn> elementi <xref:System.Windows.Controls.DataGrid> con sotto l'elemento e applicarvi i modelli.</span><span class="sxs-lookup"><span data-stu-id="5e8de-322">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="5e8de-323">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e8de-323">Build and run the application.</span></span>

6. <span data-ttu-id="5e8de-324">Selezionare una persona, quindi fare clic sul pulsante **Visualizza.**</span><span class="sxs-lookup"><span data-stu-id="5e8de-324">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="5e8de-325">Nella figura seguente vengono `ExpenseIt` illustrate entrambe le pagine dell'applicazione con controlli, layout, stili, associazione dati e modelli di dati applicati:</span><span class="sxs-lookup"><span data-stu-id="5e8de-325">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Entrambe le pagine dell'app che mostrano l'elenco dei nomi e una nota spese.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="5e8de-327">In questo esempio viene illustrata una funzionalità specifica di WPFWPF e non vengono illustrate tutte le procedure consigliate per elementi quali sicurezza, localizzazione e accessibilità.</span><span class="sxs-lookup"><span data-stu-id="5e8de-327">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="5e8de-328">Per una copertura completa delle procedure consigliate per lo sviluppo di app .NET e WPF e .NET, vedere gli argomenti seguenti:For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span><span class="sxs-lookup"><span data-stu-id="5e8de-328">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="5e8de-329">Accessibilità</span><span class="sxs-lookup"><span data-stu-id="5e8de-329">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
> - [<span data-ttu-id="5e8de-330">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5e8de-330">Security</span></span>](../security-wpf.md)
> - [<span data-ttu-id="5e8de-331">Globalizzazione e localizzazione WPF</span><span class="sxs-lookup"><span data-stu-id="5e8de-331">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
> - [<span data-ttu-id="5e8de-332">Prestazioni WPFWPF performance</span><span class="sxs-lookup"><span data-stu-id="5e8de-332">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="5e8de-333">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5e8de-333">Next steps</span></span>

<span data-ttu-id="5e8de-334">In questa procedura dettagliata sono state illustrate diverse tecniche per la creazione di un'interfaccia utente tramite Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="5e8de-334">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="5e8de-335">A questo punto dovresti avere una conoscenza di base dei blocchi predefiniti di un'app .NET con associazione a dati.</span><span class="sxs-lookup"><span data-stu-id="5e8de-335">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="5e8de-336">Per altre informazioni sull'architettura WPF e i modelli di programmazione, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e8de-336">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="5e8de-337">Architettura WPFWPF architecture</span><span class="sxs-lookup"><span data-stu-id="5e8de-337">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="5e8de-338">Panoramica di XAML (WPF)XAML overview (WPF)</span><span class="sxs-lookup"><span data-stu-id="5e8de-338">XAML overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="5e8de-339">Panoramica delle proprietà di dipendenzaDependency properties overview</span><span class="sxs-lookup"><span data-stu-id="5e8de-339">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="5e8de-340">Layout</span><span class="sxs-lookup"><span data-stu-id="5e8de-340">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="5e8de-341">Per altre informazioni sulla creazione di applicazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e8de-341">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="5e8de-342">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="5e8de-342">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="5e8de-343">Controlli</span><span class="sxs-lookup"><span data-stu-id="5e8de-343">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="5e8de-344">Panoramica del data binding</span><span class="sxs-lookup"><span data-stu-id="5e8de-344">Data binding overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="5e8de-345">Grafica e multimedia</span><span class="sxs-lookup"><span data-stu-id="5e8de-345">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="5e8de-346">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="5e8de-346">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="5e8de-347">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e8de-347">See also</span></span>

- [<span data-ttu-id="5e8de-348">Panoramica dei pannelli</span><span class="sxs-lookup"><span data-stu-id="5e8de-348">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="5e8de-349">Panoramica dei modelli di datiData templating overview</span><span class="sxs-lookup"><span data-stu-id="5e8de-349">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="5e8de-350">Compilare un'applicazione WPFBuild a WPF application</span><span class="sxs-lookup"><span data-stu-id="5e8de-350">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="5e8de-351">Stili e modelli</span><span class="sxs-lookup"><span data-stu-id="5e8de-351">Styles and templates</span></span>](../controls/styles-and-templates.md)
