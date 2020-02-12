---
title: Creare la prima app WPF in Visual Studio 2019-.NET Framework
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
ms.openlocfilehash: bc47405636c4727f502caf1f6e27050367eda74a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124338"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a><span data-ttu-id="a7678-102">Esercitazione: creare la prima applicazione WPF in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="a7678-102">Tutorial: Create your first WPF application in Visual Studio 2019</span></span>

<span data-ttu-id="a7678-103">Questo articolo illustra come sviluppare un'applicazione desktop Windows Presentation Foundation (WPF) che include gli elementi comuni alla maggior parte delle applicazioni WPF: markup Extensible Application Markup Language (XAML), code-behind, definizioni delle applicazioni, controlli, layout, data binding e stili.</span><span class="sxs-lookup"><span data-stu-id="a7678-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="a7678-104">Per sviluppare l'applicazione, si userà Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a7678-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="a7678-105">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="a7678-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="a7678-106">Creare un progetto WPF.</span><span class="sxs-lookup"><span data-stu-id="a7678-106">Create a WPF project.</span></span>
> - <span data-ttu-id="a7678-107">Utilizzare XAML per progettare l'aspetto dell'interfaccia utente (UI) dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-107">Use XAML to design the appearance of the application's user interface (UI).</span></span>
> - <span data-ttu-id="a7678-108">Scrivere il codice per compilare il comportamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-108">Write code to build the application's behavior.</span></span>
> - <span data-ttu-id="a7678-109">Creare una definizione di applicazione per gestire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-109">Create an application definition to manage the application.</span></span>
> - <span data-ttu-id="a7678-110">Aggiungere i controlli e creare il layout per comporre l'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-110">Add controls and create the layout to compose the application UI.</span></span>
> - <span data-ttu-id="a7678-111">Creare stili per un aspetto coerente nell'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-111">Create styles for a consistent appearance throughout the application's UI.</span></span>
> - <span data-ttu-id="a7678-112">Associare l'interfaccia utente ai dati, sia per popolare l'interfaccia utente dai dati, sia per sincronizzare i dati e l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="a7678-112">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="a7678-113">Al termine dell'esercitazione, verrà creata un'applicazione Windows autonoma che consente agli utenti di visualizzare i report delle spese per le persone selezionate.</span><span class="sxs-lookup"><span data-stu-id="a7678-113">By the end of the tutorial, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="a7678-114">L'applicazione è costituita da diverse pagine WPF ospitate in una finestra di tipo browser.</span><span class="sxs-lookup"><span data-stu-id="a7678-114">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="a7678-115">Il codice di esempio usato in questa esercitazione è disponibile sia per Visual Basic che per C# il [codice di esempio dell'app WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="a7678-115">The sample code that is used in this tutorial is available for both Visual Basic and C# at [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="a7678-116">È possibile abilitare o disabilitare il linguaggio del codice di esempio tra C# e Visual Basic usando il selettore della lingua nella parte superiore di questa pagina.</span><span class="sxs-lookup"><span data-stu-id="a7678-116">You can toggle the code language of the sample code between C# and Visual Basic by using the language selector on top of this page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a7678-117">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="a7678-117">Prerequisites</span></span>

- <span data-ttu-id="a7678-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro sviluppo di applicazioni **desktop .NET** installato.</span><span class="sxs-lookup"><span data-stu-id="a7678-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET desktop development** workload installed.</span></span>

   <span data-ttu-id="a7678-119">Per ulteriori informazioni sull'installazione della versione più recente di Visual Studio, vedere [Install Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="a7678-119">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="a7678-120">Creare il progetto dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="a7678-120">Create the application project</span></span>

