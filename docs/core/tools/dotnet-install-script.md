---
title: Script dotnet-install
description: Informazioni sugli script dotnet-install per l'installazione degli strumenti dell'interfaccia della riga di comando di .NET Core e del runtime condiviso.
author: blackdwarf
ms.author: mairaw
ms.date: 09/11/2017
ms.openlocfilehash: acdf49950ebb49751c55ae72b3f623e590489202
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33214380"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="87762-103">Riferimento agli script dotnet-install</span><span class="sxs-lookup"><span data-stu-id="87762-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="87762-104">nome</span><span class="sxs-lookup"><span data-stu-id="87762-104">Name</span></span>

<span data-ttu-id="87762-105">`dotnet-install.ps1` | `dotnet-install.sh`: script usato per l'installazione degli strumenti dell'interfaccia della riga di comando e del runtime condiviso di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="87762-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core CLI tools and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="87762-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="87762-106">Synopsis</span></span>

<span data-ttu-id="87762-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="87762-107">Windows:</span></span>

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress] [--Verbose] [--Help]`

<span data-ttu-id="87762-108">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="87762-108">macOS/Linux:</span></span>

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--dry-run] [--no-path] [--azure-feed] [--verbose] [--help]`

## <a name="description"></a><span data-ttu-id="87762-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87762-109">Description</span></span>

<span data-ttu-id="87762-110">Gli script `dotnet-install` vengono usati per eseguire un'installazione non amministrativa di .NET Core SDK, che include gli strumenti dell'interfaccia della riga di comando e il runtime condiviso di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="87762-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="87762-111">È consigliabile usare la versione stabile ospitata nel [sito Web principale di .NET Core](https://dot.net).</span><span class="sxs-lookup"><span data-stu-id="87762-111">We recommend that you use the stable version that is hosted on [.NET Core main website](https://dot.net).</span></span> <span data-ttu-id="87762-112">I percorsi diretti per gli script sono:</span><span class="sxs-lookup"><span data-stu-id="87762-112">The direct paths to the scripts are:</span></span>

* <span data-ttu-id="87762-113">https://dot.net/v1/dotnet-install.sh (Bash, UNIX)</span><span class="sxs-lookup"><span data-stu-id="87762-113">https://dot.net/v1/dotnet-install.sh (bash, UNIX)</span></span>
* <span data-ttu-id="87762-114">https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)</span><span class="sxs-lookup"><span data-stu-id="87762-114">https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)</span></span>

<span data-ttu-id="87762-115">Gli script vengono usati principalmente negli scenari di automazione e nelle installazioni senza privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="87762-115">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="87762-116">Sono disponibili due script, uno per PowerShell, che funziona in Windows,</span><span class="sxs-lookup"><span data-stu-id="87762-116">There are two scripts: One is a PowerShell script that works on Windows.</span></span> <span data-ttu-id="87762-117">L'altro script è uno script bash che funziona su Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="87762-117">The other script is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="87762-118">Entrambi gli script hanno lo stesso comportamento.</span><span class="sxs-lookup"><span data-stu-id="87762-118">Both scripts have the same behavior.</span></span> <span data-ttu-id="87762-119">Lo script bash legge anche le opzioni PowerShell, che possono quindi essere usate con lo script in sistemi Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="87762-119">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span> 

<span data-ttu-id="87762-120">Gli script di installazione scaricano il file ZIP/tarball da destinazioni di compilazione dell'interfaccia della riga di comando e lo installano nel percorso predefinito o in un percorso specificato da `-InstallDir|--install-dir`.</span><span class="sxs-lookup"><span data-stu-id="87762-120">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="87762-121">Per impostazione predefinita, lo script di installazione scarica e installa l'SDK.</span><span class="sxs-lookup"><span data-stu-id="87762-121">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="87762-122">Se si vuole ottenere solo il runtime condiviso, è possibile specificare l'argomento `--shared-runtime`.</span><span class="sxs-lookup"><span data-stu-id="87762-122">If you wish to only obtain the shared runtime, specify the `--shared-runtime` argument.</span></span> 

