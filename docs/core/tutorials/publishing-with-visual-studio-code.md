---
title: Pubblicare un'applicazione console .NET Core usando Visual Studio Code
description: La pubblicazione crea il set di file necessari per eseguire un'applicazione .NET Core.
ms.date: 07/04/2020
ms.openlocfilehash: 8fd9975e8a88704b9dea45b40127c8dc03f7d09f
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051883"
---
# <a name="tutorial-publish-a-net-core-console-application-using-visual-studio-code"></a><span data-ttu-id="05118-103">Esercitazione: pubblicare un'applicazione console .NET Core usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="05118-103">Tutorial: Publish a .NET Core console application using Visual Studio Code</span></span>

<span data-ttu-id="05118-104">Questa esercitazione illustra come pubblicare un'app console in modo che gli altri utenti possano eseguirla.</span><span class="sxs-lookup"><span data-stu-id="05118-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="05118-105">La pubblicazione crea il set di file necessari per eseguire un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="05118-105">Publishing creates the set of files that are needed to run an application.</span></span> <span data-ttu-id="05118-106">Per distribuire i file, copiarli nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="05118-106">To deploy the files, copy them to the target machine.</span></span>

<span data-ttu-id="05118-107">Il interfaccia della riga di comando di .NET Core viene usato per pubblicare l'app, quindi è possibile seguire questa esercitazione con un editor di codice diverso da Visual Studio Code se lo si preferisce.</span><span class="sxs-lookup"><span data-stu-id="05118-107">The .NET Core CLI is used to publish the app, so you can follow this tutorial with a code editor other than Visual Studio Code if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="05118-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="05118-108">Prerequisites</span></span>

