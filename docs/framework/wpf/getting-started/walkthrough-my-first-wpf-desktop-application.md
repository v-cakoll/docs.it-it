---
title: 'Procedura dettagliata: Prima applicazione desktop WPF'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
caps.latest.revision: 71
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3725e96b514b0204f10f6b5c45ed2bbec1d892de
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="48dbd-102">Procedura dettagliata: Prima applicazione desktop WPF</span><span class="sxs-lookup"><span data-stu-id="48dbd-102">Walkthrough: My first WPF desktop application</span></span>
<span data-ttu-id="48dbd-103">Questa procedura dettagliata viene fornita un'introduzione allo sviluppo di un [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] applicazione che include gli elementi che sono comuni alla maggior parte [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazioni: [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup, codice, le definizioni di applicazioni, controlli, layout, Data binding e stili.</span><span class="sxs-lookup"><span data-stu-id="48dbd-103">This walkthrough provides an introduction to the development of a [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] application that includes the elements that are common to most [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications: [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> 
  
<span data-ttu-id="48dbd-104">In questa procedura dettagliata è illustrato lo sviluppo di un semplice [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione usando la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="48dbd-104">This walkthrough guides you through the development of a simple [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application using the following steps.</span></span> 
  
-   <span data-ttu-id="48dbd-105">Definizione [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per progettare l'aspetto dell'applicazione [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48dbd-105">Defining [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to design the appearance of the application's [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> 
  
-   <span data-ttu-id="48dbd-106">Scrittura di codice per compilare il comportamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-106">Writing code to build the application's behavior.</span></span> 
  
-   <span data-ttu-id="48dbd-107">Creazione di una definizione dell'applicazione per gestire l'applicazione stessa.</span><span class="sxs-lookup"><span data-stu-id="48dbd-107">Creating an application definition to manage the application.</span></span> 
  
-   <span data-ttu-id="48dbd-108">Aggiunta di controlli e la creazione di layout per la composizione dell'applicazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48dbd-108">Adding controls and creating the layout to compose the application [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> 
  
-   <span data-ttu-id="48dbd-109">Creazione di stili per creare un aspetto coerente in tutta l'applicazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48dbd-109">Creating styles to create a consistent appearance throughout an application's [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> 
  
-   <span data-ttu-id="48dbd-110">Associazione di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ai dati sia popolare il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] da dati e di mantenere i dati e [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="48dbd-110">Binding the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to data to both populate the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] from data and keep the data and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] synchronized.</span></span> 
  
<span data-ttu-id="48dbd-111">Al termine della procedura dettagliata, verrà creata un'autonoma [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] applicazione che consente agli utenti di visualizzare i report di spesa per gli utenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="48dbd-111">By the end of the walkthrough, you will have built a standalone [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="48dbd-112">L'applicazione sarà costituita da più [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pagine in cui sono ospitate in una finestra del browser stile.</span><span class="sxs-lookup"><span data-stu-id="48dbd-112">The application will be composed of several [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pages that are hosted in a browser-style window.</span></span> 
  
<span data-ttu-id="48dbd-113">Il codice di esempio che consente di compilare in questa procedura dettagliata è disponibile sia per [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] e [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] in [Introduzione alla compilazione di applicazioni WPF](http://go.microsoft.com/fwlink/?LinkID=160008).</span><span class="sxs-lookup"><span data-stu-id="48dbd-113">The sample code that is used to build this walkthrough is available for both [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] and [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] at  [Introduction to Building WPF Applications](http://go.microsoft.com/fwlink/?LinkID=160008).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="48dbd-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="48dbd-114">Prerequisites</span></span>  

- [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="48dbd-115"> o versione successiva</span><span class="sxs-lookup"><span data-stu-id="48dbd-115"> or later</span></span>

<span data-ttu-id="48dbd-116">Per ulteriori informazioni sull'installazione della versione più recente di Visual Studio, vedere [installare Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="48dbd-116">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>
  
## <a name="creating-the-application-project"></a><span data-ttu-id="48dbd-117">Creazione del progetto di applicazione</span><span class="sxs-lookup"><span data-stu-id="48dbd-117">Creating the application project</span></span>  
<span data-ttu-id="48dbd-118">In questa sezione si crea l'infrastruttura dell'applicazione che include una definizione dell'applicazione, due pagine e un'immagine.</span><span class="sxs-lookup"><span data-stu-id="48dbd-118">In this section, you create the application infrastructure, which includes an application definition, two pages, and an image.</span></span> 
  
1. <span data-ttu-id="48dbd-119">Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual C# denominato `ExpenseIt`.</span><span class="sxs-lookup"><span data-stu-id="48dbd-119">Create a new WPF Application project in Visual Basic or Visual C# named `ExpenseIt`.</span></span> <span data-ttu-id="48dbd-120">Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione WPF](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="48dbd-120">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span> 
  
    > [!NOTE]
    >  <span data-ttu-id="48dbd-121">Questa procedura dettagliata Usa il <xref:System.Windows.Controls.DataGrid> controllo che è disponibile in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="48dbd-121">This walkthrough uses the <xref:System.Windows.Controls.DataGrid> control that is available in the .NET Framework 4.</span></span> <span data-ttu-id="48dbd-122">È possibile che il progetto è destinato a .NET Framework 4 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="48dbd-122">Be sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="48dbd-123">Per altre informazioni, vedere [Procedura: Destinare una versione di .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="48dbd-123">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span> 
  
2. <span data-ttu-id="48dbd-124">Aprire Application.xaml (Visual Basic) o App.xaml (C#).</span><span class="sxs-lookup"><span data-stu-id="48dbd-124">Open Application.xaml (Visual Basic) or App.xaml (C#).</span></span> 
  
     <span data-ttu-id="48dbd-125">Questo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file definisce un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione e tutte le risorse dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-125">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file defines a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application and any application resources.</span></span> <span data-ttu-id="48dbd-126">Utilizzare questo file per specificare il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] visualizzata automaticamente all'avvio dell'applicazione; in questo caso, MainWindow. Xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-126">You also use this file to specify the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] that automatically shows when the application starts; in this case, MainWindow.xaml.</span></span> 
  
     <span data-ttu-id="48dbd-127">Il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dovrebbe essere simile al seguente in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="48dbd-127">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]  
  
     <span data-ttu-id="48dbd-128">Oppure l'aspetto seguente in C#:</span><span class="sxs-lookup"><span data-stu-id="48dbd-128">Or like this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]  
  
3. <span data-ttu-id="48dbd-129">Aprire MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-129">Open MainWindow.xaml.</span></span> 
  
     <span data-ttu-id="48dbd-130">Questo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file la finestra principale dell'applicazione e visualizza il contenuto creato nelle pagine.</span><span class="sxs-lookup"><span data-stu-id="48dbd-130">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="48dbd-131">La <xref:System.Windows.Window> classe definisce le proprietà di una finestra, ad esempio titolo, dimensioni o sull'icona e gestisce gli eventi, ad esempio la chiusura o disattivazione della visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-131">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span> 
  
4. <span data-ttu-id="48dbd-132">Modifica il <xref:System.Windows.Window> elemento da un <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="48dbd-132">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> 
  
     <span data-ttu-id="48dbd-133">Questa applicazione passerà a contenuto diverso a seconda dell'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="48dbd-133">This application will navigate to different content depending on the user interaction.</span></span> <span data-ttu-id="48dbd-134">Pertanto, il principale <xref:System.Windows.Window> deve essere modificato in un <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="48dbd-134">Therefore, the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="48dbd-135"><xref:System.Windows.Navigation.NavigationWindow> eredita tutte le proprietà di <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="48dbd-135"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="48dbd-136">Il <xref:System.Windows.Navigation.NavigationWindow> elemento nel file XAML crea un'istanza di <xref:System.Windows.Navigation.NavigationWindow> classe.</span><span class="sxs-lookup"><span data-stu-id="48dbd-136">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="48dbd-137">Per altre informazioni, vedere [Cenni preliminari sulla navigazione](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="48dbd-137">For more information, see [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span></span> 
  
5. <span data-ttu-id="48dbd-138">Modificare le proprietà seguenti nel <xref:System.Windows.Navigation.NavigationWindow> elemento:</span><span class="sxs-lookup"><span data-stu-id="48dbd-138">Change the following properties on the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>  
  
    -   <span data-ttu-id="48dbd-139">Impostare il <xref:System.Windows.Window.Title%2A> proprietà su "ExpenseIt".</span><span class="sxs-lookup"><span data-stu-id="48dbd-139">Set the <xref:System.Windows.Window.Title%2A> property to "ExpenseIt".</span></span> 
  
    -   <span data-ttu-id="48dbd-140">Impostare il <xref:System.Windows.FrameworkElement.Width%2A> proprietà su 500 pixel.</span><span class="sxs-lookup"><span data-stu-id="48dbd-140">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span> 
  
    -   <span data-ttu-id="48dbd-141">Impostare il <xref:System.Windows.FrameworkElement.Height%2A> proprietà 350 pixel.</span><span class="sxs-lookup"><span data-stu-id="48dbd-141">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span> 
  
    -   <span data-ttu-id="48dbd-142">Rimuovere il <xref:System.Windows.Controls.Grid> elementi tra il <xref:System.Windows.Navigation.NavigationWindow> tag.</span><span class="sxs-lookup"><span data-stu-id="48dbd-142">Remove the <xref:System.Windows.Controls.Grid> elements between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span> 
  
     <span data-ttu-id="48dbd-143">Il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dovrebbe essere simile al seguente in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="48dbd-143">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]  
  
     <span data-ttu-id="48dbd-144">Oppure l'aspetto seguente in C#:</span><span class="sxs-lookup"><span data-stu-id="48dbd-144">Or like this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]  
  
6. <span data-ttu-id="48dbd-145">Aprire MainWindow.xaml.vb o MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="48dbd-145">Open MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span> 
  
     <span data-ttu-id="48dbd-146">Questo è un file code-behind che contiene il codice per gestire gli eventi dichiarati in MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-146">This file is a code-behind file that contains code to handle the events declared in MainWindow.xaml.</span></span> <span data-ttu-id="48dbd-147">Il file contiene una classe parziale per la finestra definita in XAML.</span><span class="sxs-lookup"><span data-stu-id="48dbd-147">This file contains a partial class for the window defined in XAML.</span></span> 
  
7. <span data-ttu-id="48dbd-148">Se si utilizza c#, modificare il `MainWindow` classe deriva da <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="48dbd-148">If you are using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> 
  
     <span data-ttu-id="48dbd-149">In Visual Basic questo si verifica automaticamente quando si modifica la finestra in XAML.</span><span class="sxs-lookup"><span data-stu-id="48dbd-149">In Visual Basic, this happens automatically when you change the window in XAML.</span></span> 
  
     <span data-ttu-id="48dbd-150">Il codice dovrebbe risultare simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="48dbd-150">Your code should look like this.</span></span> 
  
    [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
    [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]  
  
## <a name="adding-files-to-the-application"></a><span data-ttu-id="48dbd-151">Aggiunta di file all'applicazione</span><span class="sxs-lookup"><span data-stu-id="48dbd-151">Adding files to the application</span></span>  
<span data-ttu-id="48dbd-152">In questa sezione si aggiungono due pagine e un'immagine all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-152">In this section, you add two pages and an image to the application.</span></span> 
  
1. <span data-ttu-id="48dbd-153">Aggiungere una nuova pagina (WPF) al progetto denominato `ExpenseItHome.xaml`.</span><span class="sxs-lookup"><span data-stu-id="48dbd-153">Add a new Page (WPF) to the project named `ExpenseItHome.xaml`.</span></span> <span data-ttu-id="48dbd-154">Per ulteriori informazioni, vedere [procedura: aggiungere nuovi elementi a un progetto WPF](http://msdn.microsoft.com/library/17e6b238-fc32-4385-98ef-2f66ca09d9ad).</span><span class="sxs-lookup"><span data-stu-id="48dbd-154">For more information, see [How to: Add New Items to a WPF Project](http://msdn.microsoft.com/library/17e6b238-fc32-4385-98ef-2f66ca09d9ad).</span></span> 
  
     <span data-ttu-id="48dbd-155">Questa è la prima pagina visualizzata quando viene avviata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-155">This page is the first page that is displayed when the application is launched.</span></span> <span data-ttu-id="48dbd-156">Mostrerà un elenco di persone in cui l'utente può selezionare la persona desiderata per la visualizzazione della nota spese.</span><span class="sxs-lookup"><span data-stu-id="48dbd-156">It will show a list of people from which a user can select a person to show an expense report for.</span></span> 
  
2. <span data-ttu-id="48dbd-157">Aprire ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-157">Open ExpenseItHome.xaml.</span></span> 
  
3. <span data-ttu-id="48dbd-158">Impostare il <xref:System.Windows.Controls.Page.Title%2A> su "ExpenseIt - Home".</span><span class="sxs-lookup"><span data-stu-id="48dbd-158">Set the <xref:System.Windows.Controls.Page.Title%2A> to "ExpenseIt - Home".</span></span> 
  
     <span data-ttu-id="48dbd-159">Il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dovrebbe essere simile al seguente in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="48dbd-159">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]  
  
     <span data-ttu-id="48dbd-160">Oppure l'aspetto seguente in C#:</span><span class="sxs-lookup"><span data-stu-id="48dbd-160">Or this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]  
  
4. <span data-ttu-id="48dbd-161">Aprire MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-161">Open MainWindow.xaml.</span></span> 
  
5. <span data-ttu-id="48dbd-162">Impostare il <xref:System.Windows.Navigation.NavigationWindow.Source%2A> proprietà il <xref:System.Windows.Navigation.NavigationWindow> a "ExpenseItHome. xaml".</span><span class="sxs-lookup"><span data-stu-id="48dbd-162">Set the <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property on the <xref:System.Windows.Navigation.NavigationWindow> to "ExpenseItHome.xaml".</span></span> 
  
     <span data-ttu-id="48dbd-163">Questo imposta ExpenseItHome.xaml come prima pagina aperta all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-163">This sets ExpenseItHome.xaml to be the first page opened when the application starts.</span></span> <span data-ttu-id="48dbd-164">Il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dovrebbe essere simile al seguente in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="48dbd-164">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]  
  
     <span data-ttu-id="48dbd-165">Oppure l'aspetto seguente in C#:</span><span class="sxs-lookup"><span data-stu-id="48dbd-165">Or this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]  
  
6. <span data-ttu-id="48dbd-166">Aggiungere una nuova pagina (WPF) al progetto denominato `ExpenseReportPage.xaml`.</span><span class="sxs-lookup"><span data-stu-id="48dbd-166">Add a new Page (WPF) to the project named `ExpenseReportPage.xaml`.</span></span> 
  
     <span data-ttu-id="48dbd-167">La pagina visualizzerà la nota spese relativa alla persona selezionata in ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-167">This page will show the expense report for the person that is selected on ExpenseItHome.xaml.</span></span> 
  
7. <span data-ttu-id="48dbd-168">Aprire ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-168">Open ExpenseReportPage.xaml.</span></span> 
  
8. <span data-ttu-id="48dbd-169">Impostare il <xref:System.Windows.Controls.Page.Title%2A> su "ExpenseIt - View Expense".</span><span class="sxs-lookup"><span data-stu-id="48dbd-169">Set the <xref:System.Windows.Controls.Page.Title%2A> to "ExpenseIt - View Expense".</span></span> 
  
     <span data-ttu-id="48dbd-170">Il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dovrebbe essere simile al seguente in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="48dbd-170">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]  
  
     <span data-ttu-id="48dbd-171">Oppure l'aspetto seguente in C#:</span><span class="sxs-lookup"><span data-stu-id="48dbd-171">Or this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]  
  
9. <span data-ttu-id="48dbd-172">Aprire ExpenseItHome.xaml.vb e ExpenseReportPage.xaml.vb o ExpenseItHome.xaml.cs e ExpenseReportPage.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="48dbd-172">Open ExpenseItHome.xaml.vb and ExpenseReportPage.xaml.vb, or ExpenseItHome.xaml.cs and ExpenseReportPage.xaml.cs.</span></span> 
  
     <span data-ttu-id="48dbd-173">Quando si crea un nuovo file di pagina, Visual Studio crea automaticamente un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="48dbd-173">When you create a new Page file, Visual Studio automatically creates a code behind file.</span></span> <span data-ttu-id="48dbd-174">Questi file code-behind gestiscono la logica per rispondere all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="48dbd-174">These code-behind files handle the logic for responding to user input.</span></span> 
  
     <span data-ttu-id="48dbd-175">Il codice dovrebbe risultare simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="48dbd-175">Your code should look like this.</span></span> 
  
    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]  
  
    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]  
  
10. <span data-ttu-id="48dbd-176">Aggiungere un'immagine denominata *watermark* al progetto.</span><span class="sxs-lookup"><span data-stu-id="48dbd-176">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="48dbd-177">È possibile creare un'immagine personalizzata oppure copiare il file dal codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="48dbd-177">You can either create your own image, or copy the file from the sample code.</span></span> <span data-ttu-id="48dbd-178">Per altre informazioni, vedere [procedura: aggiungere elementi esistenti a un progetto](/previous-versions/visualstudio/visual-studio-2008/9f4t9t92(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="48dbd-178">For more information, see [How to: Add Existing Items to a Project](/previous-versions/visualstudio/visual-studio-2008/9f4t9t92(v=vs.90)).</span></span> 

## <a name="building-and-running-the-application"></a><span data-ttu-id="48dbd-179">Compilazione e l'esecuzione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="48dbd-179">Building and running the application</span></span>  
<span data-ttu-id="48dbd-180">In questa sezione viene compilata ed eseguita l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-180">In this section, you build and run the application.</span></span> 
  
1. <span data-ttu-id="48dbd-181">Compilare ed eseguire l'applicazione premendo F5 o selezionando **Avvia debug** dal **Debug** menu.</span><span class="sxs-lookup"><span data-stu-id="48dbd-181">Build and run the application by pressing F5 or selecting **Start Debugging** from the **Debug** menu.</span></span> 
  
     <span data-ttu-id="48dbd-182">Nella figura seguente viene illustrata l'applicazione con il <xref:System.Windows.Navigation.NavigationWindow> pulsanti.</span><span class="sxs-lookup"><span data-stu-id="48dbd-182">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons.</span></span> 
  
     <span data-ttu-id="48dbd-183">![Schermata dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")</span><span class="sxs-lookup"><span data-stu-id="48dbd-183">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")</span></span>  
  
2. <span data-ttu-id="48dbd-184">Chiudere l'applicazione per tornare alla [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48dbd-184">Close the application to return to [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span> 
  
## <a name="creating-the-layout"></a><span data-ttu-id="48dbd-185">Creazione del layout</span><span class="sxs-lookup"><span data-stu-id="48dbd-185">Creating the layout</span></span>  
<span data-ttu-id="48dbd-186">Il layout consente di posizionare in modo ordinato [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi e gestisce le dimensioni e posizione degli elementi quando un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] viene ridimensionato.</span><span class="sxs-lookup"><span data-stu-id="48dbd-186">Layout provides an ordered way to place [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements, and also manages the size and position of those elements when a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is resized.</span></span> <span data-ttu-id="48dbd-187">In genere si crea un layout tramite uno dei controlli di layout seguenti:</span><span class="sxs-lookup"><span data-stu-id="48dbd-187">You typically create a layout with one of the following layout controls:</span></span>  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
<span data-ttu-id="48dbd-188">Ognuno di questi controlli di layout supporta un tipo speciale di layout per i relativi elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="48dbd-188">Each of these layout controls supports a special type of layout for its child elements.</span></span> <span data-ttu-id="48dbd-189">È possibile ridimensionare le pagine ExpenseIt e ogni pagina contiene elementi disposti in orizzontale e in verticale accanto ad altri elementi.</span><span class="sxs-lookup"><span data-stu-id="48dbd-189">ExpenseIt pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="48dbd-190">Di conseguenza, il <xref:System.Windows.Controls.Grid> è l'elemento di layout ideale per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-190">Consequently, the <xref:System.Windows.Controls.Grid> is the ideal layout element for the application.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="48dbd-191">Per ulteriori informazioni su <xref:System.Windows.Controls.Panel> elementi, vedere [Panoramica pannelli](../../../../docs/framework/wpf/controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="48dbd-191">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span> <span data-ttu-id="48dbd-192">Per ulteriori informazioni sul layout, vedere [Layout](../../../../docs/framework/wpf/advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="48dbd-192">For more information about layout, see [Layout](../../../../docs/framework/wpf/advanced/layout.md).</span></span> 
  
<span data-ttu-id="48dbd-193">Nella sezione crei una sola colonna di tabella con tre righe e un margine di 10 pixel mediante l'aggiunta di definizioni di colonna e riga di <xref:System.Windows.Controls.Grid> in ExpenseItHome. Xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-193">In the section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in ExpenseItHome.xaml.</span></span> 
  
1. <span data-ttu-id="48dbd-194">Aprire ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-194">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="48dbd-195">Impostare il <xref:System.Windows.FrameworkElement.Margin%2A> proprietà il <xref:System.Windows.Controls.Grid> elemento "10,0,10,10", che corrispondono ai margini sinistro, superiore, destro e inferiore.</span><span class="sxs-lookup"><span data-stu-id="48dbd-195">Set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10" which corresponds to left, top, right and bottom margins.</span></span> 
  
3. <span data-ttu-id="48dbd-196">Aggiungere il seguente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] tra il <xref:System.Windows.Controls.Grid> tag per creare le definizioni di riga e colonna.</span><span class="sxs-lookup"><span data-stu-id="48dbd-196">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions.</span></span> 
  
    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]  
  
     <span data-ttu-id="48dbd-197">Il <xref:System.Windows.Controls.RowDefinition.Height%2A> di due righe è impostato su <xref:System.Windows.GridLength.Auto%2A> di base che significa che le righe verranno ridimensionato in base al contenuto delle righe.</span><span class="sxs-lookup"><span data-stu-id="48dbd-197">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A> which means that the rows will be sized base on the content in the rows.</span></span> <span data-ttu-id="48dbd-198">Il valore predefinito <xref:System.Windows.Controls.RowDefinition.Height%2A> è <xref:System.Windows.GridUnitType.Star> dimensioni, il che significa che la riga sarà una proporzione ponderata dello spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="48dbd-198">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row will be a weighted proportion of the available space.</span></span> <span data-ttu-id="48dbd-199">Se ad esempio due righe hanno un'altezza pari a "\*", ognuna avrà un'altezza pari alla metà dello spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="48dbd-199">For example if two rows each have a height of "\*", they will each have a height that is half of the available space.</span></span>  
  
     <span data-ttu-id="48dbd-200">Il <xref:System.Windows.Controls.Grid> dovrebbe essere simile al codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="48dbd-200">Your <xref:System.Windows.Controls.Grid> should now look like the following XAML:</span></span>  
  
    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]  
  
## <a name="adding-controls"></a><span data-ttu-id="48dbd-201">Aggiunta di controlli</span><span class="sxs-lookup"><span data-stu-id="48dbd-201">Adding controls</span></span>  
<span data-ttu-id="48dbd-202">In questa sezione, la home page [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] viene aggiornato per visualizzare un elenco di persone che gli utenti possono selezionare per mostrare la nota spese per una persona selezionata.</span><span class="sxs-lookup"><span data-stu-id="48dbd-202">In this section, the home page [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is updated to show a list of people that users can select from to show the expense report for a selected person.</span></span> <span data-ttu-id="48dbd-203">I controlli sono oggetti dell'interfaccia utente che consentono agli utenti di interagire con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-203">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="48dbd-204">Per altre informazioni, vedere [Controlli](../../../../docs/framework/wpf/controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="48dbd-204">For more information, see [Controls](../../../../docs/framework/wpf/controls/index.md).</span></span> 
  
<span data-ttu-id="48dbd-205">Per creare questa [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], gli elementi seguenti sono aggiunti a ExpenseItHome. XAML:</span><span class="sxs-lookup"><span data-stu-id="48dbd-205">To create this [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], the following elements are added to ExpenseItHome.xaml:</span></span>  
  
-   <span data-ttu-id="48dbd-206"><xref:System.Windows.Controls.ListBox> (per un elenco di persone).</span><span class="sxs-lookup"><span data-stu-id="48dbd-206"><xref:System.Windows.Controls.ListBox> (for the list of people).</span></span> 
  
-   <span data-ttu-id="48dbd-207"><xref:System.Windows.Controls.Label> (per l'intestazione dell'elenco).</span><span class="sxs-lookup"><span data-stu-id="48dbd-207"><xref:System.Windows.Controls.Label> (for the list header).</span></span> 
  
-   <span data-ttu-id="48dbd-208"><xref:System.Windows.Controls.Button> (possibile fare clic per visualizzare la nota spese per la persona che sia selezionata nell'elenco).</span><span class="sxs-lookup"><span data-stu-id="48dbd-208"><xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span> 
  
<span data-ttu-id="48dbd-209">Ogni controllo viene posizionato in una riga del <xref:System.Windows.Controls.Grid> impostando il <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> proprietà associata.</span><span class="sxs-lookup"><span data-stu-id="48dbd-209">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="48dbd-210">Per ulteriori informazioni sulle proprietà associate, vedere [collegato Cenni preliminari sulle proprietà](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="48dbd-210">For more information about attached properties, see [Attached Properties Overview](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span></span> 
  
1. <span data-ttu-id="48dbd-211">Aprire ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-211">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="48dbd-212">Aggiungere il seguente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] tra il <xref:System.Windows.Controls.Grid> tag.</span><span class="sxs-lookup"><span data-stu-id="48dbd-212">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] between the <xref:System.Windows.Controls.Grid> tags.</span></span> 
  
    [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]  
  
3. <span data-ttu-id="48dbd-213">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-213">Build and run the application.</span></span> 
  
<span data-ttu-id="48dbd-214">La figura seguente mostra i controlli creati da XAML in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-214">The following illustration shows the controls that are created by the XAML in this section.</span></span> 
  
<span data-ttu-id="48dbd-215">![Schermata dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")</span><span class="sxs-lookup"><span data-stu-id="48dbd-215">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")</span></span>  
  
## <a name="adding-an-image-and-a-title"></a><span data-ttu-id="48dbd-216">Aggiunta di un'immagine e un titolo</span><span class="sxs-lookup"><span data-stu-id="48dbd-216">Adding an image and a title</span></span>  
<span data-ttu-id="48dbd-217">In questa sezione, la home page [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] viene aggiornato con un'immagine e un titolo della pagina.</span><span class="sxs-lookup"><span data-stu-id="48dbd-217">In this section, the home page [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is updated with an image and a page title.</span></span> 
  
1. <span data-ttu-id="48dbd-218">Aprire ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-218">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="48dbd-219">Aggiungere un'altra colonna per il <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con fisse <xref:System.Windows.Controls.ColumnDefinition.Width%2A> di 230 pixel.</span><span class="sxs-lookup"><span data-stu-id="48dbd-219">Add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels.</span></span> 
  
    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]  
  
3. <span data-ttu-id="48dbd-220">Aggiungere un'altra riga per il <xref:System.Windows.Controls.Grid.RowDefinitions%2A>.</span><span class="sxs-lookup"><span data-stu-id="48dbd-220">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>.</span></span> 
  
    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]  
  
4. <span data-ttu-id="48dbd-221">Spostare i controlli nella seconda colonna impostando <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> su 1.</span><span class="sxs-lookup"><span data-stu-id="48dbd-221">Move the controls to the second column by setting <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> to 1.</span></span> <span data-ttu-id="48dbd-222">Spostare ogni controllo in basso di una riga, aumentando la <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> di 1.</span><span class="sxs-lookup"><span data-stu-id="48dbd-222">Move each control down a row, by increasing the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> by 1.</span></span> 
  
    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]  
  
5. <span data-ttu-id="48dbd-223">Impostare il <xref:System.Windows.Controls.Panel.Background%2A> del <xref:System.Windows.Controls.Grid> come file di immagine watermark.</span><span class="sxs-lookup"><span data-stu-id="48dbd-223">Set the <xref:System.Windows.Controls.Panel.Background%2A> of the <xref:System.Windows.Controls.Grid> to be the watermark.png image file.</span></span> 
  
    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]  
  
6. <span data-ttu-id="48dbd-224">Prima di <xref:System.Windows.Controls.Border>, aggiungere un <xref:System.Windows.Controls.Label> con il contenuto "View Expense Report" per il titolo della pagina.</span><span class="sxs-lookup"><span data-stu-id="48dbd-224">Before the <xref:System.Windows.Controls.Border>, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report" to be the title of the page.</span></span> 
  
    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]  
  
7. <span data-ttu-id="48dbd-225">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-225">Build and run the application.</span></span> 
  
<span data-ttu-id="48dbd-226">La figura seguente mostra i risultati di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-226">The following illustration shows the results of this section.</span></span> 
  
<span data-ttu-id="48dbd-227">![Schermata dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")</span><span class="sxs-lookup"><span data-stu-id="48dbd-227">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")</span></span>  
  
## <a name="adding-code-to-handle-events"></a><span data-ttu-id="48dbd-228">Aggiungere il codice per gestire gli eventi</span><span class="sxs-lookup"><span data-stu-id="48dbd-228">Adding code to handle events</span></span>  
  
1. <span data-ttu-id="48dbd-229">Aprire ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-229">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="48dbd-230">Aggiungere un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi per il <xref:System.Windows.Controls.Button> elemento.</span><span class="sxs-lookup"><span data-stu-id="48dbd-230">Add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="48dbd-231">Per ulteriori informazioni, vedere [procedura: creare un semplice gestore](http://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480).</span><span class="sxs-lookup"><span data-stu-id="48dbd-231">For more information, see [How to: Create a Simple Event Handler](http://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480).</span></span> 
  
    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]  
  
3. <span data-ttu-id="48dbd-232">Aprire ExpenseItHome.xaml.vb o ExpenseItHome.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="48dbd-232">Open ExpenseItHome.xaml.vb or ExpenseItHome.xaml.cs.</span></span> 
  
4. <span data-ttu-id="48dbd-233">Aggiungere il codice seguente per il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi, che fa sì che la finestra passare al file ExpenseReportPage. Xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-233">Add the following code to the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler, which causes the window to navigate to the ExpenseReportPage.xaml file.</span></span> 
  
    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]  
  
## <a name="creating-the-ui-for-expensereportpage"></a><span data-ttu-id="48dbd-234">Creazione dell'interfaccia utente per ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="48dbd-234">Creating the UI for ExpenseReportPage</span></span>  
<span data-ttu-id="48dbd-235">ExpenseReportPage.xaml visualizza la nota spese per la persona selezionata nel file ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-235">ExpenseReportPage.xaml displays the expense report for the person that was selected on the ExpenseItHome.xaml.</span></span> <span data-ttu-id="48dbd-236">In questa sezione verranno aggiunti i controlli e crea il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] per ExpenseReportPage. Xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-236">This section adds controls and creates the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] for ExpenseReportPage.xaml.</span></span> <span data-ttu-id="48dbd-237">In questa sezione vengono inoltre aggiunti i colori di sfondo e del riempimento ai diversi [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi.</span><span class="sxs-lookup"><span data-stu-id="48dbd-237">This section also adds background and fill colors to the various [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements.</span></span> 
  
1. <span data-ttu-id="48dbd-238">Aprire ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-238">Open ExpenseReportPage.xaml.</span></span> 
  
2. <span data-ttu-id="48dbd-239">Aggiungere il seguente codice XAML tra i tag <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="48dbd-239">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags.</span></span> 
  
     <span data-ttu-id="48dbd-240">Questa interfaccia è simile all'interfaccia utente creato in ExpenseItHome. XAML, tranne i dati del report viene visualizzati un <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="48dbd-240">This UI is similar to the UI created on ExpenseItHome.xaml except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span> 
  
    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]  
  
3. <span data-ttu-id="48dbd-241">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-241">Build and run the application.</span></span> 
  
    > [!NOTE]
    >  <span data-ttu-id="48dbd-242">Se si verifica un errore di <xref:System.Windows.Controls.DataGrid> non è stato trovato o non esiste, verificare che il progetto è destinato a .NET Framework 4 o versione successivo.</span><span class="sxs-lookup"><span data-stu-id="48dbd-242">If you get an error that the <xref:System.Windows.Controls.DataGrid> was not found or does not exist, make sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="48dbd-243">Per altre informazioni, vedere [Procedura: Destinare una versione di .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="48dbd-243">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span> 
  
4. <span data-ttu-id="48dbd-244">Fare clic su di **vista** pulsante.</span><span class="sxs-lookup"><span data-stu-id="48dbd-244">Click the **View** button.</span></span> 
  
     <span data-ttu-id="48dbd-245">Viene visualizzata la pagina della nota spese.</span><span class="sxs-lookup"><span data-stu-id="48dbd-245">The expense report page appears.</span></span> 
  
<span data-ttu-id="48dbd-246">La figura seguente mostra il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi aggiunti alla ExpenseReportPage. Xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-246">The following illustration shows the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements added to ExpenseReportPage.xaml.</span></span> <span data-ttu-id="48dbd-247">Notare che il pulsante di navigazione all'indietro è abilitato.</span><span class="sxs-lookup"><span data-stu-id="48dbd-247">Notice that the back navigation button is enabled.</span></span> 
  
<span data-ttu-id="48dbd-248">![Schermata dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")</span><span class="sxs-lookup"><span data-stu-id="48dbd-248">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")</span></span>  
  
## <a name="styling-controls"></a><span data-ttu-id="48dbd-249">Stile di controlli</span><span class="sxs-lookup"><span data-stu-id="48dbd-249">Styling controls</span></span>  
<span data-ttu-id="48dbd-250">L'aspetto dei diversi elementi spesso può essere uguale per tutti gli elementi dello stesso tipo in un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48dbd-250">The appearance of various elements can often be the same for all elements of the same type in a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]<span data-ttu-id="48dbd-251"> usa gli stili per rendere l'aspetto riutilizzabile tra più elementi.</span><span class="sxs-lookup"><span data-stu-id="48dbd-251"> uses styles to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="48dbd-252">La possibilità di riutilizzo consente di semplificare [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] creazione e la gestione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-252">The reusability of styles helps to simplify [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] creation and management.</span></span> <span data-ttu-id="48dbd-253">Per ulteriori informazioni sugli stili, vedere [stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="48dbd-253">For more information about styles, see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span> <span data-ttu-id="48dbd-254">In questa sezione vengono sostituiti con gli stili gli attributi per elemento definiti nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="48dbd-254">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span> 
  
1. <span data-ttu-id="48dbd-255">Aprire Application.xaml o App.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-255">Open Application.xaml or App.xaml.</span></span> 
  
2. <span data-ttu-id="48dbd-256">Aggiungere il codice XAML seguente tra i <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tag:</span><span class="sxs-lookup"><span data-stu-id="48dbd-256">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>  
  
    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]  
  
     <span data-ttu-id="48dbd-257">Questo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] aggiunge gli stili seguenti:</span><span class="sxs-lookup"><span data-stu-id="48dbd-257">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] adds the following styles:</span></span>  
  
    -  <span data-ttu-id="48dbd-258">`headerTextStyle`: per formattare il titolo della pagina <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="48dbd-258">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span> 
  
    -  <span data-ttu-id="48dbd-259">`labelStyle`: per formattare i controlli <xref:System.Windows.Controls.Label> .</span><span class="sxs-lookup"><span data-stu-id="48dbd-259">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span> 
  
    -  <span data-ttu-id="48dbd-260">`columnHeaderStyle`: per formattare <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="48dbd-260">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span> 
  
    -  <span data-ttu-id="48dbd-261">`listHeaderStyle`: per formattare i controlli <xref:System.Windows.Controls.Border> dell'intestazione dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="48dbd-261">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span> 
  
    -  <span data-ttu-id="48dbd-262">`listHeaderTextStyle`: Per formattare l'intestazione dell'elenco <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="48dbd-262">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span> 
  
    -  <span data-ttu-id="48dbd-263">`buttonStyle`: Per formattare il <xref:System.Windows.Controls.Button> in ExpenseItHome. Xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-263">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on ExpenseItHome.xaml.</span></span> 
  
     <span data-ttu-id="48dbd-264">Si noti che gli stili sono risorse e i relativi elementi figlio di <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> elemento proprietà.</span><span class="sxs-lookup"><span data-stu-id="48dbd-264">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="48dbd-265">In questa posizione, gli stili vengono applicati a tutti gli elementi di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-265">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="48dbd-266">Per un esempio di utilizzo delle risorse in un [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] applicazione, vedere [le risorse dell'applicazione di utilizzare](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="48dbd-266">For an example of using resources in a [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] application, see [Use Application Resources](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span></span> 
  
3. <span data-ttu-id="48dbd-267">Aprire ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-267">Open ExpenseItHome.xaml.</span></span> 
  
4. <span data-ttu-id="48dbd-268">Sostituire tutto il contenuto tra il <xref:System.Windows.Controls.Grid> gli elementi con il seguente codice XAML.</span><span class="sxs-lookup"><span data-stu-id="48dbd-268">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML.</span></span> 
  
    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]  
  
     <span data-ttu-id="48dbd-269">Le proprietà come <xref:System.Windows.VerticalAlignment> e <xref:System.Windows.Media.FontFamily> che definiscono l'aspetto di ciascun controllo vengono rimosse e sostituite mediante l'applicazione degli stili.</span><span class="sxs-lookup"><span data-stu-id="48dbd-269">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="48dbd-270">Ad esempio, il `headerTextStyle` viene applicato a "View Expense Report" <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="48dbd-270">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span> 
  
