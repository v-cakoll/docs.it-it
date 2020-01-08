---
title: Pubblicare l'applicazione Hello World .NET Core con Visual Studio
description: Con la pubblicazione viene creato il set di file necessari per eseguire l'applicazione .NET Core.
author: BillWagner
ms.author: wiwagn
ms.date: 12/10/2019
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 44e799ad76848278e3731b26b14a18e7fade760f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75343170"
---
# <a name="publish-your-net-core-hello-world-application-with-visual-studio"></a><span data-ttu-id="38dc2-103">Pubblicare l'applicazione Hello World .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="38dc2-103">Publish your .NET Core Hello World application with Visual Studio</span></span>

<span data-ttu-id="38dc2-104">In [creare un'applicazione Hello World con .NET Core in Visual Studio](with-visual-studio.md)è stata compilata un'applicazione console Hello World.</span><span class="sxs-lookup"><span data-stu-id="38dc2-104">In [Create a Hello World application with .NET Core in Visual Studio](with-visual-studio.md), you built a Hello World console application.</span></span> <span data-ttu-id="38dc2-105">Per [eseguire il debug dell'applicazione Hello World con Visual Studio](debugging-with-visual-studio.md), è stato testato con il debugger di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="38dc2-105">In [Debug your Hello World application with Visual Studio](debugging-with-visual-studio.md), you tested it using the Visual Studio debugger.</span></span> <span data-ttu-id="38dc2-106">A questo punto è sicuro che l'applicazione funziona nel modo previsto ed è possibile pubblicarla in modo che possa essere eseguita da altri utenti.</span><span class="sxs-lookup"><span data-stu-id="38dc2-106">Now that you're sure that it works as expected, you can publish it so that other users can run it.</span></span> <span data-ttu-id="38dc2-107">Con la pubblicazione viene creato il set di file necessari per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="38dc2-107">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="38dc2-108">Per distribuire i file, copiarli nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="38dc2-108">To deploy the files, copy them to the target machine.</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="38dc2-109">Pubblicare l'app</span><span class="sxs-lookup"><span data-stu-id="38dc2-109">Publish the app</span></span>

1. <span data-ttu-id="38dc2-110">Verificare che Visual Studio compili la versione di rilascio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="38dc2-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="38dc2-111">Se necessario, modificare la configurazione di compilazione nella barra degli strumenti da **Debug** in **Rilascio**.</span><span class="sxs-lookup"><span data-stu-id="38dc2-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![Barra degli strumenti Visual Studio con la build di rilascio selezionata](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="38dc2-113">Fare clic con il pulsante destro del mouse sul progetto **HelloWorld**, non sulla soluzione HelloWorld, e scegliere **Pubblica** dal menu.</span><span class="sxs-lookup"><span data-stu-id="38dc2-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span> <span data-ttu-id="38dc2-114">È anche possibile selezionare **Publish HelloWorld** dal menu Main **Build** .</span><span class="sxs-lookup"><span data-stu-id="38dc2-114">(You can also select **Publish HelloWorld** from the main **Build** menu.)</span></span>

   ![Menu di scelta rapida Pubblica di Visual Studio](media/publishing-with-visual-studio/publish-context-menu.png)
   
1. <span data-ttu-id="38dc2-116">Nella pagina selezionare **una destinazione di pubblicazione** selezionare **cartella**, quindi selezionare **Crea profilo**.</span><span class="sxs-lookup"><span data-stu-id="38dc2-116">On the **Pick a publish target** page, select **Folder**, and then select **Create Profile**.</span></span>

   ![Selezionare una destinazione di pubblicazione in Visual Studio](media/publishing-with-visual-studio/pick-publish-target.png)
   
1. <span data-ttu-id="38dc2-118">Nella pagina **pubblica** selezionare **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="38dc2-118">On the **Publish** page, select **Publish**.</span></span>

   ![Finestra Pubblica di Visual Studio](media/publishing-with-visual-studio/publish-page.png)
   
## <a name="inspect-the-files"></a><span data-ttu-id="38dc2-120">Esaminare i file</span><span class="sxs-lookup"><span data-stu-id="38dc2-120">Inspect the files</span></span>

<span data-ttu-id="38dc2-121">Il processo di pubblicazione crea una distribuzione dipendente dal Framework, ovvero un tipo di distribuzione in cui l'applicazione pubblicata viene eseguita su qualsiasi piattaforma supportata da .NET Core con .NET Core installato nel sistema.</span><span class="sxs-lookup"><span data-stu-id="38dc2-121">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on any platform supported by .NET Core with .NET Core installed on the system.</span></span> <span data-ttu-id="38dc2-122">Gli utenti possono eseguire l'app pubblicata facendo doppio clic sul file eseguibile o eseguendo il comando `dotnet HelloWorld.dll` da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="38dc2-122">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="38dc2-123">Nei passaggi seguenti verranno esaminati i file creati dal processo di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="38dc2-123">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="38dc2-124">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="38dc2-124">Open a command prompt.</span></span>

   <span data-ttu-id="38dc2-125">Un modo per aprire un prompt dei comandi consiste nell'immettere un **prompt dei comandi** (o in breve **cmd** ) nella casella di ricerca della barra delle applicazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="38dc2-125">One way to open a command prompt is to enter **Command Prompt** (or **cmd** for short) in the search box on the Windows taskbar.</span></span> <span data-ttu-id="38dc2-126">Selezionare l'app desktop **prompt dei comandi** oppure premere **invio** se è già selezionata nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="38dc2-126">Select the **Command Prompt** desktop app, or press **Enter** if it's already selected in the search results.</span></span>

1. <span data-ttu-id="38dc2-127">Passare all'applicazione pubblicata nella sottodirectory *bin\Release\netcoreapp3.1\publish* della directory del progetto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="38dc2-127">Navigate to the published application in the *bin\Release\netcoreapp3.1\publish* subdirectory of the application's project directory.</span></span>

   ![Finestra della console con file pubblicati](media/publishing-with-visual-studio/published-files-output.png)

   <span data-ttu-id="38dc2-129">Come illustrato nell'immagine, l'output pubblicato include i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="38dc2-129">As the image shows, the published output includes the following files:</span></span>

      * <span data-ttu-id="38dc2-130">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="38dc2-130">*HelloWorld.deps.json*</span></span>

         <span data-ttu-id="38dc2-131">Si tratta del file delle dipendenze di runtime dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="38dc2-131">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="38dc2-132">Definisce i componenti di .NET Core e le librerie (inclusa la libreria a collegamento dinamico che contiene l'applicazione) necessari per eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="38dc2-132">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="38dc2-133">Per ulteriori informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="38dc2-133">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

      * <span data-ttu-id="38dc2-134">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="38dc2-134">*HelloWorld.dll*</span></span>

         <span data-ttu-id="38dc2-135">Si tratta della versione della [distribuzione dipendente dal Framework](../deploying/deploy-with-cli.md#framework-dependent-deployment) dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="38dc2-135">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="38dc2-136">Per eseguire questa libreria a collegamento dinamico, immettere `dotnet HelloWorld.dll` al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="38dc2-136">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span>

      * <span data-ttu-id="38dc2-137">*HelloWorld. exe*</span><span class="sxs-lookup"><span data-stu-id="38dc2-137">*HelloWorld.exe*</span></span>
      
         <span data-ttu-id="38dc2-138">Si tratta della versione [eseguibile dipendente dal Framework](../deploying/deploy-with-cli.md#framework-dependent-executable) dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="38dc2-138">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="38dc2-139">Per eseguirlo, immettere `HelloWorld.exe` al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="38dc2-139">To run it, enter `HelloWorld.exe` at a command prompt.</span></span>

      * <span data-ttu-id="38dc2-140">*HelloWorld.pdb* (facoltativo per la distribuzione)</span><span class="sxs-lookup"><span data-stu-id="38dc2-140">*HelloWorld.pdb* (optional for deployment)</span></span>

         <span data-ttu-id="38dc2-141">Questo è il file di simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="38dc2-141">This is the debug symbols file.</span></span> <span data-ttu-id="38dc2-142">Non è necessario distribuire tale file insieme all'applicazione, anche se è consigliabile salvarlo nel caso in cui sia necessario eseguire il debug della versione pubblicata dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="38dc2-142">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

      * <span data-ttu-id="38dc2-143">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="38dc2-143">*HelloWorld.runtimeconfig.json*</span></span>

         <span data-ttu-id="38dc2-144">Questo è il file di configurazione di runtime dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="38dc2-144">This is the application's runtime configuration file.</span></span> <span data-ttu-id="38dc2-145">Identifica la versione di .NET Core per la quale è stata compilata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="38dc2-145">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="38dc2-146">Per ulteriori informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="38dc2-146">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="38dc2-147">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="38dc2-147">Additional resources</span></span>

- [<span data-ttu-id="38dc2-148">Distribuzione di applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="38dc2-148">.NET Core application deployment</span></span>](../deploying/index.md)
