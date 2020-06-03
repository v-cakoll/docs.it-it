---
title: Comando dotnet list package
description: Il comando "dotnet list package" offre un'opzione utile per visualizzare un elenco dei riferimenti al pacchetto per un progetto o una soluzione.
ms.date: 02/14/2020
ms.openlocfilehash: 12d64600d178ea8cf490a0d6917e67bd3d8c6d21
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463668"
---
# <a name="dotnet-list-package"></a><span data-ttu-id="3717c-103">dotnet list package</span><span class="sxs-lookup"><span data-stu-id="3717c-103">dotnet list package</span></span>

<span data-ttu-id="3717c-104">**Questo articolo si applica a:** ✔️ .net core 2,2 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="3717c-104">**This article applies to:** ✔️ .NET Core 2.2 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="3717c-105">Nome</span><span class="sxs-lookup"><span data-stu-id="3717c-105">Name</span></span>

<span data-ttu-id="3717c-106">`dotnet list package`: elenca i riferimenti al pacchetto per un progetto o una soluzione.</span><span class="sxs-lookup"><span data-stu-id="3717c-106">`dotnet list package` - Lists the package references for a project or solution.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3717c-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3717c-107">Synopsis</span></span>

```dotnetcli
dotnet list [<PROJECT>|<SOLUTION>] package [--config <SOURCE>]
    [--framework <FRAMEWORK>] [--highest-minor] [--highest-patch]
    [--include-prerelease] [--include-transitive] [--interactive]
    [--outdated] [--source <SOURCE>]

dotnet list package -h|--help
```

## <a name="description"></a><span data-ttu-id="3717c-108">Description</span><span class="sxs-lookup"><span data-stu-id="3717c-108">Description</span></span>

<span data-ttu-id="3717c-109">Il comando `dotnet list package` offre un'opzione utile per visualizzare un elenco di tutti i riferimenti al pacchetto NuGet per un progetto o una soluzione specifica.</span><span class="sxs-lookup"><span data-stu-id="3717c-109">The `dotnet list package` command provides a convenient option to list all NuGet package references for a specific project or a solution.</span></span> <span data-ttu-id="3717c-110">Occorre prima di tutto compilare il progetto in modo da avere le risorse che il comando dovrà elaborare.</span><span class="sxs-lookup"><span data-stu-id="3717c-110">You first need to build the project in order to have the assets needed for this command to process.</span></span> <span data-ttu-id="3717c-111">L'esempio seguente mostra l'output del comando `dotnet list package` per il progetto [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis):</span><span class="sxs-lookup"><span data-stu-id="3717c-111">The following example shows the output of the `dotnet list package` command for the [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) project:</span></span>

```output
Project 'SentimentAnalysis' has the following package references
   [netcoreapp2.1]:
   Top-level Package               Requested   Resolved
   > Microsoft.ML                  1.4.0       1.4.0
   > Microsoft.NETCore.App   (A)   [2.1.0, )   2.1.0

(A) : Auto-referenced package.
```