5. <span data-ttu-id="48dbd-271">Aprire ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-271">Open ExpenseReportPage.xaml.</span></span> 
  
6. <span data-ttu-id="48dbd-272">Sostituire tutto il contenuto tra il <xref:System.Windows.Controls.Grid> gli elementi con il seguente codice XAML.</span><span class="sxs-lookup"><span data-stu-id="48dbd-272">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML.</span></span> 
  
    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]  
  
     <span data-ttu-id="48dbd-273">Vengono aggiunti gli stili agli elementi <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="48dbd-273">This adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span> 
  
7. <span data-ttu-id="48dbd-274">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-274">Build and run the application.</span></span> 
  
     <span data-ttu-id="48dbd-275">Dopo aver aggiunto il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in questa sezione, l'applicazione abbia lo stesso aspetto era prima che venga aggiornato con gli stili.</span><span class="sxs-lookup"><span data-stu-id="48dbd-275">After adding the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in this section, the application looks the same as it did before being updated with styles.</span></span> 
  
## <a name="binding-data-to-a-control"></a><span data-ttu-id="48dbd-276">Associazione dati a un controllo</span><span class="sxs-lookup"><span data-stu-id="48dbd-276">Binding data to a control</span></span>  
<span data-ttu-id="48dbd-277">In questa sezione si crea il [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] dati associati ai vari controlli.</span><span class="sxs-lookup"><span data-stu-id="48dbd-277">In this section, you create the [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] data that is bound to various controls.</span></span> 
  
