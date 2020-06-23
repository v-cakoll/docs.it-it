---
title: Script dotnet-install
description: Informazioni sugli script DotNet-install per installare il .NET Core SDK e il runtime condiviso.
ms.date: 04/30/2020
ms.openlocfilehash: 464e6fafa1c2e661892bcb3b35ba172ca1d7e76b
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141243"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="fcfa7-103">Riferimento agli script dotnet-install</span><span class="sxs-lookup"><span data-stu-id="fcfa7-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="fcfa7-104">Nome</span><span class="sxs-lookup"><span data-stu-id="fcfa7-104">Name</span></span>

<span data-ttu-id="fcfa7-105">`dotnet-install.ps1` | `dotnet-install.sh`: Script usato per installare il .NET Core SDK e il runtime condiviso.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core SDK and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fcfa7-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="fcfa7-106">Synopsis</span></span>

<span data-ttu-id="fcfa7-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-107">Windows:</span></span>

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

<span data-ttu-id="fcfa7-108">Linux/macOS:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-108">Linux/macOS:</span></span>

```bash
dotnet-install.sh  [--architecture <ARCHITECTURE>] [--azure-feed]
    [--channel <CHANNEL>] [--dry-run] [--feed-credential]
    [--install-dir <DIRECTORY>] [--jsonfile <JSONFILE>]
    [--no-cdn] [--no-path] [--runtime <RUNTIME>] [--runtime-id <RID>]
    [--skip-non-versioned-files] [--uncached-feed] [--verbose]
    [--version <VERSION>]

dotnet-install.sh --help
```

## <a name="description"></a><span data-ttu-id="fcfa7-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcfa7-109">Description</span></span>

<span data-ttu-id="fcfa7-110">Gli `dotnet-install` script vengono usati per eseguire un'installazione non amministrativa del .NET Core SDK, che include il interfaccia della riga di comando di .NET Core e il runtime condiviso.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI and the shared runtime.</span></span>

<span data-ttu-id="fcfa7-111">Si consiglia di utilizzare la versione stabile degli script:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-111">We recommend that you use the stable version of the scripts:</span></span>

- <span data-ttu-id="fcfa7-112">Bash (Linux/macOS):<https://dot.net/v1/dotnet-install.sh></span><span class="sxs-lookup"><span data-stu-id="fcfa7-112">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span></span>
- <span data-ttu-id="fcfa7-113">PowerShell (Windows):<https://dot.net/v1/dotnet-install.ps1></span><span class="sxs-lookup"><span data-stu-id="fcfa7-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span></span>

<span data-ttu-id="fcfa7-114">Gli script vengono usati principalmente negli scenari di automazione e nelle installazioni senza privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-114">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="fcfa7-115">Sono disponibili due script: uno è uno script PowerShell, che funziona in Windows, e l'altro è uno script Bash, che funziona in Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-115">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="fcfa7-116">Entrambi gli script hanno lo stesso comportamento.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-116">Both scripts have the same behavior.</span></span> <span data-ttu-id="fcfa7-117">Lo script bash legge anche le opzioni PowerShell, che possono quindi essere usate con lo script in sistemi Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-117">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="fcfa7-118">Gli script di installazione scaricano il file ZIP/tarball da destinazioni di compilazione dell'interfaccia della riga di comando e lo installano nel percorso predefinito o in un percorso specificato da `-InstallDir|--install-dir`.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-118">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="fcfa7-119">Per impostazione predefinita, lo script di installazione scarica e installa l'SDK.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-119">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="fcfa7-120">Se si vuole ottenere solo il runtime condiviso, è possibile specificare l'argomento `-Runtime|--runtime`.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-120">If you wish to only obtain the shared runtime, specify the `-Runtime|--runtime` argument.</span></span>

<span data-ttu-id="fcfa7-121">Per impostazione predefinita, lo script aggiunge il percorso di installazione a $PATH per la sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-121">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="fcfa7-122">Eseguire l'override di questo comportamento predefinito specificando l'argomento `-NoPath|--no-path`.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-122">Override this default behavior by specifying the `-NoPath|--no-path` argument.</span></span>

<span data-ttu-id="fcfa7-123">Prima di eseguire lo script, installare le [dipendenze](../install/dependencies.md) necessarie.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-123">Before running the script, install the required [dependencies](../install/dependencies.md).</span></span>

