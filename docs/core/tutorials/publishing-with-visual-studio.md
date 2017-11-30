---
title: Pubblicare l'applicazione Hello World con Visual Studio 2017
description: Con la pubblicazione viene creato il set di file necessari per eseguire l'applicazione.
keywords: .NET, .NET Core, applicazione console pubblicazione, distribuzione
author: BillWagner
ms.author: wiwagn
ms.date: 10/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a19545d3-24af-4a32-9778-cfb5ae938287
ms.openlocfilehash: a3e5bda5c99144c9ab5bbaf5e2f5566261af4813
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="publish-your-hello-world-application-with-visual-studio-2017"></a><span data-ttu-id="895d4-104">Pubblicare l'applicazione Hello World con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="895d4-104">Publish your Hello World application with Visual Studio 2017</span></span>

<span data-ttu-id="895d4-105">In [Compilare un'applicazione Hello World usando C# con .NET Core in Visual Studio 2017](with-visual-studio.md) o [Compilare un'applicazione Hello World usando Visual Basic con .NET Core in Visual Studio 2017](vb-with-visual-studio.md) si crea un'applicazione console Hello World.</span><span class="sxs-lookup"><span data-stu-id="895d4-105">In [Build a C# Hello World application with .NET Core in Visual Studio 2017](with-visual-studio.md) or [Build a Visual Basic Hello World application with .NET Core in Visual Studio 2017](vb-with-visual-studio.md), you built a Hello World console application.</span></span> <span data-ttu-id="895d4-106">In [Debug dell'applicazione Hello World usando C# con Visual Studio 2017](debugging-with-visual-studio.md) l'applicazione è stata testata con il debugger di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="895d4-106">In [Debug your C# Hello World application with Visual Studio 2017](debugging-with-visual-studio.md), you tested it using the Visual Studio debugger.</span></span> <span data-ttu-id="895d4-107">A questo punto è sicuro che l'applicazione funziona nel modo previsto ed è possibile pubblicarla in modo che possa essere eseguita da altri utenti.</span><span class="sxs-lookup"><span data-stu-id="895d4-107">Now that you're sure that it works as expected, you can publish it so that other users can run it.</span></span> <span data-ttu-id="895d4-108">Con la pubblicazione viene creato il set di file necessari per eseguire l'applicazione. È possibile distribuire tali file copiandoli in un computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="895d4-108">Publishing creates the set of files that are needed to run your application, and you can deploy the files by copying them to a target machine.</span></span>

<span data-ttu-id="895d4-109">Per pubblicare ed eseguire l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="895d4-109">To publish and run your application:</span></span> 

1. <span data-ttu-id="895d4-110">Verificare che Visual Studio compili la versione di rilascio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="895d4-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="895d4-111">Se necessario, modificare la configurazione di compilazione nella barra degli strumenti da **Debug** in **Rilascio**.</span><span class="sxs-lookup"><span data-stu-id="895d4-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![Barra degli strumenti di Visual Studio](media/publishing-with-visual-studio/toolbar.png)

1. <span data-ttu-id="895d4-113">Fare clic con il pulsante destro del mouse sul progetto **HelloWorld**, non sulla soluzione HelloWorld, e scegliere **Pubblica** dal menu.</span><span class="sxs-lookup"><span data-stu-id="895d4-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span> <span data-ttu-id="895d4-114">È anche possibile scegliere **Pubblica HelloWorld** dal menu principale **Compila** di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="895d4-114">You can also select **Publish HelloWorld** from the main Visual Studio **Build** menu.</span></span>

   ![Barra degli strumenti di Visual Studio](media/publishing-with-visual-studio/publish1.png)


   ![Barra degli strumenti di Visual Studio](media/publishing-with-visual-studio/publishwindow.png)

1. <span data-ttu-id="895d4-117">Aprire una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="895d4-117">Open a console window.</span></span> <span data-ttu-id="895d4-118">Ad esempio nella casella di testo **Digitare qui il testo di ricerca** nella barra delle applicazioni Windows, immettere `Command Prompt` o `cmd` per maggiore brevità e aprire una finestra della console selezionando l'applicazione desktop **Prompt dei comandi** o premendo INVIO se è selezionata nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="895d4-118">For example in the **Type here to search** text box in the Windows taskbar, enter `Command Prompt` (or `cmd` for short), and open a console window by either selecting the **Command Prompt** desktop app or pressing Enter if it's selected in the search results.</span></span>