1. <span data-ttu-id="48dbd-278">Aprire ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-278">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="48dbd-279">Dopo l'apertura <xref:System.Windows.Controls.Grid> elemento, aggiungere il codice XAML seguente per creare un <xref:System.Windows.Data.XmlDataProvider> che contiene i dati per ogni persona.</span><span class="sxs-lookup"><span data-stu-id="48dbd-279">After the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person.</span></span> 
  
     <span data-ttu-id="48dbd-280">I dati vengono creati come un <xref:System.Windows.Controls.Grid> risorse.</span><span class="sxs-lookup"><span data-stu-id="48dbd-280">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="48dbd-281">In genere questi dati vengono caricati sotto forma di file, ma in questo caso, per semplicità, verranno aggiunti inline.</span><span class="sxs-lookup"><span data-stu-id="48dbd-281">Normally this would be loaded as a file, but for simplicity the data is added inline.</span></span> 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
3. <span data-ttu-id="48dbd-282">Nel <xref:System.Windows.Controls.Grid> risorsa, aggiungere le seguenti <xref:System.Windows.DataTemplate>, che definisce come visualizzare i dati di <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="48dbd-282">In the <xref:System.Windows.Controls.Grid> resource, add the following <xref:System.Windows.DataTemplate>, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="48dbd-283">Per altre informazioni sui modelli di dati, vedere [Cenni preliminari sui modelli di dati](../../../../docs/framework/wpf/data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="48dbd-283">For more information about data templates, see [Data Templating Overview](../../../../docs/framework/wpf/data/data-templating-overview.md).</span></span> 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
4. <span data-ttu-id="48dbd-284">Sostituire <xref:System.Windows.Controls.ListBox> con il seguente codice XAML.</span><span class="sxs-lookup"><span data-stu-id="48dbd-284">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML.</span></span> 
  
    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]  
  
     <span data-ttu-id="48dbd-285">Questo codice XAML associa il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà del <xref:System.Windows.Controls.ListBox> all'origine dati e applica il modello di dati come il <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="48dbd-285">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span> 
  
