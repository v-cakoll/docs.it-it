---
title: Comando dotnet tool install
description: Il comando DotNet tool install installa lo strumento .NET Core specificato nel computer.
ms.date: 02/14/2020
ms.openlocfilehash: 641e6a2753b1cf3bfc334ba2495342f7c42421fc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156974"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="095ba-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="095ba-103">dotnet tool install</span></span>

<span data-ttu-id="095ba-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="095ba-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="095ba-105">Nome</span><span class="sxs-lookup"><span data-stu-id="095ba-105">Name</span></span>

<span data-ttu-id="095ba-106">`dotnet tool install`: installa lo [strumento .NET Core](global-tools.md) specificato nel computer.</span><span class="sxs-lookup"><span data-stu-id="095ba-106">`dotnet tool install` - Installs the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="095ba-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="095ba-107">Synopsis</span></span>

```dotnetcli
dotnet tool install <PACKAGE_NAME> <-g|--global> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> <--tool-path> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <-h|--help>
```

## <a name="description"></a><span data-ttu-id="095ba-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="095ba-108">Description</span></span>

<span data-ttu-id="095ba-109">Il comando `dotnet tool install` consente di installare gli strumenti di .NET Core nel computer.</span><span class="sxs-lookup"><span data-stu-id="095ba-109">The `dotnet tool install` command provides a way for you to install .NET Core tools on your machine.</span></span> <span data-ttu-id="095ba-110">Per utilizzare il comando, è necessario specificare una delle opzioni di installazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="095ba-110">To use the command, you specify one of the following installation options:</span></span>

* <span data-ttu-id="095ba-111">Per installare uno strumento globale nel percorso predefinito, usare l'opzione `--global`.</span><span class="sxs-lookup"><span data-stu-id="095ba-111">To install a global tool in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="095ba-112">Per installare uno strumento globale in un percorso personalizzato, utilizzare l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="095ba-112">To install a global tool in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="095ba-113">Per installare uno strumento locale, omettere le opzioni `--global` e `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="095ba-113">To install a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="095ba-114">**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0.**</span><span class="sxs-lookup"><span data-stu-id="095ba-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

<span data-ttu-id="095ba-115">Per impostazione predefinita, gli strumenti globali vengono installati nelle directory seguenti quando si specifica l'opzione `-g` o `--global`:</span><span class="sxs-lookup"><span data-stu-id="095ba-115">Global tools are installed in the following directories by default when you specify the `-g` or `--global` option:</span></span>

| <span data-ttu-id="095ba-116">OS</span><span class="sxs-lookup"><span data-stu-id="095ba-116">OS</span></span>          | <span data-ttu-id="095ba-117">Path</span><span class="sxs-lookup"><span data-stu-id="095ba-117">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="095ba-118">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="095ba-118">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="095ba-119">Windows</span><span class="sxs-lookup"><span data-stu-id="095ba-119">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="095ba-120">Gli strumenti locali vengono aggiunti a un file con estensione *JSON dello strumento* in una directory *. config* nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="095ba-120">Local tools are added to a *tool-manifest.json* file in a *.config* directory under the current directory.</span></span> <span data-ttu-id="095ba-121">Se un file manifesto non esiste ancora, crearlo eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="095ba-121">If a manifest file doesn't exist yet, create it by running the following command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="095ba-122">Per ulteriori informazioni, vedere [Install a local Tool](global-tools.md#install-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="095ba-122">For more information, see [Install a local tool](global-tools.md#install-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="095ba-123">Argomenti</span><span class="sxs-lookup"><span data-stu-id="095ba-123">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="095ba-124">Nome/ID del pacchetto NuGet che contiene lo strumento .NET Core da installare.</span><span class="sxs-lookup"><span data-stu-id="095ba-124">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="095ba-125">Opzioni</span><span class="sxs-lookup"><span data-stu-id="095ba-125">Options</span></span>

- **`add-source <SOURCE>`**

  <span data-ttu-id="095ba-126">Aggiunge un'altra origine pacchetto NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="095ba-126">Adds an additional NuGet package source to use during installation.</span></span>

