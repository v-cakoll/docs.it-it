---
title: Informazioni di riferimento su csproj
description: Informazioni sulle differenze tra i file csproj esistenti e .NET Core
keywords: informazioni di riferimento, csproj, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 05/24/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 63c7a6f0aa3a926c7ae01ad6c434ecf296c81811
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="b06be-104">Aggiunte al formato csproj per .NET Core</span><span class="sxs-lookup"><span data-stu-id="b06be-104">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="b06be-105">Questo documento descrive le modifiche aggiunte ai file di progetto nell'ambito del passaggio da *project.json* a *csproj* e a [MSBuild](https://github.com/Microsoft/MSBuild).</span><span class="sxs-lookup"><span data-stu-id="b06be-105">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="b06be-106">Per altre informazioni sulla sintassi generale dei file di progetto e informazioni di riferimento, vedere la documentazione del [file di progetto MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="b06be-106">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>  

## <a name="implicit-package-references"></a><span data-ttu-id="b06be-107">Riferimenti impliciti al pacchetto</span><span class="sxs-lookup"><span data-stu-id="b06be-107">Implicit package references</span></span>
<span data-ttu-id="b06be-108">È possibile fare riferimento ai metapacchetti in modo implicito in base ai framework di destinazione specificati nella proprietà `<TargetFramework>` o `<TargetFrameworks>` del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-108">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="b06be-109">`<TargetFrameworks>` viene ignorato se è specificato `<TargetFramework>`, indipendentemente dall'ordine.</span><span class="sxs-lookup"><span data-stu-id="b06be-109">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span>

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp1.1</TargetFramework>
 </PropertyGroup>
 ```
 
 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp1.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a><span data-ttu-id="b06be-110">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="b06be-110">Recommendations</span></span>
<span data-ttu-id="b06be-111">Poiché si fa riferimento ai metapacchetti `Microsoft.NETCore.App` o `NetStandard.Library` in modo implicito, ecco le procedure consigliate:</span><span class="sxs-lookup"><span data-stu-id="b06be-111">Since `Microsoft.NETCore.App` or `NetStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