<span data-ttu-id="3717c-112">La colonna **Requested** si riferisce alla versione del pacchetto specificata nel file di progetto e può essere un intervallo.</span><span class="sxs-lookup"><span data-stu-id="3717c-112">The **Requested** column refers to the package version specified in the project file and can be a range.</span></span> <span data-ttu-id="3717c-113">La colonna **Resolved** indica la versione attualmente usata dal progetto ed è sempre un valore singolo.</span><span class="sxs-lookup"><span data-stu-id="3717c-113">The **Resolved** column lists the version that the project is currently using and is always a single value.</span></span> <span data-ttu-id="3717c-114">I pacchetti contrassegnati da una `(A)` accanto al nome rappresentano [riferimenti impliciti al pacchetto](csproj.md#implicit-package-references) derivati dalle impostazioni del progetto (tipo `Sdk`, proprietà `<TargetFramework>` o `<TargetFrameworks>` e così via).</span><span class="sxs-lookup"><span data-stu-id="3717c-114">The packages displaying an `(A)` right next to their names represent [implicit package references](csproj.md#implicit-package-references) that are inferred from your project settings (`Sdk` type, `<TargetFramework>` or `<TargetFrameworks>` property, etc.)</span></span>

<span data-ttu-id="3717c-115">Usare l'opzione `--outdated` per determinare se sono disponibili versioni più recenti dei pacchetti usati nei progetti.</span><span class="sxs-lookup"><span data-stu-id="3717c-115">Use the `--outdated` option to find out if there are newer versions available of the packages you're using in your projects.</span></span> <span data-ttu-id="3717c-116">Per impostazione predefinita, `--outdated` elenca i pacchetti stabili più recenti, a meno che anche la versione risolta non sia una versione non definitiva.</span><span class="sxs-lookup"><span data-stu-id="3717c-116">By default, `--outdated` lists the latest stable packages unless the resolved version is also a prerelease version.</span></span> <span data-ttu-id="3717c-117">Per includere le versioni non definitive nell'elenco delle versioni più recenti, specificare anche l'opzione `--include-prerelease`.</span><span class="sxs-lookup"><span data-stu-id="3717c-117">To include prerelease versions when listing newer versions, also specify the `--include-prerelease` option.</span></span> <span data-ttu-id="3717c-118">Gli esempi seguenti mostrano l'output del comando `dotnet list package --outdated --include-prerelease` per lo stesso progetto dell'esempio precedente:</span><span class="sxs-lookup"><span data-stu-id="3717c-118">The following examples shows the output of the `dotnet list package --outdated --include-prerelease` command for the same project as the previous example:</span></span>

```output
The following sources were used:
   https://api.nuget.org/v3/index.json
   C:\Program Files (x86)\Microsoft SDKs\NuGetPackages\

Project `SentimentAnalysis` has the following updates to its packages
   [netcoreapp2.1]:
   Top-level Package      Requested   Resolved   Latest
   > Microsoft.ML         1.4.0       1.4.0      1.5.0-preview
```

<span data-ttu-id="3717c-119">Se occorre verificare se il progetto ha dipendenze transitive, usare l'opzione `--include-transitive`.</span><span class="sxs-lookup"><span data-stu-id="3717c-119">If you need to find out whether your project has transitive dependencies, use the `--include-transitive` option.</span></span> <span data-ttu-id="3717c-120">Le dipendenze transitive si hanno quando si aggiunge al progetto un pacchetto che a sua volta si basa su un altro pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3717c-120">Transitive dependencies occur when you add a package to your project that in turn relies on another package.</span></span> <span data-ttu-id="3717c-121">L'esempio seguente mostra l'output dell'esecuzione del comando `dotnet list package --include-transitive` per il progetto [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin), che mostra i pacchetti di primo livello e i pacchetti da cui dipendono:</span><span class="sxs-lookup"><span data-stu-id="3717c-121">The following example shows the output from running the `dotnet list package --include-transitive` command for the [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin) project, which displays top-level packages and the packages they depend on:</span></span>

```output
Project 'HelloPlugin' has the following package references
   [netcoreapp3.0]:
   Transitive Package      Resolved
   > PluginBase            1.0.0
```

## <a name="arguments"></a><span data-ttu-id="3717c-122">Arguments</span><span class="sxs-lookup"><span data-stu-id="3717c-122">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="3717c-123">File di progetto o di soluzione su cui eseguire le operazioni.</span><span class="sxs-lookup"><span data-stu-id="3717c-123">The project or solution file to operate on.</span></span> <span data-ttu-id="3717c-124">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="3717c-124">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="3717c-125">Se vengono trovati più progetti o soluzioni, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="3717c-125">If more than one solution or project is found, an error is thrown.</span></span>

## <a name="options"></a><span data-ttu-id="3717c-126">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3717c-126">Options</span></span>

- **`--config <SOURCE>`**

  <span data-ttu-id="3717c-127">Origini NuGet da usare per cercare i pacchetti più recenti.</span><span class="sxs-lookup"><span data-stu-id="3717c-127">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="3717c-128">Richiede l'opzione `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="3717c-128">Requires the `--outdated` option.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="3717c-129">Visualizza solo i pacchetti validi per il [framework di destinazione](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="3717c-129">Displays only the packages applicable for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="3717c-130">Per specificare più framework, ripetere l'opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="3717c-130">To specify multiple frameworks, repeat the option multiple times.</span></span> <span data-ttu-id="3717c-131">Ad esempio: `--framework netcoreapp2.2 --framework netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="3717c-131">For example: `--framework netcoreapp2.2 --framework netstandard2.0`.</span></span>

- **`-h|--help`**

  <span data-ttu-id="3717c-132">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="3717c-132">Prints out a short help for the command.</span></span>

- **`--highest-minor`**

  <span data-ttu-id="3717c-133">Prende in considerazione solo i pacchetti con il numero di versione principale corrispondente quando si cercano i pacchetti più recenti.</span><span class="sxs-lookup"><span data-stu-id="3717c-133">Considers only the packages with a matching major version number when searching for newer packages.</span></span> <span data-ttu-id="3717c-134">Richiede l'opzione `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="3717c-134">Requires the `--outdated` option.</span></span>

- **`--highest-patch`**

  <span data-ttu-id="3717c-135">Prende in considerazione solo i pacchetti con i numeri di versione principale e secondaria corrispondenti quando si cercano i pacchetti più recenti.</span><span class="sxs-lookup"><span data-stu-id="3717c-135">Considers only the packages with a matching major and minor version numbers when searching for newer packages.</span></span> <span data-ttu-id="3717c-136">Richiede l'opzione `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="3717c-136">Requires the `--outdated` option.</span></span>

- **`--include-prerelease`**

  <span data-ttu-id="3717c-137">Prende in considerazione i pacchetti con versioni non definitive quando si cercano i pacchetti più recenti.</span><span class="sxs-lookup"><span data-stu-id="3717c-137">Considers packages with prerelease versions when searching for newer packages.</span></span> <span data-ttu-id="3717c-138">Richiede l'opzione `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="3717c-138">Requires the `--outdated` option.</span></span>

- **`--include-transitive`**

  <span data-ttu-id="3717c-139">Elenca i pacchetti transitivi, oltre ai pacchetti di primo livello.</span><span class="sxs-lookup"><span data-stu-id="3717c-139">Lists transitive packages, in addition to the top-level packages.</span></span> <span data-ttu-id="3717c-140">Quando si specifica questa opzione, si ottiene un elenco di pacchetti da cui dipendono i pacchetti di primo livello.</span><span class="sxs-lookup"><span data-stu-id="3717c-140">When specifying this option, you get a list of packages that the top-level packages depend on.</span></span>

- **`--interactive`**

  <span data-ttu-id="3717c-141">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente,</span><span class="sxs-lookup"><span data-stu-id="3717c-141">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="3717c-142">ad esempio il completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="3717c-142">For example, to complete authentication.</span></span> <span data-ttu-id="3717c-143">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="3717c-143">Available since .NET Core 3.0 SDK.</span></span>

- **`--outdated`**

  <span data-ttu-id="3717c-144">Elenca i pacchetti per cui sono disponibili versioni più recenti.</span><span class="sxs-lookup"><span data-stu-id="3717c-144">Lists packages that have newer versions available.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="3717c-145">Origini NuGet da usare per cercare i pacchetti più recenti.</span><span class="sxs-lookup"><span data-stu-id="3717c-145">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="3717c-146">Richiede l'opzione `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="3717c-146">Requires the `--outdated` option.</span></span>

## <a name="examples"></a><span data-ttu-id="3717c-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="3717c-147">Examples</span></span>

- <span data-ttu-id="3717c-148">Elencare i riferimenti al pacchetto di un progetto specifico:</span><span class="sxs-lookup"><span data-stu-id="3717c-148">List package references of a specific project:</span></span>

  ```dotnetcli
  dotnet list SentimentAnalysis.csproj package
  ```

- <span data-ttu-id="3717c-149">Elencare i riferimenti al pacchetto per cui sono disponibili versioni più recenti, incluse le versioni non definitive:</span><span class="sxs-lookup"><span data-stu-id="3717c-149">List package references that have newer versions available, including prerelease versions:</span></span>

  ```dotnetcli
  dotnet list package --outdated --include-prerelease
  ```

- <span data-ttu-id="3717c-150">Elencare i riferimenti al pacchetto per un framework di destinazione specifico:</span><span class="sxs-lookup"><span data-stu-id="3717c-150">List package references for a specific target framework:</span></span>

  ```dotnetcli
  dotnet list package --framework netcoreapp3.0
  ```
