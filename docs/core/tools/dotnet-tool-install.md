---
title: Comando dotnet tool install
description: Il comando dotnet tool install installa lo strumento .NET Core specificato nel computer.
ms.date: 02/14/2020
ms.openlocfilehash: 1e142773d1f981a8dc3b552d5a23d2864cdd82c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146463"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="5d8c4-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="5d8c4-103">dotnet tool install</span></span>

<span data-ttu-id="5d8c4-104">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="5d8c4-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="5d8c4-105">Nome</span><span class="sxs-lookup"><span data-stu-id="5d8c4-105">Name</span></span>

<span data-ttu-id="5d8c4-106">`dotnet tool install`- Installa lo strumento .NET Core specificato nel computer.- Installs the specified [.NET Core tool](global-tools.md) on your machine.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-106">`dotnet tool install` - Installs the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5d8c4-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="5d8c4-107">Synopsis</span></span>

```dotnetcli
dotnet tool install <PACKAGE_NAME> <-g|--global>
    [--add-source] [--configfile] [--framework]
    [-v|--verbosity] [--version]

dotnet tool install <PACKAGE_NAME> <--tool-path>
    [--add-source] [--configfile] [--framework]
    [-v|--verbosity] [--version]

dotnet tool install <PACKAGE_NAME>
    [--add-source] [--configfile] [--framework]
    [-v|--verbosity] [--version]

dotnet tool install <-h|--help>
```

## <a name="description"></a><span data-ttu-id="5d8c4-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d8c4-108">Description</span></span>

<span data-ttu-id="5d8c4-109">Il `dotnet tool install` comando consente di installare gli strumenti .NET Core nel computer.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-109">The `dotnet tool install` command provides a way for you to install .NET Core tools on your machine.</span></span> <span data-ttu-id="5d8c4-110">Per utilizzare il comando, specificare una delle seguenti opzioni di installazione:</span><span class="sxs-lookup"><span data-stu-id="5d8c4-110">To use the command, you specify one of the following installation options:</span></span>

* <span data-ttu-id="5d8c4-111">Per installare uno strumento globale nel `--global` percorso predefinito, utilizzare l'opzione .</span><span class="sxs-lookup"><span data-stu-id="5d8c4-111">To install a global tool in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="5d8c4-112">Per installare uno strumento globale in `--tool-path` un percorso personalizzato, utilizzare l'opzione .</span><span class="sxs-lookup"><span data-stu-id="5d8c4-112">To install a global tool in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="5d8c4-113">Per installare uno strumento locale, `--global` `--tool-path` omettere le opzioni e .</span><span class="sxs-lookup"><span data-stu-id="5d8c4-113">To install a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="5d8c4-114">**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3.0.**</span><span class="sxs-lookup"><span data-stu-id="5d8c4-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

<span data-ttu-id="5d8c4-115">Gli strumenti globali vengono installati nelle seguenti `-g` directory `--global` per impostazione predefinita quando si specifica l'opzione o :</span><span class="sxs-lookup"><span data-stu-id="5d8c4-115">Global tools are installed in the following directories by default when you specify the `-g` or `--global` option:</span></span>

| <span data-ttu-id="5d8c4-116">OS</span><span class="sxs-lookup"><span data-stu-id="5d8c4-116">OS</span></span>          | <span data-ttu-id="5d8c4-117">Path</span><span class="sxs-lookup"><span data-stu-id="5d8c4-117">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="5d8c4-118">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="5d8c4-118">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="5d8c4-119">Windows</span><span class="sxs-lookup"><span data-stu-id="5d8c4-119">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="5d8c4-120">Gli strumenti locali vengono aggiunti a un file *tool-manifest.json* in una directory *.config* nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-120">Local tools are added to a *tool-manifest.json* file in a *.config* directory under the current directory.</span></span> <span data-ttu-id="5d8c4-121">Se non esiste ancora un file manifesto, crearlo eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5d8c4-121">If a manifest file doesn't exist yet, create it by running the following command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="5d8c4-122">Per ulteriori informazioni, consultate [Installare uno strumento locale.](global-tools.md#install-a-local-tool)</span><span class="sxs-lookup"><span data-stu-id="5d8c4-122">For more information, see [Install a local tool](global-tools.md#install-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="5d8c4-123">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5d8c4-123">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="5d8c4-124">Nome/ID del pacchetto NuGet che contiene lo strumento .NET Core da installare.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-124">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="5d8c4-125">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5d8c4-125">Options</span></span>

