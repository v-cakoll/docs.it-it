---
title: Come rimuovere il runtime e l'SDK .NET
description: Istruzioni per rimuovere i componenti Runtime di .NET Core e .NET Core SDK su Windows, Mac e Linux
ms.date: 07/28/2018
author: billwagner
ms.author: wiwagn
ms.openlocfilehash: 1806d1af3b10e44ccc2eff788d8958ca976fe85b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204916"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a><span data-ttu-id="46a87-103">Come rimuovere Runtime di .NET Core e .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="46a87-103">How to remove the .NET Core Runtime and SDK</span></span>

<span data-ttu-id="46a87-104">Nel corso del tempo, via via che si installano le versioni aggiornate di runtime e SDK di .NET Core l'utente potrebbe voler rimuovere le versioni obsolete di .NET Core dal computer.</span><span class="sxs-lookup"><span data-stu-id="46a87-104">Over time, as you install updated versions of the .NET Core runtime and SDK, you may want to remove outdated versions of .NET Core from your machine.</span></span> <span data-ttu-id="46a87-105">La rimozione delle versioni precedenti del runtime può cambiare il runtime scelto per eseguire le applicazioni di framework condiviso, come descritto in dettaglio nell'articolo [Scelta della versione di .NET Core](selection.md).</span><span class="sxs-lookup"><span data-stu-id="46a87-105">Removing older versions of the runtime may change the runtime chosen to run shared framework applications, as detailed in the article on [.NET Core version selection](selection.md).</span></span>