## <a name="connecting-data-to-controls"></a><span data-ttu-id="48dbd-286">Connessione dati a controlli</span><span class="sxs-lookup"><span data-stu-id="48dbd-286">Connecting data to controls</span></span>  
<span data-ttu-id="48dbd-287">In questa sezione, scritto il codice per recuperare l'elemento corrente che sia selezionata nell'elenco di utenti nella pagina ExpenseItHome. XAML e passa il relativo riferimento al costruttore di `ExpenseReportPage` durante la creazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="48dbd-287">In this section, you write the code that retrieves the current item that is selected in the list of people on the ExpenseItHome.xaml page, and passes its reference to the constructor of `ExpenseReportPage` during instantiation.</span></span> <span data-ttu-id="48dbd-288">`ExpenseReportPage` imposta il contesto dei dati con l'elemento passato, a cui verranno associati i controlli definiti in ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-288">`ExpenseReportPage` sets its data context with the passed item, which is what the controls defined in ExpenseReportPage.xaml will bind to.</span></span> 
  
1. <span data-ttu-id="48dbd-289">Aprire ExpenseReportPage.xaml.vb o ExpenseReportPage.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="48dbd-289">Open ExpenseReportPage.xaml.vb or ExpenseReportPage.xaml.cs.</span></span> 
  
