---
title: Script dotnet-install
description: Informazioni sugli script dotnet-install per l'installazione degli strumenti dell'interfaccia della riga di comando di .NET Core e del runtime condiviso.
ms.date: 01/16/2019
ms.openlocfilehash: f72e12fc415824a9c69eba6f52e3c01717cf654c
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740526"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="283f9-103">Riferimento agli script dotnet-install</span><span class="sxs-lookup"><span data-stu-id="283f9-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="283f9-104">Name</span><span class="sxs-lookup"><span data-stu-id="283f9-104">Name</span></span>

<span data-ttu-id="283f9-105">`dotnet-install.ps1` | `dotnet-install.sh`: script usato per l'installazione degli strumenti dell'interfaccia della riga di comando e del runtime condiviso di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="283f9-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core CLI tools and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="283f9-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="283f9-106">Synopsis</span></span>

<span data-ttu-id="283f9-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="283f9-107">Windows:</span></span>

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential] [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]`

<span data-ttu-id="283f9-108">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="283f9-108">macOS/Linux:</span></span>

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential] [--runtime-id] [--skip-non-versioned-files] [--help]`

## <a name="description"></a><span data-ttu-id="283f9-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="283f9-109">Description</span></span>

<span data-ttu-id="283f9-110">Gli script `dotnet-install` vengono usati per eseguire un'installazione non amministrativa di .NET Core SDK, che include gli strumenti dell'interfaccia della riga di comando e il runtime condiviso di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="283f9-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="283f9-111">È consigliabile usare la versione stabile ospitata nel [sito Web principale di .NET Core](https://dot.net).</span><span class="sxs-lookup"><span data-stu-id="283f9-111">We recommend that you use the stable version that is hosted on [.NET Core main website](https://dot.net).</span></span> <span data-ttu-id="283f9-112">I percorsi diretti per gli script sono:</span><span class="sxs-lookup"><span data-stu-id="283f9-112">The direct paths to the scripts are:</span></span>

- <span data-ttu-id="283f9-113"><https://dot.net/v1/dotnet-install.sh> (Bash, UNIX)</span><span class="sxs-lookup"><span data-stu-id="283f9-113"><https://dot.net/v1/dotnet-install.sh> (bash, UNIX)</span></span>
- <span data-ttu-id="283f9-114"><https://dot.net/v1/dotnet-install.ps1> (Powershell, Windows)</span><span class="sxs-lookup"><span data-stu-id="283f9-114"><https://dot.net/v1/dotnet-install.ps1> (Powershell, Windows)</span></span>

