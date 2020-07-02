---
title: Installare .NET Core in macOS
description: Informazioni sulle versioni di macOS in cui è possibile installare .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 06/25/2020
ms.openlocfilehash: bb1a0fa24e2f6e8850cbe59378793ff846f04ba9
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85804491"
---
# <a name="install-net-core-on-macos"></a><span data-ttu-id="f397f-103">Installare .NET Core in macOS</span><span class="sxs-lookup"><span data-stu-id="f397f-103">Install .NET Core on macOS</span></span>

> [!div class="op_single_selector"]
>
> - [Eseguire l'installazione in Windows](windows.md)
> - [Eseguire l'installazione in macOS](macos.md)
> - [Installare in Linux](linux.md)

<span data-ttu-id="f397f-107">Questo articolo illustra come installare .NET Core in macOS.</span><span class="sxs-lookup"><span data-stu-id="f397f-107">In this article, you'll learn how to install .NET Core on macOS.</span></span> <span data-ttu-id="f397f-108">.NET Core è costituito dal runtime e dall'SDK.</span><span class="sxs-lookup"><span data-stu-id="f397f-108">.NET Core is made up of the runtime and the SDK.</span></span> <span data-ttu-id="f397f-109">Il runtime viene usato per eseguire un'app .NET Core e può essere incluso o meno con l'app.</span><span class="sxs-lookup"><span data-stu-id="f397f-109">The runtime is used to run a .NET Core app and may or may not be included with the app.</span></span> <span data-ttu-id="f397f-110">L'SDK viene usato per creare app e librerie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f397f-110">The SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="f397f-111">Il runtime di .NET Core viene sempre installato con l'SDK.</span><span class="sxs-lookup"><span data-stu-id="f397f-111">The .NET Core runtime is always installed with the SDK.</span></span>

<span data-ttu-id="f397f-112">La versione più recente di .NET Core è 3,1.</span><span class="sxs-lookup"><span data-stu-id="f397f-112">The latest version of .NET Core is 3.1.</span></span>

[<span data-ttu-id="f397f-113">Scarica .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f397f-113">Download .NET Core.</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="f397f-114">Versioni supportate</span><span class="sxs-lookup"><span data-stu-id="f397f-114">Supported releases</span></span>

<span data-ttu-id="f397f-115">La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate e delle versioni di macOS su cui sono supportate.</span><span class="sxs-lookup"><span data-stu-id="f397f-115">The following table is a list of currently supported .NET Core releases and the versions of macOS they're supported on.</span></span> <span data-ttu-id="f397f-116">Queste versioni rimangono supportate nella versione di [.NET Core che raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="f397f-116">These versions remain supported either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

- <span data-ttu-id="f397f-117">Un ✔️ indica che la versione di .NET Core è ancora supportata.</span><span class="sxs-lookup"><span data-stu-id="f397f-117">A ✔️ indicates that the version of .NET Core is still supported.</span></span>
- <span data-ttu-id="f397f-118">❌Indica che la versione di .NET Core non è supportata.</span><span class="sxs-lookup"><span data-stu-id="f397f-118">A ❌ indicates that the version of .NET Core isn't supported.</span></span>

| <span data-ttu-id="f397f-119">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="f397f-119">Operating System</span></span>          | <span data-ttu-id="f397f-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f397f-120">.NET Core 2.1</span></span> | <span data-ttu-id="f397f-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="f397f-121">.NET Core 3.1</span></span> | <span data-ttu-id="f397f-122">.NET 5 Preview</span><span class="sxs-lookup"><span data-stu-id="f397f-122">.NET 5 Preview</span></span> |
|---------------------------|---------------|---------------|----------------|
| <span data-ttu-id="f397f-123">macOS 10,15 "Catalina"</span><span class="sxs-lookup"><span data-stu-id="f397f-123">macOS 10.15 "Catalina"</span></span>    | <span data-ttu-id="f397f-124">✔️ 2,1 ([Note sulla versione][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="f397f-124">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="f397f-125">✔️ 3,1 ([Note sulla versione][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="f397f-125">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="f397f-126">✔️ 5,0 Preview ([Note sulla versione][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="f397f-126">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="f397f-127">macOS 10,14 "Mojave"</span><span class="sxs-lookup"><span data-stu-id="f397f-127">macOS 10.14 "Mojave"</span></span>      | <span data-ttu-id="f397f-128">✔️ 2,1 ([Note sulla versione][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="f397f-128">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="f397f-129">✔️ 3,1 ([Note sulla versione][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="f397f-129">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="f397f-130">✔️ 5,0 Preview ([Note sulla versione][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="f397f-130">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="f397f-131">macOS 10,13 "High Sierra"</span><span class="sxs-lookup"><span data-stu-id="f397f-131">macOS 10.13 "High Sierra"</span></span> | <span data-ttu-id="f397f-132">✔️ 2,1 ([Note sulla versione][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="f397f-132">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="f397f-133">✔️ 3,1 ([Note sulla versione][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="f397f-133">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="f397f-134">✔️ 5,0 Preview ([Note sulla versione][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="f397f-134">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="f397f-135">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="f397f-135">macOS 10.12 "Sierra"</span></span>      | <span data-ttu-id="f397f-136">✔️ 2,1 ([Note sulla versione][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="f397f-136">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="f397f-137">❌3,1 ([Note sulla versione][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="f397f-137">❌ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="f397f-138">❌5,0 Anteprima ([Note sulla versione][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="f397f-138">❌ 5.0 Preview ([Release notes][release-notes-50])</span></span> |

## <a name="unsupported-releases"></a><span data-ttu-id="f397f-139">Versioni non supportate</span><span class="sxs-lookup"><span data-stu-id="f397f-139">Unsupported releases</span></span>

<span data-ttu-id="f397f-140">Le versioni seguenti di .NET Core ❌ non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="f397f-140">The following versions of .NET Core are ❌ no longer supported.</span></span> <span data-ttu-id="f397f-141">I download per questi ancora rimangono pubblicati:</span><span class="sxs-lookup"><span data-stu-id="f397f-141">The downloads for these still remain published:</span></span>

- <span data-ttu-id="f397f-142">3,0 ([Note sulla versione][release-notes-30])</span><span class="sxs-lookup"><span data-stu-id="f397f-142">3.0 ([Release notes][release-notes-30])</span></span>
- <span data-ttu-id="f397f-143">2,2 ([Note sulla versione][release-notes-22])</span><span class="sxs-lookup"><span data-stu-id="f397f-143">2.2 ([Release notes][release-notes-22])</span></span>
- <span data-ttu-id="f397f-144">2,0 ([Note sulla versione][release-notes-20])</span><span class="sxs-lookup"><span data-stu-id="f397f-144">2.0 ([Release notes][release-notes-20])</span></span>

## <a name="runtime-information"></a><span data-ttu-id="f397f-145">Informazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="f397f-145">Runtime information</span></span>

<span data-ttu-id="f397f-146">Il runtime viene usato per eseguire le app create con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f397f-146">The runtime is used to run apps created with .NET Core.</span></span> <span data-ttu-id="f397f-147">Quando un autore di app pubblica un'app, può includere il runtime con l'app.</span><span class="sxs-lookup"><span data-stu-id="f397f-147">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="f397f-148">Se non includono il runtime, l'utente deve installare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="f397f-148">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="f397f-149">Sono disponibili tre diversi runtime che è possibile installare in macOS:</span><span class="sxs-lookup"><span data-stu-id="f397f-149">There are three different runtimes you can install on macOS:</span></span>

<span data-ttu-id="f397f-150">*ASP.NET Core Runtime*</span><span class="sxs-lookup"><span data-stu-id="f397f-150">*ASP.NET Core runtime*</span></span>\
<span data-ttu-id="f397f-151">Esegue ASP.NET Core app.</span><span class="sxs-lookup"><span data-stu-id="f397f-151">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="f397f-152">Include il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f397f-152">Includes the .NET Core runtime.</span></span>

<span data-ttu-id="f397f-153">*Runtime di .NET Core*</span><span class="sxs-lookup"><span data-stu-id="f397f-153">*.NET Core runtime*</span></span>\
<span data-ttu-id="f397f-154">Questo runtime è il runtime più semplice e non include altri Runtime.</span><span class="sxs-lookup"><span data-stu-id="f397f-154">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="f397f-155">Si consiglia di installare *ASP.NET Core Runtime* per la compatibilità ottimale con le app .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f397f-155">It's highly recommended that you install *ASP.NET Core runtime* for the best compatibility with .NET Core apps.</span></span>

[<span data-ttu-id="f397f-156">Scaricare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f397f-156">Download .NET Core Runtime.</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="f397f-157">Informazioni SDK</span><span class="sxs-lookup"><span data-stu-id="f397f-157">SDK information</span></span>

<span data-ttu-id="f397f-158">L'SDK viene usato per creare e pubblicare app e librerie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f397f-158">The SDK is used to build and publish .NET Core apps and libraries.</span></span> <span data-ttu-id="f397f-159">L'installazione dell'SDK include entrambi i [Runtime](#runtime-information): ASP.NET Core e .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f397f-159">Installing the SDK includes both [runtimes](#runtime-information): ASP.NET Core and .NET Core.</span></span>

[<span data-ttu-id="f397f-160">Scaricare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="f397f-160">Download .NET Core SDK.</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="dependencies"></a><span data-ttu-id="f397f-161">Dependencies</span><span class="sxs-lookup"><span data-stu-id="f397f-161">Dependencies</span></span>

<span data-ttu-id="f397f-162">.NET Core è supportato nelle versioni di macOS seguenti:</span><span class="sxs-lookup"><span data-stu-id="f397f-162">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="f397f-163">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="f397f-163">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="f397f-164">Versione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="f397f-164">.NET Core Version</span></span> | <span data-ttu-id="f397f-165">macOS</span><span class="sxs-lookup"><span data-stu-id="f397f-165">macOS</span></span>                 | <span data-ttu-id="f397f-166">Architetture</span><span class="sxs-lookup"><span data-stu-id="f397f-166">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="f397f-167">3.1</span><span class="sxs-lookup"><span data-stu-id="f397f-167">3.1</span></span>               | <span data-ttu-id="f397f-168">Alta Sierra (10.13 +)</span><span class="sxs-lookup"><span data-stu-id="f397f-168">High Sierra (10.13+)</span></span>  | <span data-ttu-id="f397f-169">x64</span><span class="sxs-lookup"><span data-stu-id="f397f-169">x64</span></span> | [<span data-ttu-id="f397f-170">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="f397f-170">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="f397f-171">3.0</span><span class="sxs-lookup"><span data-stu-id="f397f-171">3.0</span></span>               | <span data-ttu-id="f397f-172">Alta Sierra (10.13 +)</span><span class="sxs-lookup"><span data-stu-id="f397f-172">High Sierra (10.13+)</span></span>  | <span data-ttu-id="f397f-173">x64</span><span class="sxs-lookup"><span data-stu-id="f397f-173">x64</span></span> | [<span data-ttu-id="f397f-174">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="f397f-174">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="f397f-175">2.2</span><span class="sxs-lookup"><span data-stu-id="f397f-175">2.2</span></span>               | <span data-ttu-id="f397f-176">Sierra (10.12 +)</span><span class="sxs-lookup"><span data-stu-id="f397f-176">Sierra (10.12+)</span></span>       | <span data-ttu-id="f397f-177">x64</span><span class="sxs-lookup"><span data-stu-id="f397f-177">x64</span></span> | [<span data-ttu-id="f397f-178">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="f397f-178">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="f397f-179">2.1</span><span class="sxs-lookup"><span data-stu-id="f397f-179">2.1</span></span>               | <span data-ttu-id="f397f-180">Sierra (10.12 +)</span><span class="sxs-lookup"><span data-stu-id="f397f-180">Sierra (10.12+)</span></span>       | <span data-ttu-id="f397f-181">x64</span><span class="sxs-lookup"><span data-stu-id="f397f-181">x64</span></span> | [<span data-ttu-id="f397f-182">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="f397f-182">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="f397f-183">A partire da macOS Catalina (versione 10,15), tutto il software creato dopo il 1 ° giugno 2019 distribuito con ID sviluppatore, deve essere autenticato.</span><span class="sxs-lookup"><span data-stu-id="f397f-183">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="f397f-184">Questo requisito si applica al runtime di .NET Core, alla .NET Core SDK e al software creato con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f397f-184">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="f397f-185">I programmi di installazione per .NET Core (Runtime e SDK) versioni 3,1, 3,0 e 2,1 sono stati autenticati dal 18 febbraio 2020.</span><span class="sxs-lookup"><span data-stu-id="f397f-185">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="f397f-186">Le versioni precedenti rilasciate non vengono autenticate.</span><span class="sxs-lookup"><span data-stu-id="f397f-186">Prior released versions aren't notarized.</span></span> <span data-ttu-id="f397f-187">Se si esegue un'app non autenticata, verrà visualizzato un errore simile all'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="f397f-187">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![avviso di autenticazione di macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="f397f-189">Per altre informazioni sul modo in cui l'autenticazione applicata a .NET Core (e sulle app .NET Core), vedere [Working with MacOS Catalina notariation](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f397f-189">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="f397f-190">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="f397f-190">libgdiplus</span></span>

<span data-ttu-id="f397f-191">Le applicazioni .NET Core che usano l'assembly *System. Drawing. Common* richiedono l'installazione di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="f397f-191">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="f397f-192">Un modo semplice per ottenere libgdiplus consiste nell'usare la gestione pacchetti [homebrew ("Brew")](https://brew.sh/) per MacOS.</span><span class="sxs-lookup"><span data-stu-id="f397f-192">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="f397f-193">Dopo l'installazione di *Brew*, installare libgdiplus eseguendo i comandi seguenti in un prompt dei comandi (Command) terminale:</span><span class="sxs-lookup"><span data-stu-id="f397f-193">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a><span data-ttu-id="f397f-194">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="f397f-194">Install with an installer</span></span>

<span data-ttu-id="f397f-195">macOS dispone di programmi di installazione autonomi che possono essere usati per installare .NET Core 3,1 SDK:</span><span class="sxs-lookup"><span data-stu-id="f397f-195">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="f397f-196">CPU x64 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="f397f-196">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="f397f-197">Scaricare e installare manualmente</span><span class="sxs-lookup"><span data-stu-id="f397f-197">Download and manually install</span></span>

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="f397f-198">In alternativa ai programmi di installazione di macOS per .NET Core, è possibile scaricare e installare manualmente l'SDK e il Runtime.</span><span class="sxs-lookup"><span data-stu-id="f397f-198">As an alternative to the macOS installers for .NET Core, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="f397f-199">L'installazione manuale viene in genere eseguita come parte del test di integrazione continua.</span><span class="sxs-lookup"><span data-stu-id="f397f-199">Manual install is usually performed as part of continuous integration testing.</span></span> <span data-ttu-id="f397f-200">Per uno sviluppatore o un utente, è in genere preferibile usare un [programma di installazione](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="f397f-200">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="f397f-201">Se si installa .NET Core SDK, non è necessario installare il runtime corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f397f-201">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="f397f-202">Scaricare prima di tutto una versione **binaria** per l'SDK o il runtime da uno dei siti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f397f-202">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="f397f-203">Download di ✔️ [.net 5,0 Preview](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="f397f-203">✔️ [.NET 5.0 preview downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="f397f-204">Download di ✔️ [.NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="f397f-204">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="f397f-205">Download di ✔️ [.NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="f397f-205">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="f397f-206">Tutti i download di .NET Core</span><span class="sxs-lookup"><span data-stu-id="f397f-206">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="f397f-207">Estrarre quindi il file scaricato e usare il `export` comando per impostare le variabili usate da .NET Core e quindi assicurarsi che .NET Core si trovi nel percorso.</span><span class="sxs-lookup"><span data-stu-id="f397f-207">Next, extract the downloaded file and use the `export` command to set variables used by .NET Core and then ensure .NET Core is in PATH.</span></span>

<span data-ttu-id="f397f-208">Per estrarre il runtime e rendere disponibili i interfaccia della riga di comando di .NET Core comandi nel terminale, scaricare prima di tutto una versione binaria di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f397f-208">To extract the runtime and make the .NET Core CLI commands available at the terminal, first download a .NET Core binary release.</span></span> <span data-ttu-id="f397f-209">Quindi, aprire un terminale ed eseguire i comandi seguenti dalla directory in cui è stato salvato il file.</span><span class="sxs-lookup"><span data-stu-id="f397f-209">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="f397f-210">Il nome del file di archivio può variare a seconda di ciò che è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="f397f-210">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="f397f-211">**Usare il comando seguente per estrarre il runtime**:</span><span class="sxs-lookup"><span data-stu-id="f397f-211">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.5-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="f397f-212">**Usare il comando seguente per estrarre l'SDK**:</span><span class="sxs-lookup"><span data-stu-id="f397f-212">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-3.1.301-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="f397f-213">I `export` comandi precedenti rendono disponibili solo i comandi di interfaccia della riga di comando di .NET Core per la sessione terminal in cui è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="f397f-213">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="f397f-214">È possibile modificare il profilo della Shell per aggiungere i comandi in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="f397f-214">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="f397f-215">Sono disponibili numerose Shell diverse per Linux e ognuna presenta un profilo diverso.</span><span class="sxs-lookup"><span data-stu-id="f397f-215">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="f397f-216">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f397f-216">For example:</span></span>
>
> - <span data-ttu-id="f397f-217">**Shell bash**: *~/. bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="f397f-217">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="f397f-218">**Korn Shell**: *~/.KSHRC* o *. profile*</span><span class="sxs-lookup"><span data-stu-id="f397f-218">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="f397f-219">**Shell Z**: *~/.zshrc* o *. zprofile*</span><span class="sxs-lookup"><span data-stu-id="f397f-219">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="f397f-220">Modificare il file di origine appropriato per la shell e aggiungere `:$HOME/dotnet` alla fine dell'istruzione esistente `PATH` .</span><span class="sxs-lookup"><span data-stu-id="f397f-220">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="f397f-221">Se non `PATH` è inclusa alcuna istruzione, aggiungere una nuova riga con `export PATH=$PATH:$HOME/dotnet` .</span><span class="sxs-lookup"><span data-stu-id="f397f-221">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="f397f-222">Aggiungere anche `export DOTNET_ROOT=$HOME/dotnet` alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="f397f-222">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="f397f-223">Questo approccio consente di installare diverse versioni in posizioni separate e scegliere in modo esplicito quello da usare per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f397f-223">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="f397f-224">Installare con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="f397f-224">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="f397f-225">Visual Studio per Mac installa l'.NET Core SDK quando si seleziona il carico di lavoro di **.NET Core** .</span><span class="sxs-lookup"><span data-stu-id="f397f-225">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="f397f-226">Per iniziare a usare lo sviluppo di .NET Core in macOS, vedere [installare Visual Studio 2019 per Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="f397f-226">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="f397f-227">Per la versione più recente, .NET Core 3,1, è necessario usare l'anteprima Visual Studio per Mac 8,4.</span><span class="sxs-lookup"><span data-stu-id="f397f-227">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="f397f-228">[![macOS Visual Studio 2019 per Mac con funzionalità di carico di lavoro .NET Core](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="f397f-228">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="f397f-229">Installare insieme a Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f397f-229">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="f397f-230">Visual Studio Code è un editor di codice sorgente potente e leggero che viene eseguito sul desktop.</span><span class="sxs-lookup"><span data-stu-id="f397f-230">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="f397f-231">Visual Studio Code è disponibile per Windows, macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="f397f-231">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="f397f-232">Anche se Visual Studio Code non dispone di un programma di installazione di .NET Core automatizzato come Visual Studio, l'aggiunta del supporto di .NET Core è semplice.</span><span class="sxs-lookup"><span data-stu-id="f397f-232">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="f397f-233">[Scaricare e installare Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="f397f-233">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="f397f-234">[Scaricare e installare il .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="f397f-234">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="f397f-235">[Installare l'estensione C# dal marketplace Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="f397f-235">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="install-with-bash-automation"></a><span data-ttu-id="f397f-236">Installare con l'automazione bash</span><span class="sxs-lookup"><span data-stu-id="f397f-236">Install with bash automation</span></span>

<span data-ttu-id="f397f-237">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime.</span><span class="sxs-lookup"><span data-stu-id="f397f-237">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="f397f-238">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="f397f-238">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="f397f-239">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="f397f-239">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="f397f-240">È possibile scegliere una versione specifica specificando l' `current` opzione.</span><span class="sxs-lookup"><span data-stu-id="f397f-240">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="f397f-241">Includere l' `runtime` opzione per installare un Runtime.</span><span class="sxs-lookup"><span data-stu-id="f397f-241">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="f397f-242">In caso contrario, lo script installa l' [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="f397f-242">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="f397f-243">Il comando precedente installa il runtime di ASP.NET Core per la massima compatibilità.</span><span class="sxs-lookup"><span data-stu-id="f397f-243">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="f397f-244">Il runtime di ASP.NET Core include anche il Runtime .NET Core standard.</span><span class="sxs-lookup"><span data-stu-id="f397f-244">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="docker"></a><span data-ttu-id="f397f-245">Docker</span><span class="sxs-lookup"><span data-stu-id="f397f-245">Docker</span></span>

<span data-ttu-id="f397f-246">I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="f397f-246">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="f397f-247">I contenitori nello stesso computer condividono solo il kernel e usano le risorse specificate per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f397f-247">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="f397f-248">.NET Core può essere eseguito in un contenitore docker.</span><span class="sxs-lookup"><span data-stu-id="f397f-248">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="f397f-249">Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="f397f-249">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="f397f-250">Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="f397f-250">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="f397f-251">Microsoft fornisce immagini progettate per scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="f397f-251">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="f397f-252">Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="f397f-252">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="f397f-253">Per altre informazioni sull'uso di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="f397f-253">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f397f-254">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f397f-254">Next steps</span></span>

- <span data-ttu-id="f397f-255">[Come verificare se .NET Core è già installato](how-to-detect-installed-versions.md?pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="f397f-255">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md?pivots=os-macos).</span></span>
- <span data-ttu-id="f397f-256">[Uso dell'autenticazione di MacOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f397f-256">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="f397f-257">[Esercitazione: Introduzione a MacOS](../tutorials/using-on-mac-vs.md).</span><span class="sxs-lookup"><span data-stu-id="f397f-257">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="f397f-258">[Esercitazione: creare una nuova app con Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="f397f-258">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="f397f-259">[Esercitazione: distribuire un'app .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="f397f-259">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
