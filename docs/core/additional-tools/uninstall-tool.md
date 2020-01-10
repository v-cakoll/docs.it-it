---
title: Strumento di disinstallazione
description: Panoramica dello strumento di disinstallazione di .NET Core, uno strumento guidato che consente la pulizia controllata degli SDK e dei runtime di .NET Core.
author: sfoslund
ms.date: 01/06/2020
ms.openlocfilehash: 4944c983cbd02b456c3a09a1b03bc28ba6e458cc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714549"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="a41df-103">Strumento di disinstallazione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="a41df-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="a41df-104">Lo [strumento di disinstallazione di .NET Core](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) consente di rimuovere gli SDK e i runtime di .NET Core da un sistema.</span><span class="sxs-lookup"><span data-stu-id="a41df-104">The [.NET Core Uninstall Tool](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="a41df-105">È disponibile una raccolta di opzioni per specificare quali versioni si desidera disinstallare.</span><span class="sxs-lookup"><span data-stu-id="a41df-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="a41df-106">Lo strumento supporta Windows e macOS.</span><span class="sxs-lookup"><span data-stu-id="a41df-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="a41df-107">Linux non è attualmente supportato.</span><span class="sxs-lookup"><span data-stu-id="a41df-107">Linux is currently not supported.</span></span>

<span data-ttu-id="a41df-108">In Windows, lo strumento può disinstallare solo gli SDK e i runtime installati usando uno dei programmi di installazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="a41df-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="a41df-109">Il programma di installazione di .NET Core SDK e Runtime.</span><span class="sxs-lookup"><span data-stu-id="a41df-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="a41df-110">Programma di installazione di Visual Studio nelle versioni precedenti a Visual Studio 2019 versione 16,3.</span><span class="sxs-lookup"><span data-stu-id="a41df-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="a41df-111">In macOS lo strumento può disinstallare solo gli SDK e i runtime che si trovano nella cartella */usr/local/share/DotNet* .</span><span class="sxs-lookup"><span data-stu-id="a41df-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="a41df-112">A causa di queste limitazioni, lo strumento potrebbe non essere in grado di disinstallare tutti gli SDK e i runtime di .NET Core nel computer.</span><span class="sxs-lookup"><span data-stu-id="a41df-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="a41df-113">È possibile usare il comando `dotnet --info` per trovare tutti gli SDK e i runtime di .NET Core installati, inclusi gli SDK e i runtime che questo strumento non è in grado di rimuovere.</span><span class="sxs-lookup"><span data-stu-id="a41df-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="a41df-114">Il comando `dotnet-core-uninstall list` Visualizza gli SDK che è possibile disinstallare con lo strumento.</span><span class="sxs-lookup"><span data-stu-id="a41df-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="a41df-115">Installare lo strumento</span><span class="sxs-lookup"><span data-stu-id="a41df-115">Install the tool</span></span>

<span data-ttu-id="a41df-116">È possibile scaricare lo strumento di disinstallazione di .NET Core dal repository GitHub [DotNet/CLI-Lab](https://github.com/dotnet/cli-lab/releases) .</span><span class="sxs-lookup"><span data-stu-id="a41df-116">You can download the .NET Core Uninstall Tool from the [dotnet/cli-lab](https://github.com/dotnet/cli-lab/releases) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="a41df-117">Per disinstallare SDK e runtime di .NET Core, lo strumento richiede l'elevazione dei privilegi.</span><span class="sxs-lookup"><span data-stu-id="a41df-117">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="a41df-118">Pertanto, deve essere installato in una directory protetta da scrittura, ad esempio *c:\Programmi* in Windows o */usr/local/bin* in MacOS.</span><span class="sxs-lookup"><span data-stu-id="a41df-118">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="a41df-119">Vedere anche [accesso con privilegi elevati per i comandi DotNet](../tools/elevated-access.md).</span><span class="sxs-lookup"><span data-stu-id="a41df-119">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="a41df-120">Le istruzioni dettagliate per l'installazione sono disponibili nella [pagina delle versioni di GitHub](https://github.com/dotnet/cli-lab/releases).</span><span class="sxs-lookup"><span data-stu-id="a41df-120">Detailed installation instructions are available on the [GitHub Releases page](https://github.com/dotnet/cli-lab/releases).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="a41df-121">Eseguire lo strumento</span><span class="sxs-lookup"><span data-stu-id="a41df-121">Run the tool</span></span>

<span data-ttu-id="a41df-122">Nei passaggi seguenti viene illustrato l'approccio consigliato per l'esecuzione dello strumento di disinstallazione:</span><span class="sxs-lookup"><span data-stu-id="a41df-122">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="a41df-123">Passaggio 1: visualizzare gli SDK e i runtime di .NET Core installati</span><span class="sxs-lookup"><span data-stu-id="a41df-123">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="a41df-124">Passaggio 2: eseguire un'esecuzione a secco</span><span class="sxs-lookup"><span data-stu-id="a41df-124">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="a41df-125">Passaggio 3: disinstallare SDK e runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="a41df-125">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="a41df-126">Passaggio 4: eliminare la cartella di fallback NuGet (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="a41df-126">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="a41df-127">Passaggio 1: visualizzare gli SDK e i runtime di .NET Core installati</span><span class="sxs-lookup"><span data-stu-id="a41df-127">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="a41df-128">Il comando `dotnet-core-uninstall list` elenca gli SDK di .NET Core installati e i runtime che possono essere rimossi con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="a41df-128">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="a41df-129">Alcuni SDK e Runtime possono essere richiesti da Visual Studio e vengono visualizzati con una nota del motivo per cui non è consigliabile disinstallarli.</span><span class="sxs-lookup"><span data-stu-id="a41df-129">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

<span data-ttu-id="a41df-130">**elenco di disinstallazione DotNet-Core**</span><span class="sxs-lookup"><span data-stu-id="a41df-130">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="a41df-131">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a41df-131">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="a41df-132">Options</span><span class="sxs-lookup"><span data-stu-id="a41df-132">Options</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="a41df-133">Windows</span><span class="sxs-lookup"><span data-stu-id="a41df-133">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="a41df-134">Elenca tutti i runtime di ASP.NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="a41df-134">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="a41df-135">Elenca tutti i pacchetti di runtime e hosting di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="a41df-135">Lists all the .NET Core runtime and hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="a41df-136">Elenca tutti i runtime di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="a41df-136">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="a41df-137">Elenca tutti gli SDK di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="a41df-137">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="a41df-138">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="a41df-138">Sets the verbosity level.</span></span> <span data-ttu-id="a41df-139">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a41df-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="a41df-140">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="a41df-140">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="a41df-141">Elenca tutti i runtime e gli SDK .NET Core x64 che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="a41df-141">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="a41df-142">Elenca tutti gli SDK di .NET core x86 e i runtime che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="a41df-142">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="a41df-143">macOS</span><span class="sxs-lookup"><span data-stu-id="a41df-143">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="a41df-144">Elenca tutti i runtime di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="a41df-144">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="a41df-145">Elenca tutti gli SDK di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="a41df-145">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="a41df-146">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="a41df-146">Sets the verbosity level.</span></span> <span data-ttu-id="a41df-147">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a41df-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="a41df-148">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="a41df-148">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="a41df-149">Esempi</span><span class="sxs-lookup"><span data-stu-id="a41df-149">Examples</span></span>

* <span data-ttu-id="a41df-150">Elencare tutti i runtime e gli SDK di .NET Core che possono essere rimossi con questo strumento:</span><span class="sxs-lookup"><span data-stu-id="a41df-150">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="a41df-151">Elencare tutti i runtime e gli SDK di .NET Core x64:</span><span class="sxs-lookup"><span data-stu-id="a41df-151">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="a41df-152">Elencare tutti gli SDK di .NET core x86:</span><span class="sxs-lookup"><span data-stu-id="a41df-152">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="a41df-153">Passaggio 2: eseguire un'esecuzione a secco</span><span class="sxs-lookup"><span data-stu-id="a41df-153">Step 2 - Do a dry run</span></span>

<span data-ttu-id="a41df-154">I comandi `dotnet-core-uninstall dry-run` e `dotnet-core-uninstall whatif` visualizzano gli SDK e i runtime di .NET Core che verranno rimossi in base alle opzioni fornite senza eseguire la disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="a41df-154">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="a41df-155">Questi comandi sono sinonimi.</span><span class="sxs-lookup"><span data-stu-id="a41df-155">These commands are synonyms.</span></span>

<span data-ttu-id="a41df-156">**DotNet-Core-Uninstall Dry-Run e DotNet-Core-Uninstall WhatIf**</span><span class="sxs-lookup"><span data-stu-id="a41df-156">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="a41df-157">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a41df-157">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="a41df-158">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a41df-158">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="a41df-159">Versione specificata da disinstallare.</span><span class="sxs-lookup"><span data-stu-id="a41df-159">The specified version to uninstall.</span></span> <span data-ttu-id="a41df-160">È possibile elencare diverse versioni una dopo l'altra, separate da spazi.</span><span class="sxs-lookup"><span data-stu-id="a41df-160">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="a41df-161">Sono supportati anche i file di risposta.</span><span class="sxs-lookup"><span data-stu-id="a41df-161">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="a41df-162">I file di risposta sono un'alternativa all'inserimento di tutte le versioni nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="a41df-162">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="a41df-163">Si tratta di file di testo, in genere con un'estensione \*. rsp e ogni versione è elencata in una riga separata.</span><span class="sxs-lookup"><span data-stu-id="a41df-163">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="a41df-164">Per specificare un file di risposta per l'argomento `VERSION`, usare il carattere \@ immediatamente seguito dal nome del file di risposta.</span><span class="sxs-lookup"><span data-stu-id="a41df-164">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="a41df-165">Options</span><span class="sxs-lookup"><span data-stu-id="a41df-165">Options</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="a41df-166">Windows</span><span class="sxs-lookup"><span data-stu-id="a41df-166">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="a41df-167">Rimuove tutti i runtime e gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a41df-167">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="a41df-168">Rimuove solo gli SDK di .NET Core e i runtime con una versione inferiore alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="a41df-168">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="a41df-169">La versione specificata rimane installata.</span><span class="sxs-lookup"><span data-stu-id="a41df-169">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="a41df-170">Rimuove tutti i runtime e gli SDK di .NET Core, ad eccezione di quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="a41df-170">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="a41df-171">Rimuove gli SDK di .NET Core e i runtime, ad eccezione di una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="a41df-171">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="a41df-172">Rimuove gli SDK di .NET Core e i runtime sostituiti da patch più elevate.</span><span class="sxs-lookup"><span data-stu-id="a41df-172">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="a41df-173">Questa opzione protegge Global. JSON.</span><span class="sxs-lookup"><span data-stu-id="a41df-173">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="a41df-174">Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime.</span><span class="sxs-lookup"><span data-stu-id="a41df-174">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="a41df-175">Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime eccetto quella più alta.</span><span class="sxs-lookup"><span data-stu-id="a41df-175">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="a41df-176">Rimuove solo i runtime ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a41df-176">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="a41df-177">Rimuove solo i pacchetti di runtime e hosting di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a41df-177">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="a41df-178">Rimuove gli SDK di .NET Core e i runtime che corrispondono alla versione del `major.minor` specificata.</span><span class="sxs-lookup"><span data-stu-id="a41df-178">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="a41df-179">Rimuove solo i runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a41df-179">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="a41df-180">Rimuove solo gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a41df-180">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="a41df-181">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="a41df-181">Sets the verbosity level.</span></span> <span data-ttu-id="a41df-182">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a41df-182">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="a41df-183">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="a41df-183">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="a41df-184">Deve essere usato con `--sdk`, `--runtime`e `--aspnet-runtime` per rimuovere gli SDK o i runtime x64.</span><span class="sxs-lookup"><span data-stu-id="a41df-184">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="a41df-185">Deve essere usato con `--sdk`, `--runtime`e `--aspnet-runtime` per rimuovere gli SDK o i Runtime x86.</span><span class="sxs-lookup"><span data-stu-id="a41df-185">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="a41df-186">**`--force`** Forza la rimozione di versioni che potrebbero essere usate da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a41df-186">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="a41df-187">Note:</span><span class="sxs-lookup"><span data-stu-id="a41df-187">Notes:</span></span>

1. <span data-ttu-id="a41df-188">È necessario specificare esattamente uno dei `--sdk`, `--runtime`, `--aspnet-runtime`e `--hosting-bundle`.</span><span class="sxs-lookup"><span data-stu-id="a41df-188">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="a41df-189">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`e `[<VERSION>...]` sono esclusive.</span><span class="sxs-lookup"><span data-stu-id="a41df-189">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="a41df-190">Se non si specifica `--x64` o `--x86`, verranno rimossi sia x64 che x86.</span><span class="sxs-lookup"><span data-stu-id="a41df-190">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="a41df-191">macOS</span><span class="sxs-lookup"><span data-stu-id="a41df-191">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="a41df-192">Rimuove tutti i runtime e gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a41df-192">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="a41df-193">Rimuove gli SDK e i Runtime .NET Core sotto la versione specificata.</span><span class="sxs-lookup"><span data-stu-id="a41df-193">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="a41df-194">La versione specificata rimarrà.</span><span class="sxs-lookup"><span data-stu-id="a41df-194">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="a41df-195">Rimuove gli SDK di .NET Core e i runtime, ad eccezione delle versioni specificate.</span><span class="sxs-lookup"><span data-stu-id="a41df-195">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="a41df-196">Rimuove gli SDK di .NET Core e i runtime, ad eccezione di una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="a41df-196">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="a41df-197">Rimuove gli SDK di .NET Core e i runtime sostituiti da patch più elevate.</span><span class="sxs-lookup"><span data-stu-id="a41df-197">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="a41df-198">Questa opzione protegge Global. JSON.</span><span class="sxs-lookup"><span data-stu-id="a41df-198">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="a41df-199">Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime.</span><span class="sxs-lookup"><span data-stu-id="a41df-199">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="a41df-200">Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime eccetto quella più alta.</span><span class="sxs-lookup"><span data-stu-id="a41df-200">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="a41df-201">Rimuove gli SDK di .NET Core e i runtime che corrispondono alla versione del `major.minor` specificata.</span><span class="sxs-lookup"><span data-stu-id="a41df-201">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="a41df-202">Rimuove solo i runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a41df-202">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="a41df-203">Rimuove solo gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a41df-203">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="a41df-204">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="a41df-204">Sets the verbosity level.</span></span> <span data-ttu-id="a41df-205">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a41df-205">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="a41df-206">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="a41df-206">The default value is `normal`.</span></span>
  
* <span data-ttu-id="a41df-207">**`--force`** Forza la rimozione di versioni che potrebbero essere usate da Visual Studio o da SDK.</span><span class="sxs-lookup"><span data-stu-id="a41df-207">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="a41df-208">Note:</span><span class="sxs-lookup"><span data-stu-id="a41df-208">Notes:</span></span>

1. <span data-ttu-id="a41df-209">È necessario specificare esattamente uno dei `--sdk` e `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="a41df-209">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="a41df-210">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`e `[<VERSION>...]` sono esclusive.</span><span class="sxs-lookup"><span data-stu-id="a41df-210">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="a41df-211">Esempi</span><span class="sxs-lookup"><span data-stu-id="a41df-211">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="a41df-212">Per impostazione predefinita, gli SDK di .NET Core e i runtime che potrebbero essere richiesti da Visual Studio o altri SDK non sono inclusi nell'output `dotnet-core-uninstall dry-run`.</span><span class="sxs-lookup"><span data-stu-id="a41df-212">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="a41df-213">Negli esempi seguenti alcuni degli SDK e dei runtime specificati potrebbero non essere inclusi nell'output, a seconda dello stato del computer.</span><span class="sxs-lookup"><span data-stu-id="a41df-213">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="a41df-214">Per includere tutti gli SDK e i runtime, elencarli in modo esplicito come argomenti oppure usare l'opzione `--force`.</span><span class="sxs-lookup"><span data-stu-id="a41df-214">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="a41df-215">Esecuzione a secco della rimozione di tutti i runtime di .NET Core sostituiti da patch superiori:</span><span class="sxs-lookup"><span data-stu-id="a41df-215">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="a41df-216">Esecuzione a secco della rimozione di tutti gli SDK di .NET Core sotto la versione `2.2.301`:</span><span class="sxs-lookup"><span data-stu-id="a41df-216">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="a41df-217">Passaggio 3: disinstallare SDK e runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="a41df-217">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="a41df-218">`dotnet-core-uninstall remove` disinstalla gli SDK e i Runtime .NET Core specificati da una raccolta di opzioni.</span><span class="sxs-lookup"><span data-stu-id="a41df-218">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="a41df-219">Non è possibile usare lo strumento per disinstallare SDK e Runtime con la versione 5,0 o successive.</span><span class="sxs-lookup"><span data-stu-id="a41df-219">The tool can't be used to uninstall SDKs and Runtimes with version 5.0 or above.</span></span>

<span data-ttu-id="a41df-220">Poiché questo strumento presenta un comportamento distruttivo, è **consigliabile eseguire** un'esecuzione a secco prima di eseguire il comando Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="a41df-220">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="a41df-221">L'esecuzione a secco mostrerà quali SDK e runtime di .NET Core verranno rimossi quando si usa il comando `remove`.</span><span class="sxs-lookup"><span data-stu-id="a41df-221">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="a41df-222">Per informazioni su quali SDK e Runtime è possibile rimuovere, fare [riferimento a.](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version)</span><span class="sxs-lookup"><span data-stu-id="a41df-222">Refer to [Should I remove a version?](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="a41df-223">Tenere presenti le indicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a41df-223">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="a41df-224">Questo strumento consente di disinstallare le versioni dei .NET Core SDK richieste da `global.json` file nel computer.</span><span class="sxs-lookup"><span data-stu-id="a41df-224">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="a41df-225">È possibile reinstallare gli SDK di .NET Core dalla pagina [Scarica .NET Core](https://dotnet.microsoft.com/download/dotnet-core) .</span><span class="sxs-lookup"><span data-stu-id="a41df-225">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="a41df-226">Questo strumento consente di disinstallare le versioni del runtime di .NET Core richieste dalle applicazioni dipendenti dal Framework nel computer.</span><span class="sxs-lookup"><span data-stu-id="a41df-226">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="a41df-227">È possibile reinstallare i runtime di .NET Core dalla pagina [Scarica .NET Core](https://dotnet.microsoft.com/download/dotnet-core) .</span><span class="sxs-lookup"><span data-stu-id="a41df-227">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="a41df-228">Questo strumento consente di disinstallare le versioni del .NET Core SDK e del runtime su cui si basa Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a41df-228">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="a41df-229">Se si interrompe l'installazione di Visual Studio, eseguire "Repair" nel programma di installazione di Visual Studio per tornare allo stato di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a41df-229">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="a41df-230">Per impostazione predefinita, tutti i comandi mantengono gli SDK e i Runtime .NET Core che potrebbero essere richiesti da Visual Studio o da altri SDK.</span><span class="sxs-lookup"><span data-stu-id="a41df-230">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="a41df-231">Questi SDK e Runtime possono essere disinstallati elencando in modo esplicito come argomenti o usando l'opzione `--force`.</span><span class="sxs-lookup"><span data-stu-id="a41df-231">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="a41df-232">Per disinstallare SDK e runtime di .NET Core, lo strumento richiede l'elevazione dei privilegi.</span><span class="sxs-lookup"><span data-stu-id="a41df-232">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="a41df-233">Eseguire lo strumento in un prompt dei comandi di amministratore in Windows e con `sudo` in macOS.</span><span class="sxs-lookup"><span data-stu-id="a41df-233">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="a41df-234">I comandi `dry-run` e `whatif` non richiedono l'elevazione dei privilegi.</span><span class="sxs-lookup"><span data-stu-id="a41df-234">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="a41df-235">**DotNet-Core-Disinstalla Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="a41df-235">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="a41df-236">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a41df-236">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="a41df-237">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a41df-237">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="a41df-238">Versione specificata da disinstallare.</span><span class="sxs-lookup"><span data-stu-id="a41df-238">The specified version to uninstall.</span></span> <span data-ttu-id="a41df-239">È possibile elencare diverse versioni una dopo l'altra, separate da spazi.</span><span class="sxs-lookup"><span data-stu-id="a41df-239">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="a41df-240">Sono supportati anche i file di risposta.</span><span class="sxs-lookup"><span data-stu-id="a41df-240">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="a41df-241">I file di risposta sono un'alternativa all'inserimento di tutte le versioni nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="a41df-241">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="a41df-242">Si tratta di file di testo, in genere con un'estensione \*. rsp e ogni versione è elencata in una riga separata.</span><span class="sxs-lookup"><span data-stu-id="a41df-242">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="a41df-243">Per specificare un file di risposta per l'argomento `VERSION`, usare il carattere \@ immediatamente seguito dal nome del file di risposta.</span><span class="sxs-lookup"><span data-stu-id="a41df-243">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="a41df-244">Options</span><span class="sxs-lookup"><span data-stu-id="a41df-244">Options</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="a41df-245">Windows</span><span class="sxs-lookup"><span data-stu-id="a41df-245">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="a41df-246">Rimuove tutti i runtime e gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a41df-246">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="a41df-247">Rimuove solo gli SDK di .NET Core e i runtime con una versione inferiore alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="a41df-247">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="a41df-248">La versione specificata rimane installata.</span><span class="sxs-lookup"><span data-stu-id="a41df-248">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="a41df-249">Rimuove tutti i runtime e gli SDK di .NET Core, ad eccezione di quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="a41df-249">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="a41df-250">Rimuove gli SDK di .NET Core e i runtime, ad eccezione di una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="a41df-250">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="a41df-251">Rimuove gli SDK di .NET Core e i runtime sostituiti da patch più elevate.</span><span class="sxs-lookup"><span data-stu-id="a41df-251">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="a41df-252">Questa opzione protegge Global. JSON.</span><span class="sxs-lookup"><span data-stu-id="a41df-252">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="a41df-253">Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime.</span><span class="sxs-lookup"><span data-stu-id="a41df-253">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="a41df-254">Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime eccetto quella più alta.</span><span class="sxs-lookup"><span data-stu-id="a41df-254">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="a41df-255">Rimuove solo i runtime ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a41df-255">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="a41df-256">Rimuove solo i pacchetti di runtime e hosting di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a41df-256">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="a41df-257">Rimuove gli SDK di .NET Core e i runtime che corrispondono alla versione del `major.minor` specificata.</span><span class="sxs-lookup"><span data-stu-id="a41df-257">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="a41df-258">Rimuove solo i runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a41df-258">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="a41df-259">Rimuove solo gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a41df-259">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="a41df-260">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="a41df-260">Sets the verbosity level.</span></span> <span data-ttu-id="a41df-261">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a41df-261">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="a41df-262">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="a41df-262">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="a41df-263">Deve essere usato con `--sdk`, `--runtime`e `--aspnet-runtime` per rimuovere gli SDK o i runtime x64.</span><span class="sxs-lookup"><span data-stu-id="a41df-263">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="a41df-264">Deve essere usato con `--sdk`, `--runtime`e `--aspnet-runtime` per rimuovere gli SDK o i Runtime x86.</span><span class="sxs-lookup"><span data-stu-id="a41df-264">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="a41df-265">**`-y, --yes`** Esegue il comando senza richiedere una conferma Yes o no.</span><span class="sxs-lookup"><span data-stu-id="a41df-265">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="a41df-266">**`--force`** Forza la rimozione di versioni che potrebbero essere usate da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a41df-266">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="a41df-267">Note:</span><span class="sxs-lookup"><span data-stu-id="a41df-267">Notes:</span></span>

1. <span data-ttu-id="a41df-268">È necessario specificare esattamente uno dei `--sdk`, `--runtime`, `--aspnet-runtime`e `--hosting-bundle`.</span><span class="sxs-lookup"><span data-stu-id="a41df-268">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="a41df-269">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`e `[<VERSION>...]` sono esclusive.</span><span class="sxs-lookup"><span data-stu-id="a41df-269">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="a41df-270">Se non si specifica `--x64` o `--x86`, verranno rimossi sia x64 che x86.</span><span class="sxs-lookup"><span data-stu-id="a41df-270">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="a41df-271">macOS</span><span class="sxs-lookup"><span data-stu-id="a41df-271">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="a41df-272">Rimuove tutti i runtime e gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a41df-272">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="a41df-273">Rimuove gli SDK e i Runtime .NET Core sotto la versione specificata.</span><span class="sxs-lookup"><span data-stu-id="a41df-273">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="a41df-274">La versione specificata rimarrà.</span><span class="sxs-lookup"><span data-stu-id="a41df-274">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="a41df-275">Rimuove gli SDK di .NET Core e i runtime, ad eccezione delle versioni specificate.</span><span class="sxs-lookup"><span data-stu-id="a41df-275">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="a41df-276">Rimuove gli SDK di .NET Core e i runtime, ad eccezione di una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="a41df-276">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="a41df-277">Rimuove gli SDK di .NET Core e i runtime sostituiti da patch più elevate.</span><span class="sxs-lookup"><span data-stu-id="a41df-277">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="a41df-278">Questa opzione protegge Global. JSON.</span><span class="sxs-lookup"><span data-stu-id="a41df-278">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="a41df-279">Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime.</span><span class="sxs-lookup"><span data-stu-id="a41df-279">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="a41df-280">Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime eccetto quella più alta.</span><span class="sxs-lookup"><span data-stu-id="a41df-280">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="a41df-281">Rimuove gli SDK di .NET Core e i runtime che corrispondono alla versione del `major.minor` specificata.</span><span class="sxs-lookup"><span data-stu-id="a41df-281">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="a41df-282">Rimuove solo i runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a41df-282">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="a41df-283">Rimuove solo gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a41df-283">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="a41df-284">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="a41df-284">Sets the verbosity level.</span></span> <span data-ttu-id="a41df-285">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a41df-285">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="a41df-286">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="a41df-286">The default value is `normal`.</span></span>

* <span data-ttu-id="a41df-287">**`-y, --yes`** Esegue il comando senza richiedere la conferma Y/N.</span><span class="sxs-lookup"><span data-stu-id="a41df-287">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="a41df-288">**`--force`** Forza la rimozione di versioni che potrebbero essere usate da Visual Studio o da SDK.</span><span class="sxs-lookup"><span data-stu-id="a41df-288">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="a41df-289">Note:</span><span class="sxs-lookup"><span data-stu-id="a41df-289">Notes:</span></span>

1. <span data-ttu-id="a41df-290">È necessario specificare esattamente uno dei `--sdk` e `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="a41df-290">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="a41df-291">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`e `[<VERSION>...]` sono esclusive.</span><span class="sxs-lookup"><span data-stu-id="a41df-291">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="a41df-292">Esempi</span><span class="sxs-lookup"><span data-stu-id="a41df-292">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="a41df-293">Per impostazione predefinita, vengono conservati gli SDK e i Runtime .NET Core che potrebbero essere richiesti da Visual Studio o altri SDK.</span><span class="sxs-lookup"><span data-stu-id="a41df-293">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="a41df-294">Negli esempi seguenti è possibile che alcuni degli SDK e dei runtime specificati rimangano, a seconda dello stato del computer.</span><span class="sxs-lookup"><span data-stu-id="a41df-294">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="a41df-295">Per rimuovere tutti gli SDK e i runtime, elencarli in modo esplicito come argomenti oppure usare l'opzione `--force`.</span><span class="sxs-lookup"><span data-stu-id="a41df-295">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="a41df-296">Rimuovere tutti i runtime di .NET Core eccetto la versione `3.0.0-preview6-27804-01` senza richiedere la conferma Y/N:</span><span class="sxs-lookup"><span data-stu-id="a41df-296">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="a41df-297">Rimuovere tutti gli SDK di .NET Core 1,1 senza richiedere la conferma Y/n:</span><span class="sxs-lookup"><span data-stu-id="a41df-297">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="a41df-298">Rimuovere .NET Core 1.1.11 SDK senza output della console:</span><span class="sxs-lookup"><span data-stu-id="a41df-298">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="a41df-299">Rimuovere tutti gli SDK di .NET Core che possono essere rimossi in modo sicuro da questo strumento:</span><span class="sxs-lookup"><span data-stu-id="a41df-299">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="a41df-300">Rimuovere tutti gli SDK di .NET Core che possono essere rimossi da questo strumento, inclusi gli SDK che potrebbero essere richiesti da Visual Studio (scelta non consigliata):</span><span class="sxs-lookup"><span data-stu-id="a41df-300">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="a41df-301">Rimuovere tutti gli SDK di .NET Core specificati nel file di risposta `versions.rsp`</span><span class="sxs-lookup"><span data-stu-id="a41df-301">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="a41df-302">Il contenuto di *Versions. rsp* è il seguente:</span><span class="sxs-lookup"><span data-stu-id="a41df-302">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="a41df-303">Passaggio 4: eliminare la cartella di fallback NuGet (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="a41df-303">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="a41df-304">In alcuni casi non è più necessario il `NuGetFallbackFolder` e potrebbe essere opportuno eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="a41df-304">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="a41df-305">Per ulteriori informazioni sull'eliminazione di questa cartella, vedere [Remove the NuGetFallbackFolder](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span><span class="sxs-lookup"><span data-stu-id="a41df-305">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="a41df-306">Disinstalla lo strumento</span><span class="sxs-lookup"><span data-stu-id="a41df-306">Uninstall the tool</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="a41df-307">Windows</span><span class="sxs-lookup"><span data-stu-id="a41df-307">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="a41df-308">Aprire **Installazione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="a41df-308">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="a41df-309">Cercare `Microsoft .NET Core SDK Uninstall Tool`.</span><span class="sxs-lookup"><span data-stu-id="a41df-309">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="a41df-310">Selezionare **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="a41df-310">Select **Uninstall**.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="a41df-311">macOS</span><span class="sxs-lookup"><span data-stu-id="a41df-311">macOS</span></span>](#tab/macos)

<span data-ttu-id="a41df-312">Eliminare il file *DotNet-Core-Uninstall. tar. gz* scaricato dalla directory in cui è stato installato.</span><span class="sxs-lookup"><span data-stu-id="a41df-312">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="a41df-313">Se il contenuto di questo file è stato decompresso in un'altra directory, assicurarsi di eliminare anche tale contenuto.</span><span class="sxs-lookup"><span data-stu-id="a41df-313">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---