<span data-ttu-id="283f9-115">Gli script vengono usati principalmente negli scenari di automazione e nelle installazioni senza privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="283f9-115">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="283f9-116">Sono disponibili due script: uno è uno script PowerShell, che funziona in Windows, e l'altro è uno script Bash, che funziona in Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="283f9-116">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="283f9-117">Entrambi gli script hanno lo stesso comportamento.</span><span class="sxs-lookup"><span data-stu-id="283f9-117">Both scripts have the same behavior.</span></span> <span data-ttu-id="283f9-118">Lo script bash legge anche le opzioni PowerShell, che possono quindi essere usate con lo script in sistemi Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="283f9-118">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="283f9-119">Gli script di installazione scaricano il file ZIP/tarball da destinazioni di compilazione dell'interfaccia della riga di comando e lo installano nel percorso predefinito o in un percorso specificato da `-InstallDir|--install-dir`.</span><span class="sxs-lookup"><span data-stu-id="283f9-119">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="283f9-120">Per impostazione predefinita, lo script di installazione scarica e installa l'SDK.</span><span class="sxs-lookup"><span data-stu-id="283f9-120">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="283f9-121">Se si vuole ottenere solo il runtime condiviso, è possibile specificare l'argomento `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="283f9-121">If you wish to only obtain the shared runtime, specify the `--runtime` argument.</span></span>

<span data-ttu-id="283f9-122">Per impostazione predefinita, lo script aggiunge il percorso di installazione a $PATH per la sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="283f9-122">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="283f9-123">Eseguire l'override di questo comportamento predefinito specificando l'argomento `--no-path`.</span><span class="sxs-lookup"><span data-stu-id="283f9-123">Override this default behavior by specifying the `--no-path` argument.</span></span>

<span data-ttu-id="283f9-124">Prima di eseguire lo script, installare le [dipendenze](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necessarie.</span><span class="sxs-lookup"><span data-stu-id="283f9-124">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

<span data-ttu-id="283f9-125">È possibile installare una versione specifica usando l'argomento `--version`.</span><span class="sxs-lookup"><span data-stu-id="283f9-125">You can install a specific version using the `--version` argument.</span></span> <span data-ttu-id="283f9-126">La versione deve essere specificata con un numero a tre parti (ad esempio, 1.0.0-13232).</span><span class="sxs-lookup"><span data-stu-id="283f9-126">The version must be specified as a three-part version (for example, 1.0.0-13232).</span></span> <span data-ttu-id="283f9-127">Se non viene fornita, viene usata la versione `latest`.</span><span class="sxs-lookup"><span data-stu-id="283f9-127">If not provided, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="283f9-128">Options</span><span class="sxs-lookup"><span data-stu-id="283f9-128">Options</span></span>

- **`-Channel <CHANNEL>`**

  <span data-ttu-id="283f9-129">Specifica il canale di origine per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="283f9-129">Specifies the source channel for the installation.</span></span> <span data-ttu-id="283f9-130">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="283f9-130">The possible values are:</span></span>

  - <span data-ttu-id="283f9-131">`Current`: versione più recente.</span><span class="sxs-lookup"><span data-stu-id="283f9-131">`Current` - Most current release.</span></span>
  - <span data-ttu-id="283f9-132">`LTS`: canale di supporto a lungo termine (versione supportata più recente).</span><span class="sxs-lookup"><span data-stu-id="283f9-132">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="283f9-133">Versione in due parti nel formato X.Y che rappresenta una versione specifica, ad esempio `2.0` o `1.0`.</span><span class="sxs-lookup"><span data-stu-id="283f9-133">Two-part version in X.Y format representing a specific release (for example, `2.0` or `1.0`).</span></span>
  - <span data-ttu-id="283f9-134">Nome ramo.</span><span class="sxs-lookup"><span data-stu-id="283f9-134">Branch name.</span></span> <span data-ttu-id="283f9-135">Ad esempio, `release/2.0.0`, `release/2.0.0-preview2` o `master` (per le versione notturne).</span><span class="sxs-lookup"><span data-stu-id="283f9-135">For example, `release/2.0.0`, `release/2.0.0-preview2`, or `master` (for nightly releases).</span></span>

  <span data-ttu-id="283f9-136">Il valore predefinito è `LTS`.</span><span class="sxs-lookup"><span data-stu-id="283f9-136">The default value is `LTS`.</span></span> <span data-ttu-id="283f9-137">Per altre informazioni sui canali di supporto per .NET, vedere la pagina [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) (Criteri di supporto per .NET).</span><span class="sxs-lookup"><span data-stu-id="283f9-137">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-Version <VERSION>`**

  <span data-ttu-id="283f9-138">Rappresenta una versione di build specifica.</span><span class="sxs-lookup"><span data-stu-id="283f9-138">Represents a specific build version.</span></span> <span data-ttu-id="283f9-139">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="283f9-139">The possible values are:</span></span>

  - <span data-ttu-id="283f9-140">`latest`: ultima build sul canale (valore usato con l'opzione `-Channel`).</span><span class="sxs-lookup"><span data-stu-id="283f9-140">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="283f9-141">`coherent`: ultima build coerente sul canale. Usa la combinazione di pacchetti stabile più recente (valore usato con le opzioni `-Channel` del nome del ramo).</span><span class="sxs-lookup"><span data-stu-id="283f9-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="283f9-142">Versione in tre parti nel formato X.Y.Z che rappresenta una versione di build specifica; sostituisce l'opzione `-Channel`.</span><span class="sxs-lookup"><span data-stu-id="283f9-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="283f9-143">Ad esempio: `2.0.0-preview2-006120`.</span><span class="sxs-lookup"><span data-stu-id="283f9-143">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="283f9-144">Se non viene specificata, `-Version` viene impostata automaticamente su `latest`.</span><span class="sxs-lookup"><span data-stu-id="283f9-144">If not specified, `-Version` defaults to `latest`.</span></span>

- **`-InstallDir <DIRECTORY>`**

  <span data-ttu-id="283f9-145">Specifica il percorso di installazione.</span><span class="sxs-lookup"><span data-stu-id="283f9-145">Specifies the installation path.</span></span> <span data-ttu-id="283f9-146">Se la directory non esiste, verrà creata.</span><span class="sxs-lookup"><span data-stu-id="283f9-146">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="283f9-147">Il valore predefinito è *%LocalAppData%\Microsoft\dotnet*.</span><span class="sxs-lookup"><span data-stu-id="283f9-147">The default value is *%LocalAppData%\Microsoft\dotnet*.</span></span> <span data-ttu-id="283f9-148">I file binari vengono inseriti direttamente in questa directory.</span><span class="sxs-lookup"><span data-stu-id="283f9-148">Binaries are placed directly in this directory.</span></span>

- **`-Architecture <ARCHITECTURE>`**

  <span data-ttu-id="283f9-149">Architettura dei file binari di .NET Core da installare.</span><span class="sxs-lookup"><span data-stu-id="283f9-149">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="283f9-150">I valori consentiti sono `<auto>`, `amd64`, `x64`, `x86`, `arm64` e `arm`.</span><span class="sxs-lookup"><span data-stu-id="283f9-150">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="283f9-151">Il valore predefinito è `<auto>`, che rappresenta l'architettura del sistema operativo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="283f9-151">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-SharedRuntime`**

  > [!NOTE]
  > <span data-ttu-id="283f9-152">Questo parametro è obsoleto e potrebbe essere rimosso in una versione futura dello script.</span><span class="sxs-lookup"><span data-stu-id="283f9-152">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="283f9-153">L'alternativa consigliata è l'opzione `Runtime`.</span><span class="sxs-lookup"><span data-stu-id="283f9-153">The recommended alternative is the `Runtime` option.</span></span>

  <span data-ttu-id="283f9-154">Installa solo i bit del runtime condiviso, non l'intero SDK.</span><span class="sxs-lookup"><span data-stu-id="283f9-154">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="283f9-155">Ciò equivale a specificare `-Runtime dotnet`.</span><span class="sxs-lookup"><span data-stu-id="283f9-155">This is equivalent to specifying `-Runtime dotnet`.</span></span>

- **`-Runtime <RUNTIME>`**

  <span data-ttu-id="283f9-156">Installa solo il runtime condiviso, non l'intero SDK.</span><span class="sxs-lookup"><span data-stu-id="283f9-156">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="283f9-157">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="283f9-157">The possible values are:</span></span>

  - <span data-ttu-id="283f9-158">`dotnet`: runtime condiviso `Microsoft.NETCore.App`.</span><span class="sxs-lookup"><span data-stu-id="283f9-158">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="283f9-159">`aspnetcore`: runtime condiviso `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="283f9-159">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>

- **`-DryRun`**

  <span data-ttu-id="283f9-160">Se impostata, lo script non eseguirà l'installazione.</span><span class="sxs-lookup"><span data-stu-id="283f9-160">If set, the script won't perform the installation.</span></span> <span data-ttu-id="283f9-161">Visualizza invece la riga di comando da usare per installare in modo coerente la versione attualmente richiesta dell'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="283f9-161">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="283f9-162">Se ad esempio si specifica la versione `latest`, verrà visualizzato un collegamento con la versione specifica in modo che questo comando possa essere usato in modo deterministico in uno script di compilazione.</span><span class="sxs-lookup"><span data-stu-id="283f9-162">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="283f9-163">Viene visualizzato anche il percorso del file binario se si preferisce installarlo o scaricarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="283f9-163">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-NoPath`**

  <span data-ttu-id="283f9-164">Se impostata, la cartella di installazione non viene esportata nel percorso per la sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="283f9-164">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="283f9-165">Per impostazione predefinita, lo script modifica il percorso rendendo disponibili gli strumenti dell'interfaccia della riga di comando immediatamente dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="283f9-165">By default, the script modifies the PATH, which makes the CLI tools available immediately after install.</span></span>

- **`-Verbose`**

  <span data-ttu-id="283f9-166">Visualizza le informazioni di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="283f9-166">Displays diagnostics information.</span></span>

- **`-AzureFeed`**

  <span data-ttu-id="283f9-167">Specifica l'URL del feed di Azure per il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="283f9-167">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="283f9-168">È consigliabile non modificare questo valore.</span><span class="sxs-lookup"><span data-stu-id="283f9-168">We recommended that you don't change this value.</span></span> <span data-ttu-id="283f9-169">Il valore predefinito è `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="283f9-169">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-UncachedFeed`**

  <span data-ttu-id="283f9-170">Consente di modificare l'URL per il feed non memorizzato nella cache usato da questo programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="283f9-170">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="283f9-171">È consigliabile non modificare questo valore.</span><span class="sxs-lookup"><span data-stu-id="283f9-171">We recommended that you don't change this value.</span></span>

- **`-NoCdn`**

  <span data-ttu-id="283f9-172">Disabilita il download dalla [Rete di distribuzione dei contenuti di Azure (rete CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) e usa direttamente il feed non memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="283f9-172">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-FeedCredential`**

  <span data-ttu-id="283f9-173">Usata come stringa di query da accodare al feed di Azure.</span><span class="sxs-lookup"><span data-stu-id="283f9-173">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="283f9-174">Consente la modifica dell'URL per usare account di archiviazione BLOB pubblici.</span><span class="sxs-lookup"><span data-stu-id="283f9-174">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="283f9-175">Se impostata, il programma di installazione usa il proxy durante le richieste Web.</span><span class="sxs-lookup"><span data-stu-id="283f9-175">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="283f9-176">(Valido solo per Windows)</span><span class="sxs-lookup"><span data-stu-id="283f9-176">(Only valid for Windows)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="283f9-177">Se impostata, il programma di installazione usa le credenziali dell'utente corrente quando si usa l'indirizzo proxy.</span><span class="sxs-lookup"><span data-stu-id="283f9-177">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="283f9-178">(Valido solo per Windows)</span><span class="sxs-lookup"><span data-stu-id="283f9-178">(Only valid for Windows)</span></span>

- **`-SkipNonVersionedFiles`**

  <span data-ttu-id="283f9-179">Ignora l'installazione dei file senza versione, ad esempio *dotnet.exe*, se esistono già.</span><span class="sxs-lookup"><span data-stu-id="283f9-179">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-Help`**

  <span data-ttu-id="283f9-180">Stampa la Guida per lo script.</span><span class="sxs-lookup"><span data-stu-id="283f9-180">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="283f9-181">Esempi</span><span class="sxs-lookup"><span data-stu-id="283f9-181">Examples</span></span>

- <span data-ttu-id="283f9-182">Installare la versione LTS (Long Term Support) più recente nel percorso predefinito:</span><span class="sxs-lookup"><span data-stu-id="283f9-182">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="283f9-183">Windows:</span><span class="sxs-lookup"><span data-stu-id="283f9-183">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="283f9-184">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="283f9-184">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="283f9-185">Installare la versione più recente dal canale 2.0 nel percorso specificato:</span><span class="sxs-lookup"><span data-stu-id="283f9-185">Install the latest version from 2.0 channel to the specified location:</span></span>

  <span data-ttu-id="283f9-186">Windows:</span><span class="sxs-lookup"><span data-stu-id="283f9-186">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli
  ```

  <span data-ttu-id="283f9-187">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="283f9-187">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 2.0 --install-dir ~/cli
  ```

- <span data-ttu-id="283f9-188">Installare la versione 1.1.0 del runtime condiviso:</span><span class="sxs-lookup"><span data-stu-id="283f9-188">Install the 1.1.0 version of the shared runtime:</span></span>

  <span data-ttu-id="283f9-189">Windows:</span><span class="sxs-lookup"><span data-stu-id="283f9-189">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 1.1.0
  ```

  <span data-ttu-id="283f9-190">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="283f9-190">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 1.1.0
  ```

- <span data-ttu-id="283f9-191">Ottenere lo script e installare la versione 2.1.2 versione dietro un proxy aziendale (solo Windows):</span><span class="sxs-lookup"><span data-stu-id="283f9-191">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="283f9-192">Ottenere lo script e installare gli esempi di .NET Core CLI di una singola riga di codice:</span><span class="sxs-lookup"><span data-stu-id="283f9-192">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="283f9-193">Windows:</span><span class="sxs-lookup"><span data-stu-id="283f9-193">Windows:</span></span>

  ```powershell
  @powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="283f9-194">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="283f9-194">macOS/Linux:</span></span>

  ```bash
  curl -ssl https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="283f9-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="283f9-195">See also</span></span>

- <span data-ttu-id="283f9-196">[.NET Core releases](https://github.com/dotnet/core/releases) (Versioni di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="283f9-196">[.NET Core releases](https://github.com/dotnet/core/releases)</span></span>
- <span data-ttu-id="283f9-197">[.NET Core Runtime and SDK download archive](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md) (Archivio di download per runtime e SDK di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="283f9-197">[.NET Core Runtime and SDK download archive](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)</span></span>
