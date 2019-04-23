---
title: Comando dotnet list package
description: Il comando "dotnet list package" offre un'opzione utile per visualizzare un elenco dei riferimenti al pacchetto per un progetto o una soluzione.
ms.date: 04/09/2019
ms.openlocfilehash: bc38b94201f85ed4b22e11722ef5cabcb6fbf040
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2019
ms.locfileid: "59481573"
---
# <a name="dotnet-list-package"></a><span data-ttu-id="38a56-103">dotnet list package</span><span class="sxs-lookup"><span data-stu-id="38a56-103">dotnet list package</span></span>

[!INCLUDE [topic-appliesto-net-core-22plus](../../../includes/topic-appliesto-net-core-22plus.md)]

## <a name="name"></a><span data-ttu-id="38a56-104">nome</span><span class="sxs-lookup"><span data-stu-id="38a56-104">Name</span></span>

`dotnet list package` <span data-ttu-id="38a56-105">- Elenca i riferimenti al pacchetto per un progetto o una soluzione.</span><span class="sxs-lookup"><span data-stu-id="38a56-105">- Lists the package references for a project or solution.</span></span>

## <a name="synopsis"></a><span data-ttu-id="38a56-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="38a56-106">Synopsis</span></span>

```
dotnet list [<PROJECT | SOLUTION>] package [--config] [--framework] [--highest-minor] [--highest-patch] 
   [--include-prerelease] [--include-transitive] [--outdated] [--source]
dotnet list package [-h|--help]
```

## <a name="description"></a><span data-ttu-id="38a56-107">Description</span><span class="sxs-lookup"><span data-stu-id="38a56-107">Description</span></span>

<span data-ttu-id="38a56-108">Il comando `dotnet list package` offre un'opzione utile per visualizzare un elenco di tutti i riferimenti al pacchetto NuGet per un progetto o una soluzione specifica.</span><span class="sxs-lookup"><span data-stu-id="38a56-108">The `dotnet list package` command provides a convenient option to list all NuGet package references for a specific project or a solution.</span></span> <span data-ttu-id="38a56-109">Occorre prima di tutto compilare il progetto in modo da avere le risorse che il comando dovrà elaborare.</span><span class="sxs-lookup"><span data-stu-id="38a56-109">You first need to build the project in order to have the assets needed for this command to process.</span></span> <span data-ttu-id="38a56-110">L'esempio seguente mostra l'output del comando `dotnet list package` per il progetto [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis):</span><span class="sxs-lookup"><span data-stu-id="38a56-110">The following example shows the output of the `dotnet list package` command for the [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) project:</span></span>

```output
Project 'SentimentAnalysis' has the following package references
   [netcoreapp2.1]:
   Top-level Package               Requested   Resolved
   > Microsoft.ML                  0.11.0      0.11.0
   > Microsoft.NETCore.App   (A)   [2.1.0, )   2.1.0

(A) : Auto-referenced package.
```