<span data-ttu-id="fcfa7-124">È possibile installare una versione specifica usando l'argomento `-Version|--version`.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-124">You can install a specific version using the `-Version|--version` argument.</span></span> <span data-ttu-id="fcfa7-125">La versione deve essere specificata come versione a tre parti (ad esempio, `2.1.0` ).</span><span class="sxs-lookup"><span data-stu-id="fcfa7-125">The version must be specified as a three-part version (for example, `2.1.0`).</span></span> <span data-ttu-id="fcfa7-126">Se non viene fornita, viene usata la versione `latest`.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-126">If not provided, it uses the `latest` version.</span></span>

<span data-ttu-id="fcfa7-127">Gli script di installazione non aggiornano il registro di sistema in Windows.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-127">The install scripts do not update the registry on Windows.</span></span> <span data-ttu-id="fcfa7-128">Scaricano semplicemente i file binari compressi e li copiano in una cartella.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-128">They just download the zipped binaries and copy them to a folder.</span></span> <span data-ttu-id="fcfa7-129">Se si vogliono aggiornare i valori delle chiavi del registro di sistema, usare i programmi di installazione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-129">If you want registry key values to be updated, use the .NET Core installers.</span></span>

## <a name="options"></a><span data-ttu-id="fcfa7-130">Opzioni</span><span class="sxs-lookup"><span data-stu-id="fcfa7-130">Options</span></span>

- **`-Architecture|--architecture <ARCHITECTURE>`**

  <span data-ttu-id="fcfa7-131">Architettura dei file binari di .NET Core da installare.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-131">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="fcfa7-132">I valori consentiti sono `<auto>`, `amd64`, `x64`, `x86`, `arm64` e `arm`.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-132">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="fcfa7-133">Il valore predefinito è `<auto>`, che rappresenta l'architettura del sistema operativo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-133">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-AzureFeed|--azure-feed`**

  <span data-ttu-id="fcfa7-134">Specifica l'URL del feed di Azure per il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-134">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="fcfa7-135">È consigliabile non modificare questo valore.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-135">We recommended that you don't change this value.</span></span> <span data-ttu-id="fcfa7-136">Il valore predefinito è `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-136">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-Channel|--channel <CHANNEL>`**

  <span data-ttu-id="fcfa7-137">Specifica il canale di origine per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-137">Specifies the source channel for the installation.</span></span> <span data-ttu-id="fcfa7-138">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-138">The possible values are:</span></span>

  - <span data-ttu-id="fcfa7-139">`Current`: versione più recente.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-139">`Current` - Most current release.</span></span>
  - <span data-ttu-id="fcfa7-140">`LTS`: canale di supporto a lungo termine (versione supportata più recente).</span><span class="sxs-lookup"><span data-stu-id="fcfa7-140">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="fcfa7-141">Versione in due parti nel formato X.Y che rappresenta una versione specifica, ad esempio `2.1` o `3.0`.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-141">Two-part version in X.Y format representing a specific release (for example, `2.1` or `3.0`).</span></span>
  - <span data-ttu-id="fcfa7-142">Nome del ramo: ad esempio `release/3.1.1xx` o `master` (per le versioni notturne).</span><span class="sxs-lookup"><span data-stu-id="fcfa7-142">Branch name: for example, `release/3.1.1xx` or `master` (for nightly releases).</span></span> <span data-ttu-id="fcfa7-143">Usare questa opzione per installare una versione da un canale di anteprima.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-143">Use this option to install a version from a preview channel.</span></span> <span data-ttu-id="fcfa7-144">Usare il nome del canale come elencato in [programmi di installazione e file binari](https://github.com/dotnet/core-sdk#installers-and-binaries).</span><span class="sxs-lookup"><span data-stu-id="fcfa7-144">Use the name of the channel as listed in [Installers and Binaries](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span>

  <span data-ttu-id="fcfa7-145">Il valore predefinito è `LTS`.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-145">The default value is `LTS`.</span></span> <span data-ttu-id="fcfa7-146">Per altre informazioni sui canali di supporto per .NET, vedere la pagina [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) (Criteri di supporto per .NET).</span><span class="sxs-lookup"><span data-stu-id="fcfa7-146">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-DryRun|--dry-run`**

  <span data-ttu-id="fcfa7-147">Se impostata, lo script non eseguirà l'installazione.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-147">If set, the script won't perform the installation.</span></span> <span data-ttu-id="fcfa7-148">Visualizza invece la riga di comando da usare per installare in modo coerente la versione attualmente richiesta dell'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-148">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="fcfa7-149">Se ad esempio si specifica la versione `latest`, verrà visualizzato un collegamento con la versione specifica in modo che questo comando possa essere usato in modo deterministico in uno script di compilazione.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-149">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="fcfa7-150">Viene visualizzato anche il percorso del file binario se si preferisce installarlo o scaricarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-150">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-FeedCredential|--feed-credential`**

  <span data-ttu-id="fcfa7-151">Usata come stringa di query da accodare al feed di Azure.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-151">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="fcfa7-152">Consente la modifica dell'URL per usare account di archiviazione BLOB pubblici.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-152">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`--help`**

  <span data-ttu-id="fcfa7-153">Stampa la Guida per lo script.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-153">Prints out help for the script.</span></span> <span data-ttu-id="fcfa7-154">Si applica solo allo script bash.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-154">Applies only to bash script.</span></span> <span data-ttu-id="fcfa7-155">Per PowerShell, usare `Get-Help ./dotnet-install.ps1` .</span><span class="sxs-lookup"><span data-stu-id="fcfa7-155">For PowerShell, use `Get-Help ./dotnet-install.ps1`.</span></span>