2. <span data-ttu-id="48dbd-290">Aggiungere un costruttore che accetti un oggetto, in modo da poter passare i dati della nota spese della persona selezionata.</span><span class="sxs-lookup"><span data-stu-id="48dbd-290">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span> 
  
    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]  
  
3. <span data-ttu-id="48dbd-291">Aprire ExpenseItHome.xaml.vb o ExpenseItHome.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="48dbd-291">Open ExpenseItHome.xaml.vb or ExpenseItHome.xaml.cs.</span></span> 
  
4. <span data-ttu-id="48dbd-292">Modifica il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi per chiamare il nuovo costruttore passando i dati della nota spese della persona selezionata.</span><span class="sxs-lookup"><span data-stu-id="48dbd-292">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span> 
  
    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]  
  
## <a name="styling-data-with-data-templates"></a><span data-ttu-id="48dbd-293">Lo stile dati con i modelli di dati</span><span class="sxs-lookup"><span data-stu-id="48dbd-293">Styling data with data templates</span></span>  
<span data-ttu-id="48dbd-294">In questa sezione, si aggiorna il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] per ciascun elemento nei dati associati gli elenchi con i modelli di dati.</span><span class="sxs-lookup"><span data-stu-id="48dbd-294">In this section, you update the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] for each item in the data bound lists by using data templates.</span></span> 
  
