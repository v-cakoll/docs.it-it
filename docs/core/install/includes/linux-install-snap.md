---
ms.openlocfilehash: 5e77b7bd73c09e061a94a29703cf5286814d1ebb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602915"
---

[<span data-ttu-id="1f799-101">.NET Core è disponibile nell'archivio di snap.</span><span class="sxs-lookup"><span data-stu-id="1f799-101">.NET Core is available from the Snap Store.</span></span>](https://snapcraft.io/dotnet-sdk)

<span data-ttu-id="1f799-102">Uno snap è un bundle di un'app e delle relative dipendenze che funziona senza modifiche in molte distribuzioni Linux diverse.</span><span class="sxs-lookup"><span data-stu-id="1f799-102">A snap is a bundle of an app and its dependencies that works without modification across many different Linux distributions.</span></span> <span data-ttu-id="1f799-103">Gli snap sono individuabili e installabili dall'archivio snap.</span><span class="sxs-lookup"><span data-stu-id="1f799-103">Snaps are discoverable and installable from the Snap Store.</span></span> <span data-ttu-id="1f799-104">Per ulteriori informazioni su snap, vedere la pagina relativa all' [Introduzione a snap](https://snapcraft.io/docs/getting-started).</span><span class="sxs-lookup"><span data-stu-id="1f799-104">For more information about Snap, see [Getting started with Snap](https://snapcraft.io/docs/getting-started).</span></span>

<span data-ttu-id="1f799-105">Solo le versioni supportate di .NET Core sono disponibili tramite snap.</span><span class="sxs-lookup"><span data-stu-id="1f799-105">Only supported versions of .NET Core are available through Snap.</span></span>

### <a name="install-the-sdk"></a><span data-ttu-id="1f799-106">Installare l'SDK</span><span class="sxs-lookup"><span data-stu-id="1f799-106">Install the SDK</span></span>

<span data-ttu-id="1f799-107">I pacchetti di snap per .NET Core SDK sono tutti pubblicati con lo stesso identificatore: `dotnet-sdk` .</span><span class="sxs-lookup"><span data-stu-id="1f799-107">Snap packages for .NET Core SDK are all published under the same identifier: `dotnet-sdk`.</span></span> <span data-ttu-id="1f799-108">È possibile installare una versione specifica dell'SDK specificando il canale.</span><span class="sxs-lookup"><span data-stu-id="1f799-108">A specific version of the SDK can be installed by specifying the channel.</span></span> <span data-ttu-id="1f799-109">L'SDK include il runtime di corisposta.</span><span class="sxs-lookup"><span data-stu-id="1f799-109">The SDK includes the coresponding runtime.</span></span> <span data-ttu-id="1f799-110">La tabella seguente elenca i canali:</span><span class="sxs-lookup"><span data-stu-id="1f799-110">The following table list the channels:</span></span>

| <span data-ttu-id="1f799-111">Versione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="1f799-111">.NET Core version</span></span> | <span data-ttu-id="1f799-112">Blocca pacchetto</span><span class="sxs-lookup"><span data-stu-id="1f799-112">Snap package</span></span>             |
|-------------------|--------------------------|
| <span data-ttu-id="1f799-113">3,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="1f799-113">3.1 (LTS)</span></span>         | <span data-ttu-id="1f799-114">`3.1` o `latest/stable`</span><span class="sxs-lookup"><span data-stu-id="1f799-114">`3.1` or `latest/stable`</span></span> |
| <span data-ttu-id="1f799-115">2,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="1f799-115">2.1 (LTS)</span></span>         | `2.1`                    |
| <span data-ttu-id="1f799-116">.NET 5,0 Preview</span><span class="sxs-lookup"><span data-stu-id="1f799-116">.NET 5.0 preview</span></span>  | `5.0/beta`               |

<span data-ttu-id="1f799-117">Usare il `snap install` comando per installare un pacchetto di snap .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="1f799-117">Use the `snap install` command to install a .NET Core SDK snap package.</span></span> <span data-ttu-id="1f799-118">Usare il `--channel` parametro per indicare la versione da installare.</span><span class="sxs-lookup"><span data-stu-id="1f799-118">Use the `--channel` parameter to indicate which version to install.</span></span> <span data-ttu-id="1f799-119">Se questo parametro viene omesso, `latest/stable` viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="1f799-119">If this parameter is omitted, `latest/stable` is used.</span></span> <span data-ttu-id="1f799-120">In questo esempio `3.1` viene specificato:</span><span class="sxs-lookup"><span data-stu-id="1f799-120">In this example, `3.1` is specified:</span></span>

```bash
sudo snap install dotnet-sdk --classic --channel=3.1
```

<span data-ttu-id="1f799-121">Registrare quindi il `dotnet` comando per il sistema con il `snap alias` comando:</span><span class="sxs-lookup"><span data-stu-id="1f799-121">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="1f799-122">Questo comando è formattato come: `sudo snap alias {package}.{command} {alias}` .</span><span class="sxs-lookup"><span data-stu-id="1f799-122">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="1f799-123">È possibile scegliere qualsiasi `{alias}` nome.</span><span class="sxs-lookup"><span data-stu-id="1f799-123">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="1f799-124">Ad esempio, è possibile denominare il comando dopo la versione specifica installata da snap: `sudo snap alias dotnet-sdk.dotnet dotnet31` .</span><span class="sxs-lookup"><span data-stu-id="1f799-124">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-sdk.dotnet dotnet31`.</span></span> <span data-ttu-id="1f799-125">Quando si usa il comando `dotnet31` , si richiama questa versione specifica di .NET.</span><span class="sxs-lookup"><span data-stu-id="1f799-125">When you use the command `dotnet31`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="1f799-126">Tuttavia, questo non è compatibile con la maggior parte delle esercitazioni ed esempi, perché si aspettano che un `dotnet` comando sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="1f799-126">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="1f799-127">Installare il runtime</span><span class="sxs-lookup"><span data-stu-id="1f799-127">Install the runtime</span></span>

<span data-ttu-id="1f799-128">I pacchetti di snap per il runtime di .NET Core sono pubblicati con il proprio identificatore del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1f799-128">Snap packages for .NET Core Runtime are each published under their own package identifier.</span></span> <span data-ttu-id="1f799-129">Nella tabella seguente sono elencati gli identificatori dei pacchetti:</span><span class="sxs-lookup"><span data-stu-id="1f799-129">The following table lists the package identifiers:</span></span>

| <span data-ttu-id="1f799-130">Versione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="1f799-130">.NET Core version</span></span> | <span data-ttu-id="1f799-131">Blocca pacchetto</span><span class="sxs-lookup"><span data-stu-id="1f799-131">Snap package</span></span>        |
|-------------------|---------------------|
| <span data-ttu-id="1f799-132">3,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="1f799-132">3.1 (LTS)</span></span>         | `dotnet-runtime-31` |
| <span data-ttu-id="1f799-133">3.0</span><span class="sxs-lookup"><span data-stu-id="1f799-133">3.0</span></span>               | `dotnet-runtime-30` |
| <span data-ttu-id="1f799-134">2.2</span><span class="sxs-lookup"><span data-stu-id="1f799-134">2.2</span></span>               | `dotnet-runtime-22` |
| <span data-ttu-id="1f799-135">2,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="1f799-135">2.1 (LTS)</span></span>         | `dotnet-runtime-21` |

<span data-ttu-id="1f799-136">Usare il `snap install` comando per installare un pacchetto di snap-in di runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1f799-136">Use the `snap install` command to install a .NET Core Runtime snap package.</span></span> <span data-ttu-id="1f799-137">In questo esempio è installato .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="1f799-137">In this example, .NET Core 3.1 is installed:</span></span>

```bash
sudo snap install dotnet-runtime-31 --classic
```

<span data-ttu-id="1f799-138">Registrare quindi il `dotnet` comando per il sistema con il `snap alias` comando:</span><span class="sxs-lookup"><span data-stu-id="1f799-138">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-runtime-31.dotnet dotnet
```

<span data-ttu-id="1f799-139">Questo comando è formattato come: `sudo snap alias {package}.{command} {alias}` .</span><span class="sxs-lookup"><span data-stu-id="1f799-139">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="1f799-140">È possibile scegliere qualsiasi `{alias}` nome.</span><span class="sxs-lookup"><span data-stu-id="1f799-140">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="1f799-141">Ad esempio, è possibile denominare il comando dopo la versione specifica installata da snap: `sudo snap alias dotnet-runtime-31.dotnet dotnet31` .</span><span class="sxs-lookup"><span data-stu-id="1f799-141">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-runtime-31.dotnet dotnet31`.</span></span> <span data-ttu-id="1f799-142">Quando si usa il comando `dotnet31` , si richiama questa versione specifica di .NET.</span><span class="sxs-lookup"><span data-stu-id="1f799-142">When you use the command `dotnet31`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="1f799-143">Tuttavia, questo non è compatibile con la maggior parte delle esercitazioni ed esempi, perché si aspettano che un `dotnet` comando sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="1f799-143">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="ssl-certificate-errors"></a><span data-ttu-id="1f799-144">Errori del certificato SSL</span><span class="sxs-lookup"><span data-stu-id="1f799-144">SSL Certificate errors</span></span>

<span data-ttu-id="1f799-145">Quando .NET viene installato tramite snap, è possibile che in alcune distribuzioni i certificati SSL .NET non vengano trovati ed è possibile che venga visualizzato un errore simile al seguente durante `restore` :</span><span class="sxs-lookup"><span data-stu-id="1f799-145">When .NET is installed through Snap, it's possible that on some distros the .NET SSL certificates may not be found and you may receive an error similar to the following during `restore`:</span></span>

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

<span data-ttu-id="1f799-146">Per risolvere questo problema, impostare alcune variabili ambiente:</span><span class="sxs-lookup"><span data-stu-id="1f799-146">To resolve this issue, set a few enviornment variables:</span></span>

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

<span data-ttu-id="1f799-147">Il percorso del certificato può variare in base alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1f799-147">The certificate location will vary by distro.</span></span> <span data-ttu-id="1f799-148">Ecco i percorsi per le distribuzioni in cui si è verificato il problema.</span><span class="sxs-lookup"><span data-stu-id="1f799-148">Here are the locations for the distros where we have experienced the issue.</span></span>

* <span data-ttu-id="1f799-149">Fedora`/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="1f799-149">Fedora - `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span></span>
* <span data-ttu-id="1f799-150">OpenSUSE`/etc/ssl/ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="1f799-150">OpenSUSE - `/etc/ssl/ca-bundle.pem`</span></span>
* <span data-ttu-id="1f799-151">Solus`/etc/ssl/certs/ca-certificates.crt`</span><span class="sxs-lookup"><span data-stu-id="1f799-151">Solus - `/etc/ssl/certs/ca-certificates.crt`</span></span>