1. <span data-ttu-id="895d4-119">Passare all'applicazione pubblicata nella sottodirectory `bin\release\PublishOutput` della directory del progetto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="895d4-119">Navigate to the published application in the `bin\release\PublishOutput` subdirectory of your application's project directory.</span></span> <span data-ttu-id="895d4-120">Come illustrato nella figura, l'output pubblicato include i quattro file seguenti:</span><span class="sxs-lookup"><span data-stu-id="895d4-120">As the following figure shows, the published output includes the following four files:</span></span>

      * <span data-ttu-id="895d4-121">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="895d4-121">*HelloWorld.deps.json*</span></span>

         <span data-ttu-id="895d4-122">File di dipendenze di runtime dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="895d4-122">The application's runtime dependencies file.</span></span> <span data-ttu-id="895d4-123">Definisce i componenti di .NET Core e le librerie (inclusa la libreria di collegamento dinamico che contiene l'applicazione) necessario per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="895d4-123">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run your application.</span></span> <span data-ttu-id="895d4-124">Per ulteriori informazioni, vedere [i file di configurazione di Runtime](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="895d4-124">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>
 
      * <span data-ttu-id="895d4-125">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="895d4-125">*HelloWorld.dll*</span></span>

         <span data-ttu-id="895d4-126">Il file che contiene l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="895d4-126">The file that contains your application.</span></span> <span data-ttu-id="895d4-127">È una libreria a collegamento dinamico che può essere eseguita tramite l'immissione di `dotnet HelloWorld.dll` comando in una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="895d4-127">It is a dynamic link library that can be executed by entering the `dotnet HelloWorld.dll` command in a console window.</span></span> 

      * <span data-ttu-id="895d4-128">*HelloWorld.pdb* (facoltativo per la distribuzione)</span><span class="sxs-lookup"><span data-stu-id="895d4-128">*HelloWorld.pdb* (optional for deployment)</span></span>

         <span data-ttu-id="895d4-129">Un file che contiene i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="895d4-129">A file that contains debug symbols.</span></span> <span data-ttu-id="895d4-130">Non è necessario distribuire tale file insieme all'applicazione, anche se è consigliabile salvarlo nel caso in cui sia necessario eseguire il debug della versione pubblicata dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="895d4-130">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

      * <span data-ttu-id="895d4-131">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="895d4-131">*HelloWorld.runtimeconfig.json*</span></span>

         <span data-ttu-id="895d4-132">File di configurazione di runtime dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="895d4-132">The application's runtime configuration file.</span></span> <span data-ttu-id="895d4-133">Identifica la versione di .NET Core che è stato compilato l'applicazione per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="895d4-133">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="895d4-134">Per ulteriori informazioni, vedere [i file di configurazione di Runtime](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="895d4-134">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>  

   ![Finestra della console con file pubblicati](media/publishing-with-visual-studio/publishedfiles.png)

<span data-ttu-id="895d4-136">Il processo di pubblicazione crea una distribuzione dipendente dal framework. Si tratta di un tipo di distribuzione in cui l'applicazione pubblicata potrà essere eseguita su qualsiasi piattaforma supportata da .NET Core, se installato nel sistema.</span><span class="sxs-lookup"><span data-stu-id="895d4-136">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application will run on any platform supported by .NET Core with .NET Core installed on the system.</span></span> <span data-ttu-id="895d4-137">Gli utenti possono eseguire l'applicazione attivando il comando `dotnet HelloWorld.dll` da una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="895d4-137">Users can run your application by issuing the `dotnet HelloWorld.dll` command from a console window.</span></span>

<span data-ttu-id="895d4-138">Per altre informazioni sulla pubblicazione e la distribuzione di applicazioni .NET Core, vedere [Distribuzione di applicazioni .NET Core](../../core/deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="895d4-138">For more information on publishing and deploying .NET Core applications, see [.NET Core Application Deployment](../../core/deploying/index.md).</span></span>