1. <span data-ttu-id="48dbd-295">Aprire ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="48dbd-295">Open ExpenseReportPage.xaml.</span></span> 
  
2. <span data-ttu-id="48dbd-296">Associare il contenuto di "Nome" e "Department" <xref:System.Windows.Controls.Label> proprietà source elementi per i dati appropriati.</span><span class="sxs-lookup"><span data-stu-id="48dbd-296">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="48dbd-297">Per altre informazioni sul data binding, vedere [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="48dbd-297">For more information about data binding, see [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span> 
  
    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]  
  
3. <span data-ttu-id="48dbd-298">Dopo l'apertura <xref:System.Windows.Controls.Grid> elemento, aggiungere i seguenti modelli di dati, che definiscono la modalità di visualizzazione dei dati della nota spese.</span><span class="sxs-lookup"><span data-stu-id="48dbd-298">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data.</span></span>  
    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]  
  
4. <span data-ttu-id="48dbd-299">Applicare i modelli per il <xref:System.Windows.Controls.DataGrid> colonne che visualizzano i costi per i dati del report.</span><span class="sxs-lookup"><span data-stu-id="48dbd-299">Apply the templates to the <xref:System.Windows.Controls.DataGrid> columns that display the expense report data.</span></span> 
  
    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]  
  