- **`configfile <FILE>`**

  <span data-ttu-id="095ba-127">File di configurazione NuGet (*nuget.config*) da usare.</span><span class="sxs-lookup"><span data-stu-id="095ba-127">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`framework <FRAMEWORK>`**

  <span data-ttu-id="095ba-128">Specifica il [framework di destinazione](../../standard/frameworks.md) per cui installare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="095ba-128">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="095ba-129">Per impostazione predefinita, .NET Core SDK tenta di scegliere il framework di destinazione più appropriato.</span><span class="sxs-lookup"><span data-stu-id="095ba-129">By default, the .NET Core SDK tries to choose the most appropriate target framework.</span></span>

- **`-g|--global`**

  <span data-ttu-id="095ba-130">Specifica che l'installazione è a livello utente.</span><span class="sxs-lookup"><span data-stu-id="095ba-130">Specifies that the installation is user wide.</span></span> <span data-ttu-id="095ba-131">Non può essere usata con l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="095ba-131">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="095ba-132">Omettere sia `--global` che `--tool-path` specifica un'installazione dello strumento locale.</span><span class="sxs-lookup"><span data-stu-id="095ba-132">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-h|--help`**

  <span data-ttu-id="095ba-133">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="095ba-133">Prints out a short help for the command.</span></span>

- **`tool-path <PATH>`**

  <span data-ttu-id="095ba-134">Specifica il percorso in cui disinstallare lo strumento globale.</span><span class="sxs-lookup"><span data-stu-id="095ba-134">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="095ba-135">Il valore di PATH può essere assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="095ba-135">PATH can be absolute or relative.</span></span> <span data-ttu-id="095ba-136">Se PATH non esiste, il comando tenta di creare la variabile.</span><span class="sxs-lookup"><span data-stu-id="095ba-136">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="095ba-137">Omettere sia `--global` che `--tool-path` specifica un'installazione dello strumento locale.</span><span class="sxs-lookup"><span data-stu-id="095ba-137">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="095ba-138">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="095ba-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="095ba-139">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="095ba-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`--version <VERSION_NUMBER>`**

  <span data-ttu-id="095ba-140">La versione dello strumento da installare.</span><span class="sxs-lookup"><span data-stu-id="095ba-140">The version of the tool to install.</span></span> <span data-ttu-id="095ba-141">Per impostazione predefinita, viene installata la versione del pacchetto stabile più recente.</span><span class="sxs-lookup"><span data-stu-id="095ba-141">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="095ba-142">Usare questa opzione per installare le versioni di anteprima o precedenti dello strumento.</span><span class="sxs-lookup"><span data-stu-id="095ba-142">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="095ba-143">Esempi</span><span class="sxs-lookup"><span data-stu-id="095ba-143">Examples</span></span>

- **`dotnet tool install -g dotnetsay`**

  <span data-ttu-id="095ba-144">Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="095ba-144">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in the default location.</span></span>

- **`dotnet tool install dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="095ba-145">Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale in una directory di Windows specifica.</span><span class="sxs-lookup"><span data-stu-id="095ba-145">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Windows directory.</span></span>

- **`dotnet tool install dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="095ba-146">Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale in una directory Linux/MacOS specifica.</span><span class="sxs-lookup"><span data-stu-id="095ba-146">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Linux/macOS directory.</span></span>

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  <span data-ttu-id="095ba-147">Installa la versione 2.0.0 di [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale.</span><span class="sxs-lookup"><span data-stu-id="095ba-147">Installs version 2.0.0 of [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool.</span></span>

- **`dotnet tool install dotnetsay`**

  <span data-ttu-id="095ba-148">Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento locale per la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="095ba-148">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a local tool for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="095ba-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="095ba-149">See also</span></span>

- [<span data-ttu-id="095ba-150">Strumenti di .NET Core</span><span class="sxs-lookup"><span data-stu-id="095ba-150">.NET Core tools</span></span>](global-tools.md)