* <span data-ttu-id="b06be-112">Non fare mai riferimento in modo esplicito ai metapacchetti `Microsoft.NETCore.App` o `NetStandard.Library` tramite l'elemento `<PackageReference>` nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-112">Never have an explicit reference to the `Microsoft.NETCore.App` or `NetStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
* <span data-ttu-id="b06be-113">Se occorre una versione specifica del runtime, è necessario usare la proprietà `<RuntimeFrameworkVersion>` del progetto, ad esempio, `1.0.4`, anziché fare riferimento al metapacchetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-113">If you need a specific version of the runtime, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
    * <span data-ttu-id="b06be-114">Ciò può avvenire se si usano [distribuzioni autosufficienti](../deploying/index.md#self-contained-deployments-scd) e occorre una versione specifica, ad esempio, della patch del runtime 1.0.0 LTS.</span><span class="sxs-lookup"><span data-stu-id="b06be-114">This might happen if you are using [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
* <span data-ttu-id="b06be-115">Se occorre una versione specifica del metapacchetto `NetStandard.Library`, è possibile usare la proprietà `<NetStandardImplicitPackageVersion>` e impostare la versione necessaria.</span><span class="sxs-lookup"><span data-stu-id="b06be-115">If you need a specific version of the `NetStandard.Library` metapackage, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span> 

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="b06be-116">Dichiarazioni Include di compilazione predefinite nei progetti .NET Core</span><span class="sxs-lookup"><span data-stu-id="b06be-116">Default compilation includes in .NET Core projects</span></span>
<span data-ttu-id="b06be-117">Con il passaggio al formato *csproj* nelle ultime versioni dell'SDK, per gli elementi di compilazione e le risorse incorporate le dichiarazioni Include ed Exclude predefinite sono state spostate nei file delle proprietà dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="b06be-117">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="b06be-118">Ciò significa che non è più necessario specificare queste dichiarazioni nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-118">This means that you no longer need to specify these items in your project file.</span></span> 

<span data-ttu-id="b06be-119">Il motivo principale di questo cambiamento è la riduzione del disordine nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-119">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="b06be-120">Le dichiarazioni predefinite presenti nell'SDK coprono i casi di utilizzo più comuni, pertanto non c'è alcuna necessità di ripeterle per ogni progetto creato.</span><span class="sxs-lookup"><span data-stu-id="b06be-120">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="b06be-121">Di conseguenza, i file di progetto sono più piccoli e molto più semplici da comprendere e, se necessario, da modificare manualmente.</span><span class="sxs-lookup"><span data-stu-id="b06be-121">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span> 

<span data-ttu-id="b06be-122">La tabella seguente mostra gli elementi e i [GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) Include ed Exclude nell'SDK:</span><span class="sxs-lookup"><span data-stu-id="b06be-122">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span> 

| <span data-ttu-id="b06be-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="b06be-123">Element</span></span>           | <span data-ttu-id="b06be-124">GLOB Include</span><span class="sxs-lookup"><span data-stu-id="b06be-124">Include glob</span></span>                              | <span data-ttu-id="b06be-125">GLOB Exclude</span><span class="sxs-lookup"><span data-stu-id="b06be-125">Exclude glob</span></span>                                                  | <span data-ttu-id="b06be-126">GLOB Remove</span><span class="sxs-lookup"><span data-stu-id="b06be-126">Remove glob</span></span>                |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="b06be-127">Compile</span><span class="sxs-lookup"><span data-stu-id="b06be-127">Compile</span></span>           | <span data-ttu-id="b06be-128">\*\*/\*.cs (o altre estensioni del linguaggio)</span><span class="sxs-lookup"><span data-stu-id="b06be-128">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="b06be-129">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="b06be-129">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="b06be-130">N/D</span><span class="sxs-lookup"><span data-stu-id="b06be-130">N/A</span></span>                        |
| <span data-ttu-id="b06be-131">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="b06be-131">EmbeddedResource</span></span>  | <span data-ttu-id="b06be-132">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="b06be-132">\*\*/\*.resx</span></span>                              | <span data-ttu-id="b06be-133">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="b06be-133">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="b06be-134">N/D</span><span class="sxs-lookup"><span data-stu-id="b06be-134">N/A</span></span>                        |
| <span data-ttu-id="b06be-135">Nessuno</span><span class="sxs-lookup"><span data-stu-id="b06be-135">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="b06be-136">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="b06be-136">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="b06be-137">- \*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="b06be-137">- \*\*/\*.cs; \*\*/\*.resx</span></span> |

<span data-ttu-id="b06be-138">Se si tenta di compilare un progetto contenente GLOB con l'SDK più recente, viene visualizzato l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="b06be-138">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="b06be-139">Duplicate Compile items were included. (Sono stati inclusi elementi di compilazione duplicati)</span><span class="sxs-lookup"><span data-stu-id="b06be-139">Duplicate Compile items were included.</span></span> <span data-ttu-id="b06be-140">The .NET SDK includes Compile items from your project directory by default. (Per impostazione predefinita, .NET SDK include elementi Compile della directory di progetto)</span><span class="sxs-lookup"><span data-stu-id="b06be-140">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="b06be-141">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file. (Rimuovere questi elementi dal file di progetto o impostare la proprietà 'EnableDefaultCompileItems' su 'false' se li si vuole includere esplicitamente nel file di progetto)</span><span class="sxs-lookup"><span data-stu-id="b06be-141">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span> 

<span data-ttu-id="b06be-142">Per ovviare a questo errore, è possibile rimuovere gli elementi `Compile` corrispondenti a quelli elencati nella tabella precedente oppure impostare la proprietà `<EnableDefaultCompileItems>` su `false`, come segue:</span><span class="sxs-lookup"><span data-stu-id="b06be-142">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
<span data-ttu-id="b06be-143">Se si imposta questa proprietà su `false`, si esegue l'override dell'inclusione implicita e viene ripristinato il comportamento degli SDK precedenti, in cui era necessario specificare i GLOB predefiniti nel progetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-143">Setting this property to `false` will override implicit inclusion and the behavior will revert back to the previous SDKs where you had to specify the default globs in your project.</span></span> 

<span data-ttu-id="b06be-144">Questa modifica non influisce sulle funzioni principali delle altre dichiarazioni Include.</span><span class="sxs-lookup"><span data-stu-id="b06be-144">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="b06be-145">Se tuttavia si vogliono specificare, ad esempio, alcuni file da pubblicare con l'app, è ancora possibile usare i meccanismi noti in *csproj*, ad esempio l'elemento `<Content>`.</span><span class="sxs-lookup"><span data-stu-id="b06be-145">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

### <a name="recommendation"></a><span data-ttu-id="b06be-146">Consiglio</span><span class="sxs-lookup"><span data-stu-id="b06be-146">Recommendation</span></span>
<span data-ttu-id="b06be-147">Con csproj è consigliabile rimuovere i GLOB predefiniti dal progetto e aggiungere solo i percorsi di file con GLOB per gli elementi necessari all'app o alla libreria per diversi scenari (ad esempio, runtime e creazione di pacchetti NuGet).</span><span class="sxs-lookup"><span data-stu-id="b06be-147">With csproj, we recommend that you remove the default globs from your project and only add file paths with globs for those artifacts that your app/library needs for various scenarios (for example, runtime and NuGet packaging).</span></span>

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="b06be-148">Visualizzare l'intero progetto come lo vede MSBuild</span><span class="sxs-lookup"><span data-stu-id="b06be-148">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="b06be-149">Mentre le modifiche di csproj semplificano notevolmente i file di progetto, si potrebbe voler vedere il progetto completamente espanso come lo vede MSBuild dopo che vengono inclusi l'SDK e le relative destinazioni.</span><span class="sxs-lookup"><span data-stu-id="b06be-149">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="b06be-150">Pre-elaborare il progetto con [l'opzione `/pp`](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando [`dotnet msbuild`](dotnet-msbuild.md), che specifica i file importati, le relative risorse e i relativi contributi alla build senza compilare il progetto:</span><span class="sxs-lookup"><span data-stu-id="b06be-150">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild /pp:fullproject.xml`

<span data-ttu-id="b06be-151">Se il progetto contiene più framework di destinazione, i risultati del comando devono essere destinati solo a uno di essi specificandolo come proprietà di MSBuild:</span><span class="sxs-lookup"><span data-stu-id="b06be-151">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild /p:TargetFramework=netcoreapp2.0 /pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="b06be-152">Aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="b06be-152">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="b06be-153">Attributo Sdk</span><span class="sxs-lookup"><span data-stu-id="b06be-153">Sdk attribute</span></span> 
<span data-ttu-id="b06be-154">L'elemento `<Project>` del file *.csproj* ha un nuovo attributo, denominato `Sdk`.</span><span class="sxs-lookup"><span data-stu-id="b06be-154">The `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="b06be-155">`Sdk` specifica l'SDK che viene usato dal progetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-155">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="b06be-156">l'SDK, come descritto dal [documento sui livelli](cli-msbuild-architecture.md), è un set di [attività](/visualstudio/msbuild/msbuild-tasks) e [destinazioni](/visualstudio/msbuild/msbuild-targets) di MSBuild che consente di compilare codice .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b06be-156">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="b06be-157">Con gli strumenti di .NET Core vengono forniti due SDK principali:</span><span class="sxs-lookup"><span data-stu-id="b06be-157">We ship two main SDKs with the .NET Core tools:</span></span>

1. <span data-ttu-id="b06be-158">.NET Core SDK con l'ID di `Microsoft.NET.Sdk`</span><span class="sxs-lookup"><span data-stu-id="b06be-158">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="b06be-159">.NET Core Web SDK con l'ID di `Microsoft.NET.Sdk.Web`</span><span class="sxs-lookup"><span data-stu-id="b06be-159">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>

<span data-ttu-id="b06be-160">Per usare gli strumenti di .NET Core e compilare il codice, è necessario impostare l'attributo `Sdk` su uno di questi ID nell'elemento `<Project>`.</span><span class="sxs-lookup"><span data-stu-id="b06be-160">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span> 

### <a name="packagereference"></a><span data-ttu-id="b06be-161">PackageReference</span><span class="sxs-lookup"><span data-stu-id="b06be-161">PackageReference</span></span>
<span data-ttu-id="b06be-162">Elemento che specifica una dipendenza NuGet nel progetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-162">Item that specifies a NuGet dependency in the project.</span></span> <span data-ttu-id="b06be-163">L'attributo `Include` specifica l'ID del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-163">The `Include` attribute specifies the package ID.</span></span> 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="b06be-164">Versione</span><span class="sxs-lookup"><span data-stu-id="b06be-164">Version</span></span>
<span data-ttu-id="b06be-165">`Version` specifica la versione del pacchetto da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="b06be-165">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="b06be-166">L'attributo rispetta le regole dello schema di [numerazione delle versioni NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="b06be-166">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="b06be-167">Il comportamento predefinito prevede la corrispondenza esatta della versione.</span><span class="sxs-lookup"><span data-stu-id="b06be-167">The default behavior is an exact version match.</span></span> <span data-ttu-id="b06be-168">Ad esempio, specificare `Version="1.2.3"` equivale alla notazione NuGet `[1.2.3]` per la versione esatta 1.2.3 del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-168">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="b06be-169">IncludeAssets, ExcludeAssets e PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="b06be-169">IncludeAssets, ExcludeAssets and PrivateAssets</span></span>
<span data-ttu-id="b06be-170">L'attributo `IncludeAssets` specifica quali asset appartenenti al pacchetto specificato dall'elemento `<PackageReference>` devono essere usati.</span><span class="sxs-lookup"><span data-stu-id="b06be-170">`IncludeAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> 

<span data-ttu-id="b06be-171">L'attributo `ExcludeAssets` specifica quali asset appartenenti al pacchetto specificato dall'elemento `<PackageReference>` non devono essere usati.</span><span class="sxs-lookup"><span data-stu-id="b06be-171">`ExcludeAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="b06be-172">L'attributo `PrivateAssets` specifica quali asset appartenenti al pacchetto specificato dall'elemento `<PackageReference>` devono essere usati. Specifica, inoltre, che tali asset non devono essere trasmessi al progetto successivo.</span><span class="sxs-lookup"><span data-stu-id="b06be-172">`PrivateAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should be consumed but that they should not flow to the next project.</span></span> 

> [!NOTE]
> <span data-ttu-id="b06be-173">`PrivateAssets` equivale all'elemento *project.json*/*xproj* `SuppressParent`.</span><span class="sxs-lookup"><span data-stu-id="b06be-173">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="b06be-174">Questi attributi possono contenere uno o più degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b06be-174">These attributes can contain one or more of the following items:</span></span>

* <span data-ttu-id="b06be-175">`Compile`: i contenuti della cartella lib sono disponibili per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="b06be-175">`Compile` – the contents of the lib folder are available to compile against.</span></span>
* <span data-ttu-id="b06be-176">`Runtime`: vengono distribuiti i contenuti della cartella runtime.</span><span class="sxs-lookup"><span data-stu-id="b06be-176">`Runtime` – the contents of the runtime folder are distributed.</span></span>
* <span data-ttu-id="b06be-177">`ContentFiles`: vengono usati i contenuti della cartella *contentfiles*.</span><span class="sxs-lookup"><span data-stu-id="b06be-177">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
* <span data-ttu-id="b06be-178">`Build`: vengono usate le proprietà/destinazioni nella cartella build.</span><span class="sxs-lookup"><span data-stu-id="b06be-178">`Build` – the props/targets in the build folder are used.</span></span>
* <span data-ttu-id="b06be-179">`Native`: i contenuti degli asset nativi vengono copiati nella cartella di output per il runtime.</span><span class="sxs-lookup"><span data-stu-id="b06be-179">`Native` – the contents from native assets are copied to the output folder for runtime.</span></span>
* <span data-ttu-id="b06be-180">`Analyzers`: vengono usati gli analizzatori.</span><span class="sxs-lookup"><span data-stu-id="b06be-180">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="b06be-181">In alternativa, l'attributo può contenere:</span><span class="sxs-lookup"><span data-stu-id="b06be-181">Alternatively, the attribute can contain:</span></span>

* <span data-ttu-id="b06be-182">`None`: nessuno degli asset viene usato.</span><span class="sxs-lookup"><span data-stu-id="b06be-182">`None` – none of the assets are used.</span></span>
* <span data-ttu-id="b06be-183">`All`: vengono usati tutti gli asset.</span><span class="sxs-lookup"><span data-stu-id="b06be-183">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="b06be-184">DotNetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="b06be-184">DotNetCliToolReference</span></span>
<span data-ttu-id="b06be-185">L'elemento `<DotNetCliToolReference>` specifica lo strumento dell'interfaccia della riga di comando che si vuole ripristinare nel contesto del progetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-185">`<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="b06be-186">Si tratta di una sostituzione per il nodo `tools` in *project.json*.</span><span class="sxs-lookup"><span data-stu-id="b06be-186">It's a replacement for the `tools` node in *project.json*.</span></span> 

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a><span data-ttu-id="b06be-187">Versione</span><span class="sxs-lookup"><span data-stu-id="b06be-187">Version</span></span>
<span data-ttu-id="b06be-188">`Version` specifica la versione del pacchetto da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="b06be-188">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="b06be-189">L'attributo rispetta le regole dello schema di [numerazione delle versioni NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="b06be-189">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="b06be-190">Il comportamento predefinito prevede la corrispondenza esatta della versione.</span><span class="sxs-lookup"><span data-stu-id="b06be-190">The default behavior is an exact version match.</span></span> <span data-ttu-id="b06be-191">Ad esempio, specificare `Version="1.2.3"` equivale alla notazione NuGet `[1.2.3]` per la versione esatta 1.2.3 del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-191">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="b06be-192">Identificatori di runtime</span><span class="sxs-lookup"><span data-stu-id="b06be-192">RuntimeIdentifiers</span></span>
<span data-ttu-id="b06be-193">L'elemento `<RuntimeIdentifiers>` consente di specificare un elenco delimitato da punto e virgola di [identificatori di runtime (RID)](../rid-catalog.md) per il progetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-193">The `<RuntimeIdentifiers>` element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="b06be-194">I RID consentono di pubblicare distribuzioni autonome.</span><span class="sxs-lookup"><span data-stu-id="b06be-194">RIDs enable publishing a self-contained deployments.</span></span> 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="b06be-195">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="b06be-195">RuntimeIdentifier</span></span>
<span data-ttu-id="b06be-196">L'elemento `<RuntimeIdentifier>` consente di specificare un solo [identificatore di runtime (RID)](../rid-catalog.md) per il progetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-196">The `<RuntimeIdentifier>` element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="b06be-197">I RID consentono di pubblicare una distribuzione autonoma.</span><span class="sxs-lookup"><span data-stu-id="b06be-197">RIDs enable publishing a self-contained deployment.</span></span> 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

### <a name="packagetargetfallback"></a><span data-ttu-id="b06be-198">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="b06be-198">PackageTargetFallback</span></span> 
<span data-ttu-id="b06be-199">L'elemento `<PackageTargetFallback>` consente di specificare un set di destinazioni compatibili da usare durante il ripristino di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="b06be-199">The `<PackageTargetFallback>` element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="b06be-200">È progettato per consentire ai pacchetti che usano il [TxM (Target x Moniker)](/nuget/schema/target-frameworks) di .NET di interagire con pacchetti che non dichiarano un TxM di .NET.</span><span class="sxs-lookup"><span data-stu-id="b06be-200">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="b06be-201">Se il progetto usa il TxM di .NET, devono averlo anche tutti i pacchetti da cui il progetto dipende, a meno che non si aggiunga `<PackageTargetFallback>` al progetto, in modo da rendere compatibili con .NET le piattaforme che non lo sono.</span><span class="sxs-lookup"><span data-stu-id="b06be-201">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span> 

<span data-ttu-id="b06be-202">L'esempio seguente include i fallback per tutte le destinazioni nel progetto:</span><span class="sxs-lookup"><span data-stu-id="b06be-202">The following example provides the fallbacks for all targets in your project:</span></span> 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="b06be-203">L'esempio seguente specifica i fallback solo per la destinazione `netcoreapp1.0`:</span><span class="sxs-lookup"><span data-stu-id="b06be-203">The following example specifies the fallbacks only for the `netcoreapp1.0` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp1.0'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a><span data-ttu-id="b06be-204">Proprietà dei metadati NuGet</span><span class="sxs-lookup"><span data-stu-id="b06be-204">NuGet metadata properties</span></span>
<span data-ttu-id="b06be-205">Con il passaggio a MSbuild, i metadati di input usati per la creazione di un pacchetto NuGet sono stati spostati da file *project.json* a file *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="b06be-205">With the move to MSbuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="b06be-206">Gli input sono proprietà di MSBuild, quindi devono trovarsi all'interno di un gruppo `<PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="b06be-206">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="b06be-207">L'elenco seguente include le proprietà usate come input per il processo di creazione del pacchetto quando si usa il comando `dotnet pack` o la destinazione di MSBuild `Pack` che fa parte dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="b06be-207">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK.</span></span> 

### <a name="ispackable"></a><span data-ttu-id="b06be-208">IsPackable</span><span class="sxs-lookup"><span data-stu-id="b06be-208">IsPackable</span></span>
<span data-ttu-id="b06be-209">Valore booleano che specifica se dal progetto può essere creato un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-209">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="b06be-210">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="b06be-210">The default value is `true`.</span></span> 

### <a name="packageversion"></a><span data-ttu-id="b06be-211">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="b06be-211">PackageVersion</span></span>
<span data-ttu-id="b06be-212">Specifica la versione che avrà il pacchetto risultante.</span><span class="sxs-lookup"><span data-stu-id="b06be-212">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="b06be-213">Accetta tutte le forme della stringa di versione NuGet.</span><span class="sxs-lookup"><span data-stu-id="b06be-213">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="b06be-214">Il valore predefinito corrisponde al valore di `$(Version)`, vale a dire della proprietà `Version` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-214">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span> 

### <a name="packageid"></a><span data-ttu-id="b06be-215">PackageId</span><span class="sxs-lookup"><span data-stu-id="b06be-215">PackageId</span></span>
<span data-ttu-id="b06be-216">Specifica il nome del pacchetto risultante.</span><span class="sxs-lookup"><span data-stu-id="b06be-216">Specifies the name for the resulting package.</span></span> <span data-ttu-id="b06be-217">Se non specificato, l'impostazione predefinita per l'operazione `pack` corrisponde all'uso di `AssemblyName` o del nome della directory come nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-217">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span> 

### <a name="title"></a><span data-ttu-id="b06be-218">Titolo</span><span class="sxs-lookup"><span data-stu-id="b06be-218">Title</span></span>
<span data-ttu-id="b06be-219">Titolo del pacchetto facilmente comprensibile per l'utente, usato di solito per la visualizzazione dell'interfaccia utente, ad esempio in nuget.org e in Gestione pacchetti in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b06be-219">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="b06be-220">Se non specificato, viene usato l'ID del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-220">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="b06be-221">Autori</span><span class="sxs-lookup"><span data-stu-id="b06be-221">Authors</span></span>
<span data-ttu-id="b06be-222">Elenco con valori delimitati da punto e virgola di autori di pacchetti, corrispondenti ai nomi di profilo in nuget.org.</span><span class="sxs-lookup"><span data-stu-id="b06be-222">A semicolon-separated list of packages authors, matching the profile names on nuget.org.</span></span> <span data-ttu-id="b06be-223">Questi, visualizzati nella raccolta NuGet in nuget.org, vengono usati per creare riferimenti incrociati ai pacchetti dello stesso autore.</span><span class="sxs-lookup"><span data-stu-id="b06be-223">These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="description"></a><span data-ttu-id="b06be-224">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b06be-224">Description</span></span>
<span data-ttu-id="b06be-225">Descrizione lunga del pacchetto per la visualizzazione dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="b06be-225">A long description of the package for UI display.</span></span>

### <a name="copyright"></a><span data-ttu-id="b06be-226">Copyright</span><span class="sxs-lookup"><span data-stu-id="b06be-226">Copyright</span></span>
<span data-ttu-id="b06be-227">Informazioni sul copyright per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-227">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="b06be-228">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="b06be-228">PackageRequireLicenseAcceptance</span></span>
<span data-ttu-id="b06be-229">Valore booleano che specifica se il client deve richiedere al consumer di accettare la licenza del pacchetto prima di installarlo.</span><span class="sxs-lookup"><span data-stu-id="b06be-229">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="b06be-230">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="b06be-230">The default is `false`.</span></span>

### <a name="packagelicenseurl"></a><span data-ttu-id="b06be-231">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="b06be-231">PackageLicenseUrl</span></span>
<span data-ttu-id="b06be-232">URL della licenza applicabile al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-232">An URL to the license that is applicable to the package.</span></span>

### <a name="packageprojecturl"></a><span data-ttu-id="b06be-233">PackageProjectUrl</span><span class="sxs-lookup"><span data-stu-id="b06be-233">PackageProjectUrl</span></span>
<span data-ttu-id="b06be-234">URL della pagina iniziale del pacchetto, spesso visualizzato nell'interfaccia utente e in nuget.org.</span><span class="sxs-lookup"><span data-stu-id="b06be-234">A URL for the package's home page, often shown in UI displays as well as nuget.org.</span></span>

### <a name="packageiconurl"></a><span data-ttu-id="b06be-235">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="b06be-235">PackageIconUrl</span></span>
<span data-ttu-id="b06be-236">URL di un'immagine 64 x 64 con sfondo trasparente da usare come icona per il pacchetto nella visualizzazione dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="b06be-236">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="b06be-237">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="b06be-237">PackageReleaseNotes</span></span>
<span data-ttu-id="b06be-238">Note sulla versione per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-238">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="b06be-239">PackageTags</span><span class="sxs-lookup"><span data-stu-id="b06be-239">PackageTags</span></span>
<span data-ttu-id="b06be-240">Elenco di tag con valori delimitati da punto e virgola che designa il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-240">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="b06be-241">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="b06be-241">PackageOutputPath</span></span>
<span data-ttu-id="b06be-242">Determina il percorso di output in cui verrà rilasciato il pacchetto creato.</span><span class="sxs-lookup"><span data-stu-id="b06be-242">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="b06be-243">Il valore predefinito è `$(OutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="b06be-243">Default is `$(OutputPath)`.</span></span> 

### <a name="includesymbols"></a><span data-ttu-id="b06be-244">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="b06be-244">IncludeSymbols</span></span>
<span data-ttu-id="b06be-245">Valore booleano che indica se al momento della creazione del pacchetto deve essere creato un pacchetto aggiuntivo di simboli.</span><span class="sxs-lookup"><span data-stu-id="b06be-245">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="b06be-246">Questo pacchetto, con estensione *.symbols.nupkg*, copierà i file PDB insieme ai file DLL e ad altri file di output.</span><span class="sxs-lookup"><span data-stu-id="b06be-246">This package will have a *.symbols.nupkg* extension and will copy the PDB files along with the DLL and other output files.</span></span>

### <a name="includesource"></a><span data-ttu-id="b06be-247">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="b06be-247">IncludeSource</span></span>
<span data-ttu-id="b06be-248">Valore booleano che indica se il processo di creazione del pacchetto deve creare un pacchetto di origine.</span><span class="sxs-lookup"><span data-stu-id="b06be-248">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="b06be-249">Il pacchetto di origine contiene il codice sorgente della libreria, nonché i file PDB.</span><span class="sxs-lookup"><span data-stu-id="b06be-249">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="b06be-250">I file di origine vengono posizionati nella directory `src/ProjectName` del file del pacchetto risultante.</span><span class="sxs-lookup"><span data-stu-id="b06be-250">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span> 

### <a name="istool"></a><span data-ttu-id="b06be-251">IsTool</span><span class="sxs-lookup"><span data-stu-id="b06be-251">IsTool</span></span>
<span data-ttu-id="b06be-252">Specifica se tutti i file di output devono essere copiati nella cartella *tools* anziché nella cartella *lib*.</span><span class="sxs-lookup"><span data-stu-id="b06be-252">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="b06be-253">È diverso da `DotNetCliTool`, che viene specificato impostando `PackageType` nel file *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="b06be-253">Note that this is different from a `DotNetCliTool` which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="b06be-254">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="b06be-254">RepositoryUrl</span></span>
<span data-ttu-id="b06be-255">Specifica l'URL per l'archivio in cui si trova il codice sorgente per il pacchetto e/o da cui il codice sorgente viene compilato.</span><span class="sxs-lookup"><span data-stu-id="b06be-255">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span> 

### <a name="repositorytype"></a><span data-ttu-id="b06be-256">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="b06be-256">RepositoryType</span></span>
<span data-ttu-id="b06be-257">Specifica il tipo dell'archivio.</span><span class="sxs-lookup"><span data-stu-id="b06be-257">Specifies the type of the repository.</span></span> <span data-ttu-id="b06be-258">Il valore predefinito è "git".</span><span class="sxs-lookup"><span data-stu-id="b06be-258">Default is "git".</span></span> 

### <a name="nopackageanalysis"></a><span data-ttu-id="b06be-259">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="b06be-259">NoPackageAnalysis</span></span>
<span data-ttu-id="b06be-260">Specifica che pack non deve eseguire l'analisi del pacchetto dopo la compilazione di quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="b06be-260">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="b06be-261">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="b06be-261">MinClientVersion</span></span>
<span data-ttu-id="b06be-262">Specifica la versione minima del client NuGet, imposta da nuget.exe e da Gestione pacchetti di Visual Studio, che può installare questo pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-262">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="b06be-263">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="b06be-263">IncludeBuildOutput</span></span>
<span data-ttu-id="b06be-264">Valore booleano che specifica se gli assembly di output di compilazione devono essere compresi nel file *.nupkg*.</span><span class="sxs-lookup"><span data-stu-id="b06be-264">This Boolean values specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="b06be-265">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="b06be-265">IncludeContentInPack</span></span>
<span data-ttu-id="b06be-266">Questo valore booleano specifica se gli elementi con tipo `Content` verranno inclusi automaticamente nel pacchetto risultante.</span><span class="sxs-lookup"><span data-stu-id="b06be-266">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="b06be-267">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="b06be-267">The default is `true`.</span></span> 

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="b06be-268">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="b06be-268">BuildOutputTargetFolder</span></span>
<span data-ttu-id="b06be-269">Specifica la cartella in cui posizionare gli assembly di output.</span><span class="sxs-lookup"><span data-stu-id="b06be-269">Specifies the folder where to place the output assemblies..</span></span> <span data-ttu-id="b06be-270">Gli assembly di output (e altri file di output) vengono copiati nelle rispettive cartelle per framework.</span><span class="sxs-lookup"><span data-stu-id="b06be-270">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="b06be-271">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="b06be-271">ContentTargetFolders</span></span>
<span data-ttu-id="b06be-272">Questa proprietà specifica il percorso predefinito in cui devono essere posizionati tutti i file di contenuto se per tali file `PackagePath` non è specificato.</span><span class="sxs-lookup"><span data-stu-id="b06be-272">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="b06be-273">Il valore predefinito è "content;contentFiles".</span><span class="sxs-lookup"><span data-stu-id="b06be-273">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="b06be-274">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="b06be-274">NuspecFile</span></span>
<span data-ttu-id="b06be-275">Percorso relativo o assoluto per il file *.nuspec* usato per la creazione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b06be-275">Relative or absolute path to the *.nuspec* file being used for packing.</span></span> 

> [!NOTE]
> <span data-ttu-id="b06be-276">Se il file *.nuspec* è specificato, viene usato **esclusivamente** per le informazioni di creazione del pacchetto e le informazioni nei progetti non vengono usate.</span><span class="sxs-lookup"><span data-stu-id="b06be-276">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span> 

### <a name="nuspecbasepath"></a><span data-ttu-id="b06be-277">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="b06be-277">NuspecBasePath</span></span>
<span data-ttu-id="b06be-278">Percorso di base per il file *.nuspec*.</span><span class="sxs-lookup"><span data-stu-id="b06be-278">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="b06be-279">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="b06be-279">NuspecProperties</span></span>
<span data-ttu-id="b06be-280">Elenco con valori delimitati da punto e virgola di coppie chiave=valore.</span><span class="sxs-lookup"><span data-stu-id="b06be-280">Semicolon separated list of key=value pairs.</span></span>

