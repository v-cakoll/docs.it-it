---
title: Aggiunte al formato csproj per .NET Core
description: Informazioni sulle differenze tra i file csproj esistenti e .NET Core
ms.date: 09/22/2017
ms.openlocfilehash: f2b028624f2a09e43aa94d8044568a8aafd07df6
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678996"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="ffb78-103">Aggiunte al formato csproj per .NET Core</span><span class="sxs-lookup"><span data-stu-id="ffb78-103">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="ffb78-104">Questo documento descrive le modifiche aggiunte ai file di progetto nell'ambito del passaggio da *project.json* a *csproj* e a [MSBuild](https://github.com/Microsoft/MSBuild).</span><span class="sxs-lookup"><span data-stu-id="ffb78-104">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="ffb78-105">Per altre informazioni sulla sintassi generale dei file di progetto e informazioni di riferimento, vedere la documentazione del [file di progetto MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="ffb78-105">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>  

## <a name="implicit-package-references"></a><span data-ttu-id="ffb78-106">Riferimenti impliciti al pacchetto</span><span class="sxs-lookup"><span data-stu-id="ffb78-106">Implicit package references</span></span>
<span data-ttu-id="ffb78-107">È possibile fare riferimento ai metapacchetti in modo implicito in base ai framework di destinazione specificati nella proprietà `<TargetFramework>` o `<TargetFrameworks>` del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-107">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="ffb78-108">`<TargetFrameworks>` viene ignorato se è specificato `<TargetFramework>`, indipendentemente dall'ordine.</span><span class="sxs-lookup"><span data-stu-id="ffb78-108">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span>

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp2.1</TargetFramework>
 </PropertyGroup>
 ```
 
 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp2.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a><span data-ttu-id="ffb78-109">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="ffb78-109">Recommendations</span></span>
<span data-ttu-id="ffb78-110">Poiché si fa riferimento ai metapacchetti `Microsoft.NETCore.App` o `NetStandard.Library` in modo implicito, ecco le procedure consigliate:</span><span class="sxs-lookup"><span data-stu-id="ffb78-110">Since `Microsoft.NETCore.App` or `NetStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

