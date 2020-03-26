---
title: Strumento di disinstallazione
description: Una panoramica dello strumento di disinstallazione di .NET Core, uno strumento guidato che consente la pulizia controllata di .NET Core SDK e runtime.
author: sfoslund
ms.date: 01/06/2020
ms.openlocfilehash: 816aef6ab8bc0e51bb8befb14fde60513d4fadfc
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507321"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="cdd73-103">Strumento di disinstallazione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="cdd73-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="cdd73-104">Lo strumento di [disinstallazione](https://aka.ms/dotnet-core-uninstall-tool) di .NET Core (`dotnet-core-uninstall`) consente di rimuovere gli SDK e i runtime di .NET Core da un sistema.</span><span class="sxs-lookup"><span data-stu-id="cdd73-104">The [.NET Core Uninstall Tool](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="cdd73-105">È disponibile una raccolta di opzioni per specificare le versioni che si desidera disinstallare.</span><span class="sxs-lookup"><span data-stu-id="cdd73-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="cdd73-106">Lo strumento supporta Windows e macOS.</span><span class="sxs-lookup"><span data-stu-id="cdd73-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="cdd73-107">Linux non è attualmente supportato.</span><span class="sxs-lookup"><span data-stu-id="cdd73-107">Linux is currently not supported.</span></span>

<span data-ttu-id="cdd73-108">In Windows, lo strumento può disinstallare solo SDK e runtime installati utilizzando uno dei seguenti programmi di installazione:</span><span class="sxs-lookup"><span data-stu-id="cdd73-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="cdd73-109">Il programma di installazione di .NET Core SDK e runtime.</span><span class="sxs-lookup"><span data-stu-id="cdd73-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="cdd73-110">Il programma di installazione di Visual Studio nelle versioni precedenti a Visual Studio 2019 versione 16.3.The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span><span class="sxs-lookup"><span data-stu-id="cdd73-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="cdd73-111">In macOS, lo strumento può disinstallare solo SDK e runtime che si trovano nella cartella */usr/local/share/dotnet.*</span><span class="sxs-lookup"><span data-stu-id="cdd73-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="cdd73-112">A causa di queste limitazioni, lo strumento potrebbe non essere in grado di disinstallare tutti gli SDK e runtime di .NET Core nel computer.</span><span class="sxs-lookup"><span data-stu-id="cdd73-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="cdd73-113">È possibile `dotnet --info` utilizzare il comando per trovare tutti gli SDK e runtime di .NET Core installati, inclusi gli SDK e i runtime che questo strumento non può rimuovere.</span><span class="sxs-lookup"><span data-stu-id="cdd73-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="cdd73-114">Il `dotnet-core-uninstall list` comando mostra quali SDK possono essere disinstallati con lo strumento.</span><span class="sxs-lookup"><span data-stu-id="cdd73-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="cdd73-115">Installare lo strumento</span><span class="sxs-lookup"><span data-stu-id="cdd73-115">Install the tool</span></span>

<span data-ttu-id="cdd73-116">È possibile scaricare lo strumento di disinstallazione di .NET Core da qui e trovare il codice sorgente nel repository dotnet/cli-lab GitHub.You can download the .NET Core Uninstall Tool from [here](https://aka.ms/dotnet-core-uninstall-tool) and find the source code at the [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub repository.</span><span class="sxs-lookup"><span data-stu-id="cdd73-116">You can download the .NET Core Uninstall Tool from [here](https://aka.ms/dotnet-core-uninstall-tool) and find the source code at the [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="cdd73-117">Lo strumento richiede l'elevazione dei privilegi per disinstallare gli SDK e i runtime di .NET Core.The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span><span class="sxs-lookup"><span data-stu-id="cdd73-117">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="cdd73-118">Pertanto, deve essere installato in una directory protetta da scrittura, ad esempio *C:* , Programmi su Windows o */usr/local/bin* su macOS.</span><span class="sxs-lookup"><span data-stu-id="cdd73-118">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="cdd73-119">Vedere anche [Accesso elevato per i comandi dotnet](../tools/elevated-access.md).</span><span class="sxs-lookup"><span data-stu-id="cdd73-119">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="cdd73-120">Per ulteriori informazioni, vedere le [istruzioni dettagliate per l'installazione.](https://aka.ms/dotnet-core-uninstall-tool)</span><span class="sxs-lookup"><span data-stu-id="cdd73-120">For more information, see the [detailed installation instructions](https://aka.ms/dotnet-core-uninstall-tool).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="cdd73-121">Eseguire lo strumento</span><span class="sxs-lookup"><span data-stu-id="cdd73-121">Run the tool</span></span>

<span data-ttu-id="cdd73-122">I passaggi seguenti illustrano l'approccio consigliato per l'esecuzione dello strumento di disinstallazione:</span><span class="sxs-lookup"><span data-stu-id="cdd73-122">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="cdd73-123">Passaggio 1 - Visualizzare gli SDK e i runtime di .NET Core installatiStep 1 - Display installed .NET Core SDKs and runtimes</span><span class="sxs-lookup"><span data-stu-id="cdd73-123">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="cdd73-124">Fase 2 - Eseguire una corsa a secco</span><span class="sxs-lookup"><span data-stu-id="cdd73-124">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="cdd73-125">Passaggio 3 - Disinstallare gli SDK e i runtime di .NET CoreStep 3 - Uninstall .NET Core SDKs and Runtimes</span><span class="sxs-lookup"><span data-stu-id="cdd73-125">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="cdd73-126">Passaggio 4 - Eliminare la cartella di fallback NuGet (facoltativo)Step 4 - Delete the NuGet fallback folder (optional)</span><span class="sxs-lookup"><span data-stu-id="cdd73-126">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="cdd73-127">Passaggio 1 - Visualizzare gli SDK e i runtime di .NET Core installatiStep 1 - Display installed .NET Core SDKs and runtimes</span><span class="sxs-lookup"><span data-stu-id="cdd73-127">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="cdd73-128">Il `dotnet-core-uninstall list` comando elenca gli SDK e i runtime .NET Core installati che possono essere rimossi con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="cdd73-128">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="cdd73-129">Alcuni SDK e runtime potrebbero essere richiesti da Visual Studio e vengono visualizzati con una nota del motivo per cui non è consigliabile disinstallarli.</span><span class="sxs-lookup"><span data-stu-id="cdd73-129">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

> [!NOTE]
> <span data-ttu-id="cdd73-130">L'output `dotnet-core-uninstall list` del comando non corrisponderà all'elenco `dotnet --info` delle versioni installate nell'output della maggior parte dei casi.</span><span class="sxs-lookup"><span data-stu-id="cdd73-130">The output of the `dotnet-core-uninstall list` command will not match the list of installed versions in the output of `dotnet --info` in most cases.</span></span> <span data-ttu-id="cdd73-131">In particolare, questo strumento non visualizzerà le versioni installate da file zip o gestite da Visual Studio (qualsiasi versione installata con Visual Studio 2019 16.3 o versioni successive).</span><span class="sxs-lookup"><span data-stu-id="cdd73-131">Specifically, this tool will not display versions installed by zip files or managed by Visual Studio (any version installed with Visual Studio 2019 16.3 or later).</span></span> <span data-ttu-id="cdd73-132">Un modo per verificare se una versione è `Add or Remove Programs`gestita da Visual Studio consiste nel visualizzarla in , in cui le versioni gestite di Visual Studio sono contrassegnate come tali nei relativi nomi visualizzati.</span><span class="sxs-lookup"><span data-stu-id="cdd73-132">One way to check if a version is managed by Visual Studio is to view it in `Add or Remove Programs`, where Visual Studio managed versions are marked as such in their display names.</span></span>

<span data-ttu-id="cdd73-133">**elenco dotnet-core-uninstall**</span><span class="sxs-lookup"><span data-stu-id="cdd73-133">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="cdd73-134">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="cdd73-134">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="cdd73-135">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cdd73-135">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="cdd73-136">Windows</span><span class="sxs-lookup"><span data-stu-id="cdd73-136">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="cdd73-137">Elenca tutti i runtime di ASP.NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="cdd73-137">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="cdd73-138">Elenca tutti i pacchetti di runtime e di hosting di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="cdd73-138">Lists all the .NET Core runtime and hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="cdd73-139">Elenca tutti i runtime di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="cdd73-139">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="cdd73-140">Elenca tutti gli SDK di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="cdd73-140">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="cdd73-141">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="cdd73-141">Sets the verbosity level.</span></span> <span data-ttu-id="cdd73-142">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cdd73-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="cdd73-143">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="cdd73-143">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="cdd73-144">Elenca tutti gli SDK e i runtime x64 .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="cdd73-144">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="cdd73-145">Elenca tutti gli SDK e i runtime x86 .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="cdd73-145">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macos"></a>[<span data-ttu-id="cdd73-146">Macos</span><span class="sxs-lookup"><span data-stu-id="cdd73-146">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="cdd73-147">Elenca tutti i runtime di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="cdd73-147">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="cdd73-148">Elenca tutti gli SDK di .NET Core che possono essere disinstallati con questo strumento.</span><span class="sxs-lookup"><span data-stu-id="cdd73-148">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="cdd73-149">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="cdd73-149">Sets the verbosity level.</span></span> <span data-ttu-id="cdd73-150">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cdd73-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="cdd73-151">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="cdd73-151">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="cdd73-152">Esempi</span><span class="sxs-lookup"><span data-stu-id="cdd73-152">Examples</span></span>

* <span data-ttu-id="cdd73-153">Elencare tutti gli SDK e i runtime di .NET Core che possono essere rimossi con questo strumento:List all .NET Core SDKs and runtimes that can be removed with this tool:</span><span class="sxs-lookup"><span data-stu-id="cdd73-153">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="cdd73-154">Elencare tutti gli SDK e i runtime x64 di .NET Core:</span><span class="sxs-lookup"><span data-stu-id="cdd73-154">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="cdd73-155">Elencare tutti gli SDK x86 .NET Core:</span><span class="sxs-lookup"><span data-stu-id="cdd73-155">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="cdd73-156">Fase 2 - Eseguire una corsa a secco</span><span class="sxs-lookup"><span data-stu-id="cdd73-156">Step 2 - Do a dry run</span></span>

<span data-ttu-id="cdd73-157">I `dotnet-core-uninstall dry-run` `dotnet-core-uninstall whatif` comandi e visualizzano gli SDK e i runtime di .NET Core che verranno rimossi in base alle opzioni fornite senza eseguire la disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="cdd73-157">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="cdd73-158">Questi comandi sono sinonimi.</span><span class="sxs-lookup"><span data-stu-id="cdd73-158">These commands are synonyms.</span></span>

<span data-ttu-id="cdd73-159">**dotnet-core-uninstall dry-run e dotnet-core-uninstall whatif**</span><span class="sxs-lookup"><span data-stu-id="cdd73-159">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="cdd73-160">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="cdd73-160">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="cdd73-161">Argomenti</span><span class="sxs-lookup"><span data-stu-id="cdd73-161">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="cdd73-162">Versione specificata da disinstallare.</span><span class="sxs-lookup"><span data-stu-id="cdd73-162">The specified version to uninstall.</span></span> <span data-ttu-id="cdd73-163">È possibile elencare diverse versioni una dopo l'altra, separate da spazi.</span><span class="sxs-lookup"><span data-stu-id="cdd73-163">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="cdd73-164">Sono supportati anche i file di risposta.</span><span class="sxs-lookup"><span data-stu-id="cdd73-164">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="cdd73-165">I file di risposta sono un'alternativa all'inserimento di tutte le versioni nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="cdd73-165">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="cdd73-166">Si tratta di file di \*testo, in genere con estensione rsp, e ogni versione è elencata su una riga separata.</span><span class="sxs-lookup"><span data-stu-id="cdd73-166">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="cdd73-167">Per specificare un `VERSION` file di \@ risposta per l'argomento, utilizzare il carattere immediatamente seguito dal nome del file di risposta.</span><span class="sxs-lookup"><span data-stu-id="cdd73-167">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="cdd73-168">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cdd73-168">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="cdd73-169">Windows</span><span class="sxs-lookup"><span data-stu-id="cdd73-169">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="cdd73-170">Rimuove tutti gli SDK e runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdd73-170">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="cdd73-171">Rimuove solo gli SDK e i runtime di .NET Core con una versione inferiore a quella specificata.</span><span class="sxs-lookup"><span data-stu-id="cdd73-171">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="cdd73-172">La versione specificata rimane installata.</span><span class="sxs-lookup"><span data-stu-id="cdd73-172">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="cdd73-173">Rimuove tutti gli SDK e runtime di .NET Core, ad eccezione di quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="cdd73-173">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="cdd73-174">Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quella più alta.</span><span class="sxs-lookup"><span data-stu-id="cdd73-174">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="cdd73-175">Rimuove gli SDK e i runtime di .NET Core sostituiti da patch più elevate.</span><span class="sxs-lookup"><span data-stu-id="cdd73-175">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="cdd73-176">Questa opzione protegge global.json.</span><span class="sxs-lookup"><span data-stu-id="cdd73-176">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="cdd73-177">Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime.</span><span class="sxs-lookup"><span data-stu-id="cdd73-177">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="cdd73-178">Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime tranne quello più alto.</span><span class="sxs-lookup"><span data-stu-id="cdd73-178">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="cdd73-179">Rimuove solo i runtime di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdd73-179">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="cdd73-180">Rimuove solo i bundle di runtime e di hosting di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdd73-180">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="cdd73-181">Rimuove gli SDK e i runtime di `major.minor` .NET Core che corrispondono alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="cdd73-181">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="cdd73-182">Rimuove solo i runtime .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdd73-182">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="cdd73-183">Rimuove solo gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdd73-183">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="cdd73-184">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="cdd73-184">Sets the verbosity level.</span></span> <span data-ttu-id="cdd73-185">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cdd73-185">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="cdd73-186">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="cdd73-186">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="cdd73-187">Deve essere `--sdk`utilizzato `--runtime`con `--aspnet-runtime` , e per rimuovere SDK o runtime x64.</span><span class="sxs-lookup"><span data-stu-id="cdd73-187">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="cdd73-188">Deve essere `--sdk`utilizzato `--runtime`con `--aspnet-runtime` , e per rimuovere SDK o runtime x86.</span><span class="sxs-lookup"><span data-stu-id="cdd73-188">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="cdd73-189">**`--force`** Forza la rimozione delle versioni che potrebbero essere utilizzate da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cdd73-189">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="cdd73-190">Note:</span><span class="sxs-lookup"><span data-stu-id="cdd73-190">Notes:</span></span>

1. <span data-ttu-id="cdd73-191">Esattamente uno `--sdk` `--runtime`dei `--aspnet-runtime`, `--hosting-bundle` , , ed è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cdd73-191">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="cdd73-192">`--all`, `--all-below` `--all-but`, `--all-but-latest` `--all-lower-patches`, `--all-previews` `--all-previews-but-latest`, `--major-minor`, `[<VERSION>...]` , , e sono esclusivi.</span><span class="sxs-lookup"><span data-stu-id="cdd73-192">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="cdd73-193">Se `--x64` `--x86` o non sono specificati, verranno rimossi sia x64 che x86.</span><span class="sxs-lookup"><span data-stu-id="cdd73-193">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="cdd73-194">Macos</span><span class="sxs-lookup"><span data-stu-id="cdd73-194">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="cdd73-195">Rimuove tutti gli SDK e runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdd73-195">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="cdd73-196">Rimuove gli SDK e i runtime di .NET Core al di sotto della versione specificata.</span><span class="sxs-lookup"><span data-stu-id="cdd73-196">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="cdd73-197">La versione specificata rimarrà.</span><span class="sxs-lookup"><span data-stu-id="cdd73-197">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="cdd73-198">Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="cdd73-198">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="cdd73-199">Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quella più alta.</span><span class="sxs-lookup"><span data-stu-id="cdd73-199">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="cdd73-200">Rimuove gli SDK e i runtime di .NET Core sostituiti da patch più elevate.</span><span class="sxs-lookup"><span data-stu-id="cdd73-200">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="cdd73-201">Questa opzione protegge global.json.</span><span class="sxs-lookup"><span data-stu-id="cdd73-201">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="cdd73-202">Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime.</span><span class="sxs-lookup"><span data-stu-id="cdd73-202">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="cdd73-203">Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime tranne quello più alto.</span><span class="sxs-lookup"><span data-stu-id="cdd73-203">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="cdd73-204">Rimuove gli SDK e i runtime di `major.minor` .NET Core che corrispondono alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="cdd73-204">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="cdd73-205">Rimuove solo i runtime .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdd73-205">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="cdd73-206">Rimuove solo gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdd73-206">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="cdd73-207">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="cdd73-207">Sets the verbosity level.</span></span> <span data-ttu-id="cdd73-208">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cdd73-208">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="cdd73-209">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="cdd73-209">The default value is `normal`.</span></span>
  
* <span data-ttu-id="cdd73-210">**`--force`** Forza la rimozione delle versioni che potrebbero essere utilizzate da Visual Studio o SDK.</span><span class="sxs-lookup"><span data-stu-id="cdd73-210">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="cdd73-211">Note:</span><span class="sxs-lookup"><span data-stu-id="cdd73-211">Notes:</span></span>

1. <span data-ttu-id="cdd73-212">Esattamente uno `--sdk` `--runtime` di ed è richiesto.</span><span class="sxs-lookup"><span data-stu-id="cdd73-212">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="cdd73-213">`--all`, `--all-below` `--all-but`, `--all-but-latest` `--all-lower-patches`, `--all-previews` `--all-previews-but-latest`, `--major-minor`, `[<VERSION>...]` , , e sono esclusivi.</span><span class="sxs-lookup"><span data-stu-id="cdd73-213">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="cdd73-214">Esempi</span><span class="sxs-lookup"><span data-stu-id="cdd73-214">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="cdd73-215">Per impostazione predefinita, gli SDK e i runtime di .NET Core che potrebbero `dotnet-core-uninstall dry-run` essere richiesti da Visual Studio o da altri SDK non sono inclusi nell'output.</span><span class="sxs-lookup"><span data-stu-id="cdd73-215">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="cdd73-216">Negli esempi seguenti, alcuni SDK e runtime specificati potrebbero non essere inclusi nell'output, a seconda dello stato del computer.</span><span class="sxs-lookup"><span data-stu-id="cdd73-216">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="cdd73-217">Per includere tutti gli SDK e i runtime, elencarli in modo esplicito come argomenti o utilizzare l'opzione `--force` .</span><span class="sxs-lookup"><span data-stu-id="cdd73-217">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="cdd73-218">Esecuzione a secco di rimozione di tutti i runtime .NET Core che sono stati sostituiti da patch più elevate:</span><span class="sxs-lookup"><span data-stu-id="cdd73-218">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="cdd73-219">Esecuzione a secco di rimozione di tutti `2.2.301`gli SDK di .NET Core sotto la versione :</span><span class="sxs-lookup"><span data-stu-id="cdd73-219">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="cdd73-220">Passaggio 3 - Disinstallare gli SDK e i runtime di .NET CoreStep 3 - Uninstall .NET Core SDKs and Runtimes</span><span class="sxs-lookup"><span data-stu-id="cdd73-220">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="cdd73-221">`dotnet-core-uninstall remove`disinstalla gli SDK e i runtime di .NET Core specificati da una raccolta di opzioni.</span><span class="sxs-lookup"><span data-stu-id="cdd73-221">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="cdd73-222">Lo strumento non può essere utilizzato per disinstallare SDK e runtime con la versione 5.0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="cdd73-222">The tool can't be used to uninstall SDKs and Runtimes with version 5.0 or above.</span></span>

<span data-ttu-id="cdd73-223">Poiché questo strumento ha un comportamento distruttivo, è **consigliabile** eseguire un'esecuzione a secco prima di eseguire il comando remove.</span><span class="sxs-lookup"><span data-stu-id="cdd73-223">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="cdd73-224">L'esecuzione a secco mostrerà quali SDK e runtime di .NET Core verranno rimossi quando si utilizza il `remove` comando.</span><span class="sxs-lookup"><span data-stu-id="cdd73-224">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="cdd73-225">Fare riferimento a [È necessario rimuovere una versione?](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version) per sapere quali SDK e runtime sono sicuri da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="cdd73-225">Refer to [Should I remove a version?](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="cdd73-226">Tenere presenti le indicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdd73-226">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="cdd73-227">Questo strumento può disinstallare le versioni di `global.json` .NET Core SDK richieste dai file nel computer.</span><span class="sxs-lookup"><span data-stu-id="cdd73-227">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="cdd73-228">È possibile reinstallare gli SDK di .NET Core dalla pagina [Scarica .NET Core.You can](https://dotnet.microsoft.com/download/dotnet-core) reinstall .NET Core SDKs from the Download .NET Core page.</span><span class="sxs-lookup"><span data-stu-id="cdd73-228">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="cdd73-229">Questo strumento può disinstallare le versioni del runtime di .NET Core richieste dalle applicazioni dipendenti dal framework nel computer.</span><span class="sxs-lookup"><span data-stu-id="cdd73-229">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="cdd73-230">È possibile reinstallare i runtime .NET Core dalla pagina [Scarica .NET Core.You can](https://dotnet.microsoft.com/download/dotnet-core) reinstall .NET Core runtimes from the Download .NET Core page.</span><span class="sxs-lookup"><span data-stu-id="cdd73-230">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="cdd73-231">Questo strumento può disinstallare le versioni di .NET Core SDK e runtime su cui si basa Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cdd73-231">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="cdd73-232">Se si interrompe l'installazione di Visual Studio, eseguire "Ripristina" nel programma di installazione di Visual Studio per tornare a uno stato funzionante.</span><span class="sxs-lookup"><span data-stu-id="cdd73-232">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="cdd73-233">Per impostazione predefinita, tutti i comandi mantengono gli SDK e i runtime di .NET Core che potrebbero essere richiesti da Visual Studio o da altri SDK.</span><span class="sxs-lookup"><span data-stu-id="cdd73-233">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="cdd73-234">Questi SDK e runtime possono essere disinstallati elencandoli in modo `--force` esplicito come argomenti o utilizzando l'opzione .</span><span class="sxs-lookup"><span data-stu-id="cdd73-234">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="cdd73-235">Lo strumento richiede l'elevazione dei privilegi per disinstallare gli SDK e i runtime di .NET Core.The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span><span class="sxs-lookup"><span data-stu-id="cdd73-235">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="cdd73-236">Esegui lo strumento in un prompt `sudo` dei comandi di amministratore su Windows e con macOS.</span><span class="sxs-lookup"><span data-stu-id="cdd73-236">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="cdd73-237">I `dry-run` `whatif` comandi e non richiedono l'elevazione dei privilegi.</span><span class="sxs-lookup"><span data-stu-id="cdd73-237">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="cdd73-238">**dotnet-core-uninstall rimuovere**</span><span class="sxs-lookup"><span data-stu-id="cdd73-238">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="cdd73-239">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="cdd73-239">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="cdd73-240">Argomenti</span><span class="sxs-lookup"><span data-stu-id="cdd73-240">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="cdd73-241">Versione specificata da disinstallare.</span><span class="sxs-lookup"><span data-stu-id="cdd73-241">The specified version to uninstall.</span></span> <span data-ttu-id="cdd73-242">È possibile elencare diverse versioni una dopo l'altra, separate da spazi.</span><span class="sxs-lookup"><span data-stu-id="cdd73-242">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="cdd73-243">Sono supportati anche i file di risposta.</span><span class="sxs-lookup"><span data-stu-id="cdd73-243">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="cdd73-244">I file di risposta sono un'alternativa all'inserimento di tutte le versioni nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="cdd73-244">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="cdd73-245">Si tratta di file di \*testo, in genere con estensione rsp, e ogni versione è elencata su una riga separata.</span><span class="sxs-lookup"><span data-stu-id="cdd73-245">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="cdd73-246">Per specificare un `VERSION` file di \@ risposta per l'argomento, utilizzare il carattere immediatamente seguito dal nome del file di risposta.</span><span class="sxs-lookup"><span data-stu-id="cdd73-246">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="cdd73-247">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cdd73-247">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="cdd73-248">Windows</span><span class="sxs-lookup"><span data-stu-id="cdd73-248">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="cdd73-249">Rimuove tutti gli SDK e runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdd73-249">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="cdd73-250">Rimuove solo gli SDK e i runtime di .NET Core con una versione inferiore a quella specificata.</span><span class="sxs-lookup"><span data-stu-id="cdd73-250">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="cdd73-251">La versione specificata rimane installata.</span><span class="sxs-lookup"><span data-stu-id="cdd73-251">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="cdd73-252">Rimuove tutti gli SDK e runtime di .NET Core, ad eccezione di quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="cdd73-252">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="cdd73-253">Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quella più alta.</span><span class="sxs-lookup"><span data-stu-id="cdd73-253">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="cdd73-254">Rimuove gli SDK e i runtime di .NET Core sostituiti da patch più elevate.</span><span class="sxs-lookup"><span data-stu-id="cdd73-254">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="cdd73-255">Questa opzione protegge global.json.</span><span class="sxs-lookup"><span data-stu-id="cdd73-255">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="cdd73-256">Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime.</span><span class="sxs-lookup"><span data-stu-id="cdd73-256">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="cdd73-257">Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime tranne quello più alto.</span><span class="sxs-lookup"><span data-stu-id="cdd73-257">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="cdd73-258">Rimuove solo i runtime di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdd73-258">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="cdd73-259">Rimuove solo i bundle di runtime e di hosting di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdd73-259">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="cdd73-260">Rimuove gli SDK e i runtime di `major.minor` .NET Core che corrispondono alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="cdd73-260">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="cdd73-261">Rimuove solo i runtime .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdd73-261">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="cdd73-262">Rimuove solo gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdd73-262">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="cdd73-263">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="cdd73-263">Sets the verbosity level.</span></span> <span data-ttu-id="cdd73-264">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cdd73-264">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="cdd73-265">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="cdd73-265">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="cdd73-266">Deve essere `--sdk`utilizzato `--runtime`con `--aspnet-runtime` , e per rimuovere SDK o runtime x64.</span><span class="sxs-lookup"><span data-stu-id="cdd73-266">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="cdd73-267">Deve essere `--sdk`utilizzato `--runtime`con `--aspnet-runtime` , e per rimuovere SDK o runtime x86.</span><span class="sxs-lookup"><span data-stu-id="cdd73-267">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="cdd73-268">**`-y, --yes`** Esegue il comando senza richiedere una conferma sì o no.</span><span class="sxs-lookup"><span data-stu-id="cdd73-268">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="cdd73-269">**`--force`** Forza la rimozione delle versioni che potrebbero essere utilizzate da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cdd73-269">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="cdd73-270">Note:</span><span class="sxs-lookup"><span data-stu-id="cdd73-270">Notes:</span></span>

1. <span data-ttu-id="cdd73-271">Esattamente uno `--sdk` `--runtime`dei `--aspnet-runtime`, `--hosting-bundle` , , ed è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cdd73-271">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="cdd73-272">`--all`, `--all-below` `--all-but`, `--all-but-latest` `--all-lower-patches`, `--all-previews` `--all-previews-but-latest`, `--major-minor`, `[<VERSION>...]` , , e sono esclusivi.</span><span class="sxs-lookup"><span data-stu-id="cdd73-272">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="cdd73-273">Se `--x64` `--x86` o non sono specificati, verranno rimossi sia x64 che x86.</span><span class="sxs-lookup"><span data-stu-id="cdd73-273">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="cdd73-274">Macos</span><span class="sxs-lookup"><span data-stu-id="cdd73-274">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="cdd73-275">Rimuove tutti gli SDK e runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdd73-275">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="cdd73-276">Rimuove gli SDK e i runtime di .NET Core al di sotto della versione specificata.</span><span class="sxs-lookup"><span data-stu-id="cdd73-276">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="cdd73-277">La versione specificata rimarrà.</span><span class="sxs-lookup"><span data-stu-id="cdd73-277">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="cdd73-278">Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="cdd73-278">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="cdd73-279">Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quella più alta.</span><span class="sxs-lookup"><span data-stu-id="cdd73-279">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="cdd73-280">Rimuove gli SDK e i runtime di .NET Core sostituiti da patch più elevate.</span><span class="sxs-lookup"><span data-stu-id="cdd73-280">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="cdd73-281">Questa opzione protegge global.json.</span><span class="sxs-lookup"><span data-stu-id="cdd73-281">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="cdd73-282">Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime.</span><span class="sxs-lookup"><span data-stu-id="cdd73-282">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="cdd73-283">Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime tranne quello più alto.</span><span class="sxs-lookup"><span data-stu-id="cdd73-283">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="cdd73-284">Rimuove gli SDK e i runtime di `major.minor` .NET Core che corrispondono alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="cdd73-284">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="cdd73-285">Rimuove solo i runtime .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdd73-285">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="cdd73-286">Rimuove solo gli SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdd73-286">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="cdd73-287">Imposta il livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="cdd73-287">Sets the verbosity level.</span></span> <span data-ttu-id="cdd73-288">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cdd73-288">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="cdd73-289">Il valore predefinito è `normal`.</span><span class="sxs-lookup"><span data-stu-id="cdd73-289">The default value is `normal`.</span></span>

* <span data-ttu-id="cdd73-290">**`-y, --yes`** Esegue il comando senza richiedere la conferma Y/N.</span><span class="sxs-lookup"><span data-stu-id="cdd73-290">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="cdd73-291">**`--force`** Forza la rimozione delle versioni che potrebbero essere utilizzate da Visual Studio o SDK.</span><span class="sxs-lookup"><span data-stu-id="cdd73-291">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="cdd73-292">Note:</span><span class="sxs-lookup"><span data-stu-id="cdd73-292">Notes:</span></span>

1. <span data-ttu-id="cdd73-293">Esattamente uno `--sdk` `--runtime` di ed è richiesto.</span><span class="sxs-lookup"><span data-stu-id="cdd73-293">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="cdd73-294">`--all`, `--all-below` `--all-but`, `--all-but-latest` `--all-lower-patches`, `--all-previews` `--all-previews-but-latest`, `--major-minor`, `[<VERSION>...]` , , e sono esclusivi.</span><span class="sxs-lookup"><span data-stu-id="cdd73-294">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="cdd73-295">Esempi</span><span class="sxs-lookup"><span data-stu-id="cdd73-295">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="cdd73-296">Per impostazione predefinita, gli SDK e i runtime di .NET Core che potrebbero essere richiesti da Visual Studio o da altri SDK vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="cdd73-296">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="cdd73-297">Negli esempi seguenti, alcuni degli SDK e dei runtime specificati possono rimanere, a seconda dello stato del computer.</span><span class="sxs-lookup"><span data-stu-id="cdd73-297">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="cdd73-298">Per rimuovere tutti gli SDK e i runtime, elencarli in modo esplicito come argomenti o utilizzare l'opzione `--force` .</span><span class="sxs-lookup"><span data-stu-id="cdd73-298">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="cdd73-299">Rimuovere tutti i runtime .NET `3.0.0-preview6-27804-01` Core tranne la versione senza richiedere la conferma Y/N:</span><span class="sxs-lookup"><span data-stu-id="cdd73-299">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="cdd73-300">Rimuovere tutti gli SDK di .NET Core 1.1 senza richiedere la conferma Y/n:Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span><span class="sxs-lookup"><span data-stu-id="cdd73-300">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="cdd73-301">Rimuovere .NET Core 1.1.11 SDK senza output della console:</span><span class="sxs-lookup"><span data-stu-id="cdd73-301">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="cdd73-302">Rimuovere tutti gli SDK di .NET Core che possono essere rimossi in modo sicuro da questo strumento:Remove all .NET Core SDKs that can safely be removed by this tool:</span><span class="sxs-lookup"><span data-stu-id="cdd73-302">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="cdd73-303">Rimuovere tutti gli SDK di .NET Core che possono essere rimossi da questo strumento, inclusi gli SDK che potrebbero essere richiesti da Visual Studio (scelta non consigliata):</span><span class="sxs-lookup"><span data-stu-id="cdd73-303">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="cdd73-304">Rimuovere tutti gli SDK di .NET Core specificati nel file di rispostaRemove all .NET Core SDKs that are specified in the response file`versions.rsp`</span><span class="sxs-lookup"><span data-stu-id="cdd73-304">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="cdd73-305">Il contenuto di *versions.rsp* è il seguente:</span><span class="sxs-lookup"><span data-stu-id="cdd73-305">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="cdd73-306">Passaggio 4 - Eliminare la cartella di fallback NuGet (facoltativo)Step 4 - Delete the NuGet fallback folder (optional)</span><span class="sxs-lookup"><span data-stu-id="cdd73-306">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="cdd73-307">In alcuni casi, non `NuGetFallbackFolder` è più necessario il e potrebbe voler eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="cdd73-307">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="cdd73-308">Per ulteriori informazioni sull'eliminazione di questa cartella, vedere [Rimuovere NuGetFallbackFolder](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span><span class="sxs-lookup"><span data-stu-id="cdd73-308">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="cdd73-309">Disinstallare lo strumento</span><span class="sxs-lookup"><span data-stu-id="cdd73-309">Uninstall the tool</span></span>

## <a name="windows"></a>[<span data-ttu-id="cdd73-310">Windows</span><span class="sxs-lookup"><span data-stu-id="cdd73-310">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="cdd73-311">Aprire **Installazione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="cdd73-311">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="cdd73-312">Cercare `Microsoft .NET Core SDK Uninstall Tool`.</span><span class="sxs-lookup"><span data-stu-id="cdd73-312">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="cdd73-313">Selezionare **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="cdd73-313">Select **Uninstall**.</span></span>

## <a name="macos"></a>[<span data-ttu-id="cdd73-314">Macos</span><span class="sxs-lookup"><span data-stu-id="cdd73-314">macOS</span></span>](#tab/macos)

<span data-ttu-id="cdd73-315">Eliminare il file *dotnet-core-uninstall.tar.gz* scaricato dalla directory in cui è stato installato.</span><span class="sxs-lookup"><span data-stu-id="cdd73-315">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="cdd73-316">Se hai decompresso il contenuto di questo file in un'altra directory, assicurati di eliminare anche quel contenuto.</span><span class="sxs-lookup"><span data-stu-id="cdd73-316">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---
