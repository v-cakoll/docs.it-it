---
title: Disinstalla strumento
description: Panoramica dello strumento di disinstallazione di .NET Core, uno strumento guidato che consente la pulizia controllata degli SDK e dei runtime di .NET Core.
author: sfoslund
ms.date: 05/27/2020
ms.openlocfilehash: 4e70fd3438b582bd5a0d6a52d7e58ed5e07f8811
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446906"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="40188-103">Strumento di disinstallazione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="40188-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="40188-104">Lo [strumento di disinstallazione di .NET Core](https://aka.ms/dotnet-core-uninstall-tool) ( `dotnet-core-uninstall` ) consente di rimuovere gli SDK e i runtime di .NET Core da un sistema.</span><span class="sxs-lookup"><span data-stu-id="40188-104">The [.NET Core Uninstall Tool](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="40188-105">È disponibile una raccolta di opzioni per specificare quali versioni si desidera disinstallare.</span><span class="sxs-lookup"><span data-stu-id="40188-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="40188-106">Lo strumento supporta Windows e macOS.</span><span class="sxs-lookup"><span data-stu-id="40188-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="40188-107">Linux non è attualmente supportato.</span><span class="sxs-lookup"><span data-stu-id="40188-107">Linux is currently not supported.</span></span>

<span data-ttu-id="40188-108">In Windows, lo strumento può disinstallare solo gli SDK e i runtime installati usando uno dei programmi di installazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="40188-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="40188-109">Il programma di installazione di .NET Core SDK e Runtime.</span><span class="sxs-lookup"><span data-stu-id="40188-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="40188-110">Programma di installazione di Visual Studio nelle versioni precedenti a Visual Studio 2019 versione 16,3.</span><span class="sxs-lookup"><span data-stu-id="40188-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="40188-111">In macOS lo strumento può disinstallare solo gli SDK e i runtime che si trovano nella cartella */usr/local/share/DotNet* .</span><span class="sxs-lookup"><span data-stu-id="40188-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="40188-112">A causa di queste limitazioni, lo strumento potrebbe non essere in grado di disinstallare tutti gli SDK e i runtime di .NET Core nel computer.</span><span class="sxs-lookup"><span data-stu-id="40188-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="40188-113">È possibile usare il `dotnet --info` comando per trovare tutti gli SDK e i runtime di .net core installati, inclusi gli SDK e i runtime che questo strumento non è in grado di rimuovere.</span><span class="sxs-lookup"><span data-stu-id="40188-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="40188-114">Il `dotnet-core-uninstall list` comando Visualizza gli SDK che è possibile disinstallare con lo strumento.</span><span class="sxs-lookup"><span data-stu-id="40188-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="40188-115">Installare lo strumento</span><span class="sxs-lookup"><span data-stu-id="40188-115">Install the tool</span></span>

<span data-ttu-id="40188-116">È possibile scaricare lo strumento di disinstallazione di .NET Core da [qui](https://aka.ms/dotnet-core-uninstall-tool) e trovare il codice sorgente nel repository GitHub [DotNet/CLI-Lab](https://github.com/dotnet/cli-lab) .</span><span class="sxs-lookup"><span data-stu-id="40188-116">You can download the .NET Core Uninstall Tool from [here](https://aka.ms/dotnet-core-uninstall-tool) and find the source code at the [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="40188-117">Per disinstallare SDK e runtime di .NET Core, lo strumento richiede l'elevazione dei privilegi.</span><span class="sxs-lookup"><span data-stu-id="40188-117">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="40188-118">Pertanto, deve essere installato in una directory protetta da scrittura, ad esempio *c:\Programmi* in Windows o */usr/local/bin* in MacOS.</span><span class="sxs-lookup"><span data-stu-id="40188-118">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="40188-119">Vedere anche [accesso con privilegi elevati per i comandi DotNet](../tools/elevated-access.md).</span><span class="sxs-lookup"><span data-stu-id="40188-119">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="40188-120">Per ulteriori informazioni, vedere le [istruzioni dettagliate](https://aka.ms/dotnet-core-uninstall-tool)per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="40188-120">For more information, see the [detailed installation instructions](https://aka.ms/dotnet-core-uninstall-tool).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="40188-121">Eseguire lo strumento</span><span class="sxs-lookup"><span data-stu-id="40188-121">Run the tool</span></span>

<span data-ttu-id="40188-122">Nei passaggi seguenti viene illustrato l'approccio consigliato per l'esecuzione dello strumento di disinstallazione:</span><span class="sxs-lookup"><span data-stu-id="40188-122">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="40188-123">Passaggio 1: visualizzare gli SDK e i runtime di .NET Core installati</span><span class="sxs-lookup"><span data-stu-id="40188-123">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="40188-124">Passaggio 2: eseguire un'esecuzione a secco</span><span class="sxs-lookup"><span data-stu-id="40188-124">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="40188-125">Passaggio 3: disinstallare SDK e runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="40188-125">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="40188-126">Passaggio 4: eliminare la cartella di fallback NuGet (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="40188-126">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="40188-127">Passaggio 1: visualizzare gli SDK e i runtime di .NET Core installati</span><span class="sxs-lookup"><span data-stu-id="40188-127">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="40188-128">Il `dotnet-core-uninstall list` comando elenca gli SDK e i runtime di .net core installati che possono essere rimossi con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="40188-128">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="40188-129">Alcuni SDK e Runtime possono essere richiesti da Visual Studio e vengono visualizzati con una nota del motivo per cui non è consigliabile disinstallarli.</span><span class="sxs-lookup"><span data-stu-id="40188-129">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

> [!NOTE]
> <span data-ttu-id="40188-130">L'output del `dotnet-core-uninstall list` comando non corrisponderà all'elenco di versioni installate nell'output di `dotnet --info` nella maggior parte dei casi.</span><span class="sxs-lookup"><span data-stu-id="40188-130">The output of the `dotnet-core-uninstall list` command will not match the list of installed versions in the output of `dotnet --info` in most cases.</span></span> <span data-ttu-id="40188-131">In particolare, questo strumento non Visualizza le versioni installate da file zip o gestite da Visual Studio (qualsiasi versione installata con Visual Studio 2019 16,3 o versioni successive).</span><span class="sxs-lookup"><span data-stu-id="40188-131">Specifically, this tool will not display versions installed by zip files or managed by Visual Studio (any version installed with Visual Studio 2019 16.3 or later).</span></span> <span data-ttu-id="40188-132">Un modo per verificare se una versione è gestita da Visual Studio è visualizzarla in `Add or Remove Programs` , in cui le versioni gestite di Visual Studio sono contrassegnate come tali nei rispettivi nomi visualizzati.</span><span class="sxs-lookup"><span data-stu-id="40188-132">One way to check if a version is managed by Visual Studio is to view it in `Add or Remove Programs`, where Visual Studio managed versions are marked as such in their display names.</span></span>

<span data-ttu-id="40188-133">**elenco di disinstallazione DotNet-Core**</span><span class="sxs-lookup"><span data-stu-id="40188-133">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="40188-134">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="40188-134">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="40188-135">Opzioni</span><span class="sxs-lookup"><span data-stu-id="40188-135">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="40188-136">Windows</span><span class="sxs-lookup"><span data-stu-id="40188-136">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="40188-137">Elenca tutti i runtime di ASP.NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="40188-137">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="40188-138">Elenca tutti i bundle di hosting .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="40188-138">Lists all the .NET Core hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="40188-139">Elenca tutti i runtime di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="40188-139">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="40188-140">Elenca tutti gli SDK di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="40188-140">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="40188-141">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="40188-141">Sets the verbosity level.</span></span> <span data-ttu-id="40188-142">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="40188-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="40188-143">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="40188-143">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="40188-144">Elenca tutti i runtime e gli SDK .NET Core x64 che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="40188-144">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="40188-145">Elenca tutti gli SDK di .NET core x86 e i runtime che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="40188-145">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macos"></a>[<span data-ttu-id="40188-146">macOS</span><span class="sxs-lookup"><span data-stu-id="40188-146">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="40188-147">Elenca tutti i runtime di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="40188-147">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="40188-148">Elenca tutti gli SDK di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="40188-148">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="40188-149">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="40188-149">Sets the verbosity level.</span></span> <span data-ttu-id="40188-150">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="40188-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="40188-151">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="40188-151">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="40188-152">Esempi</span><span class="sxs-lookup"><span data-stu-id="40188-152">Examples</span></span>

* <span data-ttu-id="40188-153">Elencare tutti i runtime e gli SDK di .NET Core che possono essere rimossi con questo strumento:</span><span class="sxs-lookup"><span data-stu-id="40188-153">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="40188-154">Elencare tutti i runtime e gli SDK di .NET Core x64:</span><span class="sxs-lookup"><span data-stu-id="40188-154">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="40188-155">Elencare tutti gli SDK di .NET core x86:</span><span class="sxs-lookup"><span data-stu-id="40188-155">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="40188-156">Passaggio 2: eseguire un'esecuzione a secco</span><span class="sxs-lookup"><span data-stu-id="40188-156">Step 2 - Do a dry run</span></span>

<span data-ttu-id="40188-157">I `dotnet-core-uninstall dry-run` `dotnet-core-uninstall whatif` comandi e visualizzano gli SDK e i runtime di .NET Core che verranno rimossi in base alle opzioni fornite senza eseguire la disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="40188-157">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="40188-158">Questi comandi sono sinonimi.</span><span class="sxs-lookup"><span data-stu-id="40188-158">These commands are synonyms.</span></span>

<span data-ttu-id="40188-159">**DotNet-Core-Uninstall Dry-Run e DotNet-Core-Uninstall WhatIf**</span><span class="sxs-lookup"><span data-stu-id="40188-159">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="40188-160">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="40188-160">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="40188-161">Argomenti</span><span class="sxs-lookup"><span data-stu-id="40188-161">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="40188-162">Versione specificata da disinstallare.</span><span class="sxs-lookup"><span data-stu-id="40188-162">The specified version to uninstall.</span></span> <span data-ttu-id="40188-163">È possibile elencare diverse versioni una dopo l'altra, separate da spazi.</span><span class="sxs-lookup"><span data-stu-id="40188-163">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="40188-164">Sono supportati anche i file di risposta.</span><span class="sxs-lookup"><span data-stu-id="40188-164">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="40188-165">I file di risposta sono un'alternativa all'inserimento di tutte le versioni nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="40188-165">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="40188-166">Si tratta di file di testo, in genere con \* estensione rsp, e ogni versione è elencata in una riga separata.</span><span class="sxs-lookup"><span data-stu-id="40188-166">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="40188-167">Per specificare un file di risposta per l' `VERSION` argomento, usare il \@ carattere immediatamente seguito dal nome del file di risposta.</span><span class="sxs-lookup"><span data-stu-id="40188-167">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="40188-168">Opzioni</span><span class="sxs-lookup"><span data-stu-id="40188-168">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="40188-169">Windows</span><span class="sxs-lookup"><span data-stu-id="40188-169">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="40188-170">Rimuove tutti i runtime e gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40188-170">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="40188-171">Rimuove solo gli SDK di .NET Core e i runtime con una versione inferiore alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="40188-171">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="40188-172">La versione specificata rimane installata.</span><span class="sxs-lookup"><span data-stu-id="40188-172">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="40188-173">Rimuove tutti i runtime e gli SDK di .NET Core, ad eccezione di quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="40188-173">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="40188-174">Rimuove gli SDK di .NET Core e i runtime, ad eccezione di una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="40188-174">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="40188-175">Rimuove gli SDK di .NET Core e i runtime sostituiti da patch più elevate.</span><span class="sxs-lookup"><span data-stu-id="40188-175">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="40188-176">Questa opzione protegge Global. JSON.</span><span class="sxs-lookup"><span data-stu-id="40188-176">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="40188-177">Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime.</span><span class="sxs-lookup"><span data-stu-id="40188-177">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="40188-178">Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime eccetto quella più alta.</span><span class="sxs-lookup"><span data-stu-id="40188-178">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="40188-179">Rimuove solo i runtime ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="40188-179">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="40188-180">Rimuove solo i pacchetti di runtime e hosting di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40188-180">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="40188-181">Rimuove gli SDK di .NET Core e i runtime che corrispondono alla `major.minor` versione specificata.</span><span class="sxs-lookup"><span data-stu-id="40188-181">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="40188-182">Rimuove solo i runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40188-182">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="40188-183">Rimuove solo gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40188-183">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="40188-184">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="40188-184">Sets the verbosity level.</span></span> <span data-ttu-id="40188-185">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="40188-185">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="40188-186">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="40188-186">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="40188-187">Deve essere utilizzato con `--sdk` , `--runtime` e `--aspnet-runtime` per rimuovere gli SDK o i runtime x64.</span><span class="sxs-lookup"><span data-stu-id="40188-187">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="40188-188">`--sdk` `--runtime` `--aspnet-runtime` Per rimuovere gli SDK o i Runtime x86, è necessario usare con, e.</span><span class="sxs-lookup"><span data-stu-id="40188-188">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="40188-189">**`--force`** Forza la rimozione di versioni che potrebbero essere usate da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="40188-189">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="40188-190">Note:</span><span class="sxs-lookup"><span data-stu-id="40188-190">Notes:</span></span>

1. <span data-ttu-id="40188-191">È richiesto esattamente uno degli `--sdk` ,, `--runtime` `--aspnet-runtime` e `--hosting-bundle` .</span><span class="sxs-lookup"><span data-stu-id="40188-191">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="40188-192">`--all`, `--all-below` , `--all-but` , `--all-but-latest` , `--all-lower-patches` , `--all-previews` , `--all-previews-but-latest` , `--major-minor` e `[<VERSION>...]` sono esclusivi.</span><span class="sxs-lookup"><span data-stu-id="40188-192">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="40188-193">Se `--x64` o `--x86` non sono specificati, verranno rimossi sia x64 che x86.</span><span class="sxs-lookup"><span data-stu-id="40188-193">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="40188-194">macOS</span><span class="sxs-lookup"><span data-stu-id="40188-194">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="40188-195">Rimuove tutti i runtime e gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40188-195">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="40188-196">Rimuove gli SDK e i Runtime .NET Core sotto la versione specificata.</span><span class="sxs-lookup"><span data-stu-id="40188-196">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="40188-197">La versione specificata rimarrà.</span><span class="sxs-lookup"><span data-stu-id="40188-197">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="40188-198">Rimuove gli SDK di .NET Core e i runtime, ad eccezione delle versioni specificate.</span><span class="sxs-lookup"><span data-stu-id="40188-198">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="40188-199">Rimuove gli SDK di .NET Core e i runtime, ad eccezione di una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="40188-199">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="40188-200">Rimuove gli SDK di .NET Core e i runtime sostituiti da patch più elevate.</span><span class="sxs-lookup"><span data-stu-id="40188-200">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="40188-201">Questa opzione protegge Global. JSON.</span><span class="sxs-lookup"><span data-stu-id="40188-201">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="40188-202">Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime.</span><span class="sxs-lookup"><span data-stu-id="40188-202">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="40188-203">Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime eccetto quella più alta.</span><span class="sxs-lookup"><span data-stu-id="40188-203">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="40188-204">Rimuove gli SDK di .NET Core e i runtime che corrispondono alla `major.minor` versione specificata.</span><span class="sxs-lookup"><span data-stu-id="40188-204">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="40188-205">Rimuove solo i runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40188-205">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="40188-206">Rimuove solo gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40188-206">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="40188-207">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="40188-207">Sets the verbosity level.</span></span> <span data-ttu-id="40188-208">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="40188-208">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="40188-209">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="40188-209">The default value is `normal`.</span></span>
  
* <span data-ttu-id="40188-210">**`--force`** Forza la rimozione di versioni che potrebbero essere usate da Visual Studio o da SDK.</span><span class="sxs-lookup"><span data-stu-id="40188-210">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="40188-211">Note:</span><span class="sxs-lookup"><span data-stu-id="40188-211">Notes:</span></span>

1. <span data-ttu-id="40188-212">È necessario specificare esattamente uno dei `--sdk` e `--runtime` .</span><span class="sxs-lookup"><span data-stu-id="40188-212">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="40188-213">`--all`, `--all-below` , `--all-but` , `--all-but-latest` , `--all-lower-patches` , `--all-previews` , `--all-previews-but-latest` , `--major-minor` e `[<VERSION>...]` sono esclusivi.</span><span class="sxs-lookup"><span data-stu-id="40188-213">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="40188-214">Esempi</span><span class="sxs-lookup"><span data-stu-id="40188-214">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="40188-215">Per impostazione predefinita, gli SDK di .NET Core e i runtime che potrebbero essere richiesti da Visual Studio o altri SDK non sono inclusi nell' `dotnet-core-uninstall dry-run` output.</span><span class="sxs-lookup"><span data-stu-id="40188-215">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="40188-216">Negli esempi seguenti alcuni degli SDK e dei runtime specificati potrebbero non essere inclusi nell'output, a seconda dello stato del computer.</span><span class="sxs-lookup"><span data-stu-id="40188-216">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="40188-217">Per includere tutti gli SDK e i runtime, elencarli in modo esplicito come argomenti oppure usare l' `--force` opzione.</span><span class="sxs-lookup"><span data-stu-id="40188-217">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="40188-218">Esecuzione a secco della rimozione di tutti i runtime di .NET Core sostituiti da patch superiori:</span><span class="sxs-lookup"><span data-stu-id="40188-218">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="40188-219">Esecuzione a secco della rimozione di tutti gli SDK di .NET Core sotto la versione `2.2.301` :</span><span class="sxs-lookup"><span data-stu-id="40188-219">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="40188-220">Passaggio 3: disinstallare SDK e runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="40188-220">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="40188-221">`dotnet-core-uninstall remove`Disinstalla gli SDK e i Runtime .NET Core specificati da una raccolta di opzioni.</span><span class="sxs-lookup"><span data-stu-id="40188-221">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="40188-222">Non è possibile usare lo strumento per disinstallare SDK e Runtime con la versione 5,0 o successive.</span><span class="sxs-lookup"><span data-stu-id="40188-222">The tool can't be used to uninstall SDKs and Runtimes with version 5.0 or above.</span></span>

<span data-ttu-id="40188-223">Poiché questo strumento presenta un comportamento distruttivo, è **consigliabile eseguire** un'esecuzione a secco prima di eseguire il comando Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="40188-223">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="40188-224">L'esecuzione a secco mostrerà quali SDK e runtime di .NET Core verranno rimossi quando si usa il `remove` comando.</span><span class="sxs-lookup"><span data-stu-id="40188-224">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="40188-225">Per informazioni su quali SDK e Runtime è possibile rimuovere, fare [riferimento a.](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version)</span><span class="sxs-lookup"><span data-stu-id="40188-225">Refer to [Should I remove a version?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="40188-226">Tenere presenti le indicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40188-226">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="40188-227">Questo strumento consente di disinstallare le versioni dei .NET Core SDK richieste dai `global.json` file nel computer.</span><span class="sxs-lookup"><span data-stu-id="40188-227">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="40188-228">È possibile reinstallare gli SDK di .NET Core dalla pagina [Scarica .NET Core](https://dotnet.microsoft.com/download/dotnet-core) .</span><span class="sxs-lookup"><span data-stu-id="40188-228">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="40188-229">Questo strumento consente di disinstallare le versioni del runtime di .NET Core richieste dalle applicazioni dipendenti dal Framework nel computer.</span><span class="sxs-lookup"><span data-stu-id="40188-229">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="40188-230">È possibile reinstallare i runtime di .NET Core dalla pagina [Scarica .NET Core](https://dotnet.microsoft.com/download/dotnet-core) .</span><span class="sxs-lookup"><span data-stu-id="40188-230">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="40188-231">Questo strumento consente di disinstallare le versioni del .NET Core SDK e del runtime su cui si basa Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="40188-231">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="40188-232">Se si interrompe l'installazione di Visual Studio, eseguire "Repair" nel programma di installazione di Visual Studio per tornare allo stato di lavoro.</span><span class="sxs-lookup"><span data-stu-id="40188-232">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="40188-233">Per impostazione predefinita, tutti i comandi mantengono gli SDK e i Runtime .NET Core che potrebbero essere richiesti da Visual Studio o da altri SDK.</span><span class="sxs-lookup"><span data-stu-id="40188-233">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="40188-234">Questi SDK e Runtime possono essere disinstallati elencando in modo esplicito come argomenti o usando l' `--force` opzione.</span><span class="sxs-lookup"><span data-stu-id="40188-234">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="40188-235">Per disinstallare SDK e runtime di .NET Core, lo strumento richiede l'elevazione dei privilegi.</span><span class="sxs-lookup"><span data-stu-id="40188-235">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="40188-236">Eseguire lo strumento in un prompt dei comandi dell'amministratore in Windows e con `sudo` in MacOS.</span><span class="sxs-lookup"><span data-stu-id="40188-236">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="40188-237">I `dry-run` `whatif` comandi e non richiedono l'elevazione dei privilegi.</span><span class="sxs-lookup"><span data-stu-id="40188-237">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="40188-238">**DotNet-Core-Disinstalla Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="40188-238">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="40188-239">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="40188-239">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="40188-240">Argomenti</span><span class="sxs-lookup"><span data-stu-id="40188-240">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="40188-241">Versione specificata da disinstallare.</span><span class="sxs-lookup"><span data-stu-id="40188-241">The specified version to uninstall.</span></span> <span data-ttu-id="40188-242">È possibile elencare diverse versioni una dopo l'altra, separate da spazi.</span><span class="sxs-lookup"><span data-stu-id="40188-242">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="40188-243">Sono supportati anche i file di risposta.</span><span class="sxs-lookup"><span data-stu-id="40188-243">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="40188-244">I file di risposta sono un'alternativa all'inserimento di tutte le versioni nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="40188-244">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="40188-245">Si tratta di file di testo, in genere con \* estensione rsp, e ogni versione è elencata in una riga separata.</span><span class="sxs-lookup"><span data-stu-id="40188-245">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="40188-246">Per specificare un file di risposta per l' `VERSION` argomento, usare il \@ carattere immediatamente seguito dal nome del file di risposta.</span><span class="sxs-lookup"><span data-stu-id="40188-246">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="40188-247">Opzioni</span><span class="sxs-lookup"><span data-stu-id="40188-247">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="40188-248">Windows</span><span class="sxs-lookup"><span data-stu-id="40188-248">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="40188-249">Rimuove tutti i runtime e gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40188-249">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="40188-250">Rimuove solo gli SDK di .NET Core e i runtime con una versione inferiore alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="40188-250">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="40188-251">La versione specificata rimane installata.</span><span class="sxs-lookup"><span data-stu-id="40188-251">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="40188-252">Rimuove tutti i runtime e gli SDK di .NET Core, ad eccezione di quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="40188-252">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="40188-253">Rimuove gli SDK di .NET Core e i runtime, ad eccezione di una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="40188-253">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="40188-254">Rimuove gli SDK di .NET Core e i runtime sostituiti da patch più elevate.</span><span class="sxs-lookup"><span data-stu-id="40188-254">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="40188-255">Questa opzione protegge Global. JSON.</span><span class="sxs-lookup"><span data-stu-id="40188-255">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="40188-256">Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime.</span><span class="sxs-lookup"><span data-stu-id="40188-256">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="40188-257">Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime eccetto quella più alta.</span><span class="sxs-lookup"><span data-stu-id="40188-257">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="40188-258">Rimuove solo i runtime ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="40188-258">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="40188-259">Rimuove solo i bundle di hosting .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40188-259">Removes .NET Core hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="40188-260">Rimuove gli SDK di .NET Core e i runtime che corrispondono alla `major.minor` versione specificata.</span><span class="sxs-lookup"><span data-stu-id="40188-260">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="40188-261">Rimuove solo i runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40188-261">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="40188-262">Rimuove solo gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40188-262">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="40188-263">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="40188-263">Sets the verbosity level.</span></span> <span data-ttu-id="40188-264">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="40188-264">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="40188-265">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="40188-265">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="40188-266">Deve essere utilizzato con `--sdk` , `--runtime` e `--aspnet-runtime` per rimuovere gli SDK o i runtime x64.</span><span class="sxs-lookup"><span data-stu-id="40188-266">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="40188-267">`--sdk` `--runtime` `--aspnet-runtime` Per rimuovere gli SDK o i Runtime x86, è necessario usare con, e.</span><span class="sxs-lookup"><span data-stu-id="40188-267">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="40188-268">**`-y, --yes`** Esegue il comando senza richiedere una conferma Yes o no.</span><span class="sxs-lookup"><span data-stu-id="40188-268">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="40188-269">**`--force`** Forza la rimozione di versioni che potrebbero essere usate da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="40188-269">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="40188-270">Note:</span><span class="sxs-lookup"><span data-stu-id="40188-270">Notes:</span></span>

1. <span data-ttu-id="40188-271">È richiesto esattamente uno degli `--sdk` ,, `--runtime` `--aspnet-runtime` e `--hosting-bundle` .</span><span class="sxs-lookup"><span data-stu-id="40188-271">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="40188-272">`--all`, `--all-below` , `--all-but` , `--all-but-latest` , `--all-lower-patches` , `--all-previews` , `--all-previews-but-latest` , `--major-minor` e `[<VERSION>...]` sono esclusivi.</span><span class="sxs-lookup"><span data-stu-id="40188-272">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="40188-273">Se `--x64` o `--x86` non sono specificati, verranno rimossi sia x64 che x86.</span><span class="sxs-lookup"><span data-stu-id="40188-273">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="40188-274">macOS</span><span class="sxs-lookup"><span data-stu-id="40188-274">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="40188-275">Rimuove tutti i runtime e gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40188-275">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="40188-276">Rimuove gli SDK e i Runtime .NET Core sotto la versione specificata.</span><span class="sxs-lookup"><span data-stu-id="40188-276">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="40188-277">La versione specificata rimarrà.</span><span class="sxs-lookup"><span data-stu-id="40188-277">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="40188-278">Rimuove gli SDK di .NET Core e i runtime, ad eccezione delle versioni specificate.</span><span class="sxs-lookup"><span data-stu-id="40188-278">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="40188-279">Rimuove gli SDK di .NET Core e i runtime, ad eccezione di una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="40188-279">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="40188-280">Rimuove gli SDK di .NET Core e i runtime sostituiti da patch più elevate.</span><span class="sxs-lookup"><span data-stu-id="40188-280">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="40188-281">Questa opzione protegge Global. JSON.</span><span class="sxs-lookup"><span data-stu-id="40188-281">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="40188-282">Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime.</span><span class="sxs-lookup"><span data-stu-id="40188-282">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="40188-283">Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime eccetto quella più alta.</span><span class="sxs-lookup"><span data-stu-id="40188-283">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="40188-284">Rimuove gli SDK di .NET Core e i runtime che corrispondono alla `major.minor` versione specificata.</span><span class="sxs-lookup"><span data-stu-id="40188-284">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="40188-285">Rimuove solo i runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40188-285">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="40188-286">Rimuove solo gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40188-286">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="40188-287">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="40188-287">Sets the verbosity level.</span></span> <span data-ttu-id="40188-288">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="40188-288">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="40188-289">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="40188-289">The default value is `normal`.</span></span>

* <span data-ttu-id="40188-290">**`-y, --yes`** Esegue il comando senza richiedere la conferma Y/N.</span><span class="sxs-lookup"><span data-stu-id="40188-290">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="40188-291">**`--force`** Forza la rimozione di versioni che potrebbero essere usate da Visual Studio o da SDK.</span><span class="sxs-lookup"><span data-stu-id="40188-291">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="40188-292">Note:</span><span class="sxs-lookup"><span data-stu-id="40188-292">Notes:</span></span>

1. <span data-ttu-id="40188-293">È necessario specificare esattamente uno dei `--sdk` e `--runtime` .</span><span class="sxs-lookup"><span data-stu-id="40188-293">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="40188-294">`--all`, `--all-below` , `--all-but` , `--all-but-latest` , `--all-lower-patches` , `--all-previews` , `--all-previews-but-latest` , `--major-minor` e `[<VERSION>...]` sono esclusivi.</span><span class="sxs-lookup"><span data-stu-id="40188-294">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="40188-295">Esempi</span><span class="sxs-lookup"><span data-stu-id="40188-295">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="40188-296">Per impostazione predefinita, vengono conservati gli SDK e i Runtime .NET Core che potrebbero essere richiesti da Visual Studio o altri SDK.</span><span class="sxs-lookup"><span data-stu-id="40188-296">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="40188-297">Negli esempi seguenti è possibile che alcuni degli SDK e dei runtime specificati rimangano, a seconda dello stato del computer.</span><span class="sxs-lookup"><span data-stu-id="40188-297">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="40188-298">Per rimuovere tutti gli SDK e i runtime, elencarli in modo esplicito come argomenti oppure usare l' `--force` opzione.</span><span class="sxs-lookup"><span data-stu-id="40188-298">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="40188-299">Rimuovere tutti i runtime di .NET Core eccetto la versione `3.0.0-preview6-27804-01` senza richiedere la conferma Y/N:</span><span class="sxs-lookup"><span data-stu-id="40188-299">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="40188-300">Rimuovere tutti gli SDK di .NET Core 1,1 senza richiedere la conferma Y/n:</span><span class="sxs-lookup"><span data-stu-id="40188-300">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="40188-301">Rimuovere .NET Core 1.1.11 SDK senza output della console:</span><span class="sxs-lookup"><span data-stu-id="40188-301">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="40188-302">Rimuovere tutti gli SDK di .NET Core che possono essere rimossi in modo sicuro da questo strumento:</span><span class="sxs-lookup"><span data-stu-id="40188-302">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="40188-303">Rimuovere tutti gli SDK di .NET Core che possono essere rimossi da questo strumento, inclusi gli SDK che potrebbero essere richiesti da Visual Studio (scelta non consigliata):</span><span class="sxs-lookup"><span data-stu-id="40188-303">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="40188-304">Rimuovere tutti gli SDK di .NET Core specificati nel file di risposta`versions.rsp`</span><span class="sxs-lookup"><span data-stu-id="40188-304">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="40188-305">Il contenuto di *Versions. rsp* è il seguente:</span><span class="sxs-lookup"><span data-stu-id="40188-305">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="40188-306">Passaggio 4: eliminare la cartella di fallback NuGet (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="40188-306">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="40188-307">In alcuni casi non è più necessario `NuGetFallbackFolder` e può essere opportuno eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="40188-307">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="40188-308">Per ulteriori informazioni sull'eliminazione di questa cartella, vedere [Remove the NuGetFallbackFolder](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span><span class="sxs-lookup"><span data-stu-id="40188-308">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="40188-309">Disinstalla lo strumento</span><span class="sxs-lookup"><span data-stu-id="40188-309">Uninstall the tool</span></span>

## <a name="windows"></a>[<span data-ttu-id="40188-310">Windows</span><span class="sxs-lookup"><span data-stu-id="40188-310">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="40188-311">Aprire **Installazione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="40188-311">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="40188-312">Cercare `Microsoft .NET Core SDK Uninstall Tool`.</span><span class="sxs-lookup"><span data-stu-id="40188-312">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="40188-313">Selezionare **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="40188-313">Select **Uninstall**.</span></span>

## <a name="macos"></a>[<span data-ttu-id="40188-314">macOS</span><span class="sxs-lookup"><span data-stu-id="40188-314">macOS</span></span>](#tab/macos)

<span data-ttu-id="40188-315">Eliminare il file *DotNet-Core-Uninstall. tar. gz* scaricato dalla directory in cui è stato installato.</span><span class="sxs-lookup"><span data-stu-id="40188-315">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="40188-316">Se il contenuto di questo file è stato decompresso in un'altra directory, assicurarsi di eliminare anche tale contenuto.</span><span class="sxs-lookup"><span data-stu-id="40188-316">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---
