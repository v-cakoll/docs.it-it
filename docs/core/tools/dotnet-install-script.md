---
title: Script dotnet-install
description: Informazioni sugli script DotNet-install per installare il .NET Core SDK e il runtime condiviso.
ms.date: 04/30/2020
ms.openlocfilehash: d03877d76212f7b22de0a1075cf50fc75bd104b6
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324426"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="9012c-103">Riferimento agli script dotnet-install</span><span class="sxs-lookup"><span data-stu-id="9012c-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="9012c-104">Nome</span><span class="sxs-lookup"><span data-stu-id="9012c-104">Name</span></span>

<span data-ttu-id="9012c-105">`dotnet-install.ps1` | `dotnet-install.sh`: Script usato per installare il .NET Core SDK e il runtime condiviso.</span><span class="sxs-lookup"><span data-stu-id="9012c-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core SDK and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9012c-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="9012c-106">Synopsis</span></span>

<span data-ttu-id="9012c-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="9012c-107">Windows:</span></span>

```powershell
dotnet-install.ps1 [-Architecture <ARCHITECTURE>] [-AzureFeed]
    [-Channel <CHANNEL>] [-DryRun] [-FeedCredential]
    [-InstallDir <DIRECTORY>] [-JSonFile <JSONFILE>]
    [-NoCdn] [-NoPath] [-ProxyAddress]
    [-ProxyUseDefaultCredentials] [-Runtime <RUNTIME>]
    [-SkipNonVersionedFiles] [-UncachedFeed] [-Verbose]
    [-Version <VERSION>]

Get-Help ./dotnet-install.ps1
```

<span data-ttu-id="9012c-108">Linux/macOS:</span><span class="sxs-lookup"><span data-stu-id="9012c-108">Linux/macOS:</span></span>

```bash
dotnet-install.sh  [--architecture <ARCHITECTURE>] [--azure-feed]
    [--channel <CHANNEL>] [--dry-run] [--feed-credential]
    [--install-dir <DIRECTORY>] [--jsonfile <JSONFILE>]
    [--no-cdn] [--no-path] [--runtime <RUNTIME>] [--runtime-id <RID>]
    [--skip-non-versioned-files] [--uncached-feed] [--verbose]
    [--version <VERSION>]

dotnet-install.sh --help
```

<span data-ttu-id="9012c-109">Lo script bash legge anche le opzioni PowerShell, che possono quindi essere usate con lo script in sistemi Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="9012c-109">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

## <a name="description"></a><span data-ttu-id="9012c-110">Description</span><span class="sxs-lookup"><span data-stu-id="9012c-110">Description</span></span>

<span data-ttu-id="9012c-111">Gli `dotnet-install` script eseguono un'installazione non amministrativa del .NET Core SDK, che include i interfaccia della riga di comando di .NET Core e il runtime condiviso.</span><span class="sxs-lookup"><span data-stu-id="9012c-111">The `dotnet-install` scripts perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI and the shared runtime.</span></span> <span data-ttu-id="9012c-112">Sono disponibili due script:</span><span class="sxs-lookup"><span data-stu-id="9012c-112">There are two scripts:</span></span>

* <span data-ttu-id="9012c-113">Uno script di PowerShell che funziona in Windows.</span><span class="sxs-lookup"><span data-stu-id="9012c-113">A PowerShell script that works on Windows.</span></span>
* <span data-ttu-id="9012c-114">Uno script bash che funziona in Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="9012c-114">A bash script that works on Linux/macOS.</span></span>

### <a name="purpose"></a><span data-ttu-id="9012c-115">Scopo</span><span class="sxs-lookup"><span data-stu-id="9012c-115">Purpose</span></span>

 <span data-ttu-id="9012c-116">L'uso previsto degli script è per gli scenari di integrazione continua (CI), in cui:</span><span class="sxs-lookup"><span data-stu-id="9012c-116">The intended use of the scripts is for Continuous Integration (CI) scenarios, where:</span></span>