<span data-ttu-id="46a87-106">A partire da .NET Core 2.1, la CLI di .NET include opzioni che è possibile usare per elencare le versioni di SDK e runtime installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="46a87-106">Starting with .NET Core 2.1, the .NET CLI has options you can use to list the versions of the SDK and runtime that are installed on your machine.</span></span>  <span data-ttu-id="46a87-107">Usare [`dotnet --list-sdks`](../tools/dotnet.md#options) per visualizzare l'elenco degli SDK installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="46a87-107">Use [`dotnet --list-sdks`](../tools/dotnet.md#options) to see the list of SDKs installed on your machine.</span></span> <span data-ttu-id="46a87-108">Usare [`dotnet --list-runtimes`](../tools/dotnet.md#options) per visualizzare l'elenco dei runtime installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="46a87-108">Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) to see the list of runtimes installed on your machine.</span></span> <span data-ttu-id="46a87-109">Il testo seguente illustra un output tipico per Windows, macOS o Linux:</span><span class="sxs-lookup"><span data-stu-id="46a87-109">The following text shows typical output for Windows, macOS, or Linux:</span></span>

# <a name="windowstabwindows"></a>[<span data-ttu-id="46a87-110">Windows</span><span class="sxs-lookup"><span data-stu-id="46a87-110">Windows</span></span>](#tab/Windows)

```console
C:\> dotnet --list-sdks
2.1.200-preview-007474 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007480 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007509 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007570 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007576 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007587 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007589 [C:\Program Files\dotnet\sdk]
2.1.200 [C:\Program Files\dotnet\sdk]
2.1.201 [C:\Program Files\dotnet\sdk]
2.1.202 [C:\Program Files\dotnet\sdk]
2.1.300-preview2-008533 [C:\Program Files\dotnet\sdk]
2.1.300 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009063 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009088 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009171 [C:\Program Files\dotnet\sdk]

C:\> dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.0.6 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.7 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.9 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
```

# <a name="linuxtablinux"></a>[<span data-ttu-id="46a87-111">Linux</span><span class="sxs-lookup"><span data-stu-id="46a87-111">Linux</span></span>](#tab/Linux)

```console
$ dotnet --list-sdks
1.0.1 [/usr/share/dotnet/sdk]
1.0.4 [/usr/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/share/dotnet/sdk]
2.0.0 [/usr/share/dotnet/sdk]
2.1.4 [/usr/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/share/dotnet/sdk]
2.1.300 [/usr/share/dotnet/sdk]
2.1.301 [/usr/share/dotnet/sdk]

$ dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
```

# <a name="macostabmacos"></a>[<span data-ttu-id="46a87-112">macOS</span><span class="sxs-lookup"><span data-stu-id="46a87-112">macOS</span></span>](#tab/macOS)

```console
$ dotnet --list-sdks
1.0.1 [/usr/local/share/dotnet/sdk]
1.0.4 [/usr/local/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/local/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/local/share/dotnet/sdk]
2.0.0 [/usr/local/share/dotnet/sdk]
2.1.4 [/usr/local/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/local/share/dotnet/sdk]
2.1.300 [/usr/local/share/dotnet/sdk]
2.1.301 [/usr/local/share/dotnet/sdk]

$ dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

***

## <a name="uninstalling-net-core"></a><span data-ttu-id="46a87-113">Disinstallazione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="46a87-113">Uninstalling .NET Core</span></span>

# <a name="windowstabwindows"></a>[<span data-ttu-id="46a87-114">Windows</span><span class="sxs-lookup"><span data-stu-id="46a87-114">Windows</span></span>](#tab/Windows)

<span data-ttu-id="46a87-115">.NET Core usa la finestra di dialogo **Installazione applicazioni** di Windows per rimuovere le versioni di runtime e SDK di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="46a87-115">.NET Core uses the Windows **Add/Remove Programs** dialog to remove versions of the .NET Core runtime and SDK.</span></span> <span data-ttu-id="46a87-116">La figura seguente illustra la finestra di dialogo **Installazione applicazioni** con diverse versioni di runtime e SDK di .NET Core installati.</span><span class="sxs-lookup"><span data-stu-id="46a87-116">The following figure shows the **Add/Remove Programs** dialog with several versions of the .NET runtime and SDK installed.</span></span>

![Installazione applicazioni per la rimozione di .NET Core](./media/remove-runtime-sdk-versions/programs-and-features.png)

<span data-ttu-id="46a87-118">Selezionare tutte le versioni da rimuovere dal computer e fare clic su **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="46a87-118">Select any versions you want to remove from your machine and click **Uninstall**.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="46a87-119">Linux</span><span class="sxs-lookup"><span data-stu-id="46a87-119">Linux</span></span>](#tab/Linux)

<span data-ttu-id="46a87-120">Per disinstallare .NET Core (SDK o runtime) in Linux sono disponibili varie opzioni.</span><span class="sxs-lookup"><span data-stu-id="46a87-120">There are more options to uninstall .NET Core (either SDK or runtime) on Linux.</span></span> <span data-ttu-id="46a87-121">Il modo migliore per disinstallare .NET Core è eseguire il mirroring dell'azione usata per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="46a87-121">The best way for you to uninstall .NET Core is to mirror the action you used to install .NET Core.</span></span> <span data-ttu-id="46a87-122">Le specifiche variano in base alla distribuzione scelta e al metodo di installazione.</span><span class="sxs-lookup"><span data-stu-id="46a87-122">The specifics depend on your chosen distribution and the installation method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46a87-123">Per le installazioni di Red Hat, vedere l'[introduzione a Red Hat](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) per informazioni sull'installazione e la disinstallazione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="46a87-123">For Red Hat installations, consult the [Red Hat Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) for information on installing and uninstalling .NET Core.</span></span>

<span data-ttu-id="46a87-124">A partire da .NET Core 2.1, non è necessario disinstallare .NET Core SDK quando si esegue l'aggiornamento tramite uno strumento di gestione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="46a87-124">Starting with .NET Core 2.1, there is no need to uninstall the .NET Core SDK when upgrading it using a package manager.</span></span> <span data-ttu-id="46a87-125">La gestione pacchetti o i comandi `update` o `refresh` rimuoveranno automaticamente la versione precedente al termine dell'installazione di una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="46a87-125">The package manager `update` or `refresh` commands will automatically remove the older version upon the successful installation of a newer version.</span></span>

<span data-ttu-id="46a87-126">Se si è installato .NET Core usando uno strumento di gestione pacchetti, si userà la stessa gestione pacchetti per la disinstallazione dell'SDK o runtime .NET.</span><span class="sxs-lookup"><span data-stu-id="46a87-126">If you installed .NET Core using a package manager, you use that same package manager to uninstall .NET SDK or runtime.</span></span> <span data-ttu-id="46a87-127">Le installazioni di .NET Core supportano gli strumenti di gestione pacchetti più diffusi.</span><span class="sxs-lookup"><span data-stu-id="46a87-127">.NET Core installations support most popular package managers.</span></span> <span data-ttu-id="46a87-128">Vedere la documentazione relativa alla gestione pacchetti della propria distribuzione per l'esatta sintassi nel proprio ambiente:</span><span class="sxs-lookup"><span data-stu-id="46a87-128">Consult the documentation for your distribution's package manager for the precise syntax on your environment:</span></span>

- <span data-ttu-id="46a87-129">[apt-get(8)](https://linux.die.net/man/8/apt-get) viene usato dai sistemi basati su Debian, tra cui Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="46a87-129">[apt-get(8)](https://linux.die.net/man/8/apt-get) is used by Debian based systems, including Ubuntu.</span></span>
- <span data-ttu-id="46a87-130">[yum(8)](https://linux.die.net/man/8/yum) viene usato in Fedora, CentOS e Oracle Linux.</span><span class="sxs-lookup"><span data-stu-id="46a87-130">[yum(8)](https://linux.die.net/man/8/yum) is used on Fedora, CentOS, and Oracle Linux.</span></span>
- <span data-ttu-id="46a87-131">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) viene usato in openSUSE e SUSE Linux Enterprise System (SLES).</span><span class="sxs-lookup"><span data-stu-id="46a87-131">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) is used on openSUSE and SUSE Linux Enterprise System (SLES).</span></span>
- <span data-ttu-id="46a87-132">[dnf(8)](https://dnf.readthedocs.io/latest/command_ref.html) viene usato in Fedora.</span><span class="sxs-lookup"><span data-stu-id="46a87-132">[dnf(8)](https://dnf.readthedocs.io/latest/command_ref.html) is used on Fedora.</span></span>

<span data-ttu-id="46a87-133">Nella quasi totalità dei casi, il comando per rimuovere un pacchetto è `remove`.</span><span class="sxs-lookup"><span data-stu-id="46a87-133">In almost all cases, the command to remove a package is `remove`.</span></span>

<span data-ttu-id="46a87-134">Il nome del pacchetto per l'installazione di .NET Core SDK per la maggior parte degli strumenti di gestione pacchetti è `dotnet-sdk`, seguito dal numero di versione.</span><span class="sxs-lookup"><span data-stu-id="46a87-134">The package name for the .NET Core SDK installation for most package managers is `dotnet-sdk`, followed by the version number.</span></span> <span data-ttu-id="46a87-135">A partire dalla versione 2.1.300 di .NET Core SDK e dalla versione `2.1` del runtime, sono necessari solo i numeri di versione principale e secondario: ad esempio, .NET Core SDK versione 2.1.300 può essere indicato come pacchetto `dotnet-sdk-2.1`.</span><span class="sxs-lookup"><span data-stu-id="46a87-135">Starting with the version 2.1.300 of the .NET Core SDK and version `2.1` of the runtime, only the major and minor version numbers are necessary: for example, the .NET Core SDK version 2.1.300 can be referenced as the package `dotnet-sdk-2.1`.</span></span> <span data-ttu-id="46a87-136">Le versioni precedenti richiedono l'intera stringa di versione: ad esempio, per la versione 2.1.200 di .NET Core SDK sarebbe necessario `dotnet-sdk-2.1.200`.</span><span class="sxs-lookup"><span data-stu-id="46a87-136">Prior versions require the entire version string: for example, `dotnet-sdk-2.1.200` would be required for version 2.1.200 of the .NET Core SDK.</span></span>

<span data-ttu-id="46a87-137">Per i computer su cui è installato solo il runtime e non l'SDK, il nome del pacchetto è `dotnet-runtime-<version>` per il runtime di .NET Core e `aspnetcore-runtime-<version>` per lo stack di runtime intero.</span><span class="sxs-lookup"><span data-stu-id="46a87-137">For machines that have installed only the runtime, and not the SDK, the package name is `dotnet-runtime-<version>` for the .NET Core runtime, and `aspnetcore-runtime-<version>` for the entire runtime stack.</span></span>

<span data-ttu-id="46a87-138">Le installazioni di .NET Core precedenti a 2.0 non disinstallano l'applicazione host se l'SDK è stato disinstallato tramite uno strumento di gestione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="46a87-138">.NET Core installations prior to 2.0 did not uninstall the host application when the SDK was uninstalled using the package manager.</span></span> <span data-ttu-id="46a87-139">Usando `apt-get`, il comando è:</span><span class="sxs-lookup"><span data-stu-id="46a87-139">Using `apt-get`, the command is:</span></span>

```bash
apt-get remove dotnet-host
```

<span data-ttu-id="46a87-140">Si noti che non è presente alcuna versione collegata a `dotnet-host`.</span><span class="sxs-lookup"><span data-stu-id="46a87-140">Note that there is no version attached to `dotnet-host`.</span></span>

<span data-ttu-id="46a87-141">Se è l'installazione è stata eseguita tramite un file tarball, è necessario rimuovere .NET Core usando il metodo manuale.</span><span class="sxs-lookup"><span data-stu-id="46a87-141">If you installed using a tarball, you must remove .NET Core using the manual method.</span></span>

<span data-ttu-id="46a87-142">Rimuovere separatamente gli SDK e i runtime rimuovendo la directory contenente la relativa versione.</span><span class="sxs-lookup"><span data-stu-id="46a87-142">You remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="46a87-143">Ad esempio, per rimuovere l'SDK e il runtime versione 1.0.1, è necessario usare i comandi bash seguenti:</span><span class="sxs-lookup"><span data-stu-id="46a87-143">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="46a87-144">Le directory padre per l'SDK e il runtime sono elencate nell'output dai comandi `dotnet --list-sdks` e `dotnet --list-runtimes`, come illustrato nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="46a87-144">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="46a87-145">macOS</span><span class="sxs-lookup"><span data-stu-id="46a87-145">macOS</span></span>](#tab/macOS)

<span data-ttu-id="46a87-146">In Mac, rimuovere separatamente gli SDK e i runtime rimuovendo la directory contenente la relativa versione.</span><span class="sxs-lookup"><span data-stu-id="46a87-146">On Mac, you must remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="46a87-147">Ad esempio, per rimuovere l'SDK e il runtime versione 1.0.1, è necessario usare i comandi bash seguenti:</span><span class="sxs-lookup"><span data-stu-id="46a87-147">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/local/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="46a87-148">Le directory padre per l'SDK e il runtime sono elencate nell'output dai comandi `dotnet --list-sdks` e `dotnet --list-runtimes`, come illustrato nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="46a87-148">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

<span data-ttu-id="46a87-149">A partire da .NET Core 2.1, non è necessario disinstallare .NET Core SDK quando si esegue l'aggiornamento tramite uno strumento di gestione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="46a87-149">Starting with .NET Core 2.1, there is no need to uninstall the .NET Core SDK when upgrading it using a package manager.</span></span> <span data-ttu-id="46a87-150">La gestione pacchetti o i comandi `update` o `refresh` rimuoveranno automaticamente la versione precedente al termine dell'installazione di una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="46a87-150">The package manager `update` or `refresh` commands will automatically remove the older version upon the successful installation of a newer version.</span></span>

---
