---
title: Controllare le versioni di .NET Core installate in Windows, Linux e macOS-.NET Core
description: Informazioni su come elencare le versioni di .NET Core installate nel computer. Sono inclusi il runtime e l'SDK di .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: cc4d9c6a366cd0e5da4c3446536c93efdc9f5503
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324821"
---
# <a name="how-to-check-that-net-core-is-already-installed"></a><span data-ttu-id="95886-104">Come verificare che .NET Core sia già installato</span><span class="sxs-lookup"><span data-stu-id="95886-104">How to check that .NET Core is already installed</span></span>

<span data-ttu-id="95886-105">Questo articolo illustra come verificare quali versioni del runtime e dell'SDK di .NET Core sono installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="95886-105">This article teaches you how to check which versions of the .NET Core runtime and SDK are installed on your computer.</span></span> <span data-ttu-id="95886-106">.NET Core potrebbe essere già stato installato se si dispone di un Integrated Development Environment, ad esempio Visual Studio o Visual Studio per Mac.</span><span class="sxs-lookup"><span data-stu-id="95886-106">.NET core may have already been installed if you have an integrated development environment, such as Visual Studio or Visual Studio for Mac.</span></span>

<span data-ttu-id="95886-107">Installando un SDK viene installato il runtime corrispondente.</span><span class="sxs-lookup"><span data-stu-id="95886-107">Installing an SDK installs the corresponding runtime.</span></span>