- **`-InstallDir|--install-dir <DIRECTORY>`**

  <span data-ttu-id="fcfa7-156">Specifica il percorso di installazione.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-156">Specifies the installation path.</span></span> <span data-ttu-id="fcfa7-157">Se la directory non esiste, verrà creata.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-157">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="fcfa7-158">Il valore predefinito è *%LocalAppData%\Microsoft\dotnet* in Windows e */usr/share/DotNet* in Linux/MacOS.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-158">The default value is *%LocalAppData%\Microsoft\dotnet* on Windows and */usr/share/dotnet* on Linux/macOS.</span></span> <span data-ttu-id="fcfa7-159">I file binari vengono inseriti direttamente in questa directory.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-159">Binaries are placed directly in this directory.</span></span>

- **`-JSonFile|--jsonfile <JSONFILE>`**

  <span data-ttu-id="fcfa7-160">Specifica il percorso di un [global.jsnel](global-json.md) file che verrà usato per determinare la versione dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-160">Specifies a path to a [global.json](global-json.md) file that will be used to determine the SDK version.</span></span> <span data-ttu-id="fcfa7-161">Il *global.jsnel* file deve avere un valore per `sdk:version` .</span><span class="sxs-lookup"><span data-stu-id="fcfa7-161">The *global.json* file must have a value for `sdk:version`.</span></span>