- **`add-source <SOURCE>`**

  <span data-ttu-id="5d8c4-126">Aggiunge un'altra origine pacchetto NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-126">Adds an additional NuGet package source to use during installation.</span></span>

- **`configfile <FILE>`**

  <span data-ttu-id="5d8c4-127">File di configurazione NuGet (*nuget.config*) da usare.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-127">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`framework <FRAMEWORK>`**

  <span data-ttu-id="5d8c4-128">Specifica il [framework di destinazione](../../standard/frameworks.md) per cui installare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-128">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="5d8c4-129">Per impostazione predefinita, .NET Core SDK tenta di scegliere il framework di destinazione più appropriato.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-129">By default, the .NET Core SDK tries to choose the most appropriate target framework.</span></span>

- **`-g|--global`**

  <span data-ttu-id="5d8c4-130">Specifica che l'installazione è a livello utente.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-130">Specifies that the installation is user wide.</span></span> <span data-ttu-id="5d8c4-131">Non può essere usata con l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-131">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="5d8c4-132">Omettendo `--global` entrambi `--tool-path` e specifica un'installazione dello strumento locale.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-132">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-h|--help`**

  <span data-ttu-id="5d8c4-133">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-133">Prints out a short help for the command.</span></span>

- **`tool-path <PATH>`**

  <span data-ttu-id="5d8c4-134">Specifica il percorso in cui disinstallare lo strumento globale.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-134">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="5d8c4-135">Il valore di PATH può essere assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-135">PATH can be absolute or relative.</span></span> <span data-ttu-id="5d8c4-136">Se PATH non esiste, il comando tenta di creare la variabile.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-136">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="5d8c4-137">Omettendo `--global` entrambi `--tool-path` e specifica un'installazione dello strumento locale.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-137">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="5d8c4-138">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5d8c4-139">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`--version <VERSION_NUMBER>`**

  <span data-ttu-id="5d8c4-140">La versione dello strumento da installare.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-140">The version of the tool to install.</span></span> <span data-ttu-id="5d8c4-141">Per impostazione predefinita, viene installata la versione del pacchetto stabile più recente.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-141">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="5d8c4-142">Usare questa opzione per installare le versioni di anteprima o precedenti dello strumento.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-142">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="5d8c4-143">Esempi</span><span class="sxs-lookup"><span data-stu-id="5d8c4-143">Examples</span></span>

- **`dotnet tool install -g dotnetsay`**

  <span data-ttu-id="5d8c4-144">Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-144">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in the default location.</span></span>

- **`dotnet tool install dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="5d8c4-145">Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale in una directory di Windows specifica.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-145">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Windows directory.</span></span>

- **`dotnet tool install dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="5d8c4-146">Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale in una directory Linux/macOS specifica.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-146">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Linux/macOS directory.</span></span>

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  <span data-ttu-id="5d8c4-147">Installa la versione 2.0.0 di [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-147">Installs version 2.0.0 of [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool.</span></span>

- **`dotnet tool install dotnetsay`**

  <span data-ttu-id="5d8c4-148">Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento locale per la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="5d8c4-148">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a local tool for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d8c4-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d8c4-149">See also</span></span>

- [<span data-ttu-id="5d8c4-150">Strumenti .NET Core</span><span class="sxs-lookup"><span data-stu-id="5d8c4-150">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="5d8c4-151">Esercitazione: Installare e usare uno strumento globale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core global tool using the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="5d8c4-151">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="5d8c4-152">Esercitazione: Installare e usare uno strumento locale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core local tool using the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="5d8c4-152">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