<span data-ttu-id="95886-108">Se un comando in questo articolo ha esito negativo, il runtime o l'SDK non è installato.</span><span class="sxs-lookup"><span data-stu-id="95886-108">If any command in this article fails, you don't have the runtime or SDK installed.</span></span> <span data-ttu-id="95886-109">Per altre informazioni, vedere [scaricare e installare .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="95886-109">For more information, see [Download and install .NET Core](index.md).</span></span>

## <a name="check-sdk-versions"></a><span data-ttu-id="95886-110">Controllare le versioni dell'SDK</span><span class="sxs-lookup"><span data-stu-id="95886-110">Check SDK versions</span></span>

<span data-ttu-id="95886-111">È possibile visualizzare le versioni del .NET Core SDK attualmente installate con un terminale.</span><span class="sxs-lookup"><span data-stu-id="95886-111">You can see which versions of the .NET Core SDK are currently installed with a terminal.</span></span> <span data-ttu-id="95886-112">Aprire un terminale ed eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="95886-112">Open a terminal and run the following command.</span></span>

```dotnetcli
dotnet --list-sdks
```

<span data-ttu-id="95886-113">Si otterrà un output simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="95886-113">You get output similar to the following.</span></span>

::: zone pivot="os-windows"

```console
2.1.500 [C:\program files\dotnet\sdk]
2.1.502 [C:\program files\dotnet\sdk]
2.1.504 [C:\program files\dotnet\sdk]
2.1.600 [C:\program files\dotnet\sdk]
2.1.602 [C:\program files\dotnet\sdk]
2.2.101 [C:\program files\dotnet\sdk]
3.0.100 [C:\program files\dotnet\sdk]
3.1.100 [C:\program files\dotnet\sdk]
```

::: zone-end

::: zone pivot="os-linux"

```bash
2.1.500 [/home/user/dotnet/sdk]
2.1.502 [/home/user/dotnet/sdk]
2.1.504 [/home/user/dotnet/sdk]
2.1.600 [/home/user/dotnet/sdk]
2.1.602 [/home/user/dotnet/sdk]
2.2.101 [/home/user/dotnet/sdk]
3.0.100 [/home/user/dotnet/sdk]
3.1.100 [/home/user/dotnet/sdk]
```

::: zone-end

::: zone pivot="os-macos"

```bash
2.1.500 [/usr/local/share/dotnet/sdk]
2.1.502 [/usr/local/share/dotnet/sdk]
2.1.504 [/usr/local/share/dotnet/sdk]
2.1.600 [/usr/local/share/dotnet/sdk]
2.1.602 [/usr/local/share/dotnet/sdk]
2.2.101 [/usr/local/share/dotnet/sdk]
3.0.100 [/usr/local/share/dotnet/sdk]
3.1.100 [/usr/local/share/dotnet/sdk]
```

::: zone-end

## <a name="check-runtime-versions"></a><span data-ttu-id="95886-114">Controllare le versioni di runtime</span><span class="sxs-lookup"><span data-stu-id="95886-114">Check runtime versions</span></span>

<span data-ttu-id="95886-115">È possibile vedere quali versioni del runtime di .NET Core sono attualmente installate con il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="95886-115">You can see which versions of the .NET Core runtime are currently installed with the following command.</span></span>

```dotnetcli
dotnet --list-runtimes
```

<span data-ttu-id="95886-116">Si otterrà un output simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="95886-116">You get output similar to the following.</span></span>

::: zone pivot="os-windows"

```console
Microsoft.AspNetCore.All 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.WindowsDesktop.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
Microsoft.WindowsDesktop.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
```

::: zone-end

::: zone pivot="os-linux"

```bash
Microsoft.AspNetCore.All 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

::: zone pivot="os-macos"

```bash
Microsoft.AspNetCore.All 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

## <a name="check-for-install-folders"></a><span data-ttu-id="95886-117">Verificare la presenza di cartelle di installazione</span><span class="sxs-lookup"><span data-stu-id="95886-117">Check for install folders</span></span>

<span data-ttu-id="95886-118">È possibile che .NET Core sia installato ma non aggiunto alla `PATH` variabile per il proprio sistema operativo o profilo utente.</span><span class="sxs-lookup"><span data-stu-id="95886-118">It's possible that .NET Core is installed but not added to the `PATH` variable for your operating system or user profile.</span></span> <span data-ttu-id="95886-119">L'esecuzione dei comandi delle sezioni precedenti potrebbe non funzionare.</span><span class="sxs-lookup"><span data-stu-id="95886-119">Running the commands from the previous sections may not work.</span></span> <span data-ttu-id="95886-120">In alternativa, è possibile verificare che le cartelle di installazione di .NET Core esistano.</span><span class="sxs-lookup"><span data-stu-id="95886-120">As an alternative, you can check that the .NET Core install folders exist.</span></span>

<span data-ttu-id="95886-121">Quando si installa .NET Core da un programma di installazione o da uno script, questo viene installato in una cartella standard.</span><span class="sxs-lookup"><span data-stu-id="95886-121">When you install .NET Core from an installer or script, it's installed to a standard folder.</span></span> <span data-ttu-id="95886-122">Gran parte del tempo in cui il programma di installazione o lo script usato per installare .NET Core offre un'opzione di installazione in una cartella diversa.</span><span class="sxs-lookup"><span data-stu-id="95886-122">Much of the time the installer or script you're using to install .NET Core gives you an option to install to a different folder.</span></span> <span data-ttu-id="95886-123">Se si sceglie di eseguire l'installazione in una cartella diversa, modificare l'inizio del percorso della cartella.</span><span class="sxs-lookup"><span data-stu-id="95886-123">If you choose to install to a different folder, adjust the start of the folder path.</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="95886-124">**eseguibile DotNet**</span><span class="sxs-lookup"><span data-stu-id="95886-124">**dotnet executable**</span></span>\
<span data-ttu-id="95886-125">_C: \\ file di programma \\ DotNet \\dotnet.exe_</span><span class="sxs-lookup"><span data-stu-id="95886-125">_C:\\program files\\dotnet\\dotnet.exe_</span></span>

- <span data-ttu-id="95886-126">**.NET SDK**</span><span class="sxs-lookup"><span data-stu-id="95886-126">**.NET SDK**</span></span>\
<span data-ttu-id="95886-127">_C: \\ programmi \\ DotNet \\ SDK \\ {Version}\\_</span><span class="sxs-lookup"><span data-stu-id="95886-127">_C:\\program files\\dotnet\\sdk\\{version}\\_</span></span>

- <span data-ttu-id="95886-128">**Runtime .NET**</span><span class="sxs-lookup"><span data-stu-id="95886-128">**.NET Runtime**</span></span>\
<span data-ttu-id="95886-129">_C: \\ programmi \\ DotNet \\ Shared \\ {Runtime-Type} \\ {Version}\\_</span><span class="sxs-lookup"><span data-stu-id="95886-129">_C:\\program files\\dotnet\\shared\\{runtime-type}\\{version}\\_</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="95886-130">**eseguibile DotNet**</span><span class="sxs-lookup"><span data-stu-id="95886-130">**dotnet executable**</span></span>\
<span data-ttu-id="95886-131">_/home/user/share/dotnet/dotnet_</span><span class="sxs-lookup"><span data-stu-id="95886-131">_/home/user/share/dotnet/dotnet_</span></span>

- <span data-ttu-id="95886-132">**.NET SDK**</span><span class="sxs-lookup"><span data-stu-id="95886-132">**.NET SDK**</span></span>\
<span data-ttu-id="95886-133">_/home/user/share/dotnet/sdk/{version}/_</span><span class="sxs-lookup"><span data-stu-id="95886-133">_/home/user/share/dotnet/sdk/{version}/_</span></span>

- <span data-ttu-id="95886-134">**Runtime .NET**</span><span class="sxs-lookup"><span data-stu-id="95886-134">**.NET Runtime**</span></span>\
<span data-ttu-id="95886-135">_/home/user/share/dotnet/shared/{runtime-type}/{version}/_</span><span class="sxs-lookup"><span data-stu-id="95886-135">_/home/user/share/dotnet/shared/{runtime-type}/{version}/_</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="95886-136">**eseguibile DotNet**</span><span class="sxs-lookup"><span data-stu-id="95886-136">**dotnet executable**</span></span>\
<span data-ttu-id="95886-137">_/usr/local/share/dotnet/dotnet_</span><span class="sxs-lookup"><span data-stu-id="95886-137">_/usr/local/share/dotnet/dotnet_</span></span>

- <span data-ttu-id="95886-138">**.NET SDK**</span><span class="sxs-lookup"><span data-stu-id="95886-138">**.NET SDK**</span></span>\
<span data-ttu-id="95886-139">_/usr/local/share/dotnet/sdk/{version}/_</span><span class="sxs-lookup"><span data-stu-id="95886-139">_/usr/local/share/dotnet/sdk/{version}/_</span></span>

- <span data-ttu-id="95886-140">**Runtime .NET**</span><span class="sxs-lookup"><span data-stu-id="95886-140">**.NET Runtime**</span></span>\
<span data-ttu-id="95886-141">_/usr/local/share/dotnet/shared/{runtime-type}/{version}/_</span><span class="sxs-lookup"><span data-stu-id="95886-141">_/usr/local/share/dotnet/shared/{runtime-type}/{version}/_</span></span>

::: zone-end

## <a name="more-information"></a><span data-ttu-id="95886-142">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="95886-142">More information</span></span>

<span data-ttu-id="95886-143">È possibile visualizzare sia le versioni dell'SDK che le versioni di runtime con il comando `dotnet --info` .</span><span class="sxs-lookup"><span data-stu-id="95886-143">You can see both the SDK versions and runtime versions with the command `dotnet --info`.</span></span> <span data-ttu-id="95886-144">Si otterranno anche altre informazioni relative all'ambiente, ad esempio la versione del sistema operativo e l'identificatore di runtime (RID).</span><span class="sxs-lookup"><span data-stu-id="95886-144">You'll also get other environmental related information, such as the operating system version and runtime identifier (RID).</span></span>

## <a name="next-steps"></a><span data-ttu-id="95886-145">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="95886-145">Next steps</span></span>

- <span data-ttu-id="95886-146">[Installare il runtime di .NET Core](runtime.md).</span><span class="sxs-lookup"><span data-stu-id="95886-146">[Install the .NET Core Runtime](runtime.md).</span></span>
- <span data-ttu-id="95886-147">[Installare il .NET Core SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="95886-147">[Install the .NET Core SDK](sdk.md).</span></span>
