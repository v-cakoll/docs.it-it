---
title: Comando dotnet tool update
description: Il comando DotNet Tool Update aggiorna lo strumento .NET Core specificato nel computer.
ms.date: 07/08/2020
ms.openlocfilehash: a212fbb40af68019c1bc9a63963d960292be6b08
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86308871"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="f8ab8-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="f8ab8-103">dotnet tool update</span></span>

<span data-ttu-id="f8ab8-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="f8ab8-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="f8ab8-105">Nome</span><span class="sxs-lookup"><span data-stu-id="f8ab8-105">Name</span></span>

<span data-ttu-id="f8ab8-106">`dotnet tool update`: Aggiorna lo [strumento .NET Core](global-tools.md) specificato nel computer.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-106">`dotnet tool update` - Updates the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f8ab8-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="f8ab8-107">Synopsis</span></span>

```dotnetcli
dotnet tool update <PACKAGE_ID> -g|--global
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --tool-path <PATH>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --local
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [--tool-manifest <PATH>]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update -h|--help
```

## <a name="description"></a><span data-ttu-id="f8ab8-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8ab8-108">Description</span></span>

<span data-ttu-id="f8ab8-109">Il `dotnet tool update` comando fornisce un modo per aggiornare gli strumenti di .NET Core nel computer alla versione stabile più recente del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-109">The `dotnet tool update` command provides a way for you to update .NET Core tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="f8ab8-110">Il comando disinstalla e reinstalla uno strumento aggiornandolo.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-110">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="f8ab8-111">Per utilizzare il comando, è necessario specificare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8ab8-111">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="f8ab8-112">Per aggiornare uno strumento globale che è stato installato nel percorso predefinito, usare l' `--global` opzione</span><span class="sxs-lookup"><span data-stu-id="f8ab8-112">To update a global tool that was installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="f8ab8-113">Per aggiornare uno strumento globale installato in un percorso personalizzato, utilizzare l' `--tool-path` opzione.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-113">To update a global tool that was installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="f8ab8-114">Per aggiornare uno strumento locale, utilizzare l' `--local` opzione.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-114">To update a local tool, use the `--local` option.</span></span>

<span data-ttu-id="f8ab8-115">**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0.**</span><span class="sxs-lookup"><span data-stu-id="f8ab8-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="f8ab8-116">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f8ab8-116">Arguments</span></span>

- **`PACKAGE_ID`**

  <span data-ttu-id="f8ab8-117">Nome/ID del pacchetto NuGet che contiene lo strumento globale .NET Core da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-117">Name/ID of the NuGet package that contains the .NET Core global tool to update.</span></span> <span data-ttu-id="f8ab8-118">È possibile trovare il nome del pacchetto usando il comando [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="f8ab8-118">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="f8ab8-119">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f8ab8-119">Options</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="f8ab8-120">Aggiunge un'altra origine pacchetto NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-120">Adds an additional NuGet package source to use during installation.</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="f8ab8-121">File di configurazione NuGet (*nuget.config*) da usare.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-121">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="f8ab8-122">Impedisci il ripristino di più progetti in parallelo.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-122">Prevent restoring multiple projects in parallel.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="f8ab8-123">Specifica il [framework di destinazione](../../standard/frameworks.md) per cui aggiornare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-123">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="f8ab8-124">Considera gli errori di origine del pacchetto come avvisi.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-124">Treat package source failures as warnings.</span></span>

- **`--interactive`**

  <span data-ttu-id="f8ab8-125">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione).</span><span class="sxs-lookup"><span data-stu-id="f8ab8-125">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`--local`**

  <span data-ttu-id="f8ab8-126">Aggiornare lo strumento e il manifesto dello strumento locale.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-126">Update the tool and the local tool manifest.</span></span> <span data-ttu-id="f8ab8-127">Non può essere combinato con l' `--global` opzione o `--tool-path` .</span><span class="sxs-lookup"><span data-stu-id="f8ab8-127">Can't be combined with the `--global` option or the `--tool-path` option.</span></span>