<span data-ttu-id="38a56-111">La colonna **Requested** si riferisce alla versione del pacchetto specificata nel file di progetto e può essere un intervallo.</span><span class="sxs-lookup"><span data-stu-id="38a56-111">The **Requested** column refers to the package version specified in the project file and can be a range.</span></span> <span data-ttu-id="38a56-112">La colonna **Resolved** indica la versione attualmente usata dal progetto ed è sempre un valore singolo.</span><span class="sxs-lookup"><span data-stu-id="38a56-112">The **Resolved** column lists the version that the project is currently using and is always a single value.</span></span> <span data-ttu-id="38a56-113">I pacchetti contrassegnati da una `(A)` accanto al nome rappresentano [riferimenti impliciti al pacchetto](csproj.md#implicit-package-references) derivati dalle impostazioni del progetto (tipo `Sdk`, proprietà `<TargetFramework>` o `<TargetFrameworks>` e così via).</span><span class="sxs-lookup"><span data-stu-id="38a56-113">The packages displaying an `(A)` right next to their names represent [implicit package references](csproj.md#implicit-package-references) that are inferred from your project settings (`Sdk` type, `<TargetFramework>` or `<TargetFrameworks>` property, etc.)</span></span>

<span data-ttu-id="38a56-114">Usare l'opzione `--outdated` per determinare se sono disponibili versioni più recenti dei pacchetti usati nei progetti.</span><span class="sxs-lookup"><span data-stu-id="38a56-114">Use the `--outdated` option to find out if there are newer versions available of the packages you're using in your projects.</span></span> <span data-ttu-id="38a56-115">Per impostazione predefinita, `--outdated` elenca i pacchetti stabili più recenti, a meno che anche la versione risolta non sia una versione non definitiva.</span><span class="sxs-lookup"><span data-stu-id="38a56-115">By default, `--outdated` lists the latest stable packages unless the resolved version is also a prerelease version.</span></span> <span data-ttu-id="38a56-116">Per includere le versioni non definitive nell'elenco delle versioni più recenti, specificare anche l'opzione `--include-prerelease`.</span><span class="sxs-lookup"><span data-stu-id="38a56-116">To include prerelease versions when listing newer versions, also specify the `--include-prerelease` option.</span></span> <span data-ttu-id="38a56-117">Gli esempi seguenti mostrano l'output del comando `dotnet list package --outdated --include-prerelease` per lo stesso progetto dell'esempio precedente:</span><span class="sxs-lookup"><span data-stu-id="38a56-117">The following examples shows the output of the `dotnet list package --outdated --include-prerelease` command for the same project as the previous example:</span></span>

```output
The following sources were used:
   https://api.nuget.org/v3/index.json

Project `SentimentAnalysis` has the following updates to its packages
   [netcoreapp2.1]:
   Top-level Package      Requested   Resolved   Latest
   > Microsoft.ML         0.11.0      0.11.0     1.0.0-preview
```

<span data-ttu-id="38a56-118">Se occorre verificare se il progetto ha dipendenze transitive, usare l'opzione `--include-transitive`.</span><span class="sxs-lookup"><span data-stu-id="38a56-118">If you need to find out whether your project has transitive dependencies, use the `--include-transitive` option.</span></span> <span data-ttu-id="38a56-119">Le dipendenze transitive si hanno quando si aggiunge al progetto un pacchetto che a sua volta si basa su un altro pacchetto.</span><span class="sxs-lookup"><span data-stu-id="38a56-119">Transitive dependencies occur when you add a package to your project that in turn relies on another package.</span></span> <span data-ttu-id="38a56-120">L'esempio seguente mostra l'output dell'esecuzione del comando `dotnet list package --include-transitive` per il progetto [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin), che mostra i pacchetti di primo livello e i pacchetti da cui dipendono:</span><span class="sxs-lookup"><span data-stu-id="38a56-120">The following example shows the output from running the `dotnet list package --include-transitive` command for the [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin) project, which displays top-level packages and the packages they depend on:</span></span>

```output
Project 'HelloPlugin' has the following package references
   [netcoreapp3.0]:
   Top-level Package                      Requested                    Resolved
   > Microsoft.NETCore.Platforms    (A)   [3.0.0-preview3.19128.7, )   3.0.0-preview3.19128.7
   > Microsoft.WindowsDesktop.App   (A)   [3.0.0-preview3-27504-2, )   3.0.0-preview3-27504-2

   Transitive Package               Resolved
   > Microsoft.NETCore.Targets      2.0.0
   > PluginBase                     1.0.0

(A) : Auto-referenced package.
```

## <a name="arguments"></a><span data-ttu-id="38a56-121">Argomenti</span><span class="sxs-lookup"><span data-stu-id="38a56-121">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="38a56-122">File di progetto o di soluzione su cui eseguire le operazioni.</span><span class="sxs-lookup"><span data-stu-id="38a56-122">The project or solution file to operate on.</span></span> <span data-ttu-id="38a56-123">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="38a56-123">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="38a56-124">Se vengono trovati più progetti o soluzioni, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="38a56-124">If more than one solution or project is found, an error is thrown.</span></span>

## <a name="options"></a><span data-ttu-id="38a56-125">Opzioni</span><span class="sxs-lookup"><span data-stu-id="38a56-125">Options</span></span>

* **`--config <SOURCE>`**

  <span data-ttu-id="38a56-126">Origini NuGet da usare per cercare i pacchetti più recenti.</span><span class="sxs-lookup"><span data-stu-id="38a56-126">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="38a56-127">Richiede l'opzione `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="38a56-127">Requires the `--outdated` option.</span></span>

* **`--framework <FRAMEWORK>`**

  <span data-ttu-id="38a56-128">Visualizza solo i pacchetti validi per il [framework di destinazione](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="38a56-128">Displays only the packages applicable for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="38a56-129">Per specificare più framework, ripetere l'opzione più volte.</span><span class="sxs-lookup"><span data-stu-id="38a56-129">To specify multiple frameworks, repeat the option multiple times.</span></span> <span data-ttu-id="38a56-130">Ad esempio: `--framework netcoreapp2.2 --framework netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="38a56-130">For example: `--framework netcoreapp2.2 --framework netstandard2.0`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="38a56-131">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="38a56-131">Prints out a short help for the command.</span></span>

* **`--highest-minor`**

  <span data-ttu-id="38a56-132">Prende in considerazione solo i pacchetti con il numero di versione principale corrispondente quando si cercano i pacchetti più recenti.</span><span class="sxs-lookup"><span data-stu-id="38a56-132">Considers only the packages with a matching major version number when searching for newer packages.</span></span> <span data-ttu-id="38a56-133">Richiede l'opzione `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="38a56-133">Requires the `--outdated` option.</span></span>

* **`--highest-patch`**

  <span data-ttu-id="38a56-134">Prende in considerazione solo i pacchetti con i numeri di versione principale e secondaria corrispondenti quando si cercano i pacchetti più recenti.</span><span class="sxs-lookup"><span data-stu-id="38a56-134">Considers only the packages with a matching major and minor version numbers when searching for newer packages.</span></span> <span data-ttu-id="38a56-135">Richiede l'opzione `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="38a56-135">Requires the `--outdated` option.</span></span>

* **`--include-prerelease`**

  <span data-ttu-id="38a56-136">Prende in considerazione i pacchetti con versioni non definitive quando si cercano i pacchetti più recenti.</span><span class="sxs-lookup"><span data-stu-id="38a56-136">Considers packages with prerelease versions when searching for newer packages.</span></span> <span data-ttu-id="38a56-137">Richiede l'opzione `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="38a56-137">Requires the `--outdated` option.</span></span>

* **`--include-transitive`**

  <span data-ttu-id="38a56-138">Elenca i pacchetti transitivi, oltre ai pacchetti di primo livello.</span><span class="sxs-lookup"><span data-stu-id="38a56-138">Lists transitive packages, in addition to the top-level packages.</span></span> <span data-ttu-id="38a56-139">Quando si specifica questa opzione, si ottiene un elenco di pacchetti da cui dipendono i pacchetti di primo livello.</span><span class="sxs-lookup"><span data-stu-id="38a56-139">When specifying this option, you get a list of packages that the top-level packages depend on.</span></span>

* **`--outdated`**

  <span data-ttu-id="38a56-140">Elenca i pacchetti per cui sono disponibili versioni più recenti.</span><span class="sxs-lookup"><span data-stu-id="38a56-140">Lists packages that have newer versions available.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="38a56-141">Origini NuGet da usare per cercare i pacchetti più recenti.</span><span class="sxs-lookup"><span data-stu-id="38a56-141">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="38a56-142">Richiede l'opzione `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="38a56-142">Requires the `--outdated` option.</span></span>

## <a name="examples"></a><span data-ttu-id="38a56-143">Esempi</span><span class="sxs-lookup"><span data-stu-id="38a56-143">Examples</span></span>

* <span data-ttu-id="38a56-144">Elencare i riferimenti al pacchetto di un progetto specifico:</span><span class="sxs-lookup"><span data-stu-id="38a56-144">List package references of a specific project:</span></span>

  ```console
  dotnet list SentimentAnalysis.csproj package
  ```

* <span data-ttu-id="38a56-145">Elencare i riferimenti al pacchetto per cui sono disponibili versioni più recenti, incluse le versioni non definitive:</span><span class="sxs-lookup"><span data-stu-id="38a56-145">List package references that have newer versions available, including prerelease versions:</span></span>

  ```console
  dotnet list package --outdated --include-prerelease
  ```

* <span data-ttu-id="38a56-146">Elencare i riferimenti al pacchetto per un framework di destinazione specifico:</span><span class="sxs-lookup"><span data-stu-id="38a56-146">List package references for a specific target framework:</span></span>

  ```console
  dotnet list package --framework netcoreapp3.0
  ```