- **`-NoCdn|--no-cdn`**

  <span data-ttu-id="fcfa7-162">Disabilita il download dalla [Rete di distribuzione dei contenuti di Azure (rete CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) e usa direttamente il feed non memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-162">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-NoPath|--no-path`**

  <span data-ttu-id="fcfa7-163">Se impostata, la cartella di installazione non viene esportata nel percorso per la sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-163">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="fcfa7-164">Per impostazione predefinita, lo script modifica il percorso, rendendo il interfaccia della riga di comando di .NET Core disponibile subito dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-164">By default, the script modifies the PATH, which makes the .NET Core CLI available immediately after install.</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="fcfa7-165">Se impostata, il programma di installazione usa il proxy durante le richieste Web.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-165">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="fcfa7-166">(Valido solo per Windows).</span><span class="sxs-lookup"><span data-stu-id="fcfa7-166">(Only valid for Windows.)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="fcfa7-167">Se impostata, il programma di installazione usa le credenziali dell'utente corrente quando si usa l'indirizzo proxy.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-167">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="fcfa7-168">(Valido solo per Windows).</span><span class="sxs-lookup"><span data-stu-id="fcfa7-168">(Only valid for Windows.)</span></span>

- **`-Runtime|--runtime <RUNTIME>`**

  <span data-ttu-id="fcfa7-169">Installa solo il runtime condiviso, non l'intero SDK.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-169">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="fcfa7-170">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-170">The possible values are:</span></span>

  - <span data-ttu-id="fcfa7-171">`dotnet`: runtime condiviso `Microsoft.NETCore.App`.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-171">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="fcfa7-172">`aspnetcore`: runtime condiviso `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-172">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>
  - <span data-ttu-id="fcfa7-173">`windowsdesktop`: runtime condiviso `Microsoft.WindowsDesktop.App`.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-173">`windowsdesktop` - the `Microsoft.WindowsDesktop.App` shared runtime.</span></span>

- **`--runtime-id <RID>`**

  <span data-ttu-id="fcfa7-174">Specifica l' [identificatore di runtime](../rid-catalog.md) per il quale vengono installati gli strumenti.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-174">Specifies the [runtime identifier](../rid-catalog.md) for which the tools are being installed.</span></span> <span data-ttu-id="fcfa7-175">Usare `linux-x64` per Linux portatile.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-175">Use `linux-x64` for portable Linux.</span></span> <span data-ttu-id="fcfa7-176">(Valido solo per Linux/macOS).</span><span class="sxs-lookup"><span data-stu-id="fcfa7-176">(Only valid for Linux/macOS.)</span></span>

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > <span data-ttu-id="fcfa7-177">Questo parametro è obsoleto e potrebbe essere rimosso in una versione futura dello script.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-177">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="fcfa7-178">L'alternativa consigliata è l'opzione `-Runtime|--runtime`.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-178">The recommended alternative is the `-Runtime|--runtime` option.</span></span>

  <span data-ttu-id="fcfa7-179">Installa solo i bit del runtime condiviso, non l'intero SDK.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-179">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="fcfa7-180">Questa opzione equivale a specificare `-Runtime|--runtime dotnet` .</span><span class="sxs-lookup"><span data-stu-id="fcfa7-180">This option is equivalent to specifying `-Runtime|--runtime dotnet`.</span></span>

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  <span data-ttu-id="fcfa7-181">Ignora l'installazione dei file senza versione, ad esempio *dotnet.exe*, se esistono già.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-181">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-UncachedFeed|--uncached-feed`**

  <span data-ttu-id="fcfa7-182">Consente di modificare l'URL per il feed non memorizzato nella cache usato da questo programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-182">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="fcfa7-183">È consigliabile non modificare questo valore.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-183">We recommended that you don't change this value.</span></span>

- **`-Verbose|--verbose`**

  <span data-ttu-id="fcfa7-184">Visualizza le informazioni di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-184">Displays diagnostics information.</span></span>

- **`-Version|--version <VERSION>`**

  <span data-ttu-id="fcfa7-185">Rappresenta una versione di build specifica.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-185">Represents a specific build version.</span></span> <span data-ttu-id="fcfa7-186">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-186">The possible values are:</span></span>

  - <span data-ttu-id="fcfa7-187">`latest`: ultima build sul canale (valore usato con l'opzione `-Channel`).</span><span class="sxs-lookup"><span data-stu-id="fcfa7-187">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="fcfa7-188">`coherent`: ultima build coerente sul canale. Usa la combinazione di pacchetti stabile più recente (valore usato con le opzioni `-Channel` del nome del ramo).</span><span class="sxs-lookup"><span data-stu-id="fcfa7-188">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="fcfa7-189">Versione in tre parti nel formato X.Y.Z che rappresenta una versione di build specifica; sostituisce l'opzione `-Channel`.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-189">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="fcfa7-190">Ad esempio: `2.0.0-preview2-006120`.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-190">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="fcfa7-191">Se non viene specificata, `-Version` viene impostata automaticamente su `latest`.</span><span class="sxs-lookup"><span data-stu-id="fcfa7-191">If not specified, `-Version` defaults to `latest`.</span></span>

## <a name="examples"></a><span data-ttu-id="fcfa7-192">Esempi</span><span class="sxs-lookup"><span data-stu-id="fcfa7-192">Examples</span></span>

- <span data-ttu-id="fcfa7-193">Installare la versione LTS (Long Term Support) più recente nel percorso predefinito:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-193">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="fcfa7-194">Windows:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-194">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="fcfa7-195">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-195">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="fcfa7-196">Installare la versione più recente dal canale 3,1 nel percorso specificato:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-196">Install the latest version from 3.1 channel to the specified location:</span></span>

  <span data-ttu-id="fcfa7-197">Windows:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-197">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  <span data-ttu-id="fcfa7-198">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-198">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- <span data-ttu-id="fcfa7-199">Installare la versione 3.0.0 del runtime condiviso:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-199">Install the 3.0.0 version of the shared runtime:</span></span>

  <span data-ttu-id="fcfa7-200">Windows:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-200">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  <span data-ttu-id="fcfa7-201">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-201">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- <span data-ttu-id="fcfa7-202">Ottenere lo script e installare la versione 2.1.2 versione dietro un proxy aziendale (solo Windows):</span><span class="sxs-lookup"><span data-stu-id="fcfa7-202">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="fcfa7-203">Ottenere lo script e installare gli esempi di .NET Core CLI di una singola riga di codice:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-203">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="fcfa7-204">Windows:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-204">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="fcfa7-205">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="fcfa7-205">macOS/Linux:</span></span>

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="fcfa7-206">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcfa7-206">See also</span></span>

- <span data-ttu-id="fcfa7-207">[.NET Core releases](https://github.com/dotnet/core/releases) (Versioni di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="fcfa7-207">[.NET Core releases](https://github.com/dotnet/core/releases)</span></span>
- <span data-ttu-id="fcfa7-208">[.NET Core Runtime and SDK download archive](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md) (Archivio di download per runtime e SDK di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="fcfa7-208">[.NET Core Runtime and SDK download archive](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)</span></span>