- **`--no-cache`**

  <span data-ttu-id="f8ab8-128">Non memorizzare nella cache pacchetti e richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-128">Do not cache packages and HTTP requests.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="f8ab8-129">Percorso del file manifesto.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-129">Path to the manifest file.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="f8ab8-130">Specifica il percorso in cui è installato lo strumento globale.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-130">Specifies the location where the global tool is installed.</span></span> <span data-ttu-id="f8ab8-131">Il valore di PATH può essere assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-131">PATH can be absolute or relative.</span></span> <span data-ttu-id="f8ab8-132">Non può essere usata con l'opzione `--global`.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-132">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="f8ab8-133">`--global`Se si omette e `--tool-path` si specifica che lo strumento da aggiornare è uno strumento locale.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-133">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`--version <VERSION>`**

  <span data-ttu-id="f8ab8-134">Intervallo di versioni del pacchetto di strumenti in cui eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-134">The version range of the tool package to update to.</span></span> <span data-ttu-id="f8ab8-135">Questa operazione non può essere usata per eseguire il downgrade delle versioni. è necessario `uninstall` prima di tutto le versioni più recenti.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-135">This cannot be used to downgrade versions, you must `uninstall` newer versions first.</span></span>

- **`-g|--global`**

  <span data-ttu-id="f8ab8-136">Specifica che l'aggiornamento è per uno strumento a livello utente.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-136">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="f8ab8-137">Non può essere usata con l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-137">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="f8ab8-138">`--global`Se si omette e `--tool-path` si specifica che lo strumento da aggiornare è uno strumento locale.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-138">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`-h|--help`**

  <span data-ttu-id="f8ab8-139">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-139">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="f8ab8-140">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f8ab8-141">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="f8ab8-142">Esempi</span><span class="sxs-lookup"><span data-stu-id="f8ab8-142">Examples</span></span>

- **`dotnet tool update -g dotnetsay`**

  <span data-ttu-id="f8ab8-143">Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) .</span><span class="sxs-lookup"><span data-stu-id="f8ab8-143">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="f8ab8-144">Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) che si trova in una directory di Windows specifica.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-144">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Windows directory.</span></span>

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="f8ab8-145">Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) che si trova in una directory Linux/MacOS specifica.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-145">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Linux/macOS directory.</span></span>

- **`dotnet tool update dotnetsay`**

  <span data-ttu-id="f8ab8-146">Aggiorna lo strumento locale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) installato per la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-146">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool installed for the current directory.</span></span>

- **`dotnet tool update -g dotnetsay --version 2.0.*`**

  <span data-ttu-id="f8ab8-147">Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) alla versione più recente della patch, con una versione principale di `2` e una versione secondaria di `0` .</span><span class="sxs-lookup"><span data-stu-id="f8ab8-147">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool to the latest patch version, with a major version of `2`, and a minor version of `0`.</span></span>

- **`dotnet tool update -g dotnetsay --version (2.0.*,2.1.4)`**

  <span data-ttu-id="f8ab8-148">Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) alla versione più bassa nell'intervallo specificato `(> 2.0.0 && < 2.1.4)` `2.1.0` . verrà installata la versione.</span><span class="sxs-lookup"><span data-stu-id="f8ab8-148">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool to the lowest version within the specified range `(> 2.0.0 && < 2.1.4)`, version `2.1.0` would be installed.</span></span> <span data-ttu-id="f8ab8-149">Per altre informazioni sugli intervalli di controllo delle versioni semantico, vedere [intervalli di versione del pacchetto NuGet](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="f8ab8-149">For more information on semantic versioning ranges, see [NuGet packaging version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span>

## <a name="see-also"></a><span data-ttu-id="f8ab8-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8ab8-150">See also</span></span>

- [<span data-ttu-id="f8ab8-151">Strumenti di .NET Core</span><span class="sxs-lookup"><span data-stu-id="f8ab8-151">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="f8ab8-152">Versionamento Semantico</span><span class="sxs-lookup"><span data-stu-id="f8ab8-152">Semantic versioning</span></span>](https://semver.org)
- [<span data-ttu-id="f8ab8-153">Esercitazione: installare e usare uno strumento globale .NET Core usando il interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="f8ab8-153">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="f8ab8-154">Esercitazione: installare e usare uno strumento locale di .NET Core usando il interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="f8ab8-154">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