5. <span data-ttu-id="48dbd-300">Compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-300">Build and run the application.</span></span> 
  
6. <span data-ttu-id="48dbd-301">Selezionare una persona e fare clic su di **vista** pulsante.</span><span class="sxs-lookup"><span data-stu-id="48dbd-301">Select a person and click the **View** button.</span></span> 
  
 <span data-ttu-id="48dbd-302">La figura seguente mostra le due pagine dell'applicazione ExpenseIt con i controlli, il layout, gli stili, il data binding e i modelli di dati applicati.</span><span class="sxs-lookup"><span data-stu-id="48dbd-302">The following illustration shows both pages of the ExpenseIt application with controls, layout, styles, data binding, and data templates applied.</span></span> 
  
 <span data-ttu-id="48dbd-303">![Schermate dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")</span><span class="sxs-lookup"><span data-stu-id="48dbd-303">![ExpenseIt sample screen shots](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="48dbd-304">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="48dbd-304">Best practices</span></span>  
<span data-ttu-id="48dbd-305">Questo esempio illustra una funzionalità specifica di WPF e, di conseguenza, non segue le procedure consigliate per lo sviluppo di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="48dbd-305">This sample demonstrates a specific feature of WPF and, consequently, does not follow application development best practices.</span></span> <span data-ttu-id="48dbd-306">Per una descrizione completa di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] applicazione consigliate per lo sviluppo, vedere gli argomenti seguenti come appropriato:</span><span class="sxs-lookup"><span data-stu-id="48dbd-306">For comprehensive coverage of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] and the [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] application development best practices, see the following topics as appropriate:</span></span>  
  