- <span data-ttu-id="05118-109">Questa esercitazione funziona con l'app console creata in [creare un'applicazione console .NET Core in Visual Studio Code](with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="05118-109">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="05118-110">Pubblicare l'app</span><span class="sxs-lookup"><span data-stu-id="05118-110">Publish the app</span></span>

1. <span data-ttu-id="05118-111">Avviare Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="05118-111">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="05118-112">Aprire la cartella del progetto *HelloWorld* creata in [creare un'applicazione console .net core in Visual Studio Code](with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="05118-112">Open the *HelloWorld* project folder that you created in [Create a .NET Core console application in Visual Studio Code](with-visual-studio-code.md).</span></span>

1. <span data-ttu-id="05118-113">Scegliere **Visualizza**  >  **terminale** dal menu principale.</span><span class="sxs-lookup"><span data-stu-id="05118-113">Choose **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="05118-114">Il terminale verrà aperto nella cartella *HelloWorld* .</span><span class="sxs-lookup"><span data-stu-id="05118-114">The terminal opens in the *HelloWorld* folder.</span></span>

1. <span data-ttu-id="05118-115">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="05118-115">Run the following command:</span></span>

   ```dotnetcli
   dotnet publish --configuration Release
   ```

   <span data-ttu-id="05118-116">La configurazione di compilazione predefinita è *debug*, pertanto questo comando specifica la configurazione della build di *rilascio* .</span><span class="sxs-lookup"><span data-stu-id="05118-116">The default build configuration is *Debug*, so this command specifies the *Release* build configuration.</span></span> <span data-ttu-id="05118-117">L'output della configurazione della build di rilascio ha informazioni minime sul debug simbolico ed è completamente ottimizzato.</span><span class="sxs-lookup"><span data-stu-id="05118-117">The output from the Release build configuration has minimal symbolic debug information and is fully optimized.</span></span>

   <span data-ttu-id="05118-118">L'output del comando è simile a quello dell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="05118-118">The command output is similar to the following example:</span></span>

   ```
   Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

   Determining projects to restore...
   All projects are up-to-date for restore.
   HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\HelloWorld.dll
   HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

## <a name="inspect-the-files"></a><span data-ttu-id="05118-119">Esaminare i file</span><span class="sxs-lookup"><span data-stu-id="05118-119">Inspect the files</span></span>

<span data-ttu-id="05118-120">Per impostazione predefinita, il processo di pubblicazione crea una distribuzione dipendente dal Framework, ovvero un tipo di distribuzione in cui l'applicazione pubblicata viene eseguita in un computer in cui è installato il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="05118-120">By default, the publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on a machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="05118-121">Per eseguire l'app pubblicata, è possibile usare il file eseguibile o eseguire il `dotnet HelloWorld.dll` comando da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="05118-121">To run the published app you can use the executable file or run the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="05118-122">Nei passaggi seguenti verranno esaminati i file creati dal processo di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="05118-122">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="05118-123">Selezionare **Esplora** sulla barra di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="05118-123">Select the **Explorer** in the left navigation bar.</span></span>

1. <span data-ttu-id="05118-124">Espandere *bin/Release/netcoreapp 3.1/Publish*.</span><span class="sxs-lookup"><span data-stu-id="05118-124">Expand *bin/Release/netcoreapp3.1/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-code/published-files-output.png" alt-text="Esplora file pubblicati":::

   <span data-ttu-id="05118-126">Come illustrato nell'immagine, l'output pubblicato include i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="05118-126">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="05118-127">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="05118-127">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="05118-128">Si tratta del file delle dipendenze di runtime dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="05118-128">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="05118-129">Definisce i componenti di .NET Core e le librerie (inclusa la libreria a collegamento dinamico che contiene l'applicazione) necessari per eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="05118-129">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="05118-130">Per ulteriori informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="05118-130">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="05118-131">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="05118-131">*HelloWorld.dll*</span></span>

      <span data-ttu-id="05118-132">Si tratta della versione della [distribuzione dipendente dal Framework](../deploying/deploy-with-cli.md#framework-dependent-deployment) dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="05118-132">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="05118-133">Per eseguire questa libreria a collegamento dinamico, immettere `dotnet HelloWorld.dll` al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="05118-133">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="05118-134">Questo metodo di esecuzione dell'app funziona in qualsiasi piattaforma in cui è installato il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="05118-134">This method of running the app works on any platform that has the .NET Core runtime installed.</span></span>

   * <span data-ttu-id="05118-135">*HelloWorld.exe* (*HelloWorld* in Linux, non creato in MacOS).</span><span class="sxs-lookup"><span data-stu-id="05118-135">*HelloWorld.exe* (*HelloWorld* on Linux, not created on macOS.)</span></span>

      <span data-ttu-id="05118-136">Si tratta della versione [eseguibile dipendente dal Framework](../deploying/deploy-with-cli.md#framework-dependent-executable) dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="05118-136">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="05118-137">Il file è specifico del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="05118-137">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="05118-138">*HelloWorld.pdb* (facoltativo per la distribuzione)</span><span class="sxs-lookup"><span data-stu-id="05118-138">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="05118-139">Questo è il file di simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="05118-139">This is the debug symbols file.</span></span> <span data-ttu-id="05118-140">Non è necessario distribuire tale file insieme all'applicazione, anche se è consigliabile salvarlo nel caso in cui sia necessario eseguire il debug della versione pubblicata dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="05118-140">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="05118-141">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="05118-141">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="05118-142">Questo è il file di configurazione in fase di esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="05118-142">This is the application's run-time configuration file.</span></span> <span data-ttu-id="05118-143">Identifica la versione di .NET Core per la quale è stata compilata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="05118-143">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="05118-144">È anche possibile aggiungere opzioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="05118-144">You can also add configuration options to it.</span></span> <span data-ttu-id="05118-145">Per altre informazioni, vedere Impostazioni di configurazione della fase di [esecuzione di .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="05118-145">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="05118-146">Eseguire l'app pubblicata</span><span class="sxs-lookup"><span data-stu-id="05118-146">Run the published app</span></span>

1. <span data-ttu-id="05118-147">In **Esplora risorse**fare clic con il pulsante destro del mouse sulla cartella *Publish* (<kbd>CTRL +</kbd>clic su MacOS) e scegliere **Apri in terminale**.</span><span class="sxs-lookup"><span data-stu-id="05118-147">In **Explorer**, right-click the *publish* folder (<kbd>Ctrl</kbd>-click on macOS), and select **Open in Terminal**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-code/open-in-terminal.png" alt-text="Menu di scelta rapida che mostra Apri nel terminale":::

1. <span data-ttu-id="05118-149">In Windows o Linux eseguire l'app usando il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="05118-149">On Windows or Linux, run the app by using the executable.</span></span>

   1. <span data-ttu-id="05118-150">In Windows immettere `.\HelloWorld.exe` e premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05118-150">On Windows, enter `.\HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="05118-151">In Linux immettere `./HelloWorld` e premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05118-151">On Linux, enter `./HelloWorld` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="05118-152">Immettere un nome in risposta al prompt e premere un tasto qualsiasi per uscire.</span><span class="sxs-lookup"><span data-stu-id="05118-152">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="05118-153">Eseguire l'app su qualsiasi piattaforma usando il [`dotnet`](../tools/dotnet.md) comando:</span><span class="sxs-lookup"><span data-stu-id="05118-153">On any platform, run the app by using the  [`dotnet`](../tools/dotnet.md) command:</span></span>

   1. <span data-ttu-id="05118-154">Immettere `dotnet HelloWorld.dll` e premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05118-154">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="05118-155">Immettere un nome in risposta al prompt e premere un tasto qualsiasi per uscire.</span><span class="sxs-lookup"><span data-stu-id="05118-155">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="05118-156">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="05118-156">Additional resources</span></span>

- [<span data-ttu-id="05118-157">Distribuzione di applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="05118-157">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="05118-158">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="05118-158">Next steps</span></span>

<span data-ttu-id="05118-159">In questa esercitazione è stata pubblicata un'app console.</span><span class="sxs-lookup"><span data-stu-id="05118-159">In this tutorial, you published a console app.</span></span> <span data-ttu-id="05118-160">Nell'esercitazione successiva verrà creata una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="05118-160">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="05118-161">Creare una libreria di .NET Standard in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="05118-161">Create a .NET Standard library in Visual Studio Code</span></span>](library-with-visual-studio-code.md)
