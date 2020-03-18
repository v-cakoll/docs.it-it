---
title: Strumento di disinstallazione
description: Una panoramica dello strumento di disinstallazione di .NET Core, uno strumento guidato che consente la pulizia controllata di .NET Core SDK e runtime.
author: sfoslund
ms.date: 01/06/2020
ms.openlocfilehash: bd20cba133cbb754dcca48e48b76a391a9efacba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847052"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="f318a-103">Strumento di disinstallazione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="f318a-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="f318a-104">Lo strumento di [disinstallazione](https://aka.ms/dotnet-core-uninstall-tool) di .NET Core (`dotnet-core-uninstall`) consente di rimuovere gli SDK e i runtime di .NET Core da un sistema.</span><span class="sxs-lookup"><span data-stu-id="f318a-104">The [.NET Core Uninstall Tool](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="f318a-105">È disponibile una raccolta di opzioni per specificare le versioni che si desidera disinstallare.</span><span class="sxs-lookup"><span data-stu-id="f318a-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="f318a-106">Lo strumento supporta Windows e macOS.</span><span class="sxs-lookup"><span data-stu-id="f318a-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="f318a-107">Linux non è attualmente supportato.</span><span class="sxs-lookup"><span data-stu-id="f318a-107">Linux is currently not supported.</span></span>

<span data-ttu-id="f318a-108">In Windows, lo strumento può disinstallare solo SDK e runtime installati utilizzando uno dei seguenti programmi di installazione:</span><span class="sxs-lookup"><span data-stu-id="f318a-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="f318a-109">Il programma di installazione di .NET Core SDK e runtime.</span><span class="sxs-lookup"><span data-stu-id="f318a-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="f318a-110">Il programma di installazione di Visual Studio nelle versioni precedenti a Visual Studio 2019 versione 16.3.The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span><span class="sxs-lookup"><span data-stu-id="f318a-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="f318a-111">In macOS, lo strumento può disinstallare solo SDK e runtime che si trovano nella cartella */usr/local/share/dotnet.*</span><span class="sxs-lookup"><span data-stu-id="f318a-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="f318a-112">A causa di queste limitazioni, lo strumento potrebbe non essere in grado di disinstallare tutti gli SDK e runtime di .NET Core nel computer.</span><span class="sxs-lookup"><span data-stu-id="f318a-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="f318a-113">È possibile `dotnet --info` utilizzare il comando per trovare tutti gli SDK e runtime di .NET Core installati, inclusi gli SDK e i runtime che questo strumento non può rimuovere.</span><span class="sxs-lookup"><span data-stu-id="f318a-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="f318a-114">Il `dotnet-core-uninstall list` comando mostra quali SDK possono essere disinstallati con lo strumento.</span><span class="sxs-lookup"><span data-stu-id="f318a-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="f318a-115">Installare lo strumento</span><span class="sxs-lookup"><span data-stu-id="f318a-115">Install the tool</span></span>

<span data-ttu-id="f318a-116">È possibile scaricare lo strumento di disinstallazione di .NET Core da qui e trovare il codice sorgente nel repository dotnet/cli-lab GitHub.You can download the .NET Core Uninstall Tool from [here](https://aka.ms/dotnet-core-uninstall-tool) and find the source code at the [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub repository.</span><span class="sxs-lookup"><span data-stu-id="f318a-116">You can download the .NET Core Uninstall Tool from [here](https://aka.ms/dotnet-core-uninstall-tool) and find the source code at the [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="f318a-117">Lo strumento richiede l'elevazione dei privilegi per disinstallare gli SDK e i runtime di .NET Core.The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span><span class="sxs-lookup"><span data-stu-id="f318a-117">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="f318a-118">Pertanto, deve essere installato in una directory protetta da scrittura, ad esempio *C:* , Programmi su Windows o */usr/local/bin* su macOS.</span><span class="sxs-lookup"><span data-stu-id="f318a-118">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="f318a-119">Vedere anche [Accesso elevato per i comandi dotnet](../tools/elevated-access.md).</span><span class="sxs-lookup"><span data-stu-id="f318a-119">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="f318a-120">Per ulteriori informazioni, vedere le [istruzioni dettagliate per l'installazione.](https://aka.ms/dotnet-core-uninstall-tool)</span><span class="sxs-lookup"><span data-stu-id="f318a-120">For more information, see the [detailed installation instructions](https://aka.ms/dotnet-core-uninstall-tool).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="f318a-121">Eseguire lo strumento</span><span class="sxs-lookup"><span data-stu-id="f318a-121">Run the tool</span></span>

<span data-ttu-id="f318a-122">I passaggi seguenti illustrano l'approccio consigliato per l'esecuzione dello strumento di disinstallazione:</span><span class="sxs-lookup"><span data-stu-id="f318a-122">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="f318a-123">Passaggio 1 - Visualizzare gli SDK e i runtime di .NET Core installatiStep 1 - Display installed .NET Core SDKs and runtimes</span><span class="sxs-lookup"><span data-stu-id="f318a-123">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="f318a-124">Fase 2 - Eseguire una corsa a secco</span><span class="sxs-lookup"><span data-stu-id="f318a-124">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="f318a-125">Passaggio 3 - Disinstallare gli SDK e i runtime di .NET CoreStep 3 - Uninstall .NET Core SDKs and Runtimes</span><span class="sxs-lookup"><span data-stu-id="f318a-125">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="f318a-126">Passaggio 4 - Eliminare la cartella di fallback NuGet (facoltativo)Step 4 - Delete the NuGet fallback folder (optional)</span><span class="sxs-lookup"><span data-stu-id="f318a-126">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="f318a-127">Passaggio 1 - Visualizzare gli SDK e i runtime di .NET Core installatiStep 1 - Display installed .NET Core SDKs and runtimes</span><span class="sxs-lookup"><span data-stu-id="f318a-127">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="f318a-128">Il `dotnet-core-uninstall list` comando elenca gli SDK e i runtime .NET Core installati che possono essere rimossi con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="f318a-128">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="f318a-129">Alcuni SDK e runtime potrebbero essere richiesti da Visual Studio e vengono visualizzati con una nota del motivo per cui non è consigliabile disinstallarli.</span><span class="sxs-lookup"><span data-stu-id="f318a-129">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

<span data-ttu-id="f318a-130">**elenco dotnet-core-uninstall**</span><span class="sxs-lookup"><span data-stu-id="f318a-130">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="f318a-131">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="f318a-131">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="f318a-132">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f318a-132">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="f318a-133">Windows</span><span class="sxs-lookup"><span data-stu-id="f318a-133">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="f318a-134">Elenca tutti i runtime di ASP.NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="f318a-134">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="f318a-135">Elenca tutti i pacchetti di runtime e di hosting di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="f318a-135">Lists all the .NET Core runtime and hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="f318a-136">Elenca tutti i runtime di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="f318a-136">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="f318a-137">Elenca tutti gli SDK di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="f318a-137">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f318a-138">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f318a-138">Sets the verbosity level.</span></span> <span data-ttu-id="f318a-139">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f318a-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f318a-140">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="f318a-140">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="f318a-141">Elenca tutti gli SDK e i runtime x64 .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="f318a-141">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="f318a-142">Elenca tutti gli SDK e i runtime x86 .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="f318a-142">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macos"></a>[<span data-ttu-id="f318a-143">Macos</span><span class="sxs-lookup"><span data-stu-id="f318a-143">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="f318a-144">Elenca tutti i runtime di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="f318a-144">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="f318a-145">Elenca tutti gli SDK di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="f318a-145">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f318a-146">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f318a-146">Sets the verbosity level.</span></span> <span data-ttu-id="f318a-147">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f318a-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f318a-148">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="f318a-148">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="f318a-149">Esempi</span><span class="sxs-lookup"><span data-stu-id="f318a-149">Examples</span></span>

* <span data-ttu-id="f318a-150">Elencare tutti gli SDK e i runtime di .NET Core che possono essere rimossi con questo strumento:List all .NET Core SDKs and runtimes that can be removed with this tool:</span><span class="sxs-lookup"><span data-stu-id="f318a-150">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="f318a-151">Elencare tutti gli SDK e i runtime x64 di .NET Core:</span><span class="sxs-lookup"><span data-stu-id="f318a-151">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="f318a-152">Elencare tutti gli SDK x86 .NET Core:</span><span class="sxs-lookup"><span data-stu-id="f318a-152">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="f318a-153">Fase 2 - Eseguire una corsa a secco</span><span class="sxs-lookup"><span data-stu-id="f318a-153">Step 2 - Do a dry run</span></span>

<span data-ttu-id="f318a-154">I `dotnet-core-uninstall dry-run` `dotnet-core-uninstall whatif` comandi e visualizzano gli SDK e i runtime di .NET Core che verranno rimossi in base alle opzioni fornite senza eseguire la disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="f318a-154">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="f318a-155">Questi comandi sono sinonimi.</span><span class="sxs-lookup"><span data-stu-id="f318a-155">These commands are synonyms.</span></span>

<span data-ttu-id="f318a-156">**dotnet-core-uninstall dry-run e dotnet-core-uninstall whatif**</span><span class="sxs-lookup"><span data-stu-id="f318a-156">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="f318a-157">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="f318a-157">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="f318a-158">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f318a-158">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="f318a-159">Versione specificata da disinstallare.</span><span class="sxs-lookup"><span data-stu-id="f318a-159">The specified version to uninstall.</span></span> <span data-ttu-id="f318a-160">È possibile elencare diverse versioni una dopo l'altra, separate da spazi.</span><span class="sxs-lookup"><span data-stu-id="f318a-160">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="f318a-161">Sono supportati anche i file di risposta.</span><span class="sxs-lookup"><span data-stu-id="f318a-161">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="f318a-162">I file di risposta sono un'alternativa all'inserimento di tutte le versioni nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f318a-162">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="f318a-163">Si tratta di file di \*testo, in genere con estensione rsp, e ogni versione è elencata su una riga separata.</span><span class="sxs-lookup"><span data-stu-id="f318a-163">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="f318a-164">Per specificare un `VERSION` file di \@ risposta per l'argomento, utilizzare il carattere immediatamente seguito dal nome del file di risposta.</span><span class="sxs-lookup"><span data-stu-id="f318a-164">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="f318a-165">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f318a-165">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="f318a-166">Windows</span><span class="sxs-lookup"><span data-stu-id="f318a-166">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="f318a-167">Rimuove tutti gli SDK e runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f318a-167">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="f318a-168">Rimuove solo gli SDK e i runtime di .NET Core con una versione inferiore a quella specificata.</span><span class="sxs-lookup"><span data-stu-id="f318a-168">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="f318a-169">La versione specificata rimane installata.</span><span class="sxs-lookup"><span data-stu-id="f318a-169">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="f318a-170">Rimuove tutti gli SDK e runtime di .NET Core, ad eccezione di quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="f318a-170">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="f318a-171">Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quella più alta.</span><span class="sxs-lookup"><span data-stu-id="f318a-171">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="f318a-172">Rimuove gli SDK e i runtime di .NET Core sostituiti da patch più elevate.</span><span class="sxs-lookup"><span data-stu-id="f318a-172">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="f318a-173">Questa opzione protegge global.json.</span><span class="sxs-lookup"><span data-stu-id="f318a-173">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="f318a-174">Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime.</span><span class="sxs-lookup"><span data-stu-id="f318a-174">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="f318a-175">Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime tranne quello più alto.</span><span class="sxs-lookup"><span data-stu-id="f318a-175">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="f318a-176">Rimuove solo i runtime di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f318a-176">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="f318a-177">Rimuove solo i bundle di runtime e di hosting di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f318a-177">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="f318a-178">Rimuove gli SDK e i runtime di `major.minor` .NET Core che corrispondono alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="f318a-178">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="f318a-179">Rimuove solo i runtime .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f318a-179">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="f318a-180">Rimuove solo gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f318a-180">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f318a-181">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f318a-181">Sets the verbosity level.</span></span> <span data-ttu-id="f318a-182">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f318a-182">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f318a-183">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="f318a-183">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="f318a-184">Deve essere `--sdk`utilizzato `--runtime`con `--aspnet-runtime` , e per rimuovere SDK o runtime x64.</span><span class="sxs-lookup"><span data-stu-id="f318a-184">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="f318a-185">Deve essere `--sdk`utilizzato `--runtime`con `--aspnet-runtime` , e per rimuovere SDK o runtime x86.</span><span class="sxs-lookup"><span data-stu-id="f318a-185">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="f318a-186">**`--force`** Forza la rimozione delle versioni che potrebbero essere utilizzate da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f318a-186">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="f318a-187">Note:</span><span class="sxs-lookup"><span data-stu-id="f318a-187">Notes:</span></span>

1. <span data-ttu-id="f318a-188">Esattamente uno `--sdk` `--runtime`dei `--aspnet-runtime`, `--hosting-bundle` , , ed è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f318a-188">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="f318a-189">`--all`, `--all-below` `--all-but`, `--all-but-latest` `--all-lower-patches`, `--all-previews` `--all-previews-but-latest`, `--major-minor`, `[<VERSION>...]` , , e sono esclusivi.</span><span class="sxs-lookup"><span data-stu-id="f318a-189">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="f318a-190">Se `--x64` `--x86` o non sono specificati, verranno rimossi sia x64 che x86.</span><span class="sxs-lookup"><span data-stu-id="f318a-190">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="f318a-191">Macos</span><span class="sxs-lookup"><span data-stu-id="f318a-191">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="f318a-192">Rimuove tutti gli SDK e runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f318a-192">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="f318a-193">Rimuove gli SDK e i runtime di .NET Core al di sotto della versione specificata.</span><span class="sxs-lookup"><span data-stu-id="f318a-193">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="f318a-194">La versione specificata rimarrà.</span><span class="sxs-lookup"><span data-stu-id="f318a-194">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="f318a-195">Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="f318a-195">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="f318a-196">Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quella più alta.</span><span class="sxs-lookup"><span data-stu-id="f318a-196">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="f318a-197">Rimuove gli SDK e i runtime di .NET Core sostituiti da patch più elevate.</span><span class="sxs-lookup"><span data-stu-id="f318a-197">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="f318a-198">Questa opzione protegge global.json.</span><span class="sxs-lookup"><span data-stu-id="f318a-198">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="f318a-199">Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime.</span><span class="sxs-lookup"><span data-stu-id="f318a-199">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="f318a-200">Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime tranne quello più alto.</span><span class="sxs-lookup"><span data-stu-id="f318a-200">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="f318a-201">Rimuove gli SDK e i runtime di `major.minor` .NET Core che corrispondono alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="f318a-201">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="f318a-202">Rimuove solo i runtime .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f318a-202">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="f318a-203">Rimuove solo gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f318a-203">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f318a-204">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f318a-204">Sets the verbosity level.</span></span> <span data-ttu-id="f318a-205">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f318a-205">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f318a-206">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="f318a-206">The default value is `normal`.</span></span>
  
* <span data-ttu-id="f318a-207">**`--force`** Forza la rimozione delle versioni che potrebbero essere utilizzate da Visual Studio o SDK.</span><span class="sxs-lookup"><span data-stu-id="f318a-207">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="f318a-208">Note:</span><span class="sxs-lookup"><span data-stu-id="f318a-208">Notes:</span></span>

1. <span data-ttu-id="f318a-209">Esattamente uno `--sdk` `--runtime` di ed è richiesto.</span><span class="sxs-lookup"><span data-stu-id="f318a-209">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="f318a-210">`--all`, `--all-below` `--all-but`, `--all-but-latest` `--all-lower-patches`, `--all-previews` `--all-previews-but-latest`, `--major-minor`, `[<VERSION>...]` , , e sono esclusivi.</span><span class="sxs-lookup"><span data-stu-id="f318a-210">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="f318a-211">Esempi</span><span class="sxs-lookup"><span data-stu-id="f318a-211">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="f318a-212">Per impostazione predefinita, gli SDK e i runtime di .NET Core che potrebbero `dotnet-core-uninstall dry-run` essere richiesti da Visual Studio o da altri SDK non sono inclusi nell'output.</span><span class="sxs-lookup"><span data-stu-id="f318a-212">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="f318a-213">Negli esempi seguenti, alcuni SDK e runtime specificati potrebbero non essere inclusi nell'output, a seconda dello stato del computer.</span><span class="sxs-lookup"><span data-stu-id="f318a-213">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="f318a-214">Per includere tutti gli SDK e i runtime, elencarli in modo esplicito come argomenti o utilizzare l'opzione `--force` .</span><span class="sxs-lookup"><span data-stu-id="f318a-214">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="f318a-215">Esecuzione a secco di rimozione di tutti i runtime .NET Core che sono stati sostituiti da patch più elevate:</span><span class="sxs-lookup"><span data-stu-id="f318a-215">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="f318a-216">Esecuzione a secco di rimozione di tutti `2.2.301`gli SDK di .NET Core sotto la versione :</span><span class="sxs-lookup"><span data-stu-id="f318a-216">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="f318a-217">Passaggio 3 - Disinstallare gli SDK e i runtime di .NET CoreStep 3 - Uninstall .NET Core SDKs and Runtimes</span><span class="sxs-lookup"><span data-stu-id="f318a-217">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="f318a-218">`dotnet-core-uninstall remove`disinstalla gli SDK e i runtime di .NET Core specificati da una raccolta di opzioni.</span><span class="sxs-lookup"><span data-stu-id="f318a-218">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="f318a-219">Lo strumento non può essere utilizzato per disinstallare SDK e runtime con la versione 5.0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="f318a-219">The tool can't be used to uninstall SDKs and Runtimes with version 5.0 or above.</span></span>

<span data-ttu-id="f318a-220">Poiché questo strumento ha un comportamento distruttivo, è **consigliabile** eseguire un'esecuzione a secco prima di eseguire il comando remove.</span><span class="sxs-lookup"><span data-stu-id="f318a-220">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="f318a-221">L'esecuzione a secco mostrerà quali SDK e runtime di .NET Core verranno rimossi quando si utilizza il `remove` comando.</span><span class="sxs-lookup"><span data-stu-id="f318a-221">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="f318a-222">Fare riferimento a [È necessario rimuovere una versione?](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version) per sapere quali SDK e runtime sono sicuri da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="f318a-222">Refer to [Should I remove a version?](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="f318a-223">Tenere presenti le indicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f318a-223">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="f318a-224">Questo strumento può disinstallare le versioni di `global.json` .NET Core SDK richieste dai file nel computer.</span><span class="sxs-lookup"><span data-stu-id="f318a-224">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="f318a-225">È possibile reinstallare gli SDK di .NET Core dalla pagina [Scarica .NET Core.You can](https://dotnet.microsoft.com/download/dotnet-core) reinstall .NET Core SDKs from the Download .NET Core page.</span><span class="sxs-lookup"><span data-stu-id="f318a-225">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="f318a-226">Questo strumento può disinstallare le versioni del runtime di .NET Core richieste dalle applicazioni dipendenti dal framework nel computer.</span><span class="sxs-lookup"><span data-stu-id="f318a-226">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="f318a-227">È possibile reinstallare i runtime .NET Core dalla pagina [Scarica .NET Core.You can](https://dotnet.microsoft.com/download/dotnet-core) reinstall .NET Core runtimes from the Download .NET Core page.</span><span class="sxs-lookup"><span data-stu-id="f318a-227">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="f318a-228">Questo strumento può disinstallare le versioni di .NET Core SDK e runtime su cui si basa Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f318a-228">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="f318a-229">Se si interrompe l'installazione di Visual Studio, eseguire "Ripristina" nel programma di installazione di Visual Studio per tornare a uno stato funzionante.</span><span class="sxs-lookup"><span data-stu-id="f318a-229">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="f318a-230">Per impostazione predefinita, tutti i comandi mantengono gli SDK e i runtime di .NET Core che potrebbero essere richiesti da Visual Studio o da altri SDK.</span><span class="sxs-lookup"><span data-stu-id="f318a-230">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="f318a-231">Questi SDK e runtime possono essere disinstallati elencandoli in modo `--force` esplicito come argomenti o utilizzando l'opzione .</span><span class="sxs-lookup"><span data-stu-id="f318a-231">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="f318a-232">Lo strumento richiede l'elevazione dei privilegi per disinstallare gli SDK e i runtime di .NET Core.The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span><span class="sxs-lookup"><span data-stu-id="f318a-232">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="f318a-233">Esegui lo strumento in un prompt `sudo` dei comandi di amministratore su Windows e con macOS.</span><span class="sxs-lookup"><span data-stu-id="f318a-233">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="f318a-234">I `dry-run` `whatif` comandi e non richiedono l'elevazione dei privilegi.</span><span class="sxs-lookup"><span data-stu-id="f318a-234">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="f318a-235">**dotnet-core-uninstall rimuovere**</span><span class="sxs-lookup"><span data-stu-id="f318a-235">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="f318a-236">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="f318a-236">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="f318a-237">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f318a-237">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="f318a-238">Versione specificata da disinstallare.</span><span class="sxs-lookup"><span data-stu-id="f318a-238">The specified version to uninstall.</span></span> <span data-ttu-id="f318a-239">È possibile elencare diverse versioni una dopo l'altra, separate da spazi.</span><span class="sxs-lookup"><span data-stu-id="f318a-239">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="f318a-240">Sono supportati anche i file di risposta.</span><span class="sxs-lookup"><span data-stu-id="f318a-240">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="f318a-241">I file di risposta sono un'alternativa all'inserimento di tutte le versioni nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f318a-241">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="f318a-242">Si tratta di file di \*testo, in genere con estensione rsp, e ogni versione è elencata su una riga separata.</span><span class="sxs-lookup"><span data-stu-id="f318a-242">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="f318a-243">Per specificare un `VERSION` file di \@ risposta per l'argomento, utilizzare il carattere immediatamente seguito dal nome del file di risposta.</span><span class="sxs-lookup"><span data-stu-id="f318a-243">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="f318a-244">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f318a-244">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="f318a-245">Windows</span><span class="sxs-lookup"><span data-stu-id="f318a-245">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="f318a-246">Rimuove tutti gli SDK e runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f318a-246">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="f318a-247">Rimuove solo gli SDK e i runtime di .NET Core con una versione inferiore a quella specificata.</span><span class="sxs-lookup"><span data-stu-id="f318a-247">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="f318a-248">La versione specificata rimane installata.</span><span class="sxs-lookup"><span data-stu-id="f318a-248">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="f318a-249">Rimuove tutti gli SDK e runtime di .NET Core, ad eccezione di quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="f318a-249">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="f318a-250">Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quella più alta.</span><span class="sxs-lookup"><span data-stu-id="f318a-250">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="f318a-251">Rimuove gli SDK e i runtime di .NET Core sostituiti da patch più elevate.</span><span class="sxs-lookup"><span data-stu-id="f318a-251">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="f318a-252">Questa opzione protegge global.json.</span><span class="sxs-lookup"><span data-stu-id="f318a-252">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="f318a-253">Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime.</span><span class="sxs-lookup"><span data-stu-id="f318a-253">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="f318a-254">Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime tranne quello più alto.</span><span class="sxs-lookup"><span data-stu-id="f318a-254">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="f318a-255">Rimuove solo i runtime di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f318a-255">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="f318a-256">Rimuove solo i bundle di runtime e di hosting di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f318a-256">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="f318a-257">Rimuove gli SDK e i runtime di `major.minor` .NET Core che corrispondono alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="f318a-257">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="f318a-258">Rimuove solo i runtime .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f318a-258">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="f318a-259">Rimuove solo gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f318a-259">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f318a-260">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f318a-260">Sets the verbosity level.</span></span> <span data-ttu-id="f318a-261">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f318a-261">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f318a-262">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="f318a-262">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="f318a-263">Deve essere `--sdk`utilizzato `--runtime`con `--aspnet-runtime` , e per rimuovere SDK o runtime x64.</span><span class="sxs-lookup"><span data-stu-id="f318a-263">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="f318a-264">Deve essere `--sdk`utilizzato `--runtime`con `--aspnet-runtime` , e per rimuovere SDK o runtime x86.</span><span class="sxs-lookup"><span data-stu-id="f318a-264">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="f318a-265">**`-y, --yes`** Esegue il comando senza richiedere una conferma sì o no.</span><span class="sxs-lookup"><span data-stu-id="f318a-265">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="f318a-266">**`--force`** Forza la rimozione delle versioni che potrebbero essere utilizzate da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f318a-266">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="f318a-267">Note:</span><span class="sxs-lookup"><span data-stu-id="f318a-267">Notes:</span></span>

1. <span data-ttu-id="f318a-268">Esattamente uno `--sdk` `--runtime`dei `--aspnet-runtime`, `--hosting-bundle` , , ed è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f318a-268">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="f318a-269">`--all`, `--all-below` `--all-but`, `--all-but-latest` `--all-lower-patches`, `--all-previews` `--all-previews-but-latest`, `--major-minor`, `[<VERSION>...]` , , e sono esclusivi.</span><span class="sxs-lookup"><span data-stu-id="f318a-269">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="f318a-270">Se `--x64` `--x86` o non sono specificati, verranno rimossi sia x64 che x86.</span><span class="sxs-lookup"><span data-stu-id="f318a-270">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="f318a-271">Macos</span><span class="sxs-lookup"><span data-stu-id="f318a-271">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="f318a-272">Rimuove tutti gli SDK e runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f318a-272">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="f318a-273">Rimuove gli SDK e i runtime di .NET Core al di sotto della versione specificata.</span><span class="sxs-lookup"><span data-stu-id="f318a-273">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="f318a-274">La versione specificata rimarrà.</span><span class="sxs-lookup"><span data-stu-id="f318a-274">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="f318a-275">Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="f318a-275">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="f318a-276">Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quella più alta.</span><span class="sxs-lookup"><span data-stu-id="f318a-276">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="f318a-277">Rimuove gli SDK e i runtime di .NET Core sostituiti da patch più elevate.</span><span class="sxs-lookup"><span data-stu-id="f318a-277">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="f318a-278">Questa opzione protegge global.json.</span><span class="sxs-lookup"><span data-stu-id="f318a-278">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="f318a-279">Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime.</span><span class="sxs-lookup"><span data-stu-id="f318a-279">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="f318a-280">Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime tranne quello più alto.</span><span class="sxs-lookup"><span data-stu-id="f318a-280">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="f318a-281">Rimuove gli SDK e i runtime di `major.minor` .NET Core che corrispondono alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="f318a-281">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="f318a-282">Rimuove solo i runtime .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f318a-282">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="f318a-283">Rimuove solo gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f318a-283">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f318a-284">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f318a-284">Sets the verbosity level.</span></span> <span data-ttu-id="f318a-285">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f318a-285">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f318a-286">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="f318a-286">The default value is `normal`.</span></span>

* <span data-ttu-id="f318a-287">**`-y, --yes`** Esegue il comando senza richiedere la conferma Y/N.</span><span class="sxs-lookup"><span data-stu-id="f318a-287">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="f318a-288">**`--force`** Forza la rimozione delle versioni che potrebbero essere utilizzate da Visual Studio o SDK.</span><span class="sxs-lookup"><span data-stu-id="f318a-288">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="f318a-289">Note:</span><span class="sxs-lookup"><span data-stu-id="f318a-289">Notes:</span></span>

1. <span data-ttu-id="f318a-290">Esattamente uno `--sdk` `--runtime` di ed è richiesto.</span><span class="sxs-lookup"><span data-stu-id="f318a-290">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="f318a-291">`--all`, `--all-below` `--all-but`, `--all-but-latest` `--all-lower-patches`, `--all-previews` `--all-previews-but-latest`, `--major-minor`, `[<VERSION>...]` , , e sono esclusivi.</span><span class="sxs-lookup"><span data-stu-id="f318a-291">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="f318a-292">Esempi</span><span class="sxs-lookup"><span data-stu-id="f318a-292">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="f318a-293">Per impostazione predefinita, gli SDK e i runtime di .NET Core che potrebbero essere richiesti da Visual Studio o da altri SDK vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="f318a-293">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="f318a-294">Negli esempi seguenti, alcuni degli SDK e dei runtime specificati possono rimanere, a seconda dello stato del computer.</span><span class="sxs-lookup"><span data-stu-id="f318a-294">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="f318a-295">Per rimuovere tutti gli SDK e i runtime, elencarli in modo esplicito come argomenti o utilizzare l'opzione `--force` .</span><span class="sxs-lookup"><span data-stu-id="f318a-295">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="f318a-296">Rimuovere tutti i runtime .NET `3.0.0-preview6-27804-01` Core tranne la versione senza richiedere la conferma Y/N:</span><span class="sxs-lookup"><span data-stu-id="f318a-296">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="f318a-297">Rimuovere tutti gli SDK di .NET Core 1.1 senza richiedere la conferma Y/n:Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span><span class="sxs-lookup"><span data-stu-id="f318a-297">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="f318a-298">Rimuovere .NET Core 1.1.11 SDK senza output della console:</span><span class="sxs-lookup"><span data-stu-id="f318a-298">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="f318a-299">Rimuovere tutti gli SDK di .NET Core che possono essere rimossi in modo sicuro da questo strumento:Remove all .NET Core SDKs that can safely be removed by this tool:</span><span class="sxs-lookup"><span data-stu-id="f318a-299">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="f318a-300">Rimuovere tutti gli SDK di .NET Core che possono essere rimossi da questo strumento, inclusi gli SDK che potrebbero essere richiesti da Visual Studio (scelta non consigliata):</span><span class="sxs-lookup"><span data-stu-id="f318a-300">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="f318a-301">Rimuovere tutti gli SDK di .NET Core specificati nel file di rispostaRemove all .NET Core SDKs that are specified in the response file`versions.rsp`</span><span class="sxs-lookup"><span data-stu-id="f318a-301">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="f318a-302">Il contenuto di *versions.rsp* è il seguente:</span><span class="sxs-lookup"><span data-stu-id="f318a-302">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="f318a-303">Passaggio 4 - Eliminare la cartella di fallback NuGet (facoltativo)Step 4 - Delete the NuGet fallback folder (optional)</span><span class="sxs-lookup"><span data-stu-id="f318a-303">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="f318a-304">In alcuni casi, non `NuGetFallbackFolder` è più necessario il e potrebbe voler eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="f318a-304">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="f318a-305">Per ulteriori informazioni sull'eliminazione di questa cartella, vedere [Rimuovere NuGetFallbackFolder](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span><span class="sxs-lookup"><span data-stu-id="f318a-305">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="f318a-306">Disinstallare lo strumento</span><span class="sxs-lookup"><span data-stu-id="f318a-306">Uninstall the tool</span></span>

## <a name="windows"></a>[<span data-ttu-id="f318a-307">Windows</span><span class="sxs-lookup"><span data-stu-id="f318a-307">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="f318a-308">Aprire **Installazione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="f318a-308">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="f318a-309">Cercare `Microsoft .NET Core SDK Uninstall Tool`.</span><span class="sxs-lookup"><span data-stu-id="f318a-309">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="f318a-310">Selezionare **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="f318a-310">Select **Uninstall**.</span></span>

## <a name="macos"></a>[<span data-ttu-id="f318a-311">Macos</span><span class="sxs-lookup"><span data-stu-id="f318a-311">macOS</span></span>](#tab/macos)

<span data-ttu-id="f318a-312">Eliminare il file *dotnet-core-uninstall.tar.gz* scaricato dalla directory in cui è stato installato.</span><span class="sxs-lookup"><span data-stu-id="f318a-312">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="f318a-313">Se hai decompresso il contenuto di questo file in un'altra directory, assicurati di eliminare anche quel contenuto.</span><span class="sxs-lookup"><span data-stu-id="f318a-313">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---
