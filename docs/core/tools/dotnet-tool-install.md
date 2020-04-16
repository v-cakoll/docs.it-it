---
title: Comando dotnet tool install
description: Il comando dotnet tool install installa lo strumento .NET Core specificato nel computer.
ms.date: 02/14/2020
ms.openlocfilehash: 723d25caa6009288dbb55d55f173b04d7b983450
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463368"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="1df59-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="1df59-103">dotnet tool install</span></span>

<span data-ttu-id="1df59-104">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1df59-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="1df59-105">Nome</span><span class="sxs-lookup"><span data-stu-id="1df59-105">Name</span></span>

<span data-ttu-id="1df59-106">`dotnet tool install`- Installa lo strumento .NET Core specificato nel computer.- Installs the specified [.NET Core tool](global-tools.md) on your machine.</span><span class="sxs-lookup"><span data-stu-id="1df59-106">`dotnet tool install` - Installs the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1df59-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="1df59-107">Synopsis</span></span>

```dotnetcli
dotnet tool install <PACKAGE_NAME> -g|--global
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install <PACKAGE_NAME> --tool-path <PATH>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install <PACKAGE_NAME>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install -h|--help
```

## <a name="description"></a><span data-ttu-id="1df59-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1df59-108">Description</span></span>

<span data-ttu-id="1df59-109">Il `dotnet tool install` comando consente di installare gli strumenti .NET Core nel computer.</span><span class="sxs-lookup"><span data-stu-id="1df59-109">The `dotnet tool install` command provides a way for you to install .NET Core tools on your machine.</span></span> <span data-ttu-id="1df59-110">Per utilizzare il comando, specificare una delle seguenti opzioni di installazione:</span><span class="sxs-lookup"><span data-stu-id="1df59-110">To use the command, you specify one of the following installation options:</span></span>

* <span data-ttu-id="1df59-111">Per installare uno strumento globale nel `--global` percorso predefinito, utilizzare l'opzione .</span><span class="sxs-lookup"><span data-stu-id="1df59-111">To install a global tool in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="1df59-112">Per installare uno strumento globale in `--tool-path` un percorso personalizzato, utilizzare l'opzione .</span><span class="sxs-lookup"><span data-stu-id="1df59-112">To install a global tool in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="1df59-113">Per installare uno strumento locale, `--global` `--tool-path` omettere le opzioni e .</span><span class="sxs-lookup"><span data-stu-id="1df59-113">To install a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="1df59-114">**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3.0.**</span><span class="sxs-lookup"><span data-stu-id="1df59-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

<span data-ttu-id="1df59-115">Gli strumenti globali vengono installati nelle seguenti `-g` directory `--global` per impostazione predefinita quando si specifica l'opzione o :</span><span class="sxs-lookup"><span data-stu-id="1df59-115">Global tools are installed in the following directories by default when you specify the `-g` or `--global` option:</span></span>

| <span data-ttu-id="1df59-116">OS</span><span class="sxs-lookup"><span data-stu-id="1df59-116">OS</span></span>          | <span data-ttu-id="1df59-117">Path</span><span class="sxs-lookup"><span data-stu-id="1df59-117">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="1df59-118">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="1df59-118">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="1df59-119">Windows</span><span class="sxs-lookup"><span data-stu-id="1df59-119">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="1df59-120">Gli strumenti locali vengono aggiunti a un file *tool-manifest.json* in una directory *.config* nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="1df59-120">Local tools are added to a *tool-manifest.json* file in a *.config* directory under the current directory.</span></span> <span data-ttu-id="1df59-121">Se non esiste ancora un file manifesto, crearlo eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1df59-121">If a manifest file doesn't exist yet, create it by running the following command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="1df59-122">Per ulteriori informazioni, consultate [Installare uno strumento locale.](global-tools.md#install-a-local-tool)</span><span class="sxs-lookup"><span data-stu-id="1df59-122">For more information, see [Install a local tool](global-tools.md#install-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="1df59-123">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1df59-123">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="1df59-124">Nome/ID del pacchetto NuGet che contiene lo strumento .NET Core da installare.</span><span class="sxs-lookup"><span data-stu-id="1df59-124">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="1df59-125">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1df59-125">Options</span></span>