-   <span data-ttu-id="48dbd-307">Accessibilità: [Procedure consigliate per l'accesso facilitato](../../../../docs/framework/ui-automation/accessibility-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="48dbd-307">Accessibility - [Accessibility Best Practices](../../../../docs/framework/ui-automation/accessibility-best-practices.md)</span></span>  
  
-   <span data-ttu-id="48dbd-308">Sicurezza - [sicurezza](../../../../docs/framework/wpf/security-wpf.md)</span><span class="sxs-lookup"><span data-stu-id="48dbd-308">Security - [Security](../../../../docs/framework/wpf/security-wpf.md)</span></span>  
  
-   <span data-ttu-id="48dbd-309">Localizzazione: [Panoramica della globalizzazione e localizzazione WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)</span><span class="sxs-lookup"><span data-stu-id="48dbd-309">Localization - [WPF Globalization and Localization Overview](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)</span></span>  
  
-   <span data-ttu-id="48dbd-310">Prestazioni: [Ottimizzazione delle prestazioni di applicazioni WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)</span><span class="sxs-lookup"><span data-stu-id="48dbd-310">Performance - [Optimizing WPF Application Performance](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)</span></span>  
  
## <a name="whats-next"></a><span data-ttu-id="48dbd-311">Argomenti successivi</span><span class="sxs-lookup"><span data-stu-id="48dbd-311">What's next</span></span>  
<span data-ttu-id="48dbd-312">È ora una serie di tecniche a disposizione per la creazione di un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] utilizzando [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48dbd-312">You now have a number of techniques at your disposal for creating a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] using [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span> <span data-ttu-id="48dbd-313">È stata acquisita una conoscenza approfondita dei blocchi di compilazione di base di un controllo con associazione a dati [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48dbd-313">You should now have a broad understanding of the basic building blocks of a data-bound [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] application.</span></span> <span data-ttu-id="48dbd-314">Questo argomento non è esaustivo, ma intende fornire all'utente le informazioni e gli strumenti per approfondire autonomamente le numerose opzioni di cui dispone, che vanno oltre le tecniche descritte nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="48dbd-314">This topic is by no means exhaustive, but hopefully you also now have a sense of some of the possibilities you might discover on your own beyond the techniques in this topic.</span></span> 
  
 <span data-ttu-id="48dbd-315">Per altre informazioni sull'architettura WPF e i modelli di programmazione, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="48dbd-315">For more information about the WPF architecture and programming models, see the following topics:</span></span>  
  
-   [<span data-ttu-id="48dbd-316">Architettura WPF</span><span class="sxs-lookup"><span data-stu-id="48dbd-316">WPF Architecture</span></span>](../../../../docs/framework/wpf/advanced/wpf-architecture.md)  
  
-   [<span data-ttu-id="48dbd-317">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="48dbd-317">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
  
-   [<span data-ttu-id="48dbd-318">Panoramica sulle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="48dbd-318">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
  
-   [<span data-ttu-id="48dbd-319">Layout</span><span class="sxs-lookup"><span data-stu-id="48dbd-319">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)  
  
 <span data-ttu-id="48dbd-320">Per altre informazioni sulla creazione di applicazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="48dbd-320">For more information about creating applications, see the following topics:</span></span>  
  
-   [<span data-ttu-id="48dbd-321">Sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="48dbd-321">Application Development</span></span>](../../../../docs/framework/wpf/app-development/index.md)  
  
-   [<span data-ttu-id="48dbd-322">Controlli</span><span class="sxs-lookup"><span data-stu-id="48dbd-322">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)  
  
-   [<span data-ttu-id="48dbd-323">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="48dbd-323">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
  
-   [<span data-ttu-id="48dbd-324">Grafica e funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="48dbd-324">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
  
-   [<span data-ttu-id="48dbd-325">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="48dbd-325">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
  
## <a name="see-also"></a><span data-ttu-id="48dbd-326">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48dbd-326">See also</span></span>  
 [<span data-ttu-id="48dbd-327">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="48dbd-327">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="48dbd-328">Panoramica sui modelli di dati</span><span class="sxs-lookup"><span data-stu-id="48dbd-328">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="48dbd-329">Compilazione di un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="48dbd-329">Building a WPF Application</span></span>](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [<span data-ttu-id="48dbd-330">Stili e modelli</span><span class="sxs-lookup"><span data-stu-id="48dbd-330">Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/styles-and-templates.md)
