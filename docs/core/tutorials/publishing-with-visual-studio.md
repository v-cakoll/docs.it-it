---
title: Pubblicare l'applicazione Hello World .NET Core con Visual Studio
description: Con la pubblicazione viene creato il set di file necessari per eseguire l'applicazione .NET Core.
author: BillWagner
ms.author: wiwagn
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 745fb2af332afa278c78ec9baeea7230fe725c02
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241494"
---
# <a name="tutorial-publish-a-net-core-console-application-with-visual-studio"></a><span data-ttu-id="178f8-103">Esercitazione: pubblicare un'applicazione console .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="178f8-103">Tutorial: Publish a .NET Core console application with Visual Studio</span></span>

<span data-ttu-id="178f8-104">Questa esercitazione illustra come pubblicare un'app console in modo che gli altri utenti possano eseguirla.</span><span class="sxs-lookup"><span data-stu-id="178f8-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="178f8-105">Con la pubblicazione viene creato il set di file necessari per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="178f8-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="178f8-106">Per distribuire i file, copiarli nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="178f8-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="178f8-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="178f8-107">Prerequisites</span></span>

- <span data-ttu-id="178f8-108">Questa esercitazione funziona con l'app console creata in [creare un'applicazione console .NET Core in Visual Studio 2019](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="178f8-108">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="178f8-109">Pubblicare l'app</span><span class="sxs-lookup"><span data-stu-id="178f8-109">Publish the app</span></span>

1. <span data-ttu-id="178f8-110">Verificare che Visual Studio compili la versione di rilascio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="178f8-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="178f8-111">Se necessario, modificare la configurazione di compilazione nella barra degli strumenti da **Debug** in **Rilascio**.</span><span class="sxs-lookup"><span data-stu-id="178f8-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![Barra degli strumenti Visual Studio con la build di rilascio selezionata](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="178f8-113">Fare clic con il pulsante destro del mouse sul progetto **HelloWorld** (non sulla soluzione HelloWorld) e scegliere **pubblica** dal menu.</span><span class="sxs-lookup"><span data-stu-id="178f8-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span>

   ![Menu di scelta rapida Pubblica di Visual Studio](media/publishing-with-visual-studio/publish-context-menu.png)

1. <span data-ttu-id="178f8-115">Nella scheda **destinazione** della pagina **pubblica** Selezionare **cartella**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="178f8-115">On the **Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   ![Selezionare una destinazione di pubblicazione in Visual Studio](media/publishing-with-visual-studio/pick-publish-target.png)

1. <span data-ttu-id="178f8-117">Nella scheda **percorso** della pagina **pubblica** Selezionare **fine**.</span><span class="sxs-lookup"><span data-stu-id="178f8-117">On the **Location** tab of the **Publish** page, select **Finish**.</span></span>

   ![Scheda percorso pagina di pubblicazione di Visual Studio](media/publishing-with-visual-studio/publish-page-loc-tab.png)

1. <span data-ttu-id="178f8-119">Nella scheda **pubblica** della finestra **pubblica** Selezionare **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="178f8-119">On the **Publish** tab of the **Publish** window, select **Publish**.</span></span>

   ![Finestra Pubblica di Visual Studio](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a><span data-ttu-id="178f8-121">Esaminare i file</span><span class="sxs-lookup"><span data-stu-id="178f8-121">Inspect the files</span></span>

<span data-ttu-id="178f8-122">Il processo di pubblicazione crea una distribuzione dipendente dal Framework, ovvero un tipo di distribuzione in cui l'applicazione pubblicata viene eseguita nel computer in cui è installato il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="178f8-122">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="178f8-123">Gli utenti possono eseguire l'app pubblicata facendo doppio clic sul file eseguibile o eseguendo il `dotnet HelloWorld.dll` comando da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="178f8-123">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="178f8-124">Nei passaggi seguenti verranno esaminati i file creati dal processo di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="178f8-124">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="178f8-125">In **Esplora soluzioni**selezionare **Mostra tutti i file**.</span><span class="sxs-lookup"><span data-stu-id="178f8-125">In **Solution Explorer**, select **Show all files**.</span></span>

1. <span data-ttu-id="178f8-126">Nella cartella del progetto espandere *bin/Release/netcoreapp 3.1/Publish*.</span><span class="sxs-lookup"><span data-stu-id="178f8-126">In the project folder, expand *bin/Release/netcoreapp3.1/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="Esplora soluzioni la visualizzazione dei file pubblicati":::

   <span data-ttu-id="178f8-128">Come illustrato nell'immagine, l'output pubblicato include i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="178f8-128">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="178f8-129">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="178f8-129">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="178f8-130">Si tratta del file delle dipendenze di runtime dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="178f8-130">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="178f8-131">Definisce i componenti di .NET Core e le librerie (inclusa la libreria a collegamento dinamico che contiene l'applicazione) necessari per eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="178f8-131">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="178f8-132">Per ulteriori informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="178f8-132">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="178f8-133">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="178f8-133">*HelloWorld.dll*</span></span>

      <span data-ttu-id="178f8-134">Si tratta della versione della [distribuzione dipendente dal Framework](../deploying/deploy-with-cli.md#framework-dependent-deployment) dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="178f8-134">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="178f8-135">Per eseguire questa libreria a collegamento dinamico, immettere `dotnet HelloWorld.dll` al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="178f8-135">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="178f8-136">Questo metodo di esecuzione dell'app funziona in qualsiasi piattaforma in cui è installato il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="178f8-136">This method of running the app works on any platform that has the .NET Core runtime installed.</span></span>

   * <span data-ttu-id="178f8-137">*HelloWorld. exe*</span><span class="sxs-lookup"><span data-stu-id="178f8-137">*HelloWorld.exe*</span></span>

      <span data-ttu-id="178f8-138">Si tratta della versione [eseguibile dipendente dal Framework](../deploying/deploy-with-cli.md#framework-dependent-executable) dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="178f8-138">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="178f8-139">Per eseguirlo, immettere `HelloWorld.exe` al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="178f8-139">To run it, enter `HelloWorld.exe` at a command prompt.</span></span> <span data-ttu-id="178f8-140">Il file è specifico del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="178f8-140">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="178f8-141">*HelloWorld.pdb* (facoltativo per la distribuzione)</span><span class="sxs-lookup"><span data-stu-id="178f8-141">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="178f8-142">Questo è il file di simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="178f8-142">This is the debug symbols file.</span></span> <span data-ttu-id="178f8-143">Non è necessario distribuire tale file insieme all'applicazione, anche se è consigliabile salvarlo nel caso in cui sia necessario eseguire il debug della versione pubblicata dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="178f8-143">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="178f8-144">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="178f8-144">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="178f8-145">Questo è il file di configurazione in fase di esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="178f8-145">This is the application's run-time configuration file.</span></span> <span data-ttu-id="178f8-146">Identifica la versione di .NET Core per la quale è stata compilata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="178f8-146">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="178f8-147">È anche possibile aggiungere opzioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="178f8-147">You can also add configuration options to it.</span></span> <span data-ttu-id="178f8-148">Per altre informazioni, vedere Impostazioni di configurazione della fase di [esecuzione di .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="178f8-148">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="178f8-149">Eseguire l'app pubblicata</span><span class="sxs-lookup"><span data-stu-id="178f8-149">Run the published app</span></span>

1. <span data-ttu-id="178f8-150">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sulla cartella *Publish* e scegliere **Copia percorso completo**.</span><span class="sxs-lookup"><span data-stu-id="178f8-150">In **Solution Explorer**, right-click the *publish* folder, and select **Copy Full Path**.</span></span>

1. <span data-ttu-id="178f8-151">Aprire un prompt dei comandi e passare alla cartella di *pubblicazione* .</span><span class="sxs-lookup"><span data-stu-id="178f8-151">Open a command prompt and navigate to the *publish* folder.</span></span> <span data-ttu-id="178f8-152">Immettere `cd` e incollare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="178f8-152">Enter `cd` and then paste the full path.</span></span> <span data-ttu-id="178f8-153">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="178f8-153">For example:</span></span>

   ```
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. <span data-ttu-id="178f8-154">Eseguire l'app usando il file eseguibile:</span><span class="sxs-lookup"><span data-stu-id="178f8-154">Run the app by using the executable:</span></span>

   1. <span data-ttu-id="178f8-155">Immettere `HelloWorld.exe` e premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="178f8-155">Enter `HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="178f8-156">Immettere un nome in risposta al prompt e premere un tasto qualsiasi per uscire.</span><span class="sxs-lookup"><span data-stu-id="178f8-156">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="178f8-157">Eseguire l'app usando il `dotnet` comando:</span><span class="sxs-lookup"><span data-stu-id="178f8-157">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="178f8-158">Immettere `dotnet HelloWorld.dll` e premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="178f8-158">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="178f8-159">Immettere un nome in risposta al prompt e premere un tasto qualsiasi per uscire.</span><span class="sxs-lookup"><span data-stu-id="178f8-159">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="178f8-160">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="178f8-160">Additional resources</span></span>

- [<span data-ttu-id="178f8-161">Distribuzione di applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="178f8-161">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="178f8-162">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="178f8-162">Next steps</span></span>

<span data-ttu-id="178f8-163">In questa esercitazione è stata pubblicata un'app console.</span><span class="sxs-lookup"><span data-stu-id="178f8-163">In this tutorial, you published a console app.</span></span> <span data-ttu-id="178f8-164">Nell'esercitazione successiva verrà creata una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="178f8-164">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="178f8-165">Creare una libreria .NET Standard in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="178f8-165">Create a .NET Standard library in Visual Studio</span></span>](library-with-visual-studio.md)