- **`add-source <SOURCE>`**

  <span data-ttu-id="1df59-126">Aggiunge un'altra origine pacchetto NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="1df59-126">Adds an additional NuGet package source to use during installation.</span></span>

- **`configfile <FILE>`**

  <span data-ttu-id="1df59-127">File di configurazione NuGet (*nuget.config*) da usare.</span><span class="sxs-lookup"><span data-stu-id="1df59-127">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`framework <FRAMEWORK>`**

  <span data-ttu-id="1df59-128">Specifica il [framework di destinazione](../../standard/frameworks.md) per cui installare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="1df59-128">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="1df59-129">Per impostazione predefinita, .NET Core SDK tenta di scegliere il framework di destinazione più appropriato.</span><span class="sxs-lookup"><span data-stu-id="1df59-129">By default, the .NET Core SDK tries to choose the most appropriate target framework.</span></span>

- **`-g|--global`**

  <span data-ttu-id="1df59-130">Specifica che l'installazione è a livello utente.</span><span class="sxs-lookup"><span data-stu-id="1df59-130">Specifies that the installation is user wide.</span></span> <span data-ttu-id="1df59-131">Non può essere usata con l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="1df59-131">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="1df59-132">Omettendo `--global` entrambi `--tool-path` e specifica un'installazione dello strumento locale.</span><span class="sxs-lookup"><span data-stu-id="1df59-132">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-h|--help`**

  <span data-ttu-id="1df59-133">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="1df59-133">Prints out a short help for the command.</span></span>

- **`tool-path <PATH>`**

  <span data-ttu-id="1df59-134">Specifica il percorso in cui disinstallare lo strumento globale.</span><span class="sxs-lookup"><span data-stu-id="1df59-134">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="1df59-135">Il valore di PATH può essere assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="1df59-135">PATH can be absolute or relative.</span></span> <span data-ttu-id="1df59-136">Se PATH non esiste, il comando tenta di creare la variabile.</span><span class="sxs-lookup"><span data-stu-id="1df59-136">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="1df59-137">Omettendo `--global` entrambi `--tool-path` e specifica un'installazione dello strumento locale.</span><span class="sxs-lookup"><span data-stu-id="1df59-137">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="1df59-138">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="1df59-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1df59-139">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="1df59-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`--version <VERSION_NUMBER>`**

  <span data-ttu-id="1df59-140">La versione dello strumento da installare.</span><span class="sxs-lookup"><span data-stu-id="1df59-140">The version of the tool to install.</span></span> <span data-ttu-id="1df59-141">Per impostazione predefinita, viene installata la versione del pacchetto stabile più recente.</span><span class="sxs-lookup"><span data-stu-id="1df59-141">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="1df59-142">Usare questa opzione per installare le versioni di anteprima o precedenti dello strumento.</span><span class="sxs-lookup"><span data-stu-id="1df59-142">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="1df59-143">Esempi</span><span class="sxs-lookup"><span data-stu-id="1df59-143">Examples</span></span>

- **`dotnet tool install -g dotnetsay`**

  <span data-ttu-id="1df59-144">Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="1df59-144">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in the default location.</span></span>

- **`dotnet tool install dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="1df59-145">Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale in una directory di Windows specifica.</span><span class="sxs-lookup"><span data-stu-id="1df59-145">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Windows directory.</span></span>

- **`dotnet tool install dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="1df59-146">Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale in una directory Linux/macOS specifica.</span><span class="sxs-lookup"><span data-stu-id="1df59-146">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Linux/macOS directory.</span></span>

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  <span data-ttu-id="1df59-147">Installa la versione 2.0.0 di [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale.</span><span class="sxs-lookup"><span data-stu-id="1df59-147">Installs version 2.0.0 of [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool.</span></span>

- **`dotnet tool install dotnetsay`**

  <span data-ttu-id="1df59-148">Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento locale per la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="1df59-148">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a local tool for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="1df59-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1df59-149">See also</span></span>

- [<span data-ttu-id="1df59-150">Strumenti .NET Core</span><span class="sxs-lookup"><span data-stu-id="1df59-150">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="1df59-151">Esercitazione: Installare e usare uno strumento globale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core global tool using the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="1df59-151">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="1df59-152">Esercitazione: Installare e usare uno strumento locale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core local tool using the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="1df59-152">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