* <span data-ttu-id="9012c-117">È necessario installare l'SDK senza l'intervento dell'utente e senza diritti di amministratore.</span><span class="sxs-lookup"><span data-stu-id="9012c-117">The SDK needs to be installed without user interaction and without admin rights.</span></span>
* <span data-ttu-id="9012c-118">Non è necessario che l'installazione dell'SDK venga mantenute tra più esecuzioni CI.</span><span class="sxs-lookup"><span data-stu-id="9012c-118">The SDK installation doesn't need to persist across multiple CI runs.</span></span>

  <span data-ttu-id="9012c-119">Sequenza di eventi tipica:</span><span class="sxs-lookup"><span data-stu-id="9012c-119">The typical sequence of events:</span></span>
  * <span data-ttu-id="9012c-120">CI viene attivato.</span><span class="sxs-lookup"><span data-stu-id="9012c-120">CI is triggered.</span></span>
  * <span data-ttu-id="9012c-121">CI installa l'SDK usando uno di questi script.</span><span class="sxs-lookup"><span data-stu-id="9012c-121">CI installs the SDK using one of these scripts.</span></span>
  * <span data-ttu-id="9012c-122">CI termina il suo lavoro e cancella i dati temporanei, inclusa l'installazione dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="9012c-122">CI finishes its work and clears temporary data including the SDK installation.</span></span>

<span data-ttu-id="9012c-123">Per configurare un ambiente di sviluppo o per eseguire app, usare i programmi di installazione anziché questi script.</span><span class="sxs-lookup"><span data-stu-id="9012c-123">To set up a development environment or to run apps, use the installers rather than these scripts.</span></span>

### <a name="recommended-version"></a><span data-ttu-id="9012c-124">Versione consigliata</span><span class="sxs-lookup"><span data-stu-id="9012c-124">Recommended version</span></span>

<span data-ttu-id="9012c-125">Si consiglia di utilizzare la versione stabile degli script:</span><span class="sxs-lookup"><span data-stu-id="9012c-125">We recommend that you use the stable version of the scripts:</span></span>

- <span data-ttu-id="9012c-126">Bash (Linux/macOS):<https://dot.net/v1/dotnet-install.sh></span><span class="sxs-lookup"><span data-stu-id="9012c-126">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span></span>
- <span data-ttu-id="9012c-127">PowerShell (Windows):<https://dot.net/v1/dotnet-install.ps1></span><span class="sxs-lookup"><span data-stu-id="9012c-127">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span></span>

### <a name="script-behavior"></a><span data-ttu-id="9012c-128">Comportamento dello script</span><span class="sxs-lookup"><span data-stu-id="9012c-128">Script behavior</span></span>

<span data-ttu-id="9012c-129">Entrambi gli script hanno lo stesso comportamento.</span><span class="sxs-lookup"><span data-stu-id="9012c-129">Both scripts have the same behavior.</span></span> <span data-ttu-id="9012c-130">Scaricano il file ZIP/tarball dalle gocce di compilazione dell'interfaccia della riga di comando e lo installano nel percorso predefinito o in un percorso specificato da `-InstallDir|--install-dir` .</span><span class="sxs-lookup"><span data-stu-id="9012c-130">They download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span>

<span data-ttu-id="9012c-131">Per impostazione predefinita, lo script di installazione scarica e installa l'SDK.</span><span class="sxs-lookup"><span data-stu-id="9012c-131">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="9012c-132">Se si vuole ottenere solo il runtime condiviso, è possibile specificare l'argomento `-Runtime|--runtime`.</span><span class="sxs-lookup"><span data-stu-id="9012c-132">If you wish to only obtain the shared runtime, specify the `-Runtime|--runtime` argument.</span></span>

<span data-ttu-id="9012c-133">Per impostazione predefinita, lo script aggiunge il percorso di installazione a $PATH per la sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="9012c-133">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="9012c-134">Eseguire l'override di questo comportamento predefinito specificando l'argomento `-NoPath|--no-path`.</span><span class="sxs-lookup"><span data-stu-id="9012c-134">Override this default behavior by specifying the `-NoPath|--no-path` argument.</span></span> <span data-ttu-id="9012c-135">Lo script non imposta la `DOTNET_ROOT` variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="9012c-135">The script doesn't set the `DOTNET_ROOT` environment variable.</span></span>