<span data-ttu-id="a7678-121">Il primo passaggio consiste nel creare l'infrastruttura dell'applicazione, che include una definizione dell'applicazione, due pagine e un'immagine.</span><span class="sxs-lookup"><span data-stu-id="a7678-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="a7678-122">Creare un nuovo progetto di applicazione WPF in Visual Basic o C# in un oggetto visivo denominato **`ExpenseIt`** :</span><span class="sxs-lookup"><span data-stu-id="a7678-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="a7678-123">Aprire Visual Studio e selezionare **Crea un nuovo progetto** **nel menu inizia** .</span><span class="sxs-lookup"><span data-stu-id="a7678-123">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="a7678-124">Verrà visualizzata la finestra **di dialogo Crea un nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="a7678-124">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="a7678-125">Nell'elenco a discesa **lingua** selezionare **C#** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="a7678-125">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>
      
   3. <span data-ttu-id="a7678-126">Selezionare il modello **applicazione WPF (.NET Framework)** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a7678-126">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
     
      ![Finestra di dialogo Crea nuovo progetto](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)
    
      <span data-ttu-id="a7678-128">Verrà visualizzata la finestra di dialogo **Configura nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="a7678-128">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="a7678-129">Immettere il nome del progetto **`ExpenseIt`** e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="a7678-129">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![Finestra di dialogo Configura nuovo progetto](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="a7678-131">Visual Studio crea il progetto e apre la finestra di progettazione per la finestra dell'applicazione predefinita denominata **MainWindow. XAML**.</span><span class="sxs-lookup"><span data-stu-id="a7678-131">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="a7678-132">Aprire *Application. XAML* (Visual Basic) o *app. XAML* (C#).</span><span class="sxs-lookup"><span data-stu-id="a7678-132">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="a7678-133">Questo file XAML definisce un'applicazione WPF e tutte le risorse dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-133">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="a7678-134">Questo file viene usato anche per specificare l'interfaccia utente, in questo caso *MainWindow. XAML*, che mostra automaticamente all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-134">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="a7678-135">Il codice XAML dovrebbe essere simile al seguente in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="a7678-135">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="a7678-136">E come negli argomenti seguenti C#:</span><span class="sxs-lookup"><span data-stu-id="a7678-136">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="a7678-137">Aprire *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="a7678-137">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="a7678-138">Questo file XAML è la finestra principale dell'applicazione e visualizza il contenuto creato in pagine.</span><span class="sxs-lookup"><span data-stu-id="a7678-138">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="a7678-139">La classe <xref:System.Windows.Window> definisce le proprietà di una finestra, ad esempio il titolo, le dimensioni o l'icona, e gestisce gli eventi, ad esempio la chiusura o il nascondiglio.</span><span class="sxs-lookup"><span data-stu-id="a7678-139">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="a7678-140">Modificare l'elemento <xref:System.Windows.Window> in un <xref:System.Windows.Navigation.NavigationWindow>, come illustrato nel codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="a7678-140">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="a7678-141">Questa app passa a un contenuto diverso a seconda dell'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a7678-141">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="a7678-142">Questo è il motivo per cui è necessario modificare il <xref:System.Windows.Window> principale in una <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="a7678-142">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="a7678-143"><xref:System.Windows.Navigation.NavigationWindow> eredita tutte le proprietà di <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="a7678-143"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="a7678-144">L'elemento <xref:System.Windows.Navigation.NavigationWindow> nel file XAML crea un'istanza della classe <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="a7678-144">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="a7678-145">Per altre informazioni, vedere [Cenni preliminari sulla navigazione](../app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a7678-145">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="a7678-146">Rimuovere gli elementi <xref:System.Windows.Controls.Grid> da tra i tag di <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="a7678-146">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="a7678-147">Modificare le proprietà seguenti nel codice XAML per l'elemento <xref:System.Windows.Navigation.NavigationWindow>:</span><span class="sxs-lookup"><span data-stu-id="a7678-147">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="a7678-148">Impostare la proprietà <xref:System.Windows.Window.Title%2A> su "`ExpenseIt`".</span><span class="sxs-lookup"><span data-stu-id="a7678-148">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="a7678-149">Impostare la proprietà <xref:System.Windows.FrameworkElement.Height%2A> su 350 pixel.</span><span class="sxs-lookup"><span data-stu-id="a7678-149">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="a7678-150">Impostare la proprietà <xref:System.Windows.FrameworkElement.Width%2A> su 500 pixel.</span><span class="sxs-lookup"><span data-stu-id="a7678-150">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="a7678-151">Il codice XAML dovrebbe essere simile al seguente per Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="a7678-151">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="a7678-152">E come negli elementi seguenti C#:</span><span class="sxs-lookup"><span data-stu-id="a7678-152">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="a7678-153">Aprire *MainWindow. XAML. vb* o *MainWindow.XAML.cs*.</span><span class="sxs-lookup"><span data-stu-id="a7678-153">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="a7678-154">Questo file è un file code-behind che contiene il codice per gestire gli eventi dichiarati in *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="a7678-154">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="a7678-155">Il file contiene una classe parziale per la finestra definita in XAML.</span><span class="sxs-lookup"><span data-stu-id="a7678-155">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="a7678-156">Se si usa C#, modificare la classe `MainWindow` per derivare da <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="a7678-156">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="a7678-157">(In Visual Basic, questa operazione viene eseguita automaticamente quando si modifica la finestra in XAML.) Il C# codice dovrebbe ora essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a7678-157">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="a7678-158">Aggiunta di file all'applicazione</span><span class="sxs-lookup"><span data-stu-id="a7678-158">Add files to the application</span></span>

<span data-ttu-id="a7678-159">In questa sezione si aggiungeranno due pagine e un'immagine all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="a7678-160">Aggiungere una nuova pagina al progetto e denominarla *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="a7678-160">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="a7678-161">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nodo **`ExpenseIt`** progetto e scegliere **Aggiungi** > **pagina**.</span><span class="sxs-lookup"><span data-stu-id="a7678-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="a7678-162">Nella finestra di dialogo **Aggiungi nuovo elemento** , il modello **pagina (WPF)** è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="a7678-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="a7678-163">Immettere il nome **`ExpenseItHome`** , quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a7678-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="a7678-164">Questa pagina è la prima pagina visualizzata all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="a7678-165">Verrà visualizzato un elenco di utenti da selezionare per visualizzare una nota spese per.</span><span class="sxs-lookup"><span data-stu-id="a7678-165">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="a7678-166">Aprire *`ExpenseItHome.xaml`* .</span><span class="sxs-lookup"><span data-stu-id="a7678-166">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="a7678-167">Impostare il <xref:System.Windows.Controls.Page.Title%2A> su "`ExpenseIt - Home`".</span><span class="sxs-lookup"><span data-stu-id="a7678-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="a7678-168">Impostare il `DesignHeight` su 350 pixel e il `DesignWidth` su 500 pixel.</span><span class="sxs-lookup"><span data-stu-id="a7678-168">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="a7678-169">Il codice XAML ora viene visualizzato come segue per Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="a7678-169">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="a7678-170">E come negli elementi seguenti C#:</span><span class="sxs-lookup"><span data-stu-id="a7678-170">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="a7678-171">Aprire *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="a7678-171">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="a7678-172">Aggiungere una proprietà <xref:System.Windows.Navigation.NavigationWindow.Source%2A> all'elemento <xref:System.Windows.Navigation.NavigationWindow> e impostarla su "`ExpenseItHome.xaml`".</span><span class="sxs-lookup"><span data-stu-id="a7678-172">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="a7678-173">Consente di impostare *`ExpenseItHome.xaml`* come prima pagina aperta all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-173">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="a7678-174">XAML di esempio in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="a7678-174">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="a7678-175">E nel linguaggio c#:</span><span class="sxs-lookup"><span data-stu-id="a7678-175">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="a7678-176">È anche possibile impostare la proprietà **source** nella categoria **varie** della finestra **proprietà** .</span><span class="sxs-lookup"><span data-stu-id="a7678-176">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Proprietà di origine in Finestra Proprietà](./media/properties-source.png)

1. <span data-ttu-id="a7678-178">Aggiungere un'altra nuova pagina WPF al progetto e denominarla *ExpenseReportPage. XAML*::</span><span class="sxs-lookup"><span data-stu-id="a7678-178">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="a7678-179">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nodo **`ExpenseIt`** progetto e scegliere **Aggiungi** > **pagina**.</span><span class="sxs-lookup"><span data-stu-id="a7678-179">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="a7678-180">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare il modello **pagina (WPF)** .</span><span class="sxs-lookup"><span data-stu-id="a7678-180">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="a7678-181">Immettere il nome **ExpenseReportPage**e quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a7678-181">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="a7678-182">Questa pagina visualizzerà la nota spese per la persona selezionata nella pagina **`ExpenseItHome`** .</span><span class="sxs-lookup"><span data-stu-id="a7678-182">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="a7678-183">Aprire *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="a7678-183">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="a7678-184">Impostare il <xref:System.Windows.Controls.Page.Title%2A> su "`ExpenseIt - View Expense`".</span><span class="sxs-lookup"><span data-stu-id="a7678-184">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="a7678-185">Impostare il `DesignHeight` su 350 pixel e il `DesignWidth` su 500 pixel.</span><span class="sxs-lookup"><span data-stu-id="a7678-185">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span> 

    <span data-ttu-id="a7678-186">*ExpenseReportPage. XAML* ha ora un aspetto simile al seguente in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="a7678-186">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="a7678-187">E come negli argomenti seguenti C#:</span><span class="sxs-lookup"><span data-stu-id="a7678-187">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="a7678-188">Aprire *ExpenseItHome. XAML. vb* e *ExpenseReportPage. XAML. vb*o *ExpenseItHome.XAML.cs* e *ExpenseReportPage.XAML.cs*.</span><span class="sxs-lookup"><span data-stu-id="a7678-188">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="a7678-189">Quando si crea un nuovo file di paging, Visual Studio crea automaticamente il file *code-behind* .</span><span class="sxs-lookup"><span data-stu-id="a7678-189">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="a7678-190">Questi file code-behind gestiscono la logica per rispondere all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a7678-190">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="a7678-191">Il codice dovrebbe essere simile al seguente per **`ExpenseItHome`** :</span><span class="sxs-lookup"><span data-stu-id="a7678-191">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="a7678-192">Come indicato di seguito per **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="a7678-192">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="a7678-193">Aggiungere un'immagine denominata *Watermark. png* al progetto.</span><span class="sxs-lookup"><span data-stu-id="a7678-193">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="a7678-194">È possibile creare un'immagine personalizzata, copiare il file dal codice di esempio o ottenerlo dal repository GitHub [Microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) .</span><span class="sxs-lookup"><span data-stu-id="a7678-194">You can create your own image, copy the file from the sample code, or get it from the [microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub repository.</span></span>

    1. <span data-ttu-id="a7678-195">Fare clic con il pulsante destro del mouse sul nodo del progetto e scegliere **aggiungi** > **elemento esistente**oppure premere **MAIUSC**+**ALT**+**A**.</span><span class="sxs-lookup"><span data-stu-id="a7678-195">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="a7678-196">Nella finestra di dialogo **Aggiungi elemento esistente** impostare filtro file su **tutti** i file o **file di immagine**, passare al file di immagine che si vuole usare e quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a7678-196">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="a7678-197">Compilare ed eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="a7678-197">Build and run the application</span></span>

1. <span data-ttu-id="a7678-198">Per compilare ed eseguire l'applicazione, premere **F5** o scegliere **Avvia debug** dal menu **debug** .</span><span class="sxs-lookup"><span data-stu-id="a7678-198">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="a7678-199">Nell'illustrazione seguente viene mostrata l'applicazione con i pulsanti <xref:System.Windows.Navigation.NavigationWindow>:</span><span class="sxs-lookup"><span data-stu-id="a7678-199">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![Applicazione dopo la compilazione e l'esecuzione.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="a7678-201">Chiudere l'applicazione per tornare a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a7678-201">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="a7678-202">Creare il layout</span><span class="sxs-lookup"><span data-stu-id="a7678-202">Create the layout</span></span>

<span data-ttu-id="a7678-203">Il layout fornisce un modo ordinato per inserire gli elementi dell'interfaccia utente e gestisce anche le dimensioni e la posizione di tali elementi quando viene ridimensionata un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="a7678-203">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="a7678-204">In genere si crea un layout tramite uno dei controlli di layout seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7678-204">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="a7678-205"><xref:System.Windows.Controls.Canvas>: definisce un'area all'interno della quale è possibile posizionare in modo esplicito gli elementi figlio usando le coordinate relative all'area Canvas.</span><span class="sxs-lookup"><span data-stu-id="a7678-205"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="a7678-206"><xref:System.Windows.Controls.DockPanel>: definisce un'area in cui è possibile disporre gli elementi figlio in senso orizzontale o verticale, in relazione l'uno all'altro.</span><span class="sxs-lookup"><span data-stu-id="a7678-206"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="a7678-207"><xref:System.Windows.Controls.Grid>: definisce un'area griglia flessibile costituita da righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="a7678-207"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="a7678-208"><xref:System.Windows.Controls.StackPanel>: dispone gli elementi figlio in una sola riga che può essere orientata orizzontalmente o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="a7678-208"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="a7678-209"><xref:System.Windows.Controls.VirtualizingStackPanel>: dispone e virtualizza il contenuto su una sola riga orientata orizzontalmente o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="a7678-209"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="a7678-210"><xref:System.Windows.Controls.WrapPanel> posiziona gli elementi figlio in sequenza da sinistra a destra, suddividendo il contenuto nella riga successiva al bordo della casella contenitore.</span><span class="sxs-lookup"><span data-stu-id="a7678-210"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="a7678-211">L'ordinamento successivo avviene in sequenza dall'alto verso il basso o da destra a sinistra, a seconda del valore della proprietà Orientation.</span><span class="sxs-lookup"><span data-stu-id="a7678-211">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="a7678-212">Ognuno di questi controlli di layout supporta un particolare tipo di layout per i relativi elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="a7678-212">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="a7678-213">`ExpenseIt` le pagine possono essere ridimensionate e ogni pagina contiene elementi disposti orizzontalmente e verticalmente insieme ad altri elementi.</span><span class="sxs-lookup"><span data-stu-id="a7678-213">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="a7678-214">In questo esempio, il <xref:System.Windows.Controls.Grid> viene utilizzato come elemento layout per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-214">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="a7678-215">Per ulteriori informazioni sugli elementi di <xref:System.Windows.Controls.Panel>, vedere [Cenni preliminari sui pannelli](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a7678-215">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="a7678-216">Per ulteriori informazioni sul layout, vedere [layout](../advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="a7678-216">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="a7678-217">In questa sezione viene creata una tabella a colonna singola con tre righe e un margine di 10 pixel aggiungendo definizioni di colonna e di riga al <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`* .</span><span class="sxs-lookup"><span data-stu-id="a7678-217">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="a7678-218">In *`ExpenseItHome.xaml`* impostare la proprietà <xref:System.Windows.FrameworkElement.Margin%2A> sull'elemento <xref:System.Windows.Controls.Grid> su "10, 0, 10, 10", che corrisponde ai margini sinistro, superiore, destro e inferiore:</span><span class="sxs-lookup"><span data-stu-id="a7678-218">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="a7678-219">È inoltre possibile impostare i valori dei **margini** nella finestra **Proprietà** , sotto la categoria **layout** :</span><span class="sxs-lookup"><span data-stu-id="a7678-219">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Valori dei margini in Finestra Proprietà](./media/properties-margin.png)

2. <span data-ttu-id="a7678-221">Aggiungere il codice XAML seguente tra i tag <xref:System.Windows.Controls.Grid> per creare le definizioni di riga e di colonna:</span><span class="sxs-lookup"><span data-stu-id="a7678-221">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="a7678-222">Il <xref:System.Windows.Controls.RowDefinition.Height%2A> di due righe è impostato su <xref:System.Windows.GridLength.Auto%2A>, il che significa che le righe vengono ridimensionate in base al contenuto delle righe.</span><span class="sxs-lookup"><span data-stu-id="a7678-222">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="a7678-223">Il <xref:System.Windows.Controls.RowDefinition.Height%2A> predefinito è <xref:System.Windows.GridUnitType.Star> il ridimensionamento, il che significa che l'altezza della riga è una proporzione ponderata dello spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="a7678-223">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="a7678-224">Se, ad esempio, due righe hanno una <xref:System.Windows.Controls.RowDefinition.Height%2A> di "\*", ognuna ha un'altezza pari alla metà dello spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="a7678-224">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="a7678-225">Il <xref:System.Windows.Controls.Grid> dovrebbe ora contenere il codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="a7678-225">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="a7678-226">Aggiungi controlli</span><span class="sxs-lookup"><span data-stu-id="a7678-226">Add controls</span></span>

<span data-ttu-id="a7678-227">In questa sezione verrà aggiornata l'interfaccia utente di home page per visualizzare un elenco di persone, in cui è possibile selezionare una persona per visualizzare la nota spese.</span><span class="sxs-lookup"><span data-stu-id="a7678-227">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="a7678-228">I controlli sono oggetti dell'interfaccia utente che consentono agli utenti di interagire con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-228">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="a7678-229">Per altre informazioni, vedere [Controlli](../controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="a7678-229">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="a7678-230">Per creare questa interfaccia utente, aggiungere gli elementi seguenti a *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="a7678-230">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="a7678-231"><xref:System.Windows.Controls.ListBox> (per l'elenco di persone).</span><span class="sxs-lookup"><span data-stu-id="a7678-231">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="a7678-232"><xref:System.Windows.Controls.Label> (per l'intestazione dell'elenco).</span><span class="sxs-lookup"><span data-stu-id="a7678-232">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="a7678-233">Un <xref:System.Windows.Controls.Button> (per fare clic per visualizzare la nota spese per la persona selezionata nell'elenco).</span><span class="sxs-lookup"><span data-stu-id="a7678-233">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="a7678-234">Ogni controllo viene inserito in una riga del <xref:System.Windows.Controls.Grid> impostando la proprietà <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> associata.</span><span class="sxs-lookup"><span data-stu-id="a7678-234">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="a7678-235">Per ulteriori informazioni sulle proprietà associate, vedere [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a7678-235">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="a7678-236">In *`ExpenseItHome.xaml`* aggiungere il codice XAML seguente tra i tag <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="a7678-236">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="a7678-237">È anche possibile creare i controlli trascinandoli dalla finestra **casella degli strumenti** nella finestra di progettazione e quindi impostarne le proprietà nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="a7678-237">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="a7678-238">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-238">Build and run the application.</span></span>

    <span data-ttu-id="a7678-239">Nella figura seguente sono illustrati i controlli creati:</span><span class="sxs-lookup"><span data-stu-id="a7678-239">The following illustration shows the controls you created:</span></span>

![Schermata di esempio ExpenseIt che visualizza un elenco di nomi](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="a7678-241">Aggiungere un'immagine e un titolo</span><span class="sxs-lookup"><span data-stu-id="a7678-241">Add an image and a title</span></span>

<span data-ttu-id="a7678-242">In questa sezione si aggiornerà l'interfaccia utente di home page con un'immagine e un titolo della pagina.</span><span class="sxs-lookup"><span data-stu-id="a7678-242">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="a7678-243">In *`ExpenseItHome.xaml`* aggiungere un'altra colonna al <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con un <xref:System.Windows.Controls.ColumnDefinition.Width%2A> fisso di 230 pixel:</span><span class="sxs-lookup"><span data-stu-id="a7678-243">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="a7678-244">Aggiungere un'altra riga al <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, per un totale di quattro righe:</span><span class="sxs-lookup"><span data-stu-id="a7678-244">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="a7678-245">Spostare i controlli nella seconda colonna impostando la proprietà <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> su 1 in ognuno dei tre controlli (bordo, casella di riepilogo e pulsante).</span><span class="sxs-lookup"><span data-stu-id="a7678-245">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="a7678-246">Spostare ogni controllo verso il basso di una riga incrementando il valore di <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> di 1 per ognuno dei tre controlli (bordo, casella di riepilogo e pulsante) e per l'elemento Border.</span><span class="sxs-lookup"><span data-stu-id="a7678-246">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="a7678-247">Il codice XAML per i tre controlli ha ora un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a7678-247">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="a7678-248">Impostare la proprietà <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> sul file di immagine *Watermark. png* aggiungendo il codice XAML seguente in qualsiasi punto tra i tag `<Grid>` e `</Grid>`:</span><span class="sxs-lookup"><span data-stu-id="a7678-248">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="a7678-249">Prima dell'elemento <xref:System.Windows.Controls.Border>, aggiungere una <xref:System.Windows.Controls.Label> con il contenuto "View Expense Report".</span><span class="sxs-lookup"><span data-stu-id="a7678-249">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="a7678-250">Questa etichetta è il titolo della pagina.</span><span class="sxs-lookup"><span data-stu-id="a7678-250">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="a7678-251">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-251">Build and run the application.</span></span>

<span data-ttu-id="a7678-252">La figura seguente mostra i risultati di quanto appena aggiunto:</span><span class="sxs-lookup"><span data-stu-id="a7678-252">The following illustration shows the results of what you just added:</span></span>

![Schermata di esempio di ExpenseIt che mostra la nuova immagine di sfondo e titolo della pagina](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="a7678-254">Aggiungere codice per gestire gli eventi</span><span class="sxs-lookup"><span data-stu-id="a7678-254">Add code to handle events</span></span>

1. <span data-ttu-id="a7678-255">In *`ExpenseItHome.xaml`* aggiungere un gestore eventi <xref:System.Windows.Controls.Primitives.ButtonBase.Click> all'elemento <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="a7678-255">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="a7678-256">Per altre informazioni, vedere [procedura: creare un gestore eventi semplice](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a7678-256">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="a7678-257">Aprire *`ExpenseItHome.xaml.vb`* o *`ExpenseItHome.xaml.cs`* .</span><span class="sxs-lookup"><span data-stu-id="a7678-257">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="a7678-258">Aggiungere il codice seguente alla classe `ExpenseItHome` per aggiungere un gestore dell'evento click del pulsante.</span><span class="sxs-lookup"><span data-stu-id="a7678-258">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="a7678-259">Il gestore eventi apre la pagina **ExpenseReportPage** .</span><span class="sxs-lookup"><span data-stu-id="a7678-259">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="a7678-260">Creare l'interfaccia utente per ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="a7678-260">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="a7678-261">*ExpenseReportPage. XAML* Visualizza la nota spese per la persona selezionata nella pagina **`ExpenseItHome`** .</span><span class="sxs-lookup"><span data-stu-id="a7678-261">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="a7678-262">In questa sezione verrà creata l'interfaccia utente per **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="a7678-262">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="a7678-263">Verranno inoltre aggiunti i colori di sfondo e riempimento ai vari elementi dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="a7678-263">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="a7678-264">Aprire *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="a7678-264">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="a7678-265">Aggiungere il codice XAML seguente tra i tag <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="a7678-265">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="a7678-266">Questa interfaccia utente è simile a *`ExpenseItHome.xaml`* , ad eccezione del fatto che i dati del report vengono visualizzati in una <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="a7678-266">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="a7678-267">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-267">Build and run the application.</span></span>

4. <span data-ttu-id="a7678-268">Selezionare il pulsante **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="a7678-268">Select the **View** button.</span></span>

    <span data-ttu-id="a7678-269">Viene visualizzata la pagina della nota spese.</span><span class="sxs-lookup"><span data-stu-id="a7678-269">The expense report page appears.</span></span> <span data-ttu-id="a7678-270">Si noti anche che il pulsante di spostamento indietro è abilitato.</span><span class="sxs-lookup"><span data-stu-id="a7678-270">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="a7678-271">La figura seguente Mostra gli elementi dell'interfaccia utente aggiunti a *ExpenseReportPage. XAML*.</span><span class="sxs-lookup"><span data-stu-id="a7678-271">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Schermata di esempio ExpenseIt che mostra l'interfaccia utente appena creata per il ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="a7678-273">Controlli di stile</span><span class="sxs-lookup"><span data-stu-id="a7678-273">Style controls</span></span>

<span data-ttu-id="a7678-274">L'aspetto dei vari elementi è spesso lo stesso per tutti gli elementi dello stesso tipo in un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="a7678-274">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="a7678-275">L'interfaccia utente usa gli [stili](../controls/styling-and-templating.md) per rendere i riutilizzabili in più elementi.</span><span class="sxs-lookup"><span data-stu-id="a7678-275">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="a7678-276">La riutilizzabilità degli stili consente di semplificare la creazione e la gestione di XAML.</span><span class="sxs-lookup"><span data-stu-id="a7678-276">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="a7678-277">In questa sezione vengono sostituiti con gli stili gli attributi per elemento definiti nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="a7678-277">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="a7678-278">Aprire *Application. XAML* o *app. XAML*.</span><span class="sxs-lookup"><span data-stu-id="a7678-278">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="a7678-279">Aggiungere il codice XAML seguente tra i tag <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="a7678-279">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="a7678-280">Questo codice XAML aggiunge gli stili seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7678-280">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="a7678-281">`headerTextStyle`: per formattare il titolo della pagina <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="a7678-281">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="a7678-282">`labelStyle`: per formattare i controlli <xref:System.Windows.Controls.Label> .</span><span class="sxs-lookup"><span data-stu-id="a7678-282">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="a7678-283">`columnHeaderStyle`: per formattare <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="a7678-283">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="a7678-284">`listHeaderStyle`: per formattare i controlli <xref:System.Windows.Controls.Border> dell'intestazione dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a7678-284">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="a7678-285">`listHeaderTextStyle`: per formattare l'intestazione dell'elenco <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="a7678-285">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="a7678-286">`buttonStyle`: per formattare la <xref:System.Windows.Controls.Button> in `ExpenseItHome.xaml`.</span><span class="sxs-lookup"><span data-stu-id="a7678-286">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="a7678-287">Si noti che gli stili sono risorse e elementi figlio dell'elemento proprietà <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a7678-287">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="a7678-288">In questa posizione, gli stili vengono applicati a tutti gli elementi di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-288">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="a7678-289">Per un esempio dell'uso delle risorse in un'app .NET, vedere [usare le risorse dell'applicazione](../advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="a7678-289">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="a7678-290">In *`ExpenseItHome.xaml`* sostituire tutti gli elementi tra gli elementi <xref:System.Windows.Controls.Grid> con il codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="a7678-290">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="a7678-291">Le proprietà come <xref:System.Windows.VerticalAlignment> e <xref:System.Windows.Media.FontFamily> che definiscono l'aspetto di ciascun controllo vengono rimosse e sostituite mediante l'applicazione degli stili.</span><span class="sxs-lookup"><span data-stu-id="a7678-291">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="a7678-292">Ad esempio, il `headerTextStyle` viene applicato al <xref:System.Windows.Controls.Label>"Visualizza la nota spese".</span><span class="sxs-lookup"><span data-stu-id="a7678-292">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="a7678-293">Aprire *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="a7678-293">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="a7678-294">Sostituire tutti gli elementi di <xref:System.Windows.Controls.Grid> con il codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="a7678-294">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="a7678-295">Questo codice XAML aggiunge stili agli elementi <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="a7678-295">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="a7678-296">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-296">Build and run the application.</span></span> <span data-ttu-id="a7678-297">L'aspetto della finestra è identico a quello precedente.</span><span class="sxs-lookup"><span data-stu-id="a7678-297">The window appearance is the same as previously.</span></span>

    ![Schermata di esempio ExpenseIt con lo stesso aspetto dell'ultima sezione.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="a7678-299">Chiudere l'applicazione per tornare a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a7678-299">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="a7678-300">Associare dati a un controllo</span><span class="sxs-lookup"><span data-stu-id="a7678-300">Bind data to a control</span></span>

<span data-ttu-id="a7678-301">In questa sezione verranno creati i dati XML associati a vari controlli.</span><span class="sxs-lookup"><span data-stu-id="a7678-301">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="a7678-302">In *`ExpenseItHome.xaml`* , dopo l'elemento di apertura <xref:System.Windows.Controls.Grid> aggiungere il seguente codice XAML per creare un <xref:System.Windows.Data.XmlDataProvider> contenente i dati per ogni persona:</span><span class="sxs-lookup"><span data-stu-id="a7678-302">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="a7678-303">I dati vengono creati come una risorsa <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="a7678-303">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="a7678-304">Normalmente questi dati vengono caricati come file, ma per semplicità i dati vengono aggiunti inline.</span><span class="sxs-lookup"><span data-stu-id="a7678-304">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="a7678-305">All'interno dell'elemento `<Grid.Resources>` aggiungere il seguente elemento `<xref:System.Windows.DataTemplate>`, che definisce come visualizzare i dati nel <xref:System.Windows.Controls.ListBox>, dopo l'elemento `<XmlDataProvider>`:</span><span class="sxs-lookup"><span data-stu-id="a7678-305">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="a7678-306">Per ulteriori informazioni sui modelli di dati, vedere [Cenni preliminari](../data/data-templating-overview.md)sui modelli di dati.</span><span class="sxs-lookup"><span data-stu-id="a7678-306">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="a7678-307">Sostituire il <xref:System.Windows.Controls.ListBox> esistente con il codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="a7678-307">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="a7678-308">Questo codice XAML associa la proprietà <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> della <xref:System.Windows.Controls.ListBox> all'origine dati e applica il modello di dati come <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="a7678-308">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="a7678-309">Connettere i dati ai controlli</span><span class="sxs-lookup"><span data-stu-id="a7678-309">Connect data to controls</span></span>

<span data-ttu-id="a7678-310">Successivamente, si aggiungerà il codice per recuperare il nome selezionato nella pagina **`ExpenseItHome`** e passarlo al costruttore di **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="a7678-310">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="a7678-311">**ExpenseReportPage** imposta il contesto dei dati con l'elemento passato, ovvero l'associazione tra i controlli definiti in *ExpenseReportPage. XAML* .</span><span class="sxs-lookup"><span data-stu-id="a7678-311">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="a7678-312">Aprire *ExpenseReportPage.xaml.vb* o *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="a7678-312">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="a7678-313">Aggiungere un costruttore che accetti un oggetto, in modo da poter passare i dati della nota spese della persona selezionata.</span><span class="sxs-lookup"><span data-stu-id="a7678-313">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="a7678-314">Aprire *`ExpenseItHome.xaml.vb`* o *`ExpenseItHome.xaml.cs`* .</span><span class="sxs-lookup"><span data-stu-id="a7678-314">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="a7678-315">Modificare il gestore dell'evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> per chiamare il nuovo costruttore passando i dati della nota spese della persona selezionata.</span><span class="sxs-lookup"><span data-stu-id="a7678-315">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="a7678-316">Applicare uno stile ai dati con i modelli di dati</span><span class="sxs-lookup"><span data-stu-id="a7678-316">Style data with data templates</span></span>

<span data-ttu-id="a7678-317">In questa sezione verrà aggiornata l'interfaccia utente per ogni elemento negli elenchi associati a dati utilizzando i modelli di dati.</span><span class="sxs-lookup"><span data-stu-id="a7678-317">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="a7678-318">Aprire *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="a7678-318">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="a7678-319">Associare il contenuto degli elementi "Name" e "Department" <xref:System.Windows.Controls.Label> alla proprietà dell'origine dati appropriata.</span><span class="sxs-lookup"><span data-stu-id="a7678-319">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="a7678-320">Per ulteriori informazioni su data binding, vedere [Cenni preliminari sul data binding](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a7678-320">For more information about data binding, see [Data binding overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="a7678-321">Dopo l'elemento <xref:System.Windows.Controls.Grid> di apertura aggiungere i modelli di dati seguenti, che definiscono come visualizzare i dati della nota spese:</span><span class="sxs-lookup"><span data-stu-id="a7678-321">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="a7678-322">Sostituire gli elementi <xref:System.Windows.Controls.DataGridTextColumn> con <xref:System.Windows.Controls.DataGridTemplateColumn> nell'elemento <xref:System.Windows.Controls.DataGrid> e applicarvi i modelli.</span><span class="sxs-lookup"><span data-stu-id="a7678-322">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="a7678-323">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7678-323">Build and run the application.</span></span>

6. <span data-ttu-id="a7678-324">Selezionare una persona e quindi fare clic sul pulsante **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="a7678-324">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="a7678-325">Nella figura seguente sono illustrate entrambe le pagine dell'applicazione `ExpenseIt` con i controlli, il layout, gli stili, data binding e i modelli di dati applicati:</span><span class="sxs-lookup"><span data-stu-id="a7678-325">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Entrambe le pagine dell'app che mostrano l'elenco dei nomi e una nota spese.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="a7678-327">Questo esempio illustra una funzionalità specifica di WPF e non segue tutte le procedure consigliate per elementi come sicurezza, localizzazione e accessibilità.</span><span class="sxs-lookup"><span data-stu-id="a7678-327">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="a7678-328">Per una copertura completa delle procedure consigliate per lo sviluppo di applicazioni .NET e WPF, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7678-328">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="a7678-329">Accessibilità</span><span class="sxs-lookup"><span data-stu-id="a7678-329">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
> - [<span data-ttu-id="a7678-330">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a7678-330">Security</span></span>](../security-wpf.md)
> - [<span data-ttu-id="a7678-331">Globalizzazione e localizzazione WPF</span><span class="sxs-lookup"><span data-stu-id="a7678-331">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
> - [<span data-ttu-id="a7678-332">Prestazioni di WPF</span><span class="sxs-lookup"><span data-stu-id="a7678-332">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="a7678-333">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a7678-333">Next steps</span></span>

<span data-ttu-id="a7678-334">In questa procedura dettagliata sono state illustrate alcune tecniche per la creazione di un'interfaccia utente con Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="a7678-334">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="a7678-335">A questo punto si dovrebbe avere una conoscenza di base dei blocchi predefiniti di un'app .NET associata a dati.</span><span class="sxs-lookup"><span data-stu-id="a7678-335">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="a7678-336">Per altre informazioni sull'architettura WPF e i modelli di programmazione, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7678-336">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="a7678-337">Architettura WPF</span><span class="sxs-lookup"><span data-stu-id="a7678-337">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="a7678-338">Panoramica di XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="a7678-338">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="a7678-339">Cenni preliminari sulle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="a7678-339">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="a7678-340">Layout</span><span class="sxs-lookup"><span data-stu-id="a7678-340">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="a7678-341">Per altre informazioni sulla creazione di applicazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7678-341">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="a7678-342">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="a7678-342">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="a7678-343">Controlli</span><span class="sxs-lookup"><span data-stu-id="a7678-343">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="a7678-344">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="a7678-344">Data binding overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="a7678-345">Grafica e Multimedia</span><span class="sxs-lookup"><span data-stu-id="a7678-345">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="a7678-346">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="a7678-346">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="a7678-347">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7678-347">See also</span></span>

- [<span data-ttu-id="a7678-348">Cenni preliminari sui pannelli</span><span class="sxs-lookup"><span data-stu-id="a7678-348">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="a7678-349">Panoramica sui modelli di dati</span><span class="sxs-lookup"><span data-stu-id="a7678-349">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="a7678-350">Creare un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="a7678-350">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="a7678-351">Stili e modelli</span><span class="sxs-lookup"><span data-stu-id="a7678-351">Styles and templates</span></span>](../controls/styles-and-templates.md)
