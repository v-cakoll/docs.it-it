---
title: Script dotnet-install
description: Informazioni sugli script DotNet-install per installare il .NET Core SDK e il runtime condiviso.
ms.date: 01/23/2020
ms.openlocfilehash: 169991ac4cd24ccab90634ff265c3ae5b603f8e9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734209"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="66468-103">Riferimento agli script dotnet-install</span><span class="sxs-lookup"><span data-stu-id="66468-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="66468-104">Name</span><span class="sxs-lookup"><span data-stu-id="66468-104">Name</span></span>

<span data-ttu-id="66468-105">`dotnet-install.ps1` | `dotnet-install.sh` script utilizzato per installare il .NET Core SDK e il runtime condiviso.</span><span class="sxs-lookup"><span data-stu-id="66468-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core SDK and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="66468-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="66468-106">Synopsis</span></span>

<span data-ttu-id="66468-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="66468-107">Windows:</span></span>

```powershell
dotnet-install.ps1 [-Channel] [-Version] [-JSonFile] [-InstallDir] [-Architecture]
    [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential]
    [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]
```

<span data-ttu-id="66468-108">Linux/macOs:</span><span class="sxs-lookup"><span data-stu-id="66468-108">Linux/macOs:</span></span>

```bash
dotnet-install.sh [--channel] [--version] [--jsonfile] [--install-dir] [--architecture]
    [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential]
    [--runtime-id] [--skip-non-versioned-files] [--help]
```

## <a name="description"></a><span data-ttu-id="66468-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66468-109">Description</span></span>

<span data-ttu-id="66468-110">Gli script `dotnet-install` vengono usati per eseguire un'installazione non amministrativa di .NET Core SDK, che include gli strumenti dell'interfaccia della riga di comando e il runtime condiviso di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="66468-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="66468-111">Si consiglia di utilizzare la versione stabile degli script:</span><span class="sxs-lookup"><span data-stu-id="66468-111">We recommend that you use the stable version of the scripts:</span></span>

- <span data-ttu-id="66468-112">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span><span class="sxs-lookup"><span data-stu-id="66468-112">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span></span>
- <span data-ttu-id="66468-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span><span class="sxs-lookup"><span data-stu-id="66468-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span></span>

<span data-ttu-id="66468-114">Gli script vengono usati principalmente negli scenari di automazione e nelle installazioni senza privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="66468-114">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="66468-115">Sono disponibili due script: uno è uno script PowerShell, che funziona in Windows, e l'altro è uno script Bash, che funziona in Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="66468-115">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="66468-116">Entrambi gli script hanno lo stesso comportamento.</span><span class="sxs-lookup"><span data-stu-id="66468-116">Both scripts have the same behavior.</span></span> <span data-ttu-id="66468-117">Lo script bash legge anche le opzioni PowerShell, che possono quindi essere usate con lo script in sistemi Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="66468-117">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="66468-118">Gli script di installazione scaricano il file ZIP/tarball da destinazioni di compilazione dell'interfaccia della riga di comando e lo installano nel percorso predefinito o in un percorso specificato da `-InstallDir|--install-dir`.</span><span class="sxs-lookup"><span data-stu-id="66468-118">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="66468-119">Per impostazione predefinita, lo script di installazione scarica e installa l'SDK.</span><span class="sxs-lookup"><span data-stu-id="66468-119">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="66468-120">Se si vuole ottenere solo il runtime condiviso, è possibile specificare l'argomento `-Runtime|--runtime`.</span><span class="sxs-lookup"><span data-stu-id="66468-120">If you wish to only obtain the shared runtime, specify the `-Runtime|--runtime` argument.</span></span>

<span data-ttu-id="66468-121">Per impostazione predefinita, lo script aggiunge il percorso di installazione a $PATH per la sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="66468-121">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="66468-122">Eseguire l'override di questo comportamento predefinito specificando l'argomento `-NoPath|--no-path`.</span><span class="sxs-lookup"><span data-stu-id="66468-122">Override this default behavior by specifying the `-NoPath|--no-path` argument.</span></span>

<span data-ttu-id="66468-123">Prima di eseguire lo script, installare le [dipendenze](../install/dependencies.md) necessarie.</span><span class="sxs-lookup"><span data-stu-id="66468-123">Before running the script, install the required [dependencies](../install/dependencies.md).</span></span>

<span data-ttu-id="66468-124">È possibile installare una versione specifica usando l'argomento `-Version|--version`.</span><span class="sxs-lookup"><span data-stu-id="66468-124">You can install a specific version using the `-Version|--version` argument.</span></span> <span data-ttu-id="66468-125">La versione deve essere specificata come versione in tre parti, ad esempio `2.1.0`.</span><span class="sxs-lookup"><span data-stu-id="66468-125">The version must be specified as a three-part version (for example, `2.1.0`).</span></span> <span data-ttu-id="66468-126">Se non viene fornita, viene usata la versione `latest`.</span><span class="sxs-lookup"><span data-stu-id="66468-126">If not provided, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="66468-127">Options</span><span class="sxs-lookup"><span data-stu-id="66468-127">Options</span></span>