<span data-ttu-id="9012c-136">Prima di eseguire lo script, installare le [dipendenze](../install/dependencies.md) necessarie.</span><span class="sxs-lookup"><span data-stu-id="9012c-136">Before running the script, install the required [dependencies](../install/dependencies.md).</span></span>

<span data-ttu-id="9012c-137">È possibile installare una versione specifica usando l'argomento `-Version|--version`.</span><span class="sxs-lookup"><span data-stu-id="9012c-137">You can install a specific version using the `-Version|--version` argument.</span></span> <span data-ttu-id="9012c-138">La versione deve essere specificata come numero di versione in tre parti, ad esempio `2.1.0` .</span><span class="sxs-lookup"><span data-stu-id="9012c-138">The version must be specified as a three-part version number, such as `2.1.0`.</span></span> <span data-ttu-id="9012c-139">Se la versione non è specificata, lo script installa la `latest` versione.</span><span class="sxs-lookup"><span data-stu-id="9012c-139">If the version isn't specified, the script installs the `latest` version.</span></span>

<span data-ttu-id="9012c-140">Gli script di installazione non aggiornano il registro di sistema in Windows.</span><span class="sxs-lookup"><span data-stu-id="9012c-140">The install scripts do not update the registry on Windows.</span></span> <span data-ttu-id="9012c-141">Scaricano semplicemente i file binari compressi e li copiano in una cartella.</span><span class="sxs-lookup"><span data-stu-id="9012c-141">They just download the zipped binaries and copy them to a folder.</span></span> <span data-ttu-id="9012c-142">Se si vogliono aggiornare i valori delle chiavi del registro di sistema, usare i programmi di installazione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9012c-142">If you want registry key values to be updated, use the .NET Core installers.</span></span>

## <a name="options"></a><span data-ttu-id="9012c-143">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9012c-143">Options</span></span>

