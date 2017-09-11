---
title: Comando dotnet-publish - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-publish consente di pubblicare il progetto .NET Core in una directory.
keywords: dotnet-publish, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a8a37b1eacab13682d4f4a2bea2f9ea248cdd9eb
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-publish"></a><span data-ttu-id="cce37-104">dotnet-publish</span><span class="sxs-lookup"><span data-stu-id="cce37-104">dotnet-publish</span></span>

## <a name="name"></a><span data-ttu-id="cce37-105">Nome</span><span class="sxs-lookup"><span data-stu-id="cce37-105">Name</span></span>

<span data-ttu-id="cce37-106">`dotnet-publish`: inserisce l'applicazione e le relative dipendenze in una cartella per la distribuzione in un sistema host.</span><span class="sxs-lookup"><span data-stu-id="cce37-106">`dotnet-publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cce37-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="cce37-107">Synopsis</span></span>

`dotnet publish [<PROJECT>] [-f|--framework] [-r|--runtime] [-o|--output] [-c|--configuration] [--version-suffix] [-v|--verbosity] [-h|--help]`

## <a name="description"></a><span data-ttu-id="cce37-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cce37-108">Description</span></span>

<span data-ttu-id="cce37-109">`dotnet publish` compila l'applicazione, legge le relative dipendenze specificate nel file di progetto e pubblica il set di file risultante in una directory.</span><span class="sxs-lookup"><span data-stu-id="cce37-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="cce37-110">L'output conterrà quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cce37-110">The output will contain the following:</span></span>

* <span data-ttu-id="cce37-111">Codice Intermediate Language (IL) in un assembly con un'estensione `*.dll`.</span><span class="sxs-lookup"><span data-stu-id="cce37-111">Intermediate Language (IL) code in an assembly with a `*.dll` extension.</span></span>
* <span data-ttu-id="cce37-112">File *\*.deps.json* contenente tutte le dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="cce37-112">*\*.deps.json* file that contains all of the dependencies of the project.</span></span>
* <span data-ttu-id="cce37-113">File *\*.runtime.config.json* che specifica il runtime condiviso previsto dall'applicazione e altre opzioni di configurazione per il runtime, ad esempio il tipo di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="cce37-113">*\*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="cce37-114">Dipendenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cce37-114">The application's dependencies.</span></span> <span data-ttu-id="cce37-115">Questi dati vengono copiati dalla cache NuGet nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="cce37-115">These are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="cce37-116">L'output del comando `dotnet publish` è pronto per la distribuzione in un sistema host (ad esempio un server, un computer PC o Mac o un laptop) per l'esecuzione. Questa è l'unica modalità supportata ufficialmente per preparare l'applicazione per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cce37-116">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution and is the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="cce37-117">A seconda del tipo di distribuzione specificato dal progetto, nel sistema host il runtime condiviso di .NET Core può essere installato o meno.</span><span class="sxs-lookup"><span data-stu-id="cce37-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="cce37-118">Per altre informazioni, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="cce37-118">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="cce37-119">Per la struttura di directory di un'applicazione pubblicata, vedere [Directory structure](/aspnet/core/hosting/directory-structure) (Struttura di directory).</span><span class="sxs-lookup"><span data-stu-id="cce37-119">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

## <a name="arguments"></a><span data-ttu-id="cce37-120">Argomenti</span><span class="sxs-lookup"><span data-stu-id="cce37-120">Arguments</span></span>

`PROJECT` 

<span data-ttu-id="cce37-121">Progetto da pubblicare che, se non specificato, corrisponde per impostazione predefinita alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="cce37-121">The project to publish, which defaults to the current directory if not specified.</span></span> 

## <a name="options"></a><span data-ttu-id="cce37-122">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cce37-122">Options</span></span>

`-h|--help`

<span data-ttu-id="cce37-123">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="cce37-123">Prints out a short help for the command.</span></span>  

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="cce37-124">Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="cce37-124">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="cce37-125">È necessario specificare il framework di destinazione nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="cce37-125">You must specify the target framework in the project file.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="cce37-126">Pubblica l'applicazione per un determinato runtime.</span><span class="sxs-lookup"><span data-stu-id="cce37-126">Publishes the application for a given runtime.</span></span> <span data-ttu-id="cce37-127">Viene usato durante la creazione di una [distribuzione indipendente (SCD, Self-Contained Deployment)](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="cce37-127">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="cce37-128">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="cce37-128">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="cce37-129">L'impostazione predefinita prevede la pubblicazione di una [distribuzione dipendente da framework (FDD, Framework-Dependent Deployment)](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="cce37-129">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="cce37-130">Specifica il percorso della directory di output.</span><span class="sxs-lookup"><span data-stu-id="cce37-130">Specifies the path for the output directory.</span></span> <span data-ttu-id="cce37-131">Se non specificato, il percorso predefinito sarà *./bin/[configuration]/[framework]/* per una distribuzione dipendente da framework o *./bin/[configuration]/[framework]/[runtime]* per una distribuzione indipendente.</span><span class="sxs-lookup"><span data-stu-id="cce37-131">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>

`-c|--configuration <CONFIGURATION>`

<span data-ttu-id="cce37-132">Configurazione da usare durante la compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cce37-132">Configuration to use when building the project.</span></span> <span data-ttu-id="cce37-133">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="cce37-133">The default value is `Debug`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="cce37-134">Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.</span><span class="sxs-lookup"><span data-stu-id="cce37-134">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="cce37-135">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="cce37-135">Sets the verbosity level of the command.</span></span> <span data-ttu-id="cce37-136">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cce37-136">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="cce37-137">Esempi</span><span class="sxs-lookup"><span data-stu-id="cce37-137">Examples</span></span>

<span data-ttu-id="cce37-138">Pubblicare il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="cce37-138">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="cce37-139">Pubblicare l'applicazione usando il file di progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="cce37-139">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`
    
<span data-ttu-id="cce37-140">Pubblicare il progetto nella directory corrente usando il framework `netcoreapp1.1`:</span><span class="sxs-lookup"><span data-stu-id="cce37-140">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`
    
<span data-ttu-id="cce37-141">Pubblicare l'applicazione corrente usando il framework `netcoreapp1.1` e il runtime per `OS X 10.10`. Questo identificatore di runtime deve essere elencato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="cce37-141">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a><span data-ttu-id="cce37-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cce37-142">See also</span></span>

* [<span data-ttu-id="cce37-143">Framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="cce37-143">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="cce37-144">Catalogo RID (Runtime IDentifier)</span><span class="sxs-lookup"><span data-stu-id="cce37-144">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)