- **`-Channel|--channel <CHANNEL>`**

  <span data-ttu-id="66468-128">Specifica il canale di origine per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="66468-128">Specifies the source channel for the installation.</span></span> <span data-ttu-id="66468-129">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="66468-129">The possible values are:</span></span>

  - <span data-ttu-id="66468-130">`Current`: versione più recente.</span><span class="sxs-lookup"><span data-stu-id="66468-130">`Current` - Most current release.</span></span>
  - <span data-ttu-id="66468-131">`LTS`: canale di supporto a lungo termine (versione supportata più recente).</span><span class="sxs-lookup"><span data-stu-id="66468-131">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="66468-132">Versione in due parti nel formato X.Y che rappresenta una versione specifica, ad esempio `2.1` o `3.0`.</span><span class="sxs-lookup"><span data-stu-id="66468-132">Two-part version in X.Y format representing a specific release (for example, `2.1` or `3.0`).</span></span>
  - <span data-ttu-id="66468-133">Nome del ramo: ad esempio, `release/3.1.1xx` o `master` (per le versioni notturne).</span><span class="sxs-lookup"><span data-stu-id="66468-133">Branch name: for example, `release/3.1.1xx` or `master` (for nightly releases).</span></span> <span data-ttu-id="66468-134">Usare questa opzione per installare una versione da un canale di anteprima.</span><span class="sxs-lookup"><span data-stu-id="66468-134">Use this option to install a version from a preview channel.</span></span> <span data-ttu-id="66468-135">Usare il nome del canale come elencato in [programmi di installazione e file binari](https://github.com/dotnet/core-sdk#installers-and-binaries).</span><span class="sxs-lookup"><span data-stu-id="66468-135">Use the name of the channel as listed in [Installers and Binaries](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span>

  <span data-ttu-id="66468-136">Il valore predefinito è `LTS`.</span><span class="sxs-lookup"><span data-stu-id="66468-136">The default value is `LTS`.</span></span> <span data-ttu-id="66468-137">Per altre informazioni sui canali di supporto per .NET, vedere la pagina [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) (Criteri di supporto per .NET).</span><span class="sxs-lookup"><span data-stu-id="66468-137">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-Version|--version <VERSION>`**

  <span data-ttu-id="66468-138">Rappresenta una versione di build specifica.</span><span class="sxs-lookup"><span data-stu-id="66468-138">Represents a specific build version.</span></span> <span data-ttu-id="66468-139">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="66468-139">The possible values are:</span></span>

  - <span data-ttu-id="66468-140">`latest`: ultima build sul canale (valore usato con l'opzione `-Channel`).</span><span class="sxs-lookup"><span data-stu-id="66468-140">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="66468-141">`coherent`: ultima build coerente sul canale. Usa la combinazione di pacchetti stabile più recente (valore usato con le opzioni `-Channel` del nome del ramo).</span><span class="sxs-lookup"><span data-stu-id="66468-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="66468-142">Versione in tre parti nel formato X.Y.Z che rappresenta una versione di build specifica; sostituisce l'opzione `-Channel`.</span><span class="sxs-lookup"><span data-stu-id="66468-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="66468-143">Ad esempio: `2.0.0-preview2-006120`.</span><span class="sxs-lookup"><span data-stu-id="66468-143">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="66468-144">Se non viene specificata, `-Version` viene impostata automaticamente su `latest`.</span><span class="sxs-lookup"><span data-stu-id="66468-144">If not specified, `-Version` defaults to `latest`.</span></span>

- **`-JSonFile|--jsonfile <JSONFILE>`**

  <span data-ttu-id="66468-145">Specifica il percorso di un file [Global. JSON](global-json.md) che verrà usato per determinare la versione dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="66468-145">Specifies a path to a [global.json](global-json.md) file that will be used to determine the SDK version.</span></span> <span data-ttu-id="66468-146">Il file *Global. JSON* deve avere un valore per `sdk:version`.</span><span class="sxs-lookup"><span data-stu-id="66468-146">The *global.json* file must have a value for `sdk:version`.</span></span>

- **`-InstallDir|--install-dir <DIRECTORY>`**

  <span data-ttu-id="66468-147">Specifica il percorso di installazione.</span><span class="sxs-lookup"><span data-stu-id="66468-147">Specifies the installation path.</span></span> <span data-ttu-id="66468-148">Se la directory non esiste, verrà creata.</span><span class="sxs-lookup"><span data-stu-id="66468-148">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="66468-149">Il valore predefinito è *%LocalAppData%\Microsoft\dotnet*.</span><span class="sxs-lookup"><span data-stu-id="66468-149">The default value is *%LocalAppData%\Microsoft\dotnet*.</span></span> <span data-ttu-id="66468-150">I file binari vengono inseriti direttamente in questa directory.</span><span class="sxs-lookup"><span data-stu-id="66468-150">Binaries are placed directly in this directory.</span></span>

- **`-Architecture|--architecture <ARCHITECTURE>`**

  <span data-ttu-id="66468-151">Architettura dei file binari di .NET Core da installare.</span><span class="sxs-lookup"><span data-stu-id="66468-151">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="66468-152">I valori consentiti sono `<auto>`, `amd64`, `x64`, `x86`, `arm64` e `arm`.</span><span class="sxs-lookup"><span data-stu-id="66468-152">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="66468-153">Il valore predefinito è `<auto>`, che rappresenta l'architettura del sistema operativo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="66468-153">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > <span data-ttu-id="66468-154">Questo parametro è obsoleto e potrebbe essere rimosso in una versione futura dello script.</span><span class="sxs-lookup"><span data-stu-id="66468-154">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="66468-155">L'alternativa consigliata è l'opzione `-Runtime|--runtime`.</span><span class="sxs-lookup"><span data-stu-id="66468-155">The recommended alternative is the `-Runtime|--runtime` option.</span></span>

  <span data-ttu-id="66468-156">Installa solo i bit del runtime condiviso, non l'intero SDK.</span><span class="sxs-lookup"><span data-stu-id="66468-156">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="66468-157">Questa opzione equivale a specificare `-Runtime|--runtime dotnet`.</span><span class="sxs-lookup"><span data-stu-id="66468-157">This option is equivalent to specifying `-Runtime|--runtime dotnet`.</span></span>

- **`-Runtime|--runtime <RUNTIME>`**

  <span data-ttu-id="66468-158">Installa solo il runtime condiviso, non l'intero SDK.</span><span class="sxs-lookup"><span data-stu-id="66468-158">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="66468-159">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="66468-159">The possible values are:</span></span>

  - <span data-ttu-id="66468-160">`dotnet`: runtime condiviso `Microsoft.NETCore.App`.</span><span class="sxs-lookup"><span data-stu-id="66468-160">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="66468-161">`aspnetcore`: runtime condiviso `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="66468-161">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>
  - <span data-ttu-id="66468-162">`windowsdesktop`: runtime condiviso `Microsoft.WindowsDesktop.App`.</span><span class="sxs-lookup"><span data-stu-id="66468-162">`windowsdesktop` - the `Microsoft.WindowsDesktop.App` shared runtime.</span></span>

- **`-DryRun|--dry-run`**

  <span data-ttu-id="66468-163">Se impostata, lo script non eseguirà l'installazione.</span><span class="sxs-lookup"><span data-stu-id="66468-163">If set, the script won't perform the installation.</span></span> <span data-ttu-id="66468-164">Visualizza invece la riga di comando da usare per installare in modo coerente la versione attualmente richiesta dell'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="66468-164">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="66468-165">Se ad esempio si specifica la versione `latest`, verrà visualizzato un collegamento con la versione specifica in modo che questo comando possa essere usato in modo deterministico in uno script di compilazione.</span><span class="sxs-lookup"><span data-stu-id="66468-165">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="66468-166">Viene visualizzato anche il percorso del file binario se si preferisce installarlo o scaricarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="66468-166">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-NoPath|--no-path`**

  <span data-ttu-id="66468-167">Se impostata, la cartella di installazione non viene esportata nel percorso per la sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="66468-167">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="66468-168">Per impostazione predefinita, lo script modifica il percorso rendendo disponibili gli strumenti dell'interfaccia della riga di comando immediatamente dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="66468-168">By default, the script modifies the PATH, which makes the CLI tools available immediately after install.</span></span>

- **`-Verbose|--verbose`**

  <span data-ttu-id="66468-169">Visualizza le informazioni di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="66468-169">Displays diagnostics information.</span></span>

- **`-AzureFeed|--azure-feed`**

  <span data-ttu-id="66468-170">Specifica l'URL del feed di Azure per il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="66468-170">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="66468-171">È consigliabile non modificare questo valore.</span><span class="sxs-lookup"><span data-stu-id="66468-171">We recommended that you don't change this value.</span></span> <span data-ttu-id="66468-172">Il valore predefinito è `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="66468-172">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-UncachedFeed|--uncached-feed`**

  <span data-ttu-id="66468-173">Consente di modificare l'URL per il feed non memorizzato nella cache usato da questo programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="66468-173">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="66468-174">È consigliabile non modificare questo valore.</span><span class="sxs-lookup"><span data-stu-id="66468-174">We recommended that you don't change this value.</span></span>

- **`-NoCdn|--no-cdn`**

  <span data-ttu-id="66468-175">Disabilita il download dalla [Rete di distribuzione dei contenuti di Azure (rete CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) e usa direttamente il feed non memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="66468-175">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-FeedCredential|--feed-credential`**

  <span data-ttu-id="66468-176">Usata come stringa di query da accodare al feed di Azure.</span><span class="sxs-lookup"><span data-stu-id="66468-176">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="66468-177">Consente la modifica dell'URL per usare account di archiviazione BLOB pubblici.</span><span class="sxs-lookup"><span data-stu-id="66468-177">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`--runtime-id`**

  <span data-ttu-id="66468-178">Specifica l' [identificatore di runtime](../rid-catalog.md) per il quale vengono installati gli strumenti.</span><span class="sxs-lookup"><span data-stu-id="66468-178">Specifies the [runtime identifier](../rid-catalog.md) for which the tools are being installed.</span></span> <span data-ttu-id="66468-179">Usare `linux-x64` per Linux portatile.</span><span class="sxs-lookup"><span data-stu-id="66468-179">Use `linux-x64` for portable Linux.</span></span> <span data-ttu-id="66468-180">(Valido solo per Linux/macOS)</span><span class="sxs-lookup"><span data-stu-id="66468-180">(Only valid for Linux/macOS)</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="66468-181">Se impostata, il programma di installazione usa il proxy durante le richieste Web.</span><span class="sxs-lookup"><span data-stu-id="66468-181">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="66468-182">(Valido solo per Windows)</span><span class="sxs-lookup"><span data-stu-id="66468-182">(Only valid for Windows)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="66468-183">Se impostata, il programma di installazione usa le credenziali dell'utente corrente quando si usa l'indirizzo proxy.</span><span class="sxs-lookup"><span data-stu-id="66468-183">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="66468-184">(Valido solo per Windows)</span><span class="sxs-lookup"><span data-stu-id="66468-184">(Only valid for Windows)</span></span>

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  <span data-ttu-id="66468-185">Ignora l'installazione dei file senza versione, ad esempio *dotnet.exe*, se esistono già.</span><span class="sxs-lookup"><span data-stu-id="66468-185">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-Help|--help`**

  <span data-ttu-id="66468-186">Stampa la Guida per lo script.</span><span class="sxs-lookup"><span data-stu-id="66468-186">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="66468-187">Esempi</span><span class="sxs-lookup"><span data-stu-id="66468-187">Examples</span></span>

- <span data-ttu-id="66468-188">Installare la versione LTS (Long Term Support) più recente nel percorso predefinito:</span><span class="sxs-lookup"><span data-stu-id="66468-188">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="66468-189">Windows:</span><span class="sxs-lookup"><span data-stu-id="66468-189">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="66468-190">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="66468-190">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="66468-191">Installare la versione più recente dal canale 3,1 nel percorso specificato:</span><span class="sxs-lookup"><span data-stu-id="66468-191">Install the latest version from 3.1 channel to the specified location:</span></span>

  <span data-ttu-id="66468-192">Windows:</span><span class="sxs-lookup"><span data-stu-id="66468-192">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  <span data-ttu-id="66468-193">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="66468-193">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- <span data-ttu-id="66468-194">Installare la versione 3.0.0 del runtime condiviso:</span><span class="sxs-lookup"><span data-stu-id="66468-194">Install the 3.0.0 version of the shared runtime:</span></span>

  <span data-ttu-id="66468-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="66468-195">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  <span data-ttu-id="66468-196">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="66468-196">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- <span data-ttu-id="66468-197">Ottenere lo script e installare la versione 2.1.2 versione dietro un proxy aziendale (solo Windows):</span><span class="sxs-lookup"><span data-stu-id="66468-197">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="66468-198">Ottenere lo script e installare gli esempi di .NET Core CLI di una singola riga di codice:</span><span class="sxs-lookup"><span data-stu-id="66468-198">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="66468-199">Windows:</span><span class="sxs-lookup"><span data-stu-id="66468-199">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="66468-200">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="66468-200">macOS/Linux:</span></span>

  ```bash
  curl -ssl https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="66468-201">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66468-201">See also</span></span>

- <span data-ttu-id="66468-202">[.NET Core releases](https://github.com/dotnet/core/releases) (Versioni di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="66468-202">[.NET Core releases](https://github.com/dotnet/core/releases)</span></span>
- <span data-ttu-id="66468-203">[.NET Core Runtime and SDK download archive](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md) (Archivio di download per runtime e SDK di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="66468-203">[.NET Core Runtime and SDK download archive](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)</span></span>
