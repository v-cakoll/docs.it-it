---
title: Pubblicare un'applicazione console .NET Core usando Visual Studio per Mac
description: La pubblicazione crea il set di file necessari per eseguire un'applicazione .NET Core.
ms.date: 06/08/2020
ms.openlocfilehash: 67762481d3a56b8473e643f71b8df909b6e54fc6
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84713665"
---
# <a name="tutorial-publish-a-net-core-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="eedc4-103">Esercitazione: pubblicare un'applicazione console .NET Core usando Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="eedc4-103">Tutorial: Publish a .NET Core console application using Visual Studio for Mac</span></span>

<span data-ttu-id="eedc4-104">Questa esercitazione illustra come pubblicare un'app console in modo che gli altri utenti possano eseguirla.</span><span class="sxs-lookup"><span data-stu-id="eedc4-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="eedc4-105">Con la pubblicazione viene creato il set di file necessari per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eedc4-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="eedc4-106">Per distribuire i file, copiarli nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="eedc4-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eedc4-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="eedc4-107">Prerequisites</span></span>

- <span data-ttu-id="eedc4-108">Questa esercitazione funziona con l'app console creata in [creare un'applicazione console .NET Core in Visual Studio per Mac](with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="eedc4-108">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio for Mac](with-visual-studio-mac.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="eedc4-109">Pubblicare l'app</span><span class="sxs-lookup"><span data-stu-id="eedc4-109">Publish the app</span></span>

1. <span data-ttu-id="eedc4-110">Avviare Visual Studio per Mac.</span><span class="sxs-lookup"><span data-stu-id="eedc4-110">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="eedc4-111">Aprire il progetto HelloWorld creato in [creare un'applicazione console .NET Core in Visual Studio per Mac](with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="eedc4-111">Open the HelloWorld project that you created in [Create a .NET Core console application in Visual Studio for Mac](with-visual-studio-mac.md).</span></span>

1. <span data-ttu-id="eedc4-112">Verificare che Visual Studio compili la versione di rilascio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eedc4-112">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="eedc4-113">Se necessario, modificare la configurazione di compilazione nella barra degli strumenti da **Debug** in **Rilascio**.</span><span class="sxs-lookup"><span data-stu-id="eedc4-113">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-mac/toolbar-release.png" alt-text="Barra degli strumenti Visual Studio con la build di rilascio selezionata":::

1. <span data-ttu-id="eedc4-115">Dal menu principale scegliere **Compila**  >  **pubblicazione nella cartella...**.</span><span class="sxs-lookup"><span data-stu-id="eedc4-115">From the main menu, choose **Build** > **Publish to Folder...**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-context-menu.png" alt-text="Menu di scelta rapida Pubblica di Visual Studio":::

1. <span data-ttu-id="eedc4-117">Nella finestra **di dialogo pubblica nella cartella** selezionare **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="eedc4-117">In the **Publish to Folder** dialog, select **Publish**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-to-folder-dialog.png" alt-text="Finestra di dialogo pubblica nella cartella di Visual Studio":::

   <span data-ttu-id="eedc4-119">Verrà visualizzata la cartella publish, che mostra i file creati.</span><span class="sxs-lookup"><span data-stu-id="eedc4-119">The publish folder opens, showing the files that were created.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-folder.png" alt-text="cartella di pubblicazione":::

1. <span data-ttu-id="eedc4-121">Selezionare l'icona a forma di ingranaggio e selezionare **copia "pubblica" come nome percorso** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="eedc4-121">Select the gear icon, and select **Copy "publish" as Pathname** from the context menu.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-mac/copy-path.png" alt-text="Copia il percorso della cartella di pubblicazione":::

## <a name="inspect-the-files"></a><span data-ttu-id="eedc4-123">Esaminare i file</span><span class="sxs-lookup"><span data-stu-id="eedc4-123">Inspect the files</span></span>

<span data-ttu-id="eedc4-124">Il processo di pubblicazione crea una distribuzione dipendente dal Framework, ovvero un tipo di distribuzione in cui l'applicazione pubblicata viene eseguita in un computer in cui è installato il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="eedc4-124">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on a machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="eedc4-125">Gli utenti possono eseguire l'app pubblicata eseguendo il `dotnet HelloWorld.dll` comando da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="eedc4-125">Users can run the published app by running the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="eedc4-126">Come illustrato nell'immagine precedente, l'output pubblicato include i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="eedc4-126">As the preceding image shows, the published output includes the following files:</span></span>

* <span data-ttu-id="eedc4-127">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="eedc4-127">*HelloWorld.deps.json*</span></span>

  <span data-ttu-id="eedc4-128">Si tratta del file delle dipendenze di runtime dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eedc4-128">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="eedc4-129">Definisce i componenti di .NET Core e le librerie (inclusa la libreria a collegamento dinamico che contiene l'applicazione) necessari per eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="eedc4-129">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="eedc4-130">Per ulteriori informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="eedc4-130">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

* <span data-ttu-id="eedc4-131">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="eedc4-131">*HelloWorld.dll*</span></span>

   <span data-ttu-id="eedc4-132">Si tratta della versione della [distribuzione dipendente dal Framework](../deploying/deploy-with-cli.md#framework-dependent-deployment) dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eedc4-132">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="eedc4-133">Per eseguire questa libreria a collegamento dinamico, immettere `dotnet HelloWorld.dll` al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="eedc4-133">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="eedc4-134">Questo metodo di esecuzione dell'app funziona in qualsiasi piattaforma in cui è installato il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="eedc4-134">This method of running the app works on any platform that has the .NET Core runtime installed.</span></span>

* <span data-ttu-id="eedc4-135">*HelloWorld.pdb* (facoltativo per la distribuzione)</span><span class="sxs-lookup"><span data-stu-id="eedc4-135">*HelloWorld.pdb* (optional for deployment)</span></span>

   <span data-ttu-id="eedc4-136">Questo è il file di simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="eedc4-136">This is the debug symbols file.</span></span> <span data-ttu-id="eedc4-137">Non è necessario distribuire tale file insieme all'applicazione, anche se è consigliabile salvarlo nel caso in cui sia necessario eseguire il debug della versione pubblicata dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eedc4-137">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

* <span data-ttu-id="eedc4-138">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="eedc4-138">*HelloWorld.runtimeconfig.json*</span></span>

   <span data-ttu-id="eedc4-139">Questo è il file di configurazione in fase di esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eedc4-139">This is the application's run-time configuration file.</span></span> <span data-ttu-id="eedc4-140">Identifica la versione di .NET Core per la quale è stata compilata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eedc4-140">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="eedc4-141">È anche possibile aggiungere opzioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="eedc4-141">You can also add configuration options to it.</span></span> <span data-ttu-id="eedc4-142">Per altre informazioni, vedere Impostazioni di configurazione della fase di [esecuzione di .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="eedc4-142">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="eedc4-143">Eseguire l'app pubblicata</span><span class="sxs-lookup"><span data-stu-id="eedc4-143">Run the published app</span></span>

1. <span data-ttu-id="eedc4-144">Aprire un terminale e passare alla cartella di *pubblicazione* .</span><span class="sxs-lookup"><span data-stu-id="eedc4-144">Open a terminal and navigate to the *publish* folder.</span></span> <span data-ttu-id="eedc4-145">A tale scopo, immettere `cd` e incollare il percorso copiato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="eedc4-145">To do that, enter `cd` and then paste the path that you copied earlier.</span></span> <span data-ttu-id="eedc4-146">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="eedc4-146">For example:</span></span>

   ```
   cd ~/Projects/HelloWorld/HelloWorld/bin/Release/netcoreapp3.1/publish/
   ```

1. <span data-ttu-id="eedc4-147">Eseguire l'app usando il `dotnet` comando:</span><span class="sxs-lookup"><span data-stu-id="eedc4-147">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="eedc4-148">Immettere `dotnet HelloWorld.dll` e premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="eedc4-148">Enter `dotnet HelloWorld.dll` and press <kbd>enter</kbd>.</span></span>

   1. <span data-ttu-id="eedc4-149">Immettere un nome in risposta al prompt e premere un tasto qualsiasi per uscire.</span><span class="sxs-lookup"><span data-stu-id="eedc4-149">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="eedc4-150">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="eedc4-150">Additional resources</span></span>

- [<span data-ttu-id="eedc4-151">Distribuzione di applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="eedc4-151">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="eedc4-152">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="eedc4-152">Next steps</span></span>

<span data-ttu-id="eedc4-153">In questa esercitazione è stata pubblicata un'app console.</span><span class="sxs-lookup"><span data-stu-id="eedc4-153">In this tutorial, you published a console app.</span></span> <span data-ttu-id="eedc4-154">Nell'esercitazione successiva verrà creata una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="eedc4-154">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="eedc4-155">Creare una libreria di .NET Standard in Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="eedc4-155">Create a .NET Standard library in Visual Studio for mac</span></span>](library-with-visual-studio-mac.md)