* <span data-ttu-id="ffb78-111">Quando la destinazione è .NET Core o .NET Standard, non fare mai riferimento in modo esplicito ai metapacchetti `Microsoft.NETCore.App` o `NetStandard.Library` tramite l'elemento `<PackageReference>` nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-111">When targeting .NET Core or .NET Standard, never have an explicit reference to the `Microsoft.NETCore.App` or `NetStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
* <span data-ttu-id="ffb78-112">Se occorre una versione specifica del runtime quando la destinazione è .NET Core, è necessario usare la proprietà `<RuntimeFrameworkVersion>` del progetto, ad esempio, `1.0.4`, anziché fare riferimento al metapacchetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-112">If you need a specific version of the runtime when targeting .NET Core, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
    * <span data-ttu-id="ffb78-113">Ciò può avvenire se si usano [distribuzioni autosufficienti](../deploying/index.md#self-contained-deployments-scd) e occorre una versione specifica, ad esempio, della patch del runtime 1.0.0 LTS.</span><span class="sxs-lookup"><span data-stu-id="ffb78-113">This might happen if you are using [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
* <span data-ttu-id="ffb78-114">Se occorre una versione specifica del metapacchetto `NetStandard.Library` quando la destinazione è .NET Standard, è possibile usare la proprietà `<NetStandardImplicitPackageVersion>` e impostare la versione necessaria.</span><span class="sxs-lookup"><span data-stu-id="ffb78-114">If you need a specific version of the `NetStandard.Library` metapackage when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>
* <span data-ttu-id="ffb78-115">Non aggiungere o aggiornare in modo esplicito i riferimenti al metapacchetto `Microsoft.NETCore.App` o `NetStandard.Library` nei progetti .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ffb78-115">Don't explicitly add or update references to either the `Microsoft.NETCore.App` or `NetStandard.Library` metapackage in .NET Framework projects.</span></span> <span data-ttu-id="ffb78-116">Se è necessaria qualsiasi versione di `NetStandard.Library` durante l'uso di un pacchetto NuGet basato su .NET Standard, NuGet installa automaticamente tale versione.</span><span class="sxs-lookup"><span data-stu-id="ffb78-116">If any version of `NetStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="ffb78-117">Dichiarazioni Include di compilazione predefinite nei progetti .NET Core</span><span class="sxs-lookup"><span data-stu-id="ffb78-117">Default compilation includes in .NET Core projects</span></span>
<span data-ttu-id="ffb78-118">Con il passaggio al formato *csproj* nelle ultime versioni dell'SDK, per gli elementi di compilazione e le risorse incorporate le dichiarazioni Include ed Exclude predefinite sono state spostate nei file delle proprietà dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="ffb78-118">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="ffb78-119">Ciò significa che non è più necessario specificare queste dichiarazioni nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-119">This means that you no longer need to specify these items in your project file.</span></span> 

<span data-ttu-id="ffb78-120">Il motivo principale di questo cambiamento è la riduzione del disordine nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-120">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="ffb78-121">Le dichiarazioni predefinite presenti nell'SDK coprono i casi di utilizzo più comuni, pertanto non c'è alcuna necessità di ripeterle per ogni progetto creato.</span><span class="sxs-lookup"><span data-stu-id="ffb78-121">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="ffb78-122">Di conseguenza, i file di progetto sono più piccoli e molto più semplici da comprendere e, se necessario, da modificare manualmente.</span><span class="sxs-lookup"><span data-stu-id="ffb78-122">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span> 

<span data-ttu-id="ffb78-123">La tabella seguente mostra gli elementi e i [GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) Include ed Exclude nell'SDK:</span><span class="sxs-lookup"><span data-stu-id="ffb78-123">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span> 

| <span data-ttu-id="ffb78-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="ffb78-124">Element</span></span>           | <span data-ttu-id="ffb78-125">GLOB Include</span><span class="sxs-lookup"><span data-stu-id="ffb78-125">Include glob</span></span>                                | <span data-ttu-id="ffb78-126">GLOB Exclude</span><span class="sxs-lookup"><span data-stu-id="ffb78-126">Exclude glob</span></span>                                                    | <span data-ttu-id="ffb78-127">GLOB Remove</span><span class="sxs-lookup"><span data-stu-id="ffb78-127">Remove glob</span></span>                |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="ffb78-128">Compile</span><span class="sxs-lookup"><span data-stu-id="ffb78-128">Compile</span></span>           | <span data-ttu-id="ffb78-129">\*\*/\*.cs (o altre estensioni del linguaggio)</span><span class="sxs-lookup"><span data-stu-id="ffb78-129">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="ffb78-130">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="ffb78-130">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="ffb78-131">N/D</span><span class="sxs-lookup"><span data-stu-id="ffb78-131">N/A</span></span>                        |
| <span data-ttu-id="ffb78-132">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="ffb78-132">EmbeddedResource</span></span>  | <span data-ttu-id="ffb78-133">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="ffb78-133">\*\*/\*.resx</span></span>                              | <span data-ttu-id="ffb78-134">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="ffb78-134">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="ffb78-135">N/D</span><span class="sxs-lookup"><span data-stu-id="ffb78-135">N/A</span></span>                        |
| <span data-ttu-id="ffb78-136">nessuno</span><span class="sxs-lookup"><span data-stu-id="ffb78-136">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="ffb78-137">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="ffb78-137">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="ffb78-138">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="ffb78-138">\*\*/\*.cs; \*\*/\*.resx</span></span>   |

> [!NOTE]
> <span data-ttu-id="ffb78-139">Il criterio **GLOB Exclude** esclude sempre le cartelle `./bin` e `./obj`, rappresentate rispettivamente dalle proprietà MSBuild `$(BaseOutputPath)` e `$(BaseIntermediateOutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-139">**Exclude glob** always excludes the `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, respectively.</span></span> <span data-ttu-id="ffb78-140">Nel complesso, tutte le esclusioni sono rappresentate da `$(DefaultItemExcludes)`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-140">As a whole, all excludes are represented by `$(DefaultItemExcludes)`.</span></span>

<span data-ttu-id="ffb78-141">Se si tenta di compilare un progetto contenente GLOB con l'SDK più recente, viene visualizzato l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="ffb78-141">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="ffb78-142">Duplicate Compile items were included. (Sono stati inclusi elementi di compilazione duplicati)</span><span class="sxs-lookup"><span data-stu-id="ffb78-142">Duplicate Compile items were included.</span></span> <span data-ttu-id="ffb78-143">The .NET SDK includes Compile items from your project directory by default. (Per impostazione predefinita, .NET SDK include elementi Compile della directory di progetto)</span><span class="sxs-lookup"><span data-stu-id="ffb78-143">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="ffb78-144">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file. (Rimuovere questi elementi dal file di progetto o impostare la proprietà 'EnableDefaultCompileItems' su 'false' se li si vuole includere esplicitamente nel file di progetto)</span><span class="sxs-lookup"><span data-stu-id="ffb78-144">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span> 

<span data-ttu-id="ffb78-145">Per ovviare a questo errore, è possibile rimuovere gli elementi `Compile` corrispondenti a quelli elencati nella tabella precedente oppure impostare la proprietà `<EnableDefaultCompileItems>` su `false`, come segue:</span><span class="sxs-lookup"><span data-stu-id="ffb78-145">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
<span data-ttu-id="ffb78-146">Se si imposta questa proprietà su `false`, si disabilita l'inclusione implicita e viene ripristinato il comportamento degli SDK precedenti, in cui era necessario specificare i GLOB predefiniti nel progetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-146">Setting this property to `false` will disable implicit inclusion, reverting to the behavior of previous SDKs where you had to specify the default globs in your project.</span></span>

<span data-ttu-id="ffb78-147">Questa modifica non influisce sulle funzioni principali delle altre dichiarazioni Include.</span><span class="sxs-lookup"><span data-stu-id="ffb78-147">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="ffb78-148">Se tuttavia si vogliono specificare, ad esempio, alcuni file da pubblicare con l'app, è ancora possibile usare i meccanismi noti in *csproj*, ad esempio l'elemento `<Content>`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-148">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

<span data-ttu-id="ffb78-149">`<EnableDefaultCompileItems>` disabilita solo i glob `Compile` ma non influisce su altri glob, come il glob implicito `None`, che si applica anche agli elementi \*.cs.</span><span class="sxs-lookup"><span data-stu-id="ffb78-149">`<EnableDefaultCompileItems>` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob, which also applies to \*.cs items.</span></span> <span data-ttu-id="ffb78-150">Per questo motivo, **Esplora soluzioni** continuerà a visualizzare elementi \*.cs come parte del progetto, inclusi come elementi `None`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-150">Because of that, **Solution Explorer** will continue show \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="ffb78-151">In modo analogo, è possibile usare `<EnableDefaultNoneItems>` per disabilitare il glob implicito `None`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-151">In a similar way, you can use `<EnableDefaultNoneItems>` to disable the implicit `None` glob.</span></span>

<span data-ttu-id="ffb78-152">Per disabilitare **tutti i glob impliciti**, è possibile impostare la proprietà `<EnableDefaultItems>` su `false` come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ffb78-152">To disable **all implicit globs**, you can set the `<EnableDefaultItems>` property to `false` as in the following example:</span></span>
```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="ffb78-153">Visualizzare l'intero progetto come lo vede MSBuild</span><span class="sxs-lookup"><span data-stu-id="ffb78-153">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="ffb78-154">Mentre le modifiche di csproj semplificano notevolmente i file di progetto, si potrebbe voler vedere il progetto completamente espanso come lo vede MSBuild dopo che vengono inclusi l'SDK e le relative destinazioni.</span><span class="sxs-lookup"><span data-stu-id="ffb78-154">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="ffb78-155">Pre-elaborare il progetto con [l'opzione `/pp`](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando [`dotnet msbuild`](dotnet-msbuild.md), che specifica i file importati, le relative risorse e i relativi contributi alla build senza compilare il progetto:</span><span class="sxs-lookup"><span data-stu-id="ffb78-155">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild -pp:fullproject.xml`

<span data-ttu-id="ffb78-156">Se il progetto contiene più framework di destinazione, i risultati del comando devono essere destinati solo a uno di essi specificandolo come proprietà di MSBuild:</span><span class="sxs-lookup"><span data-stu-id="ffb78-156">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="ffb78-157">Aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="ffb78-157">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="ffb78-158">Attributo Sdk</span><span class="sxs-lookup"><span data-stu-id="ffb78-158">Sdk attribute</span></span> 
<span data-ttu-id="ffb78-159">L'elemento radice `<Project>` del file con estensione *csproj* ha un nuovo attributo, denominato `Sdk`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-159">The root `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="ffb78-160">`Sdk` specifica l'SDK che viene usato dal progetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-160">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="ffb78-161">l'SDK, come descritto dal [documento sui livelli](cli-msbuild-architecture.md), è un set di [attività](/visualstudio/msbuild/msbuild-tasks) e [destinazioni](/visualstudio/msbuild/msbuild-targets) di MSBuild che consente di compilare codice .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ffb78-161">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="ffb78-162">Con gli strumenti di .NET Core vengono forniti tre SDK principali:</span><span class="sxs-lookup"><span data-stu-id="ffb78-162">We ship three main SDKs with the .NET Core tools:</span></span>

1. <span data-ttu-id="ffb78-163">.NET Core SDK con l'ID di `Microsoft.NET.Sdk`</span><span class="sxs-lookup"><span data-stu-id="ffb78-163">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="ffb78-164">.NET Core Web SDK con l'ID di `Microsoft.NET.Sdk.Web`</span><span class="sxs-lookup"><span data-stu-id="ffb78-164">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>
3. <span data-ttu-id="ffb78-165">.NET Core Razor Class Library SDK con l'ID di `Microsoft.NET.Sdk.Razor`</span><span class="sxs-lookup"><span data-stu-id="ffb78-165">The .NET Core Razor Class Library SDK with the ID of `Microsoft.NET.Sdk.Razor`</span></span>

<span data-ttu-id="ffb78-166">Per usare gli strumenti di .NET Core e compilare il codice, è necessario impostare l'attributo `Sdk` su uno di questi ID nell'elemento `<Project>`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-166">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span> 

### <a name="packagereference"></a><span data-ttu-id="ffb78-167">PackageReference</span><span class="sxs-lookup"><span data-stu-id="ffb78-167">PackageReference</span></span>
<span data-ttu-id="ffb78-168">Un elemento `<PackageReference>` specifica una [dipendenza NuGet nel progetto](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="ffb78-168">A `<PackageReference>` item element specifies a [NuGet dependency in the project](/nuget/consume-packages/package-references-in-project-files).</span></span> <span data-ttu-id="ffb78-169">L'attributo `Include` specifica l'ID del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-169">The `Include` attribute specifies the package ID.</span></span> 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="ffb78-170">Versione</span><span class="sxs-lookup"><span data-stu-id="ffb78-170">Version</span></span>
<span data-ttu-id="ffb78-171">L'attributo `Version` obbligatorio specifica la versione del pacchetto da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="ffb78-171">The required `Version` attribute specifies the version of the package to restore.</span></span> <span data-ttu-id="ffb78-172">L'attributo rispetta le regole dello schema di [numerazione delle versioni NuGet](/nuget/reference/package-versioning#version-ranges-and-wildcards).</span><span class="sxs-lookup"><span data-stu-id="ffb78-172">The attribute respects the rules of the [NuGet versioning](/nuget/reference/package-versioning#version-ranges-and-wildcards) scheme.</span></span> <span data-ttu-id="ffb78-173">Il comportamento predefinito prevede la corrispondenza esatta della versione.</span><span class="sxs-lookup"><span data-stu-id="ffb78-173">The default behavior is an exact version match.</span></span> <span data-ttu-id="ffb78-174">Ad esempio, specificare `Version="1.2.3"` equivale alla notazione NuGet `[1.2.3]` per la versione esatta 1.2.3 del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-174">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="ffb78-175">IncludeAssets, ExcludeAssets e PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="ffb78-175">IncludeAssets, ExcludeAssets and PrivateAssets</span></span>
<span data-ttu-id="ffb78-176">L'attributo `IncludeAssets` specifica gli asset appartenenti al pacchetto specificato da `<PackageReference>` che devono essere usati.</span><span class="sxs-lookup"><span data-stu-id="ffb78-176">`IncludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> <span data-ttu-id="ffb78-177">Per impostazione predefinita, sono inclusi tutti gli asset del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-177">By default, all package assets are included.</span></span>

<span data-ttu-id="ffb78-178">L'attributo `ExcludeAssets` specifica gli asset appartenenti al pacchetto specificato da `<PackageReference>` che non devono essere usati.</span><span class="sxs-lookup"><span data-stu-id="ffb78-178">`ExcludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="ffb78-179">L'attributo `PrivateAssets` specifica gli asset appartenenti al pacchetto specificato da `<PackageReference>` che devono essere usati, indicando inoltre che non devono essere trasmessi al progetto successivo.</span><span class="sxs-lookup"><span data-stu-id="ffb78-179">`PrivateAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed but not flow to the next project.</span></span> <span data-ttu-id="ffb78-180">Gli asset `Analyzers`, `Build` e `ContentFiles` sono privati per impostazione predefinita quando questo attributo non è presente.</span><span class="sxs-lookup"><span data-stu-id="ffb78-180">The `Analyzers`, `Build` and `ContentFiles` assets are private by default when this attribute is not present.</span></span>

> [!NOTE]
> <span data-ttu-id="ffb78-181">`PrivateAssets` equivale all'elemento *project.json*/*xproj* `SuppressParent`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-181">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="ffb78-182">Questi attributi possono contenere uno o più degli elementi seguenti, separati dal carattere punto e virgola `;` se ne vengono elencati vari:</span><span class="sxs-lookup"><span data-stu-id="ffb78-182">These attributes can contain one or more of the following items, separated by the semicolon `;` character if more than one is listed:</span></span>

* <span data-ttu-id="ffb78-183">`Compile`: i contenuti della cartella lib sono disponibili per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="ffb78-183">`Compile` – the contents of the lib folder are available to compile against.</span></span>
* <span data-ttu-id="ffb78-184">`Runtime`: vengono distribuiti i contenuti della cartella runtime.</span><span class="sxs-lookup"><span data-stu-id="ffb78-184">`Runtime` – the contents of the runtime folder are distributed.</span></span>
* <span data-ttu-id="ffb78-185">`ContentFiles`: vengono usati i contenuti della cartella *contentfiles*.</span><span class="sxs-lookup"><span data-stu-id="ffb78-185">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
* <span data-ttu-id="ffb78-186">`Build`: vengono usate le proprietà/destinazioni nella cartella build.</span><span class="sxs-lookup"><span data-stu-id="ffb78-186">`Build` – the props/targets in the build folder are used.</span></span>
* <span data-ttu-id="ffb78-187">`Native`: i contenuti degli asset nativi vengono copiati nella cartella di output per il runtime.</span><span class="sxs-lookup"><span data-stu-id="ffb78-187">`Native` – the contents from native assets are copied to the output folder for runtime.</span></span>
* <span data-ttu-id="ffb78-188">`Analyzers`: vengono usati gli analizzatori.</span><span class="sxs-lookup"><span data-stu-id="ffb78-188">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="ffb78-189">In alternativa, l'attributo può contenere:</span><span class="sxs-lookup"><span data-stu-id="ffb78-189">Alternatively, the attribute can contain:</span></span>

* <span data-ttu-id="ffb78-190">`None`: nessuno degli asset viene usato.</span><span class="sxs-lookup"><span data-stu-id="ffb78-190">`None` – none of the assets are used.</span></span>
* <span data-ttu-id="ffb78-191">`All`: vengono usati tutti gli asset.</span><span class="sxs-lookup"><span data-stu-id="ffb78-191">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="ffb78-192">DotNetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="ffb78-192">DotNetCliToolReference</span></span>
<span data-ttu-id="ffb78-193">Un elemento `<DotNetCliToolReference>` specifica lo strumento dell'interfaccia della riga di comando che si vuole ripristinare nel contesto del progetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-193">A `<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="ffb78-194">Si tratta di una sostituzione per il nodo `tools` in *project.json*.</span><span class="sxs-lookup"><span data-stu-id="ffb78-194">It's a replacement for the `tools` node in *project.json*.</span></span> 

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a><span data-ttu-id="ffb78-195">Versione</span><span class="sxs-lookup"><span data-stu-id="ffb78-195">Version</span></span>
<span data-ttu-id="ffb78-196">`Version` specifica la versione del pacchetto da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="ffb78-196">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="ffb78-197">L'attributo rispetta le regole dello schema di [numerazione delle versioni NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="ffb78-197">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="ffb78-198">Il comportamento predefinito prevede la corrispondenza esatta della versione.</span><span class="sxs-lookup"><span data-stu-id="ffb78-198">The default behavior is an exact version match.</span></span> <span data-ttu-id="ffb78-199">Ad esempio, specificare `Version="1.2.3"` equivale alla notazione NuGet `[1.2.3]` per la versione esatta 1.2.3 del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-199">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="ffb78-200">Identificatori di runtime</span><span class="sxs-lookup"><span data-stu-id="ffb78-200">RuntimeIdentifiers</span></span>
<span data-ttu-id="ffb78-201">L'elemento di proprietà `<RuntimeIdentifiers>` consente di specificare un elenco delimitato da punto e virgola di [identificatori di runtime (RID)](../rid-catalog.md) per il progetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-201">The `<RuntimeIdentifiers>` property element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="ffb78-202">I RID consentono di pubblicare distribuzioni autonome.</span><span class="sxs-lookup"><span data-stu-id="ffb78-202">RIDs enable publishing self-contained deployments.</span></span> 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="ffb78-203">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="ffb78-203">RuntimeIdentifier</span></span>
<span data-ttu-id="ffb78-204">L'elemento di proprietà `<RuntimeIdentifier>` consente di specificare un solo [identificatore di runtime (RID)](../rid-catalog.md) per il progetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-204">The `<RuntimeIdentifier>` property element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="ffb78-205">Il RID consente di pubblicare una distribuzione autonoma.</span><span class="sxs-lookup"><span data-stu-id="ffb78-205">The RID enables publishing a self-contained deployment.</span></span>

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

<span data-ttu-id="ffb78-206">Usare invece `<RuntimeIdentifiers>` (plurale) se è necessario pubblicare per più runtime.</span><span class="sxs-lookup"><span data-stu-id="ffb78-206">Use `<RuntimeIdentifiers>` (plural) instead if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="ffb78-207">`<RuntimeIdentifier>` può offrire compilazioni più veloci quando è necessario solo un singolo runtime.</span><span class="sxs-lookup"><span data-stu-id="ffb78-207">`<RuntimeIdentifier>` can provide faster builds when only a single runtime is required.</span></span>

### <a name="packagetargetfallback"></a><span data-ttu-id="ffb78-208">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="ffb78-208">PackageTargetFallback</span></span> 
<span data-ttu-id="ffb78-209">L'elemento di proprietà `<PackageTargetFallback>` consente di specificare un set di destinazioni compatibili da usare durante il ripristino di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="ffb78-209">The `<PackageTargetFallback>` property element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="ffb78-210">È progettato per consentire ai pacchetti che usano il [TxM (Target x Moniker)](/nuget/schema/target-frameworks) di .NET di interagire con pacchetti che non dichiarano un TxM di .NET.</span><span class="sxs-lookup"><span data-stu-id="ffb78-210">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="ffb78-211">Se il progetto usa il TxM di .NET, devono averlo anche tutti i pacchetti da cui il progetto dipende, a meno che non si aggiunga `<PackageTargetFallback>` al progetto, in modo da rendere compatibili con .NET le piattaforme che non lo sono.</span><span class="sxs-lookup"><span data-stu-id="ffb78-211">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span> 

<span data-ttu-id="ffb78-212">L'esempio seguente include i fallback per tutte le destinazioni nel progetto:</span><span class="sxs-lookup"><span data-stu-id="ffb78-212">The following example provides the fallbacks for all targets in your project:</span></span> 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="ffb78-213">L'esempio seguente specifica i fallback solo per la destinazione `netcoreapp2.1`:</span><span class="sxs-lookup"><span data-stu-id="ffb78-213">The following example specifies the fallbacks only for the `netcoreapp2.1` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a><span data-ttu-id="ffb78-214">Proprietà dei metadati NuGet</span><span class="sxs-lookup"><span data-stu-id="ffb78-214">NuGet metadata properties</span></span>
<span data-ttu-id="ffb78-215">Con il passaggio a MSBuild, i metadati di input usati per la creazione di un pacchetto NuGet sono stati spostati da file *project.json* a file con estensione *csproj*.</span><span class="sxs-lookup"><span data-stu-id="ffb78-215">With the move to MSBuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="ffb78-216">Gli input sono proprietà di MSBuild, quindi devono trovarsi all'interno di un gruppo `<PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-216">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="ffb78-217">L'elenco seguente include le proprietà usate come input per il processo di creazione del pacchetto quando si usa il comando `dotnet pack` o la destinazione di MSBuild `Pack` che fa parte dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="ffb78-217">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK.</span></span> 

### <a name="ispackable"></a><span data-ttu-id="ffb78-218">IsPackable</span><span class="sxs-lookup"><span data-stu-id="ffb78-218">IsPackable</span></span>
<span data-ttu-id="ffb78-219">Valore booleano che specifica se dal progetto può essere creato un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-219">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="ffb78-220">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-220">The default value is `true`.</span></span> 

### <a name="packageversion"></a><span data-ttu-id="ffb78-221">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="ffb78-221">PackageVersion</span></span>
<span data-ttu-id="ffb78-222">Specifica la versione che avrà il pacchetto risultante.</span><span class="sxs-lookup"><span data-stu-id="ffb78-222">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="ffb78-223">Accetta tutte le forme della stringa di versione NuGet.</span><span class="sxs-lookup"><span data-stu-id="ffb78-223">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="ffb78-224">Il valore predefinito corrisponde al valore di `$(Version)`, vale a dire della proprietà `Version` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-224">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span> 

### <a name="packageid"></a><span data-ttu-id="ffb78-225">PackageId</span><span class="sxs-lookup"><span data-stu-id="ffb78-225">PackageId</span></span>
<span data-ttu-id="ffb78-226">Specifica il nome del pacchetto risultante.</span><span class="sxs-lookup"><span data-stu-id="ffb78-226">Specifies the name for the resulting package.</span></span> <span data-ttu-id="ffb78-227">Se non specificato, l'impostazione predefinita per l'operazione `pack` corrisponde all'uso di `AssemblyName` o del nome della directory come nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-227">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span> 

### <a name="title"></a><span data-ttu-id="ffb78-228">Titolo</span><span class="sxs-lookup"><span data-stu-id="ffb78-228">Title</span></span>
<span data-ttu-id="ffb78-229">Titolo del pacchetto facilmente comprensibile per l'utente, usato di solito per la visualizzazione dell'interfaccia utente, ad esempio in nuget.org e in Gestione pacchetti in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ffb78-229">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="ffb78-230">Se non specificato, viene usato l'ID del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-230">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="ffb78-231">Autori</span><span class="sxs-lookup"><span data-stu-id="ffb78-231">Authors</span></span>
<span data-ttu-id="ffb78-232">Elenco con valori delimitati da punto e virgola di autori di pacchetti, corrispondenti ai nomi di profilo in nuget.org. Questi, visualizzati nella raccolta NuGet in nuget.org, vengono usati per creare riferimenti incrociati ai pacchetti dello stesso autore.</span><span class="sxs-lookup"><span data-stu-id="ffb78-232">A semicolon-separated list of packages authors, matching the profile names on nuget.org. These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="packagedescription"></a><span data-ttu-id="ffb78-233">PackageDescription</span><span class="sxs-lookup"><span data-stu-id="ffb78-233">PackageDescription</span></span>

<span data-ttu-id="ffb78-234">Descrizione lunga del pacchetto per la visualizzazione dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ffb78-234">A long description of the package for UI display.</span></span>

### <a name="description"></a><span data-ttu-id="ffb78-235">Description</span><span class="sxs-lookup"><span data-stu-id="ffb78-235">Description</span></span>
<span data-ttu-id="ffb78-236">Descrizione lunga per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="ffb78-236">A long description for the assembly.</span></span> <span data-ttu-id="ffb78-237">Se `PackageDescription` non è specificata, questa proprietà viene usata anche come descrizione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-237">If `PackageDescription` is not specified then this property is also used as the description of the package.</span></span>

### <a name="copyright"></a><span data-ttu-id="ffb78-238">Copyright</span><span class="sxs-lookup"><span data-stu-id="ffb78-238">Copyright</span></span>
<span data-ttu-id="ffb78-239">Informazioni sul copyright per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-239">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="ffb78-240">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="ffb78-240">PackageRequireLicenseAcceptance</span></span>
<span data-ttu-id="ffb78-241">Valore booleano che specifica se il client deve richiedere al consumer di accettare la licenza del pacchetto prima di installarlo.</span><span class="sxs-lookup"><span data-stu-id="ffb78-241">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="ffb78-242">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-242">The default is `false`.</span></span>

### <a name="packagelicenseexpression"></a><span data-ttu-id="ffb78-243">PackageLicenseExpression</span><span class="sxs-lookup"><span data-stu-id="ffb78-243">PackageLicenseExpression</span></span>

<span data-ttu-id="ffb78-244">Un [identificatore di licenza SPDX](https://spdx.org/licenses/) o un'espressione.</span><span class="sxs-lookup"><span data-stu-id="ffb78-244">An [SPDX license identifier](https://spdx.org/licenses/) or expression.</span></span> <span data-ttu-id="ffb78-245">Ad esempio `Apache-2.0`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-245">For example, `Apache-2.0`.</span></span>

<span data-ttu-id="ffb78-246">Ecco l'elenco completo degli [identificatori di licenza SPDX](https://spdx.org/licenses/).</span><span class="sxs-lookup"><span data-stu-id="ffb78-246">Here is the complete list of [SPDX license identifiers](https://spdx.org/licenses/).</span></span> <span data-ttu-id="ffb78-247">NuGet.org accetta solo licenze approvate OSI o FSF quando si usa un'espressione del tipo di licenza.</span><span class="sxs-lookup"><span data-stu-id="ffb78-247">NuGet.org accepts only OSI or FSF approved licenses when using license type expression.</span></span>

<span data-ttu-id="ffb78-248">La sintassi esatta delle espressioni di licenza è descritta di seguito in [ABNF](https://tools.ietf.org/html/rfc5234).</span><span class="sxs-lookup"><span data-stu-id="ffb78-248">The exact syntax of the license expressions is described below in [ABNF](https://tools.ietf.org/html/rfc5234).</span></span>
```cli
license-id            = <short form license identifier from https://spdx.org/spdx-specification-21-web-version#h.luq9dgcle9mo>

license-exception-id  = <short form license exception identifier from https://spdx.org/spdx-specification-21-web-version#h.ruv3yl8g6czd>

simple-expression = license-id / license-id”+”

compound-expression =  1*1(simple-expression /
                simple-expression "WITH" license-exception-id /
                compound-expression "AND" compound-expression /
                compound-expression "OR" compound-expression ) /                
                "(" compound-expression ")" )

license-expression =  1*1(simple-expression / compound-expression / UNLICENSED)
```

> [!NOTE]
> <span data-ttu-id="ffb78-249">È possibile specificare solo uno degli elementi `PackageLicenseExpression`, `PackageLicenseFile` e `PackageLicenseUrl` contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="ffb78-249">Only one of `PackageLicenseExpression`, `PackageLicenseFile` and `PackageLicenseUrl` can be specified at a time.</span></span>

### <a name="packagelicensefile"></a><span data-ttu-id="ffb78-250">PackageLicenseFile</span><span class="sxs-lookup"><span data-stu-id="ffb78-250">PackageLicenseFile</span></span>

<span data-ttu-id="ffb78-251">Percorso di un file di licenza all'interno del pacchetto se si usa una licenza a cui non è stato assegnato un identificatore SPDX oppure una licenza personalizzata (in caso contrario, è preferibile l'elemento `PackageLicenseExpression`)</span><span class="sxs-lookup"><span data-stu-id="ffb78-251">Path to a license file within the package if you are using a license that hasn’t been assigned an SPDX identifier, or it is a custom license (Otherwise `PackageLicenseExpression` is prefered)</span></span>

<span data-ttu-id="ffb78-252">Sostituisce `PackageLicenseUrl`, non può essere combinato con `PackageLicenseExpression` e richiede Visual Studio 15.9.4, .NET SDK 2.1.502 o 2.2.101 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="ffb78-252">Replaces `PackageLicenseUrl`, can't be combined with `PackageLicenseExpression` and requires Visual Studio 15.9.4, .NET SDK 2.1.502 or 2.2.101, or newer.</span></span>

<span data-ttu-id="ffb78-253">Sarà necessario assicurarsi che il file di licenza venga incluso nel pacchetto aggiungendolo in modo esplicito al progetto, come in questo esempio di utilizzo:</span><span class="sxs-lookup"><span data-stu-id="ffb78-253">You will need to ensure the license file is packed by adding it explicitly to the project, example usage:</span></span>
```xml
<PropertyGroup>
  <PackageLicenseFile>LICENSE.txt</PackageLicenseFile>
</PropertyGroup>
<ItemGroup>
  <None Include="licenses\LICENSE.txt" Pack="true" PackagePath="$(PackageLicenseFile)"/>
</ItemGroup>
```

### <a name="packagelicenseurl"></a><span data-ttu-id="ffb78-254">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="ffb78-254">PackageLicenseUrl</span></span>

<span data-ttu-id="ffb78-255">URL della licenza applicabile al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-255">An URL to the license that is applicable to the package.</span></span> <span data-ttu-id="ffb78-256">(_deprecato da Visual Studio 15.9.4, .NET SDK 2.1.502 e 2.2.101_)</span><span class="sxs-lookup"><span data-stu-id="ffb78-256">(_deprecated since Visual Studio 15.9.4, .NET SDK 2.1.502 and 2.2.101_)</span></span>


### <a name="packageiconurl"></a><span data-ttu-id="ffb78-257">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="ffb78-257">PackageIconUrl</span></span>
<span data-ttu-id="ffb78-258">URL di un'immagine 64 x 64 con sfondo trasparente da usare come icona per il pacchetto nella visualizzazione dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ffb78-258">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="ffb78-259">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="ffb78-259">PackageReleaseNotes</span></span>
<span data-ttu-id="ffb78-260">Note sulla versione per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-260">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="ffb78-261">PackageTags</span><span class="sxs-lookup"><span data-stu-id="ffb78-261">PackageTags</span></span>
<span data-ttu-id="ffb78-262">Elenco di tag con valori delimitati da punto e virgola che designa il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-262">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="ffb78-263">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="ffb78-263">PackageOutputPath</span></span>
<span data-ttu-id="ffb78-264">Determina il percorso di output in cui verrà rilasciato il pacchetto creato.</span><span class="sxs-lookup"><span data-stu-id="ffb78-264">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="ffb78-265">Il valore predefinito è `$(OutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-265">Default is `$(OutputPath)`.</span></span> 

### <a name="includesymbols"></a><span data-ttu-id="ffb78-266">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="ffb78-266">IncludeSymbols</span></span>
<span data-ttu-id="ffb78-267">Valore booleano che indica se al momento della creazione del pacchetto deve essere creato un pacchetto aggiuntivo di simboli.</span><span class="sxs-lookup"><span data-stu-id="ffb78-267">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="ffb78-268">Questo pacchetto, con estensione *.symbols.nupkg*, copierà i file PDB insieme ai file DLL e ad altri file di output.</span><span class="sxs-lookup"><span data-stu-id="ffb78-268">This package will have a *.symbols.nupkg* extension and will copy the PDB files along with the DLL and other output files.</span></span>

### <a name="includesource"></a><span data-ttu-id="ffb78-269">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="ffb78-269">IncludeSource</span></span>
<span data-ttu-id="ffb78-270">Valore booleano che indica se il processo di creazione del pacchetto deve creare un pacchetto di origine.</span><span class="sxs-lookup"><span data-stu-id="ffb78-270">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="ffb78-271">Il pacchetto di origine contiene il codice sorgente della libreria, nonché i file PDB.</span><span class="sxs-lookup"><span data-stu-id="ffb78-271">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="ffb78-272">I file di origine vengono posizionati nella directory `src/ProjectName` del file del pacchetto risultante.</span><span class="sxs-lookup"><span data-stu-id="ffb78-272">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span> 

### <a name="istool"></a><span data-ttu-id="ffb78-273">IsTool</span><span class="sxs-lookup"><span data-stu-id="ffb78-273">IsTool</span></span>
<span data-ttu-id="ffb78-274">Specifica se tutti i file di output devono essere copiati nella cartella *tools* anziché nella cartella *lib*.</span><span class="sxs-lookup"><span data-stu-id="ffb78-274">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="ffb78-275">È diverso da `DotNetCliTool`, che viene specificato impostando `PackageType` nel file *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="ffb78-275">Note that this is different from a `DotNetCliTool` which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="ffb78-276">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="ffb78-276">RepositoryUrl</span></span>
<span data-ttu-id="ffb78-277">Specifica l'URL per l'archivio in cui si trova il codice sorgente per il pacchetto e/o da cui il codice sorgente viene compilato.</span><span class="sxs-lookup"><span data-stu-id="ffb78-277">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span> 

### <a name="repositorytype"></a><span data-ttu-id="ffb78-278">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="ffb78-278">RepositoryType</span></span>
<span data-ttu-id="ffb78-279">Specifica il tipo dell'archivio.</span><span class="sxs-lookup"><span data-stu-id="ffb78-279">Specifies the type of the repository.</span></span> <span data-ttu-id="ffb78-280">Il valore predefinito è "git".</span><span class="sxs-lookup"><span data-stu-id="ffb78-280">Default is "git".</span></span> 

### <a name="nopackageanalysis"></a><span data-ttu-id="ffb78-281">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="ffb78-281">NoPackageAnalysis</span></span>
<span data-ttu-id="ffb78-282">Specifica che pack non deve eseguire l'analisi del pacchetto dopo la compilazione di quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="ffb78-282">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="ffb78-283">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="ffb78-283">MinClientVersion</span></span>
<span data-ttu-id="ffb78-284">Specifica la versione minima del client NuGet, imposta da nuget.exe e da Gestione pacchetti di Visual Studio, che può installare questo pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-284">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="ffb78-285">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="ffb78-285">IncludeBuildOutput</span></span>
<span data-ttu-id="ffb78-286">Valore booleano che specifica se gli assembly di output di compilazione devono essere compresi nel file *.nupkg*.</span><span class="sxs-lookup"><span data-stu-id="ffb78-286">This Boolean values specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="ffb78-287">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="ffb78-287">IncludeContentInPack</span></span>
<span data-ttu-id="ffb78-288">Questo valore booleano specifica se gli elementi con tipo `Content` verranno inclusi automaticamente nel pacchetto risultante.</span><span class="sxs-lookup"><span data-stu-id="ffb78-288">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="ffb78-289">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-289">The default is `true`.</span></span> 

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="ffb78-290">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="ffb78-290">BuildOutputTargetFolder</span></span>
<span data-ttu-id="ffb78-291">Specifica la cartella in cui inserire gli assembly di output.</span><span class="sxs-lookup"><span data-stu-id="ffb78-291">Specifies the folder where to place the output assemblies.</span></span> <span data-ttu-id="ffb78-292">Gli assembly di output (e altri file di output) vengono copiati nelle rispettive cartelle per framework.</span><span class="sxs-lookup"><span data-stu-id="ffb78-292">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="ffb78-293">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="ffb78-293">ContentTargetFolders</span></span>
<span data-ttu-id="ffb78-294">Questa proprietà specifica il percorso predefinito in cui devono essere posizionati tutti i file di contenuto se per tali file `PackagePath` non è specificato.</span><span class="sxs-lookup"><span data-stu-id="ffb78-294">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="ffb78-295">Il valore predefinito è "content;contentFiles".</span><span class="sxs-lookup"><span data-stu-id="ffb78-295">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="ffb78-296">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="ffb78-296">NuspecFile</span></span>
<span data-ttu-id="ffb78-297">Percorso relativo o assoluto per il file *.nuspec* usato per la creazione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ffb78-297">Relative or absolute path to the *.nuspec* file being used for packing.</span></span> 

> [!NOTE]
> <span data-ttu-id="ffb78-298">Se il file *.nuspec* è specificato, viene usato **esclusivamente** per le informazioni di creazione del pacchetto e le informazioni nei progetti non vengono usate.</span><span class="sxs-lookup"><span data-stu-id="ffb78-298">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span> 

### <a name="nuspecbasepath"></a><span data-ttu-id="ffb78-299">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="ffb78-299">NuspecBasePath</span></span>
<span data-ttu-id="ffb78-300">Percorso di base per il file *.nuspec*.</span><span class="sxs-lookup"><span data-stu-id="ffb78-300">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="ffb78-301">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="ffb78-301">NuspecProperties</span></span>
<span data-ttu-id="ffb78-302">Elenco con valori delimitati da punto e virgola di coppie chiave=valore.</span><span class="sxs-lookup"><span data-stu-id="ffb78-302">Semicolon separated list of key=value pairs.</span></span>

## <a name="assemblyinfo-properties"></a><span data-ttu-id="ffb78-303">Proprietà AssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="ffb78-303">AssemblyInfo properties</span></span>
<span data-ttu-id="ffb78-304">Gli [attributi dell'assembly](../../framework/app-domains/set-assembly-attributes.md) che in genere erano presenti in un file *AssemblyInfo* ora vengono automaticamente generati dalle proprietà.</span><span class="sxs-lookup"><span data-stu-id="ffb78-304">[Assembly attributes](../../framework/app-domains/set-assembly-attributes.md) that were typically present in an *AssemblyInfo* file are now automatically generated from properties.</span></span>

### <a name="properties-per-attribute"></a><span data-ttu-id="ffb78-305">Proprietà dei singoli attributi</span><span class="sxs-lookup"><span data-stu-id="ffb78-305">Properties per attribute</span></span>

<span data-ttu-id="ffb78-306">Ogni attributo ha una proprietà che ne controlla il contenuto e un'altra per disabilitarne la generazione, come illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="ffb78-306">Each attribute has a property that control its content and another to disable its generation as shown in the following table:</span></span>

| <span data-ttu-id="ffb78-307">Attributo</span><span class="sxs-lookup"><span data-stu-id="ffb78-307">Attribute</span></span>                                                      | <span data-ttu-id="ffb78-308">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ffb78-308">Property</span></span>               | <span data-ttu-id="ffb78-309">Proprietà da disabilitare</span><span class="sxs-lookup"><span data-stu-id="ffb78-309">Property to disable</span></span>                             |
|----------------------------------------------------------------|------------------------|-------------------------------------------------|
| <xref:System.Reflection.AssemblyCompanyAttribute>              | `Company`              | `GenerateAssemblyCompanyAttribute`              |
| <xref:System.Reflection.AssemblyConfigurationAttribute>        | `Configuration`        | `GenerateAssemblyConfigurationAttribute`        |
| <xref:System.Reflection.AssemblyCopyrightAttribute>            | `Copyright`            | `GenerateAssemblyCopyrightAttribute`            |
| <xref:System.Reflection.AssemblyDescriptionAttribute>          | `Description`          | `GenerateAssemblyDescriptionAttribute`          |
| <xref:System.Reflection.AssemblyFileVersionAttribute>          | `FileVersion`          | `GenerateAssemblyFileVersionAttribute`          |
| <xref:System.Reflection.AssemblyInformationalVersionAttribute> | `InformationalVersion` | `GenerateAssemblyInformationalVersionAttribute` |
| <xref:System.Reflection.AssemblyProductAttribute>              | `Product`              | `GenerateAssemblyProductAttribute`              |
| <xref:System.Reflection.AssemblyTitleAttribute>                | `AssemblyTitle`        | `GenerateAssemblyTitleAttribute`                |
| <xref:System.Reflection.AssemblyVersionAttribute>              | `AssemblyVersion`      | `GenerateAssemblyVersionAttribute`              |
| <xref:System.Resources.NeutralResourcesLanguageAttribute>      | `NeutralLanguage`      | `GenerateNeutralResourcesLanguageAttribute`     |

<span data-ttu-id="ffb78-310">Note:</span><span class="sxs-lookup"><span data-stu-id="ffb78-310">Notes:</span></span>

* <span data-ttu-id="ffb78-311">Per impostazione predefinita, `AssemblyVersion` e `FileVersion` usano il valore di `$(Version)` senza suffisso.</span><span class="sxs-lookup"><span data-stu-id="ffb78-311">`AssemblyVersion` and `FileVersion` default is to take the value of `$(Version)` without suffix.</span></span> <span data-ttu-id="ffb78-312">Se ad esempio `$(Version)` è `1.2.3-beta.4`, il valore sarà `1.2.3`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-312">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
* <span data-ttu-id="ffb78-313">Il valore predefinito di `InformationalVersion` è `$(Version)`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-313">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
* <span data-ttu-id="ffb78-314">A `InformationalVersion` viene aggiunto `$(SourceRevisionId)` se la proprietà è presente.</span><span class="sxs-lookup"><span data-stu-id="ffb78-314">`InformationalVersion` has `$(SourceRevisionId)` appended if the property is present.</span></span> <span data-ttu-id="ffb78-315">Può essere disabilitata usando `IncludeSourceRevisionInInformationalVersion`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-315">It can be disabled using `IncludeSourceRevisionInInformationalVersion`.</span></span>
* <span data-ttu-id="ffb78-316">Le proprietà `Copyright` e `Description` vengono usate anche per i metadati NuGet.</span><span class="sxs-lookup"><span data-stu-id="ffb78-316">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
* <span data-ttu-id="ffb78-317">`Configuration` viene condivisa con tutto il processo di compilazione e impostata tramite il parametro `--configuration` dei comandi `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-317">`Configuration` is shared with all the build process and set via the `--configuration` parameter of `dotnet` commands.</span></span>

### <a name="generateassemblyinfo"></a><span data-ttu-id="ffb78-318">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="ffb78-318">GenerateAssemblyInfo</span></span> 
<span data-ttu-id="ffb78-319">Valore booleano che abilita o disabilita tutta la generazione di AssemblyInfo.</span><span class="sxs-lookup"><span data-stu-id="ffb78-319">A Boolean that enable or disable all the AssemblyInfo generation.</span></span> <span data-ttu-id="ffb78-320">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="ffb78-320">The default value is `true`.</span></span> 

### <a name="generatedassemblyinfofile"></a><span data-ttu-id="ffb78-321">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="ffb78-321">GeneratedAssemblyInfoFile</span></span> 
<span data-ttu-id="ffb78-322">Percorso del file di informazioni sull'assembly generato.</span><span class="sxs-lookup"><span data-stu-id="ffb78-322">The path of the generated assembly info file.</span></span> <span data-ttu-id="ffb78-323">L'impostazione predefinita è un file nella directory `$(IntermediateOutputPath)` (obj).</span><span class="sxs-lookup"><span data-stu-id="ffb78-323">Default to a file in the `$(IntermediateOutputPath)` (obj) directory.</span></span>