<span data-ttu-id="87762-123">Per impostazione predefinita, lo script aggiunge il percorso di installazione a $PATH per la sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="87762-123">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="87762-124">Eseguire l'override di questo comportamento predefinito specificando l'argomento `--no-path`.</span><span class="sxs-lookup"><span data-stu-id="87762-124">Override this default behavior by specifying the `--no-path` argument.</span></span> 

<span data-ttu-id="87762-125">Prima di eseguire lo script, installare le [dipendenze](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necessarie.</span><span class="sxs-lookup"><span data-stu-id="87762-125">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

<span data-ttu-id="87762-126">È possibile installare una versione specifica usando l'argomento `--version`.</span><span class="sxs-lookup"><span data-stu-id="87762-126">You can install a specific version using the `--version` argument.</span></span> <span data-ttu-id="87762-127">La versione deve essere specificata con un numero a tre parti (ad esempio, 1.0.0-13232).</span><span class="sxs-lookup"><span data-stu-id="87762-127">The version must be specified as a 3-part version (for example, 1.0.0-13232).</span></span> <span data-ttu-id="87762-128">Se omessa, viene usata la versione `latest`.</span><span class="sxs-lookup"><span data-stu-id="87762-128">If omitted, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="87762-129">Opzioni</span><span class="sxs-lookup"><span data-stu-id="87762-129">Options</span></span>

`-Channel <CHANNEL>`

<span data-ttu-id="87762-130">Specifica il canale di origine per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="87762-130">Specifies the source channel for the installation.</span></span> <span data-ttu-id="87762-131">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="87762-131">The possible values are:</span></span>

- <span data-ttu-id="87762-132">`Current` - Versione corrente</span><span class="sxs-lookup"><span data-stu-id="87762-132">`Current` - Current release</span></span>
- <span data-ttu-id="87762-133">`LTS` - Canale di supporto a lungo termine (versione supportata corrente)</span><span class="sxs-lookup"><span data-stu-id="87762-133">`LTS` - Long-Term Support channel (current supported release)</span></span>
- <span data-ttu-id="87762-134">Versione in due parti nel formato X.Y che rappresenta una versione specifica, ad esempio `2.0` o `1.0`</span><span class="sxs-lookup"><span data-stu-id="87762-134">Two-part version in X.Y format representing a specific release (for example, `2.0` or `1.0`)</span></span>
- <span data-ttu-id="87762-135">Nome del ramo, ad esempio, `release/2.0.0`, `release/2.0.0-preview2` o `master` per la versione più recente dal ramo `master` (versioni notturne "all'avanguardia")</span><span class="sxs-lookup"><span data-stu-id="87762-135">Branch name [for example, `release/2.0.0`, `release/2.0.0-preview2`, or `master` for the latest from the `master` branch ("bleeding edge" nightly releases)]</span></span>

<span data-ttu-id="87762-136">Il valore predefinito è `LTS`.</span><span class="sxs-lookup"><span data-stu-id="87762-136">The default value is `LTS`.</span></span> <span data-ttu-id="87762-137">Per altre informazioni sui canali di supporto per .NET, vedere l'argomento [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support) (Ciclo di vita del supporto per .NET Core).</span><span class="sxs-lookup"><span data-stu-id="87762-137">For more information on .NET support channels, see the [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support) topic.</span></span>

`-Version <VERSION>`

<span data-ttu-id="87762-138">Rappresenta una versione di build specifica.</span><span class="sxs-lookup"><span data-stu-id="87762-138">Represents a specific build version.</span></span> <span data-ttu-id="87762-139">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="87762-139">The possible values are:</span></span>

- <span data-ttu-id="87762-140">`latest` - Ultima build sul canale (valore usato con l'opzione `-Channel`)</span><span class="sxs-lookup"><span data-stu-id="87762-140">`latest` - Latest build on the channel (used with the `-Channel` option)</span></span>
- <span data-ttu-id="87762-141">`coherent` - Ultima build coerente sul canale; usa la combinazione di pacchetti stabile più recente (valore usato con le opzioni `-Channel` del nome di ramo)</span><span class="sxs-lookup"><span data-stu-id="87762-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options)</span></span>
- <span data-ttu-id="87762-142">Versione in tre parti nel formato X.Y.Z che rappresenta una versione di build specifica; sostituisce l'opzione `-Channel`.</span><span class="sxs-lookup"><span data-stu-id="87762-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="87762-143">Ad esempio: `2.0.0-preview2-006120`</span><span class="sxs-lookup"><span data-stu-id="87762-143">For example: `2.0.0-preview2-006120`</span></span>

<span data-ttu-id="87762-144">Se omesso, `-Version` viene impostato automaticamente su `latest`.</span><span class="sxs-lookup"><span data-stu-id="87762-144">If omitted, `-Version` defaults to `latest`.</span></span>

`-InstallDir <DIRECTORY>`

<span data-ttu-id="87762-145">Specifica il percorso di installazione.</span><span class="sxs-lookup"><span data-stu-id="87762-145">Specifies the installation path.</span></span> <span data-ttu-id="87762-146">Se la directory non esiste, verrà creata.</span><span class="sxs-lookup"><span data-stu-id="87762-146">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="87762-147">Il valore predefinito è *%LocalAppData%\.dotnet*.</span><span class="sxs-lookup"><span data-stu-id="87762-147">The default value is *%LocalAppData%\.dotnet*.</span></span> <span data-ttu-id="87762-148">Si noti che i file binari vengono inseriti direttamente nella directory.</span><span class="sxs-lookup"><span data-stu-id="87762-148">Note that binaries are placed directly in the directory.</span></span>

`-Architecture <ARCHITECTURE>`

<span data-ttu-id="87762-149">Architettura dei file binari di .NET Core da installare.</span><span class="sxs-lookup"><span data-stu-id="87762-149">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="87762-150">I valori possibili sono `auto`, `x64` e `x86`.</span><span class="sxs-lookup"><span data-stu-id="87762-150">Possible values are `auto`, `x64`, and `x86`.</span></span> <span data-ttu-id="87762-151">Il valore predefinito è `auto`, che rappresenta l'architettura del sistema operativo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="87762-151">The default value is `auto`, which represents the currently running OS architecture.</span></span>

`-SharedRuntime`

<span data-ttu-id="87762-152">Se impostata, questa opzione limita l'installazione al runtime condiviso.</span><span class="sxs-lookup"><span data-stu-id="87762-152">If set, this switch limits installation to the shared runtime.</span></span> <span data-ttu-id="87762-153">Non viene installato l'intero SDK.</span><span class="sxs-lookup"><span data-stu-id="87762-153">The entire SDK isn't installed.</span></span>

`-DryRun`

<span data-ttu-id="87762-154">Se impostata, lo script non esegue l'installazione, ma visualizza la riga di comando da usare per installare in modo coerente la versione attualmente richiesta dell'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="87762-154">If set, the script won't perform the installation; but instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="87762-155">Se ad esempio si specifica la versione `latest`, verrà visualizzato un collegamento con la versione specifica in modo che questo comando possa essere usato in modo deterministico in uno script di compilazione.</span><span class="sxs-lookup"><span data-stu-id="87762-155">For example if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="87762-156">Viene visualizzato anche il percorso del file binario se si preferisce installarlo o scaricarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="87762-156">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

`-NoPath`

<span data-ttu-id="87762-157">Se impostata, il prefisso o la directory di installazione non viene esportata nel percorso per la sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="87762-157">If set, the prefix/installdir are not exported to the path for the current session.</span></span> <span data-ttu-id="87762-158">Per impostazione predefinita, lo script modifica il percorso rendendo disponibili gli strumenti dell'interfaccia della riga di comando immediatamente dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="87762-158">By default, the script will modify the PATH, which makes the CLI tools available immediately after install.</span></span>

`-AzureFeed`

<span data-ttu-id="87762-159">Specifica l'URL del feed di Azure per il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="87762-159">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="87762-160">È consigliabile non modificare questo valore.</span><span class="sxs-lookup"><span data-stu-id="87762-160">It isn't recommended that you change this value.</span></span> <span data-ttu-id="87762-161">Il valore predefinito è `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="87762-161">The default is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

`-ProxyAddress`

<span data-ttu-id="87762-162">Se impostata, il programma di installazione usa il proxy durante le richieste Web.</span><span class="sxs-lookup"><span data-stu-id="87762-162">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="87762-163">(Valido solo per Windows)</span><span class="sxs-lookup"><span data-stu-id="87762-163">(Only valid for Windows)</span></span>

`--verbose`

<span data-ttu-id="87762-164">Visualizza le informazioni di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="87762-164">Display diagnostics information.</span></span>

`--help`

<span data-ttu-id="87762-165">Stampa la Guida per lo script.</span><span class="sxs-lookup"><span data-stu-id="87762-165">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="87762-166">Esempi</span><span class="sxs-lookup"><span data-stu-id="87762-166">Examples</span></span>

<span data-ttu-id="87762-167">Installare la versione LTS (Long Term Support) più recente nel percorso predefinito:</span><span class="sxs-lookup"><span data-stu-id="87762-167">Install the latest long-term supported (LTS) version to the default location:</span></span>

<span data-ttu-id="87762-168">Windows:</span><span class="sxs-lookup"><span data-stu-id="87762-168">Windows:</span></span>

`./dotnet-install.ps1 -Channel LTS`

<span data-ttu-id="87762-169">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="87762-169">macOS/Linux:</span></span>

`./dotnet-install.sh --channel LTS`

<span data-ttu-id="87762-170">Installare la versione più recente dal canale 2.0 nel percorso specificato:</span><span class="sxs-lookup"><span data-stu-id="87762-170">Install the latest version from 2.0 channel to the specified location:</span></span>

<span data-ttu-id="87762-171">Windows:</span><span class="sxs-lookup"><span data-stu-id="87762-171">Windows:</span></span>

`./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli`

<span data-ttu-id="87762-172">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="87762-172">macOS/Linux:</span></span>

`./dotnet-install.sh --channel 2.0 --install-dir ~/cli`

<span data-ttu-id="87762-173">Installare la versione 1.1.0 del runtime condiviso:</span><span class="sxs-lookup"><span data-stu-id="87762-173">Install the 1.1.0 version of the shared runtime:</span></span>

<span data-ttu-id="87762-174">Windows:</span><span class="sxs-lookup"><span data-stu-id="87762-174">Windows:</span></span>

`./dotnet-install.ps1 -SharedRuntime -Version 1.1.0`

<span data-ttu-id="87762-175">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="87762-175">macOS/Linux:</span></span>

`./dotnet-install.sh --shared-runtime --version 1.1.0`

<span data-ttu-id="87762-176">Ottenere lo script e installare gli esempi di .NET Core CLI di una singola riga di codice:</span><span class="sxs-lookup"><span data-stu-id="87762-176">Obtain script and install .NET Core CLI one-liner examples:</span></span>

<span data-ttu-id="87762-177">Windows:</span><span class="sxs-lookup"><span data-stu-id="87762-177">Windows:</span></span>

`@powershell -NoProfile -ExecutionPolicy unrestricted -Command "&([scriptblock]::Create((Invoke-WebRequest -useb 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"`

<span data-ttu-id="87762-178">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="87762-178">macOS/Linux:</span></span>

`curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>`

## <a name="see-also"></a><span data-ttu-id="87762-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87762-179">See also</span></span>

<span data-ttu-id="87762-180">[Versioni di .NET Core](https://github.com/dotnet/core/releases) </span><span class="sxs-lookup"><span data-stu-id="87762-180">[.NET Core releases](https://github.com/dotnet/core/releases) </span></span>  
<span data-ttu-id="87762-181">[.NET Core Runtime and SDK download archive](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md) (Archivio di download per runtime e SDK di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="87762-181">[.NET Core Runtime and SDK download archive](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)</span></span>