- **`-Architecture|--architecture <ARCHITECTURE>`**

  <span data-ttu-id="9012c-144">Architettura dei file binari di .NET Core da installare.</span><span class="sxs-lookup"><span data-stu-id="9012c-144">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="9012c-145">I valori consentiti sono `<auto>`, `amd64`, `x64`, `x86`, `arm64` e `arm`.</span><span class="sxs-lookup"><span data-stu-id="9012c-145">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="9012c-146">Il valore predefinito è `<auto>`, che rappresenta l'architettura del sistema operativo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9012c-146">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-AzureFeed|--azure-feed`**

  <span data-ttu-id="9012c-147">Specifica l'URL del feed di Azure per il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="9012c-147">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="9012c-148">È consigliabile non modificare questo valore.</span><span class="sxs-lookup"><span data-stu-id="9012c-148">We recommended that you don't change this value.</span></span> <span data-ttu-id="9012c-149">Il valore predefinito è `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="9012c-149">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-Channel|--channel <CHANNEL>`**

  <span data-ttu-id="9012c-150">Specifica il canale di origine per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="9012c-150">Specifies the source channel for the installation.</span></span> <span data-ttu-id="9012c-151">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="9012c-151">The possible values are:</span></span>

  - <span data-ttu-id="9012c-152">`Current`: versione più recente.</span><span class="sxs-lookup"><span data-stu-id="9012c-152">`Current` - Most current release.</span></span>
  - <span data-ttu-id="9012c-153">`LTS`: canale di supporto a lungo termine (versione supportata più recente).</span><span class="sxs-lookup"><span data-stu-id="9012c-153">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="9012c-154">Versione in due parti nel formato X.Y che rappresenta una versione specifica, ad esempio `2.1` o `3.0`.</span><span class="sxs-lookup"><span data-stu-id="9012c-154">Two-part version in X.Y format representing a specific release (for example, `2.1` or `3.0`).</span></span>
  - <span data-ttu-id="9012c-155">Nome del ramo: ad esempio `release/3.1.1xx` o `master` (per le versioni notturne).</span><span class="sxs-lookup"><span data-stu-id="9012c-155">Branch name: for example, `release/3.1.1xx` or `master` (for nightly releases).</span></span> <span data-ttu-id="9012c-156">Usare questa opzione per installare una versione da un canale di anteprima.</span><span class="sxs-lookup"><span data-stu-id="9012c-156">Use this option to install a version from a preview channel.</span></span> <span data-ttu-id="9012c-157">Usare il nome del canale come elencato in [programmi di installazione e file binari](https://github.com/dotnet/core-sdk#installers-and-binaries).</span><span class="sxs-lookup"><span data-stu-id="9012c-157">Use the name of the channel as listed in [Installers and Binaries](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span>

  <span data-ttu-id="9012c-158">Il valore predefinito è `LTS`.</span><span class="sxs-lookup"><span data-stu-id="9012c-158">The default value is `LTS`.</span></span> <span data-ttu-id="9012c-159">Per altre informazioni sui canali di supporto per .NET, vedere la pagina [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) (Criteri di supporto per .NET).</span><span class="sxs-lookup"><span data-stu-id="9012c-159">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-DryRun|--dry-run`**

  <span data-ttu-id="9012c-160">Se impostata, lo script non eseguirà l'installazione.</span><span class="sxs-lookup"><span data-stu-id="9012c-160">If set, the script won't perform the installation.</span></span> <span data-ttu-id="9012c-161">Visualizza invece la riga di comando da usare per installare in modo coerente la versione attualmente richiesta dell'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9012c-161">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="9012c-162">Se ad esempio si specifica la versione `latest`, verrà visualizzato un collegamento con la versione specifica in modo che questo comando possa essere usato in modo deterministico in uno script di compilazione.</span><span class="sxs-lookup"><span data-stu-id="9012c-162">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="9012c-163">Viene visualizzato anche il percorso del file binario se si preferisce installarlo o scaricarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="9012c-163">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-FeedCredential|--feed-credential`**

  <span data-ttu-id="9012c-164">Usata come stringa di query da accodare al feed di Azure.</span><span class="sxs-lookup"><span data-stu-id="9012c-164">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="9012c-165">Consente la modifica dell'URL per usare account di archiviazione BLOB pubblici.</span><span class="sxs-lookup"><span data-stu-id="9012c-165">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`--help`**

  <span data-ttu-id="9012c-166">Stampa la Guida per lo script.</span><span class="sxs-lookup"><span data-stu-id="9012c-166">Prints out help for the script.</span></span> <span data-ttu-id="9012c-167">Si applica solo allo script bash.</span><span class="sxs-lookup"><span data-stu-id="9012c-167">Applies only to bash script.</span></span> <span data-ttu-id="9012c-168">Per PowerShell, usare `Get-Help ./dotnet-install.ps1` .</span><span class="sxs-lookup"><span data-stu-id="9012c-168">For PowerShell, use `Get-Help ./dotnet-install.ps1`.</span></span>

- **`-InstallDir|--install-dir <DIRECTORY>`**

  <span data-ttu-id="9012c-169">Specifica il percorso di installazione.</span><span class="sxs-lookup"><span data-stu-id="9012c-169">Specifies the installation path.</span></span> <span data-ttu-id="9012c-170">Se la directory non esiste, verrà creata.</span><span class="sxs-lookup"><span data-stu-id="9012c-170">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="9012c-171">Il valore predefinito è *%LocalAppData%\Microsoft\dotnet* in Windows e */usr/share/DotNet* in Linux/MacOS.</span><span class="sxs-lookup"><span data-stu-id="9012c-171">The default value is *%LocalAppData%\Microsoft\dotnet* on Windows and */usr/share/dotnet* on Linux/macOS.</span></span> <span data-ttu-id="9012c-172">I file binari vengono inseriti direttamente in questa directory.</span><span class="sxs-lookup"><span data-stu-id="9012c-172">Binaries are placed directly in this directory.</span></span>

- **`-JSonFile|--jsonfile <JSONFILE>`**

  <span data-ttu-id="9012c-173">Specifica il percorso di un [global.jsnel](global-json.md) file che verrà usato per determinare la versione dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="9012c-173">Specifies a path to a [global.json](global-json.md) file that will be used to determine the SDK version.</span></span> <span data-ttu-id="9012c-174">Il *global.jsnel* file deve avere un valore per `sdk:version` .</span><span class="sxs-lookup"><span data-stu-id="9012c-174">The *global.json* file must have a value for `sdk:version`.</span></span>

- **`-NoCdn|--no-cdn`**

  <span data-ttu-id="9012c-175">Disabilita il download dalla [Rete di distribuzione dei contenuti di Azure (rete CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) e usa direttamente il feed non memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="9012c-175">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-NoPath|--no-path`**

  <span data-ttu-id="9012c-176">Se impostata, la cartella di installazione non viene esportata nel percorso per la sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="9012c-176">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="9012c-177">Per impostazione predefinita, lo script modifica il percorso, rendendo il interfaccia della riga di comando di .NET Core disponibile subito dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="9012c-177">By default, the script modifies the PATH, which makes the .NET Core CLI available immediately after install.</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="9012c-178">Se impostata, il programma di installazione usa il proxy durante le richieste Web.</span><span class="sxs-lookup"><span data-stu-id="9012c-178">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="9012c-179">(Valido solo per Windows).</span><span class="sxs-lookup"><span data-stu-id="9012c-179">(Only valid for Windows.)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="9012c-180">Se impostata, il programma di installazione usa le credenziali dell'utente corrente quando si usa l'indirizzo proxy.</span><span class="sxs-lookup"><span data-stu-id="9012c-180">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="9012c-181">(Valido solo per Windows).</span><span class="sxs-lookup"><span data-stu-id="9012c-181">(Only valid for Windows.)</span></span>

- **`-Runtime|--runtime <RUNTIME>`**

  <span data-ttu-id="9012c-182">Installa solo il runtime condiviso, non l'intero SDK.</span><span class="sxs-lookup"><span data-stu-id="9012c-182">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="9012c-183">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="9012c-183">The possible values are:</span></span>

  - <span data-ttu-id="9012c-184">`dotnet`: runtime condiviso `Microsoft.NETCore.App`.</span><span class="sxs-lookup"><span data-stu-id="9012c-184">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="9012c-185">`aspnetcore`: runtime condiviso `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="9012c-185">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>
  - <span data-ttu-id="9012c-186">`windowsdesktop`: runtime condiviso `Microsoft.WindowsDesktop.App`.</span><span class="sxs-lookup"><span data-stu-id="9012c-186">`windowsdesktop` - the `Microsoft.WindowsDesktop.App` shared runtime.</span></span>

- **`--runtime-id <RID>`**

  <span data-ttu-id="9012c-187">Specifica l' [identificatore di runtime](../rid-catalog.md) per il quale vengono installati gli strumenti.</span><span class="sxs-lookup"><span data-stu-id="9012c-187">Specifies the [runtime identifier](../rid-catalog.md) for which the tools are being installed.</span></span> <span data-ttu-id="9012c-188">Usare `linux-x64` per Linux portatile.</span><span class="sxs-lookup"><span data-stu-id="9012c-188">Use `linux-x64` for portable Linux.</span></span> <span data-ttu-id="9012c-189">(Valido solo per Linux/macOS).</span><span class="sxs-lookup"><span data-stu-id="9012c-189">(Only valid for Linux/macOS.)</span></span>

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > <span data-ttu-id="9012c-190">Questo parametro è obsoleto e potrebbe essere rimosso in una versione futura dello script.</span><span class="sxs-lookup"><span data-stu-id="9012c-190">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="9012c-191">L'alternativa consigliata è l'opzione `-Runtime|--runtime`.</span><span class="sxs-lookup"><span data-stu-id="9012c-191">The recommended alternative is the `-Runtime|--runtime` option.</span></span>

  <span data-ttu-id="9012c-192">Installa solo i bit del runtime condiviso, non l'intero SDK.</span><span class="sxs-lookup"><span data-stu-id="9012c-192">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="9012c-193">Questa opzione equivale a specificare `-Runtime|--runtime dotnet` .</span><span class="sxs-lookup"><span data-stu-id="9012c-193">This option is equivalent to specifying `-Runtime|--runtime dotnet`.</span></span>

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  <span data-ttu-id="9012c-194">Ignora l'installazione dei file senza versione, ad esempio *dotnet.exe*, se esistono già.</span><span class="sxs-lookup"><span data-stu-id="9012c-194">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-UncachedFeed|--uncached-feed`**

  <span data-ttu-id="9012c-195">Consente di modificare l'URL per il feed non memorizzato nella cache usato da questo programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="9012c-195">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="9012c-196">È consigliabile non modificare questo valore.</span><span class="sxs-lookup"><span data-stu-id="9012c-196">We recommended that you don't change this value.</span></span>

- **`-Verbose|--verbose`**

  <span data-ttu-id="9012c-197">Visualizza le informazioni di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="9012c-197">Displays diagnostics information.</span></span>

- **`-Version|--version <VERSION>`**

  <span data-ttu-id="9012c-198">Rappresenta una versione di build specifica.</span><span class="sxs-lookup"><span data-stu-id="9012c-198">Represents a specific build version.</span></span> <span data-ttu-id="9012c-199">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="9012c-199">The possible values are:</span></span>

  - <span data-ttu-id="9012c-200">`latest`: ultima build sul canale (valore usato con l'opzione `-Channel`).</span><span class="sxs-lookup"><span data-stu-id="9012c-200">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="9012c-201">`coherent`: ultima build coerente sul canale. Usa la combinazione di pacchetti stabile più recente (valore usato con le opzioni `-Channel` del nome del ramo).</span><span class="sxs-lookup"><span data-stu-id="9012c-201">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="9012c-202">Versione in tre parti nel formato X.Y.Z che rappresenta una versione di build specifica; sostituisce l'opzione `-Channel`.</span><span class="sxs-lookup"><span data-stu-id="9012c-202">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="9012c-203">Ad esempio: `2.0.0-preview2-006120`.</span><span class="sxs-lookup"><span data-stu-id="9012c-203">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="9012c-204">Se non viene specificata, `-Version` viene impostata automaticamente su `latest`.</span><span class="sxs-lookup"><span data-stu-id="9012c-204">If not specified, `-Version` defaults to `latest`.</span></span>

## <a name="examples"></a><span data-ttu-id="9012c-205">Esempio</span><span class="sxs-lookup"><span data-stu-id="9012c-205">Examples</span></span>

- <span data-ttu-id="9012c-206">Installare la versione LTS (Long Term Support) più recente nel percorso predefinito:</span><span class="sxs-lookup"><span data-stu-id="9012c-206">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="9012c-207">Windows:</span><span class="sxs-lookup"><span data-stu-id="9012c-207">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="9012c-208">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="9012c-208">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="9012c-209">Installare la versione più recente dal canale 3,1 nel percorso specificato:</span><span class="sxs-lookup"><span data-stu-id="9012c-209">Install the latest version from 3.1 channel to the specified location:</span></span>

  <span data-ttu-id="9012c-210">Windows:</span><span class="sxs-lookup"><span data-stu-id="9012c-210">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  <span data-ttu-id="9012c-211">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="9012c-211">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- <span data-ttu-id="9012c-212">Installare la versione 3.0.0 del runtime condiviso:</span><span class="sxs-lookup"><span data-stu-id="9012c-212">Install the 3.0.0 version of the shared runtime:</span></span>

  <span data-ttu-id="9012c-213">Windows:</span><span class="sxs-lookup"><span data-stu-id="9012c-213">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  <span data-ttu-id="9012c-214">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="9012c-214">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- <span data-ttu-id="9012c-215">Ottenere lo script e installare la versione 2.1.2 versione dietro un proxy aziendale (solo Windows):</span><span class="sxs-lookup"><span data-stu-id="9012c-215">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="9012c-216">Ottenere lo script e installare gli esempi di .NET Core CLI di una singola riga di codice:</span><span class="sxs-lookup"><span data-stu-id="9012c-216">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="9012c-217">Windows:</span><span class="sxs-lookup"><span data-stu-id="9012c-217">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="9012c-218">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="9012c-218">macOS/Linux:</span></span>

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="9012c-219">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="9012c-219">See also</span></span>

- <span data-ttu-id="9012c-220">[.NET Core releases](https://github.com/dotnet/core/releases) (Versioni di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="9012c-220">[.NET Core releases](https://github.com/dotnet/core/releases)</span></span>
- <span data-ttu-id="9012c-221">[.NET Core Runtime and SDK download archive](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md) (Archivio di download per runtime e SDK di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="9012c-221">[.NET Core Runtime and SDK download archive](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)</span></span>
