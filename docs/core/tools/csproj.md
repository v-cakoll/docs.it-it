---
title: Aggiunte al formato csproj per .NET Core
description: Informazioni sulle differenze tra i file csproj esistenti e .NET Core
ms.date: 04/08/2019
ms.openlocfilehash: 4a05709da63c4f6a200039ba5dd59358c700130e
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899875"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="57a71-103">Aggiunte al formato csproj per .NET Core</span><span class="sxs-lookup"><span data-stu-id="57a71-103">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="57a71-104">Questo documento descrive le modifiche aggiunte ai file di progetto nell'ambito del passaggio da *project.json* a *csproj* e a [MSBuild](https://github.com/Microsoft/MSBuild).</span><span class="sxs-lookup"><span data-stu-id="57a71-104">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="57a71-105">Per altre informazioni sulla sintassi generale dei file di progetto e informazioni di riferimento, vedere la documentazione del [file di progetto MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="57a71-105">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>

## <a name="implicit-package-references"></a><span data-ttu-id="57a71-106">Riferimenti impliciti al pacchetto</span><span class="sxs-lookup"><span data-stu-id="57a71-106">Implicit package references</span></span>

<span data-ttu-id="57a71-107">È possibile fare riferimento ai metapacchetti in modo implicito in base ai framework di destinazione specificati nella proprietà `<TargetFramework>` o `<TargetFrameworks>` del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-107">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="57a71-108">`<TargetFrameworks>` viene ignorato se è specificato `<TargetFramework>`, indipendentemente dall'ordine.</span><span class="sxs-lookup"><span data-stu-id="57a71-108">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span> <span data-ttu-id="57a71-109">Per altre informazioni, vedere [Pacchetti, metapacchetti e framework](../packages.md).</span><span class="sxs-lookup"><span data-stu-id="57a71-109">For more information, see [Packages, metapackages and frameworks](../packages.md).</span></span> 

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

### <a name="recommendations"></a><span data-ttu-id="57a71-110">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="57a71-110">Recommendations</span></span>

<span data-ttu-id="57a71-111">Poiché si fa riferimento ai metapacchetti `Microsoft.NETCore.App` o `NETStandard.Library` in modo implicito, ecco le procedure consigliate:</span><span class="sxs-lookup"><span data-stu-id="57a71-111">Since `Microsoft.NETCore.App` or `NETStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

- <span data-ttu-id="57a71-112">Quando la destinazione è .NET Core o .NET Standard, non fare mai riferimento in modo esplicito ai metapacchetti `Microsoft.NETCore.App` o `NETStandard.Library` tramite l'elemento `<PackageReference>` nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-112">When targeting .NET Core or .NET Standard, never have an explicit reference to the `Microsoft.NETCore.App` or `NETStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
- <span data-ttu-id="57a71-113">Se occorre una versione specifica del runtime quando la destinazione è .NET Core, è necessario usare la proprietà `<RuntimeFrameworkVersion>` del progetto, ad esempio, `1.0.4`, anziché fare riferimento al metapacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-113">If you need a specific version of the runtime when targeting .NET Core, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
  - <span data-ttu-id="57a71-114">Ciò può avvenire se si usano [distribuzioni autosufficienti](../deploying/index.md#self-contained-deployments-scd) e occorre una versione specifica, ad esempio, della patch del runtime 1.0.0 LTS.</span><span class="sxs-lookup"><span data-stu-id="57a71-114">This might happen if you are using [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
- <span data-ttu-id="57a71-115">Se occorre una versione specifica del metapacchetto `NETStandard.Library` quando la destinazione è .NET Standard, è possibile usare la proprietà `<NetStandardImplicitPackageVersion>` e impostare la versione necessaria.</span><span class="sxs-lookup"><span data-stu-id="57a71-115">If you need a specific version of the `NETStandard.Library` metapackage when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>
- <span data-ttu-id="57a71-116">Non aggiungere o aggiornare in modo esplicito i riferimenti al metapacchetto `Microsoft.NETCore.App` o `NETStandard.Library` nei progetti .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="57a71-116">Don't explicitly add or update references to either the `Microsoft.NETCore.App` or `NETStandard.Library` metapackage in .NET Framework projects.</span></span> <span data-ttu-id="57a71-117">Se è necessaria qualsiasi versione di `NETStandard.Library` durante l'uso di un pacchetto NuGet basato su .NET Standard, NuGet installa automaticamente tale versione.</span><span class="sxs-lookup"><span data-stu-id="57a71-117">If any version of `NETStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>

## <a name="implicit-version-for-some-package-references"></a><span data-ttu-id="57a71-118">Versione implicita per alcuni riferimenti al pacchetto</span><span class="sxs-lookup"><span data-stu-id="57a71-118">Implicit version for some package references</span></span>

<span data-ttu-id="57a71-119">La maggior parte degli utilizzi di [`<PackageReference>`](#packagereference) richiede l'impostazione dell'attributo `Version` per specificare la versione del pacchetto NuGet da usare.</span><span class="sxs-lookup"><span data-stu-id="57a71-119">Most usages of [`<PackageReference>`](#packagereference) require setting the `Version` attribute to specify the NuGet package version to be used.</span></span> <span data-ttu-id="57a71-120">Se però si usa .NET Core 2.1 o 2.2 e si fa riferimento a [Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) o [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage), l'attributo non è necessario.</span><span class="sxs-lookup"><span data-stu-id="57a71-120">When using .NET Core 2.1 or 2.2 and referencing [Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) or [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage), however, the  attribute is unnecessary.</span></span> <span data-ttu-id="57a71-121">.NET Core SDK può selezionare automaticamente la versione dei pacchetti che deve essere usata.</span><span class="sxs-lookup"><span data-stu-id="57a71-121">The .NET Core SDK can automatically select the version of these packages that should be used.</span></span>

### <a name="recommendation"></a><span data-ttu-id="57a71-122">Indicazione</span><span class="sxs-lookup"><span data-stu-id="57a71-122">Recommendation</span></span>

<span data-ttu-id="57a71-123">Quando si fa riferimento ai pacchetti `Microsoft.AspNetCore.App` o `Microsoft.AspNetCore.All`, non specificarne la versione.</span><span class="sxs-lookup"><span data-stu-id="57a71-123">When referencing the `Microsoft.AspNetCore.App` or `Microsoft.AspNetCore.All` packages, do not specify their version.</span></span> <span data-ttu-id="57a71-124">Se si specifica una versione, l'SDK potrebbe visualizzare l'avviso NETSDK1071.</span><span class="sxs-lookup"><span data-stu-id="57a71-124">If a version is specified, the SDK may produce warning NETSDK1071.</span></span> <span data-ttu-id="57a71-125">Per non visualizzare più questo avviso, rimuovere la versione del pacchetto come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="57a71-125">To fix this warning, remove the package version like in the following example:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore.App" />
</ItemGroup>
```

> <span data-ttu-id="57a71-126">Problema noto: .NET Core 2.1 SDK supportava questa sintassi solo quando il progetto usa anche Microsoft.NET.Sdk.Web.</span><span class="sxs-lookup"><span data-stu-id="57a71-126">Known issue: the .NET Core 2.1 SDK only supported this syntax when the project also uses Microsoft.NET.Sdk.Web.</span></span> <span data-ttu-id="57a71-127">Questo problema è stato risolto in .NET Core SDK 2.2.</span><span class="sxs-lookup"><span data-stu-id="57a71-127">This is resolved in the .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="57a71-128">Questi riferimenti ai metapacchetti ASP.NET Core hanno un comportamento leggermente diverso dalla maggior parte dei normali pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="57a71-128">These references to ASP.NET Core metapackages have a slightly different behavior from most normal NuGet packages.</span></span> <span data-ttu-id="57a71-129">Le [distribuzioni dipendenti dal framework](../deploying/index.md#framework-dependent-deployments-fdd) delle applicazioni che usano questi metapacchetti sfruttano automaticamente il framework condiviso di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="57a71-129">[Framework-dependent deployments](../deploying/index.md#framework-dependent-deployments-fdd) of applications that use these metapackages automatically take advantage of the ASP.NET Core shared framework.</span></span> <span data-ttu-id="57a71-130">Quando si usano i metapacchetti, con l'applicazione **non** vengono distribuiti asset dai pacchetti NuGet di riferimento di ASP.NET Core. Questi asset sono infatti inclusi nel framework condiviso di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="57a71-130">When you use the metapackages, **no** assets from the referenced ASP.NET Core NuGet packages are deployed with the application—the ASP.NET Core shared framework contains these assets.</span></span> <span data-ttu-id="57a71-131">Gli asset contenuti nel framework condiviso sono ottimizzati per la piattaforma di destinazione per migliorare i tempi di avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="57a71-131">The assets in the shared framework are optimized for the target platform to improve application startup time.</span></span> <span data-ttu-id="57a71-132">Per altre informazioni sul framework condiviso, vedere [Creazione di pacchetti di distribuzione di .NET Core](../build/distribution-packaging.md).</span><span class="sxs-lookup"><span data-stu-id="57a71-132">For more information about shared framework, see [.NET Core distribution packaging](../build/distribution-packaging.md).</span></span>

<span data-ttu-id="57a71-133">Se *è* specificata una versione, questa viene considerata come la versione *minima* del framework condiviso ASP.NET Core per le distribuzioni dipendenti dal framework e come una versione *esatta* per le distribuzioni autonome.</span><span class="sxs-lookup"><span data-stu-id="57a71-133">If a version *is* specified, it's treated as the *minimum* version of ASP.NET Core shared framework for framework-dependent deployments and as an *exact* version for self-contained deployments.</span></span> <span data-ttu-id="57a71-134">Questo comportamento può avere le conseguenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="57a71-134">This can have the following consequences:</span></span>

- <span data-ttu-id="57a71-135">Se la versione di ASP.NET Core installata nel server è inferiore alla versione specificata in PackageReference, l'avvio del processo .NET Core non riesce.</span><span class="sxs-lookup"><span data-stu-id="57a71-135">If the version of ASP.NET Core installed on the server is less than the version specified on the PackageReference, the .NET Core process fails to launch.</span></span> <span data-ttu-id="57a71-136">Gli aggiornamenti per il metapacchetto sono spesso disponibili su NuGet.org prima che vengano resi disponibili in ambienti di hosting come Azure.</span><span class="sxs-lookup"><span data-stu-id="57a71-136">Updates to the metapackage are often available on NuGet.org before updates have been made available in hosting environments such as Azure.</span></span> <span data-ttu-id="57a71-137">L'aggiornamento ad ASP.NET Core della versione in PackageReference potrebbe causare un errore in un'applicazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="57a71-137">Updating the version on the PackageReference to ASP.NET Core could cause a deployed application to fail.</span></span>
- <span data-ttu-id="57a71-138">Se l'applicazione è stata distribuita come [distribuzione autonoma](../deploying/index.md#self-contained-deployments-scd), potrebbe non contenere gli ultimi aggiornamenti della sicurezza a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="57a71-138">If the application is deployed as a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd), the application may not contain the latest security updates to .NET Core.</span></span> <span data-ttu-id="57a71-139">Quando non è specificata una versione, l'SDK può includere automaticamente la versione più recente di ASP.NET Core nella distribuzione autonoma.</span><span class="sxs-lookup"><span data-stu-id="57a71-139">When a version isn't specified, the SDK can automatically include the newest version of ASP.NET Core in the self-contained deployment.</span></span>

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="57a71-140">Dichiarazioni Include di compilazione predefinite nei progetti .NET Core</span><span class="sxs-lookup"><span data-stu-id="57a71-140">Default compilation includes in .NET Core projects</span></span>

<span data-ttu-id="57a71-141">Con il passaggio al formato *csproj* nelle ultime versioni dell'SDK, per gli elementi di compilazione e le risorse incorporate le dichiarazioni Include ed Exclude predefinite sono state spostate nei file delle proprietà dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="57a71-141">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="57a71-142">Ciò significa che non è più necessario specificare queste dichiarazioni nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-142">This means that you no longer need to specify these items in your project file.</span></span>

<span data-ttu-id="57a71-143">Il motivo principale di questo cambiamento è la riduzione del disordine nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-143">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="57a71-144">Le dichiarazioni predefinite presenti nell'SDK coprono i casi di utilizzo più comuni, pertanto non c'è alcuna necessità di ripeterle per ogni progetto creato.</span><span class="sxs-lookup"><span data-stu-id="57a71-144">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="57a71-145">Di conseguenza, i file di progetto sono più piccoli e molto più semplici da comprendere e, se necessario, da modificare manualmente.</span><span class="sxs-lookup"><span data-stu-id="57a71-145">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span>

<span data-ttu-id="57a71-146">La tabella seguente mostra gli elementi e i [GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) Include ed Exclude nell'SDK:</span><span class="sxs-lookup"><span data-stu-id="57a71-146">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span>

| <span data-ttu-id="57a71-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="57a71-147">Element</span></span>           | <span data-ttu-id="57a71-148">GLOB Include</span><span class="sxs-lookup"><span data-stu-id="57a71-148">Include glob</span></span>                              | <span data-ttu-id="57a71-149">GLOB Exclude</span><span class="sxs-lookup"><span data-stu-id="57a71-149">Exclude glob</span></span>                                                  | <span data-ttu-id="57a71-150">GLOB Remove</span><span class="sxs-lookup"><span data-stu-id="57a71-150">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="57a71-151">Compile</span><span class="sxs-lookup"><span data-stu-id="57a71-151">Compile</span></span>           | <span data-ttu-id="57a71-152">\*\*/\*.cs (o altre estensioni del linguaggio)</span><span class="sxs-lookup"><span data-stu-id="57a71-152">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="57a71-153">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="57a71-153">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="57a71-154">N/D</span><span class="sxs-lookup"><span data-stu-id="57a71-154">N/A</span></span>                      |
| <span data-ttu-id="57a71-155">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="57a71-155">EmbeddedResource</span></span>  | <span data-ttu-id="57a71-156">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="57a71-156">\*\*/\*.resx</span></span>                              | <span data-ttu-id="57a71-157">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="57a71-157">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="57a71-158">N/D</span><span class="sxs-lookup"><span data-stu-id="57a71-158">N/A</span></span>                      |
| <span data-ttu-id="57a71-159">nessuna</span><span class="sxs-lookup"><span data-stu-id="57a71-159">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="57a71-160">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="57a71-160">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="57a71-161">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="57a71-161">\*\*/\*.cs; \*\*/\*.resx</span></span>   |

> [!NOTE]
> <span data-ttu-id="57a71-162">Il criterio **GLOB Exclude** esclude sempre le cartelle `./bin` e `./obj`, rappresentate rispettivamente dalle proprietà MSBuild `$(BaseOutputPath)` e `$(BaseIntermediateOutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="57a71-162">**Exclude glob** always excludes the `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, respectively.</span></span> <span data-ttu-id="57a71-163">Nel complesso, tutte le esclusioni sono rappresentate da `$(DefaultItemExcludes)`.</span><span class="sxs-lookup"><span data-stu-id="57a71-163">As a whole, all excludes are represented by `$(DefaultItemExcludes)`.</span></span>

<span data-ttu-id="57a71-164">Se si tenta di compilare un progetto contenente GLOB con l'SDK più recente, viene visualizzato l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="57a71-164">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="57a71-165">Duplicate Compile items were included. (Sono stati inclusi elementi di compilazione duplicati)</span><span class="sxs-lookup"><span data-stu-id="57a71-165">Duplicate Compile items were included.</span></span> <span data-ttu-id="57a71-166">The .NET SDK includes Compile items from your project directory by default. (Per impostazione predefinita, .NET SDK include elementi Compile della directory di progetto)</span><span class="sxs-lookup"><span data-stu-id="57a71-166">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="57a71-167">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file. (Rimuovere questi elementi dal file di progetto o impostare la proprietà 'EnableDefaultCompileItems' su 'false' se li si vuole includere esplicitamente nel file di progetto)</span><span class="sxs-lookup"><span data-stu-id="57a71-167">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span>

<span data-ttu-id="57a71-168">Per ovviare a questo errore, è possibile rimuovere gli elementi `Compile` corrispondenti a quelli elencati nella tabella precedente oppure impostare la proprietà `<EnableDefaultCompileItems>` su `false`, come segue:</span><span class="sxs-lookup"><span data-stu-id="57a71-168">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

<span data-ttu-id="57a71-169">Se si imposta questa proprietà su `false`, si disabilita l'inclusione implicita e viene ripristinato il comportamento degli SDK precedenti, in cui era necessario specificare i GLOB predefiniti nel progetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-169">Setting this property to `false` will disable implicit inclusion, reverting to the behavior of previous SDKs where you had to specify the default globs in your project.</span></span>

<span data-ttu-id="57a71-170">Questa modifica non influisce sulle funzioni principali delle altre dichiarazioni Include.</span><span class="sxs-lookup"><span data-stu-id="57a71-170">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="57a71-171">Se tuttavia si vogliono specificare, ad esempio, alcuni file da pubblicare con l'app, è ancora possibile usare i meccanismi noti in *csproj*, ad esempio l'elemento `<Content>`.</span><span class="sxs-lookup"><span data-stu-id="57a71-171">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

<span data-ttu-id="57a71-172">`<EnableDefaultCompileItems>` disabilita solo i glob `Compile` ma non influisce su altri glob, come il glob implicito `None`, che si applica anche agli elementi \*.cs.</span><span class="sxs-lookup"><span data-stu-id="57a71-172">`<EnableDefaultCompileItems>` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob, which also applies to \*.cs items.</span></span> <span data-ttu-id="57a71-173">Per questo motivo, **Esplora soluzioni** continuerà a visualizzare elementi \*.cs come parte del progetto, inclusi come elementi `None`.</span><span class="sxs-lookup"><span data-stu-id="57a71-173">Because of that, **Solution Explorer** will continue show \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="57a71-174">Analogamente, è possibile impostare `<EnableDefaultNoneItems>` sul False per disabilitare il criterio GLOB `None` implicito nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="57a71-174">In a similar way, you can set `<EnableDefaultNoneItems>` to false to disable the implicit `None` glob, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

<span data-ttu-id="57a71-175">Per disabilitare **tutti i glob impliciti**, è possibile impostare la proprietà `<EnableDefaultItems>` su `false` come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="57a71-175">To disable **all implicit globs**, you can set the `<EnableDefaultItems>` property to `false` as in the following example:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="57a71-176">Visualizzare l'intero progetto come lo vede MSBuild</span><span class="sxs-lookup"><span data-stu-id="57a71-176">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="57a71-177">Mentre le modifiche di csproj semplificano notevolmente i file di progetto, si potrebbe voler vedere il progetto completamente espanso come lo vede MSBuild dopo che vengono inclusi l'SDK e le relative destinazioni.</span><span class="sxs-lookup"><span data-stu-id="57a71-177">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="57a71-178">Pre-elaborare il progetto con [l'opzione `/pp`](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando [`dotnet msbuild`](dotnet-msbuild.md), che specifica i file importati, le relative risorse e i relativi contributi alla build senza compilare il progetto:</span><span class="sxs-lookup"><span data-stu-id="57a71-178">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild -pp:fullproject.xml`

<span data-ttu-id="57a71-179">Se il progetto contiene più framework di destinazione, i risultati del comando devono essere destinati solo a uno di essi specificandolo come proprietà di MSBuild:</span><span class="sxs-lookup"><span data-stu-id="57a71-179">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="57a71-180">Aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="57a71-180">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="57a71-181">Attributo Sdk</span><span class="sxs-lookup"><span data-stu-id="57a71-181">Sdk attribute</span></span>

<span data-ttu-id="57a71-182">L'elemento radice `<Project>` del file con estensione *csproj* ha un nuovo attributo, denominato `Sdk`.</span><span class="sxs-lookup"><span data-stu-id="57a71-182">The root `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="57a71-183">`Sdk` specifica l'SDK che viene usato dal progetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-183">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="57a71-184">l'SDK, come descritto dal [documento sui livelli](cli-msbuild-architecture.md), è un set di [attività](/visualstudio/msbuild/msbuild-tasks) e [destinazioni](/visualstudio/msbuild/msbuild-targets) di MSBuild che consente di compilare codice .NET Core.</span><span class="sxs-lookup"><span data-stu-id="57a71-184">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="57a71-185">Per .NET Core sono disponibili gli SDK seguenti:</span><span class="sxs-lookup"><span data-stu-id="57a71-185">The following SDKs are available for .NET Core:</span></span>

1. <span data-ttu-id="57a71-186">.NET Core SDK con l'ID di `Microsoft.NET.Sdk`</span><span class="sxs-lookup"><span data-stu-id="57a71-186">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="57a71-187">.NET Core Web SDK con l'ID di `Microsoft.NET.Sdk.Web`</span><span class="sxs-lookup"><span data-stu-id="57a71-187">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>
3. <span data-ttu-id="57a71-188">.NET Core Razor Class Library SDK con l'ID di `Microsoft.NET.Sdk.Razor`</span><span class="sxs-lookup"><span data-stu-id="57a71-188">The .NET Core Razor Class Library SDK with the ID of `Microsoft.NET.Sdk.Razor`</span></span>
4. <span data-ttu-id="57a71-189">Il servizio del ruolo di lavoro di .NET Core con ID `Microsoft.NET.Sdk.Worker` (a partire da .NET Core 3,0)</span><span class="sxs-lookup"><span data-stu-id="57a71-189">The .NET Core Worker Service with the ID of `Microsoft.NET.Sdk.Worker` (since .NET Core 3.0)</span></span>
5. <span data-ttu-id="57a71-190">WinForms di .NET Core e WPF con ID `Microsoft.NET.Sdk.WindowsDesktop` (a partire da .NET Core 3,0)</span><span class="sxs-lookup"><span data-stu-id="57a71-190">The .NET Core WinForms and WPF with the ID of `Microsoft.NET.Sdk.WindowsDesktop` (since .NET Core 3.0)</span></span>

<span data-ttu-id="57a71-191">Per usare gli strumenti di .NET Core e compilare il codice, è necessario impostare l'attributo `Sdk` su uno di questi ID nell'elemento `<Project>`.</span><span class="sxs-lookup"><span data-stu-id="57a71-191">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span>

### <a name="packagereference"></a><span data-ttu-id="57a71-192">PackageReference</span><span class="sxs-lookup"><span data-stu-id="57a71-192">PackageReference</span></span>

<span data-ttu-id="57a71-193">Un elemento `<PackageReference>` specifica una [dipendenza NuGet nel progetto](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="57a71-193">A `<PackageReference>` item element specifies a [NuGet dependency in the project](/nuget/consume-packages/package-references-in-project-files).</span></span> <span data-ttu-id="57a71-194">L'attributo `Include` specifica l'ID del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-194">The `Include` attribute specifies the package ID.</span></span>

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="57a71-195">Versione</span><span class="sxs-lookup"><span data-stu-id="57a71-195">Version</span></span>

<span data-ttu-id="57a71-196">L'attributo `Version` obbligatorio specifica la versione del pacchetto da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="57a71-196">The required `Version` attribute specifies the version of the package to restore.</span></span> <span data-ttu-id="57a71-197">L'attributo rispetta le regole dello schema di [numerazione delle versioni NuGet](/nuget/reference/package-versioning#version-ranges-and-wildcards).</span><span class="sxs-lookup"><span data-stu-id="57a71-197">The attribute respects the rules of the [NuGet versioning](/nuget/reference/package-versioning#version-ranges-and-wildcards) scheme.</span></span> <span data-ttu-id="57a71-198">Il comportamento predefinito prevede la corrispondenza esatta della versione.</span><span class="sxs-lookup"><span data-stu-id="57a71-198">The default behavior is an exact version match.</span></span> <span data-ttu-id="57a71-199">Ad esempio, specificare `Version="1.2.3"` equivale alla notazione NuGet `[1.2.3]` per la versione esatta 1.2.3 del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-199">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="57a71-200">IncludeAssets, ExcludeAssets e PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="57a71-200">IncludeAssets, ExcludeAssets and PrivateAssets</span></span>

<span data-ttu-id="57a71-201">L'attributo `IncludeAssets` specifica gli asset appartenenti al pacchetto specificato da `<PackageReference>` che devono essere usati.</span><span class="sxs-lookup"><span data-stu-id="57a71-201">`IncludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> <span data-ttu-id="57a71-202">Per impostazione predefinita, sono inclusi tutti gli asset del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-202">By default, all package assets are included.</span></span>

<span data-ttu-id="57a71-203">L'attributo `ExcludeAssets` specifica gli asset appartenenti al pacchetto specificato da `<PackageReference>` che non devono essere usati.</span><span class="sxs-lookup"><span data-stu-id="57a71-203">`ExcludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="57a71-204">L'attributo `PrivateAssets` specifica gli asset appartenenti al pacchetto specificato da `<PackageReference>` che devono essere usati, indicando inoltre che non devono essere trasmessi al progetto successivo.</span><span class="sxs-lookup"><span data-stu-id="57a71-204">`PrivateAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed but not flow to the next project.</span></span> <span data-ttu-id="57a71-205">Gli asset `Analyzers`, `Build` e `ContentFiles` sono privati per impostazione predefinita quando questo attributo non è presente.</span><span class="sxs-lookup"><span data-stu-id="57a71-205">The `Analyzers`, `Build` and `ContentFiles` assets are private by default when this attribute is not present.</span></span>

> [!NOTE]
> <span data-ttu-id="57a71-206">`PrivateAssets` equivale all'elemento `SuppressParent` *Project. json*/*xproj* .</span><span class="sxs-lookup"><span data-stu-id="57a71-206">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="57a71-207">Questi attributi possono contenere uno o più degli elementi seguenti, separati dal carattere punto e virgola `;` se ne vengono elencati vari:</span><span class="sxs-lookup"><span data-stu-id="57a71-207">These attributes can contain one or more of the following items, separated by the semicolon `;` character if more than one is listed:</span></span>

- <span data-ttu-id="57a71-208">`Compile`: i contenuti della cartella *lib* sono disponibili per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="57a71-208">`Compile` – the contents of the *lib* folder are available to compile against.</span></span>
- <span data-ttu-id="57a71-209">`Runtime`: il contenuto della cartella di *Runtime* viene distribuito.</span><span class="sxs-lookup"><span data-stu-id="57a71-209">`Runtime` – the contents of the *runtime* folder are distributed.</span></span>
- <span data-ttu-id="57a71-210">`ContentFiles`: vengono usati i contenuti della cartella *contentfiles*.</span><span class="sxs-lookup"><span data-stu-id="57a71-210">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
- <span data-ttu-id="57a71-211">`Build`: vengono usati i props/targets nella cartella *Build* .</span><span class="sxs-lookup"><span data-stu-id="57a71-211">`Build` – the props/targets in the *build* folder are used.</span></span>
- <span data-ttu-id="57a71-212">`Native`: i contenuti degli asset nativi vengono copiati nella cartella di *output* per il Runtime.</span><span class="sxs-lookup"><span data-stu-id="57a71-212">`Native` – the contents from native assets are copied to the *output* folder for runtime.</span></span>
- <span data-ttu-id="57a71-213">`Analyzers`: vengono usati gli analizzatori.</span><span class="sxs-lookup"><span data-stu-id="57a71-213">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="57a71-214">In alternativa, l'attributo può contenere:</span><span class="sxs-lookup"><span data-stu-id="57a71-214">Alternatively, the attribute can contain:</span></span>

- <span data-ttu-id="57a71-215">`None`: nessuno degli asset viene usato.</span><span class="sxs-lookup"><span data-stu-id="57a71-215">`None` – none of the assets are used.</span></span>
- <span data-ttu-id="57a71-216">`All`: vengono usati tutti gli asset.</span><span class="sxs-lookup"><span data-stu-id="57a71-216">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="57a71-217">DotNetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="57a71-217">DotNetCliToolReference</span></span>

<span data-ttu-id="57a71-218">Un elemento `<DotNetCliToolReference>` specifica lo strumento dell'interfaccia della riga di comando che si vuole ripristinare nel contesto del progetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-218">A `<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="57a71-219">Si tratta di una sostituzione per il nodo `tools` in *project.json*.</span><span class="sxs-lookup"><span data-stu-id="57a71-219">It's a replacement for the `tools` node in *project.json*.</span></span>

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

<span data-ttu-id="57a71-220">Si noti che `DotNetCliToolReference` è [ora deprecato](https://github.com/dotnet/announcements/issues/107) a favore degli [strumenti locali di .NET Core](https://aka.ms/local-tools).</span><span class="sxs-lookup"><span data-stu-id="57a71-220">Note that `DotNetCliToolReference` is [now deprecated](https://github.com/dotnet/announcements/issues/107) in favor of [.NET Core Local Tools](https://aka.ms/local-tools).</span></span>

#### <a name="version"></a><span data-ttu-id="57a71-221">Versione</span><span class="sxs-lookup"><span data-stu-id="57a71-221">Version</span></span>

<span data-ttu-id="57a71-222">`Version` specifica la versione del pacchetto da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="57a71-222">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="57a71-223">L'attributo rispetta le regole dello schema di [numerazione delle versioni NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="57a71-223">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="57a71-224">Il comportamento predefinito prevede la corrispondenza esatta della versione.</span><span class="sxs-lookup"><span data-stu-id="57a71-224">The default behavior is an exact version match.</span></span> <span data-ttu-id="57a71-225">Ad esempio, specificare `Version="1.2.3"` equivale alla notazione NuGet `[1.2.3]` per la versione esatta 1.2.3 del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-225">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="57a71-226">Identificatori di runtime</span><span class="sxs-lookup"><span data-stu-id="57a71-226">RuntimeIdentifiers</span></span>

<span data-ttu-id="57a71-227">L'elemento di proprietà `<RuntimeIdentifiers>` consente di specificare un elenco delimitato da punto e virgola di [identificatori di runtime (RID)](../rid-catalog.md) per il progetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-227">The `<RuntimeIdentifiers>` property element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span>
<span data-ttu-id="57a71-228">I RID consentono di pubblicare distribuzioni autonome.</span><span class="sxs-lookup"><span data-stu-id="57a71-228">RIDs enable publishing self-contained deployments.</span></span>

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="57a71-229">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="57a71-229">RuntimeIdentifier</span></span>

<span data-ttu-id="57a71-230">L'elemento di proprietà `<RuntimeIdentifier>` consente di specificare un solo [identificatore di runtime (RID)](../rid-catalog.md) per il progetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-230">The `<RuntimeIdentifier>` property element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="57a71-231">Il RID consente di pubblicare una distribuzione autonoma.</span><span class="sxs-lookup"><span data-stu-id="57a71-231">The RID enables publishing a self-contained deployment.</span></span>

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

<span data-ttu-id="57a71-232">Usare invece `<RuntimeIdentifiers>` (plurale) se è necessario pubblicare per più runtime.</span><span class="sxs-lookup"><span data-stu-id="57a71-232">Use `<RuntimeIdentifiers>` (plural) instead if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="57a71-233">`<RuntimeIdentifier>` può offrire compilazioni più veloci quando è necessario solo un singolo runtime.</span><span class="sxs-lookup"><span data-stu-id="57a71-233">`<RuntimeIdentifier>` can provide faster builds when only a single runtime is required.</span></span>

### <a name="packagetargetfallback"></a><span data-ttu-id="57a71-234">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="57a71-234">PackageTargetFallback</span></span>

<span data-ttu-id="57a71-235">L'elemento di proprietà `<PackageTargetFallback>` consente di specificare un set di destinazioni compatibili da usare durante il ripristino di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="57a71-235">The `<PackageTargetFallback>` property element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="57a71-236">È progettato per consentire ai pacchetti che usano il [TxM (Target x Moniker)](/nuget/schema/target-frameworks) di .NET di interagire con pacchetti che non dichiarano un TxM di .NET.</span><span class="sxs-lookup"><span data-stu-id="57a71-236">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="57a71-237">Se il progetto usa il TxM di .NET, devono averlo anche tutti i pacchetti da cui il progetto dipende, a meno che non si aggiunga `<PackageTargetFallback>` al progetto, in modo da rendere compatibili con .NET le piattaforme che non lo sono.</span><span class="sxs-lookup"><span data-stu-id="57a71-237">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span>

<span data-ttu-id="57a71-238">L'esempio seguente include i fallback per tutte le destinazioni nel progetto:</span><span class="sxs-lookup"><span data-stu-id="57a71-238">The following example provides the fallbacks for all targets in your project:</span></span>

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="57a71-239">L'esempio seguente specifica i fallback solo per la destinazione `netcoreapp2.1`:</span><span class="sxs-lookup"><span data-stu-id="57a71-239">The following example specifies the fallbacks only for the `netcoreapp2.1` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="build-events"></a><span data-ttu-id="57a71-240">Eventi di compilazione</span><span class="sxs-lookup"><span data-stu-id="57a71-240">Build events</span></span>

<span data-ttu-id="57a71-241">Il modo in cui vengono specificati gli eventi di pre-compilazione e post-compilazione nel file di progetto è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="57a71-241">The way that pre-build and post-build events are specified in the project file has changed.</span></span> <span data-ttu-id="57a71-242">Le proprietà PreBuildEvent e PostBuildEvent non sono consigliate nel formato di progetto in stile SDK, perché le macro come $ (ProjectDir) non vengono risolte.</span><span class="sxs-lookup"><span data-stu-id="57a71-242">The properties PreBuildEvent and PostBuildEvent are not recommended in the SDK-style project format, because macros such as $(ProjectDir) are not resolved.</span></span> <span data-ttu-id="57a71-243">Il codice seguente, ad esempio, non è più supportato:</span><span class="sxs-lookup"><span data-stu-id="57a71-243">For example, the following code is no longer supported:</span></span>

```xml
<PropertyGroup>
    <PreBuildEvent>"$(ProjectDir)PreBuildEvent.bat" "$(ProjectDir)..\" "$(ProjectDir)" "$(TargetDir)" />
</PropertyGroup>
```

<span data-ttu-id="57a71-244">Nei progetti in stile SDK usare una destinazione MSBuild denominata `PreBuild` o `PostBuild` e impostare la proprietà `BeforeTargets` per `PreBuild` o la proprietà `AfterTargets` per `PostBuild`.</span><span class="sxs-lookup"><span data-stu-id="57a71-244">In SDK-style projects, use an MSBuild target named `PreBuild` or `PostBuild` and set the `BeforeTargets` property for `PreBuild` or the `AfterTargets` property for `PostBuild`.</span></span> <span data-ttu-id="57a71-245">Per l'esempio precedente, usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="57a71-245">For the preceding example, use the following code:</span></span>

```xml
<Target Name="PreBuild" BeforeTargets="PreBuildEvent">
    <Exec Command="&quot;$(ProjectDir)PreBuildEvent.bat&quot; &quot;$(ProjectDir)..\&quot; &quot;$(ProjectDir)&quot; &quot;$(TargetDir)&quot;" />
</Target>

<Target Name="PostBuild" AfterTargets="PostBuildEvent">
   <Exec Command="echo Output written to $(TargetDir)" />
</Target>
```

> [!NOTE]
><span data-ttu-id="57a71-246">È possibile usare qualsiasi nome per le destinazioni di MSBuild, ma l'IDE di Visual Studio riconosce `PreBuild` e `PostBuild` destinazioni, quindi è consigliabile usare questi nomi in modo che sia possibile modificare i comandi nell'IDE di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="57a71-246">You can use any name for the MSBuild targets, but the Visual Studio IDE recognizes `PreBuild` and `PostBuild` targets, so we recommend using those names so that you can edit the commands in the Visual Studio IDE.</span></span> 

## <a name="nuget-metadata-properties"></a><span data-ttu-id="57a71-247">Proprietà dei metadati NuGet</span><span class="sxs-lookup"><span data-stu-id="57a71-247">NuGet metadata properties</span></span>

<span data-ttu-id="57a71-248">Con il passaggio a MSBuild, i metadati di input usati per la creazione di un pacchetto NuGet sono stati spostati da file *project.json* a file con estensione *csproj*.</span><span class="sxs-lookup"><span data-stu-id="57a71-248">With the move to MSBuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="57a71-249">Gli input sono proprietà di MSBuild, quindi devono trovarsi all'interno di un gruppo `<PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="57a71-249">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="57a71-250">Di seguito è riportato l'elenco delle proprietà usate come input per il processo di compressione quando si usa il comando `dotnet pack` o la destinazione `Pack` MSBuild che fa parte dell'SDK:</span><span class="sxs-lookup"><span data-stu-id="57a71-250">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK:</span></span>

### <a name="ispackable"></a><span data-ttu-id="57a71-251">IsPackable</span><span class="sxs-lookup"><span data-stu-id="57a71-251">IsPackable</span></span>

<span data-ttu-id="57a71-252">Valore booleano che specifica se dal progetto può essere creato un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-252">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="57a71-253">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="57a71-253">The default value is `true`.</span></span>

### <a name="packageversion"></a><span data-ttu-id="57a71-254">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="57a71-254">PackageVersion</span></span>

<span data-ttu-id="57a71-255">Specifica la versione che avrà il pacchetto risultante.</span><span class="sxs-lookup"><span data-stu-id="57a71-255">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="57a71-256">Accetta tutte le forme della stringa di versione NuGet.</span><span class="sxs-lookup"><span data-stu-id="57a71-256">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="57a71-257">Il valore predefinito corrisponde al valore di `$(Version)`, vale a dire della proprietà `Version` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-257">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span>

### <a name="packageid"></a><span data-ttu-id="57a71-258">PackageId</span><span class="sxs-lookup"><span data-stu-id="57a71-258">PackageId</span></span>

<span data-ttu-id="57a71-259">Specifica il nome del pacchetto risultante.</span><span class="sxs-lookup"><span data-stu-id="57a71-259">Specifies the name for the resulting package.</span></span> <span data-ttu-id="57a71-260">Se non specificato, l'impostazione predefinita per l'operazione `pack` corrisponde all'uso di `AssemblyName` o del nome della directory come nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-260">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span>

### <a name="title"></a><span data-ttu-id="57a71-261">Titolo</span><span class="sxs-lookup"><span data-stu-id="57a71-261">Title</span></span>

<span data-ttu-id="57a71-262">Titolo del pacchetto facilmente comprensibile per l'utente, usato di solito per la visualizzazione dell'interfaccia utente, ad esempio in nuget.org e in Gestione pacchetti in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="57a71-262">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="57a71-263">Se non specificato, viene usato l'ID del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-263">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="57a71-264">Autori</span><span class="sxs-lookup"><span data-stu-id="57a71-264">Authors</span></span>

<span data-ttu-id="57a71-265">Elenco delimitato da punti e virgola di autori di pacchetti, corrispondenti ai nomi di profilo in nuget.org. Questi vengono visualizzati nella raccolta NuGet in nuget.org e vengono usati per fare riferimento a pacchetti con gli stessi autori.</span><span class="sxs-lookup"><span data-stu-id="57a71-265">A semicolon-separated list of packages authors, matching the profile names on nuget.org. These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="packagedescription"></a><span data-ttu-id="57a71-266">PackageDescription</span><span class="sxs-lookup"><span data-stu-id="57a71-266">PackageDescription</span></span>

<span data-ttu-id="57a71-267">Descrizione lunga del pacchetto per la visualizzazione dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="57a71-267">A long description of the package for UI display.</span></span>

### <a name="description"></a><span data-ttu-id="57a71-268">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57a71-268">Description</span></span>

<span data-ttu-id="57a71-269">Descrizione lunga per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="57a71-269">A long description for the assembly.</span></span> <span data-ttu-id="57a71-270">Se `PackageDescription` non è specificata, questa proprietà viene usata anche come descrizione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-270">If `PackageDescription` is not specified then this property is also used as the description of the package.</span></span>

### <a name="copyright"></a><span data-ttu-id="57a71-271">Copyright</span><span class="sxs-lookup"><span data-stu-id="57a71-271">Copyright</span></span>

<span data-ttu-id="57a71-272">Informazioni sul copyright per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-272">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="57a71-273">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="57a71-273">PackageRequireLicenseAcceptance</span></span>

<span data-ttu-id="57a71-274">Valore booleano che specifica se il client deve richiedere al consumer di accettare la licenza del pacchetto prima di installarlo.</span><span class="sxs-lookup"><span data-stu-id="57a71-274">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="57a71-275">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="57a71-275">The default is `false`.</span></span>

### <a name="packagelicenseexpression"></a><span data-ttu-id="57a71-276">PackageLicenseExpression</span><span class="sxs-lookup"><span data-stu-id="57a71-276">PackageLicenseExpression</span></span>

<span data-ttu-id="57a71-277">Un [identificatore di licenza SPDX](https://spdx.org/licenses/) o un'espressione.</span><span class="sxs-lookup"><span data-stu-id="57a71-277">An [SPDX license identifier](https://spdx.org/licenses/) or expression.</span></span> <span data-ttu-id="57a71-278">Ad esempio `Apache-2.0`.</span><span class="sxs-lookup"><span data-stu-id="57a71-278">For example, `Apache-2.0`.</span></span>

<span data-ttu-id="57a71-279">Ecco l'elenco completo degli [identificatori di licenza SPDX](https://spdx.org/licenses/).</span><span class="sxs-lookup"><span data-stu-id="57a71-279">Here is the complete list of [SPDX license identifiers](https://spdx.org/licenses/).</span></span> <span data-ttu-id="57a71-280">NuGet.org accetta solo licenze approvate OSI o FSF quando si usa un'espressione del tipo di licenza.</span><span class="sxs-lookup"><span data-stu-id="57a71-280">NuGet.org accepts only OSI or FSF approved licenses when using license type expression.</span></span>

<span data-ttu-id="57a71-281">La sintassi esatta delle espressioni di licenza è descritta di seguito in [ABNF](https://tools.ietf.org/html/rfc5234).</span><span class="sxs-lookup"><span data-stu-id="57a71-281">The exact syntax of the license expressions is described below in [ABNF](https://tools.ietf.org/html/rfc5234).</span></span>

```abnf
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
> <span data-ttu-id="57a71-282">È possibile specificare solo uno degli elementi `PackageLicenseExpression`, `PackageLicenseFile` e `PackageLicenseUrl` contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="57a71-282">Only one of `PackageLicenseExpression`, `PackageLicenseFile` and `PackageLicenseUrl` can be specified at a time.</span></span>

### <a name="packagelicensefile"></a><span data-ttu-id="57a71-283">PackageLicenseFile</span><span class="sxs-lookup"><span data-stu-id="57a71-283">PackageLicenseFile</span></span>

<span data-ttu-id="57a71-284">Percorso di un file di licenza all'interno del pacchetto se si usa una licenza a cui non è stato assegnato un identificatore SPDX oppure una licenza personalizzata (in caso contrario, è preferibile l'elemento `PackageLicenseExpression`)</span><span class="sxs-lookup"><span data-stu-id="57a71-284">Path to a license file within the package if you are using a license that hasn’t been assigned an SPDX identifier, or it is a custom license (Otherwise `PackageLicenseExpression` is preferred)</span></span>

<span data-ttu-id="57a71-285">Sostituisce `PackageLicenseUrl`, non può essere combinato con `PackageLicenseExpression` e richiede Visual Studio 15.9.4, .NET SDK 2.1.502 o 2.2.101 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="57a71-285">Replaces `PackageLicenseUrl`, can't be combined with `PackageLicenseExpression` and requires Visual Studio 15.9.4, .NET SDK 2.1.502 or 2.2.101, or newer.</span></span>

<span data-ttu-id="57a71-286">Sarà necessario assicurarsi che il file di licenza venga incluso nel pacchetto aggiungendolo in modo esplicito al progetto, come in questo esempio di utilizzo:</span><span class="sxs-lookup"><span data-stu-id="57a71-286">You will need to ensure the license file is packed by adding it explicitly to the project, example usage:</span></span>

```xml
<PropertyGroup>
  <PackageLicenseFile>LICENSE.txt</PackageLicenseFile>
</PropertyGroup>
<ItemGroup>
  <None Include="licenses\LICENSE.txt" Pack="true" PackagePath="$(PackageLicenseFile)"/>
</ItemGroup>
```

### <a name="packagelicenseurl"></a><span data-ttu-id="57a71-287">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="57a71-287">PackageLicenseUrl</span></span>

<span data-ttu-id="57a71-288">URL della licenza applicabile al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-288">An URL to the license that is applicable to the package.</span></span> <span data-ttu-id="57a71-289">(_deprecato da Visual Studio 15.9.4, .NET SDK 2.1.502 e 2.2.101_)</span><span class="sxs-lookup"><span data-stu-id="57a71-289">(_deprecated since Visual Studio 15.9.4, .NET SDK 2.1.502 and 2.2.101_)</span></span>

### <a name="packageiconurl"></a><span data-ttu-id="57a71-290">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="57a71-290">PackageIconUrl</span></span>

<span data-ttu-id="57a71-291">URL di un'immagine 64 x 64 con sfondo trasparente da usare come icona per il pacchetto nella visualizzazione dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="57a71-291">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="57a71-292">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="57a71-292">PackageReleaseNotes</span></span>

<span data-ttu-id="57a71-293">Note sulla versione per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-293">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="57a71-294">PackageTags</span><span class="sxs-lookup"><span data-stu-id="57a71-294">PackageTags</span></span>

<span data-ttu-id="57a71-295">Elenco di tag con valori delimitati da punto e virgola che designa il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-295">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="57a71-296">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="57a71-296">PackageOutputPath</span></span>

<span data-ttu-id="57a71-297">Determina il percorso di output in cui verrà rilasciato il pacchetto creato.</span><span class="sxs-lookup"><span data-stu-id="57a71-297">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="57a71-298">Il valore predefinito è `$(OutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="57a71-298">Default is `$(OutputPath)`.</span></span>

### <a name="includesymbols"></a><span data-ttu-id="57a71-299">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="57a71-299">IncludeSymbols</span></span>
<span data-ttu-id="57a71-300">Valore booleano che indica se al momento della creazione del pacchetto deve essere creato un pacchetto aggiuntivo di simboli.</span><span class="sxs-lookup"><span data-stu-id="57a71-300">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="57a71-301">Il formato del pacchetto di simboli è controllato dalla proprietà `SymbolPackageFormat`.</span><span class="sxs-lookup"><span data-stu-id="57a71-301">The symbols package's format is controlled by the `SymbolPackageFormat` property.</span></span>

### <a name="symbolpackageformat"></a><span data-ttu-id="57a71-302">SymbolPackageFormat</span><span class="sxs-lookup"><span data-stu-id="57a71-302">SymbolPackageFormat</span></span>
<span data-ttu-id="57a71-303">Specifica il formato del pacchetto di simboli.</span><span class="sxs-lookup"><span data-stu-id="57a71-303">Specifies the format of the symbols package.</span></span> <span data-ttu-id="57a71-304">Se il valore è "symbols.nupkg", verrà creato un pacchetto di simboli legacy con estensione *symbols.nupkg* che contiene i file PDB, DLL e altri file di output.</span><span class="sxs-lookup"><span data-stu-id="57a71-304">If "symbols.nupkg", a legacy symbols package will be created with a *.symbols.nupkg* extension containing PDBs, DLLs, and other output files.</span></span> <span data-ttu-id="57a71-305">Se il valore è "snupkg", verrà creato un pacchetto di simboli snupkg che contiene i file PDB portatili.</span><span class="sxs-lookup"><span data-stu-id="57a71-305">If "snupkg", a snupkg symbol package will be created containing the portable PDBs.</span></span> <span data-ttu-id="57a71-306">Il valore predefinito è "symbols.nupkg".</span><span class="sxs-lookup"><span data-stu-id="57a71-306">Default is "symbols.nupkg".</span></span>

### <a name="includesource"></a><span data-ttu-id="57a71-307">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="57a71-307">IncludeSource</span></span>

<span data-ttu-id="57a71-308">Valore booleano che indica se il processo di creazione del pacchetto deve creare un pacchetto di origine.</span><span class="sxs-lookup"><span data-stu-id="57a71-308">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="57a71-309">Il pacchetto di origine contiene il codice sorgente della libreria, nonché i file PDB.</span><span class="sxs-lookup"><span data-stu-id="57a71-309">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="57a71-310">I file di origine vengono posizionati nella directory `src/ProjectName` del file del pacchetto risultante.</span><span class="sxs-lookup"><span data-stu-id="57a71-310">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span>

### <a name="istool"></a><span data-ttu-id="57a71-311">IsTool</span><span class="sxs-lookup"><span data-stu-id="57a71-311">IsTool</span></span>

<span data-ttu-id="57a71-312">Specifica se tutti i file di output devono essere copiati nella cartella *tools* anziché nella cartella *lib*.</span><span class="sxs-lookup"><span data-stu-id="57a71-312">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="57a71-313">È diverso da `DotNetCliTool`, che viene specificato impostando `PackageType` nel file *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="57a71-313">Note that this is different from a `DotNetCliTool` which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="57a71-314">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="57a71-314">RepositoryUrl</span></span>

<span data-ttu-id="57a71-315">Specifica l'URL per l'archivio in cui si trova il codice sorgente per il pacchetto e/o da cui il codice sorgente viene compilato.</span><span class="sxs-lookup"><span data-stu-id="57a71-315">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span>

### <a name="repositorytype"></a><span data-ttu-id="57a71-316">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="57a71-316">RepositoryType</span></span>

<span data-ttu-id="57a71-317">Specifica il tipo dell'archivio.</span><span class="sxs-lookup"><span data-stu-id="57a71-317">Specifies the type of the repository.</span></span> <span data-ttu-id="57a71-318">Il valore predefinito è "git".</span><span class="sxs-lookup"><span data-stu-id="57a71-318">Default is "git".</span></span>

### <a name="repositorybranch"></a><span data-ttu-id="57a71-319">RepositoryBranch</span><span class="sxs-lookup"><span data-stu-id="57a71-319">RepositoryBranch</span></span>
<span data-ttu-id="57a71-320">Specifica il nome del ramo di origine nel repository.</span><span class="sxs-lookup"><span data-stu-id="57a71-320">Specifies the name of the source branch in the repository.</span></span> <span data-ttu-id="57a71-321">Quando il progetto viene incluso in un pacchetto NuGet, viene aggiunto ai metadati del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-321">When the project is packaged in a NuGet package, it's added to the package metadata.</span></span>

### <a name="repositorycommit"></a><span data-ttu-id="57a71-322">RepositoryCommit</span><span class="sxs-lookup"><span data-stu-id="57a71-322">RepositoryCommit</span></span>
<span data-ttu-id="57a71-323">Commit o insieme di modifiche facoltativo del repository per indicare l'origine su cui è stato compilato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-323">Optional repository commit or changeset to indicate which source the package was built against.</span></span> <span data-ttu-id="57a71-324">per includere questa proprietà, è necessario specificare anche `RepositoryUrl`.</span><span class="sxs-lookup"><span data-stu-id="57a71-324">`RepositoryUrl` must also be specified for this property to be included.</span></span> <span data-ttu-id="57a71-325">Quando il progetto viene incluso in un pacchetto NuGet, questo commit o insieme di modifiche viene aggiunto ai metadati del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-325">When the project is packaged in a NuGet package, this commit or changeset is added to the package metadata.</span></span>

### <a name="nopackageanalysis"></a><span data-ttu-id="57a71-326">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="57a71-326">NoPackageAnalysis</span></span>

<span data-ttu-id="57a71-327">Specifica che pack non deve eseguire l'analisi del pacchetto dopo la compilazione di quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="57a71-327">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="57a71-328">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="57a71-328">MinClientVersion</span></span>

<span data-ttu-id="57a71-329">Specifica la versione minima del client NuGet, imposta da nuget.exe e da Gestione pacchetti di Visual Studio, che può installare questo pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-329">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="57a71-330">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="57a71-330">IncludeBuildOutput</span></span>

<span data-ttu-id="57a71-331">Valore booleano che specifica se gli assembly di output di compilazione devono essere compresi nel file *.nupkg*.</span><span class="sxs-lookup"><span data-stu-id="57a71-331">This Boolean values specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="57a71-332">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="57a71-332">IncludeContentInPack</span></span>

<span data-ttu-id="57a71-333">Questo valore booleano specifica se gli elementi con tipo `Content` verranno inclusi automaticamente nel pacchetto risultante.</span><span class="sxs-lookup"><span data-stu-id="57a71-333">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="57a71-334">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="57a71-334">The default is `true`.</span></span>

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="57a71-335">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="57a71-335">BuildOutputTargetFolder</span></span>

<span data-ttu-id="57a71-336">Specifica la cartella in cui inserire gli assembly di output.</span><span class="sxs-lookup"><span data-stu-id="57a71-336">Specifies the folder where to place the output assemblies.</span></span> <span data-ttu-id="57a71-337">Gli assembly di output (e altri file di output) vengono copiati nelle rispettive cartelle per framework.</span><span class="sxs-lookup"><span data-stu-id="57a71-337">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="57a71-338">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="57a71-338">ContentTargetFolders</span></span>

<span data-ttu-id="57a71-339">Questa proprietà specifica il percorso predefinito in cui devono essere posizionati tutti i file di contenuto se per tali file `PackagePath` non è specificato.</span><span class="sxs-lookup"><span data-stu-id="57a71-339">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="57a71-340">Il valore predefinito è "content;contentFiles".</span><span class="sxs-lookup"><span data-stu-id="57a71-340">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="57a71-341">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="57a71-341">NuspecFile</span></span>

<span data-ttu-id="57a71-342">Percorso relativo o assoluto per il file *.nuspec* usato per la creazione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="57a71-342">Relative or absolute path to the *.nuspec* file being used for packing.</span></span>

> [!NOTE]
> <span data-ttu-id="57a71-343">Se il file *.nuspec* è specificato, viene usato **esclusivamente** per le informazioni di creazione del pacchetto e le informazioni nei progetti non vengono usate.</span><span class="sxs-lookup"><span data-stu-id="57a71-343">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span>

### <a name="nuspecbasepath"></a><span data-ttu-id="57a71-344">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="57a71-344">NuspecBasePath</span></span>

<span data-ttu-id="57a71-345">Percorso di base per il file *.nuspec*.</span><span class="sxs-lookup"><span data-stu-id="57a71-345">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="57a71-346">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="57a71-346">NuspecProperties</span></span>

<span data-ttu-id="57a71-347">Elenco con valori delimitati da punto e virgola di coppie chiave=valore.</span><span class="sxs-lookup"><span data-stu-id="57a71-347">Semicolon separated list of key=value pairs.</span></span>

## <a name="assemblyinfo-properties"></a><span data-ttu-id="57a71-348">Proprietà AssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="57a71-348">AssemblyInfo properties</span></span>

<span data-ttu-id="57a71-349">Gli [attributi dell'assembly](../../standard/assembly/set-attributes.md) che in genere erano presenti in un file *AssemblyInfo* ora vengono automaticamente generati dalle proprietà.</span><span class="sxs-lookup"><span data-stu-id="57a71-349">[Assembly attributes](../../standard/assembly/set-attributes.md) that were typically present in an *AssemblyInfo* file are now automatically generated from properties.</span></span>

### <a name="properties-per-attribute"></a><span data-ttu-id="57a71-350">Proprietà dei singoli attributi</span><span class="sxs-lookup"><span data-stu-id="57a71-350">Properties per attribute</span></span>

<span data-ttu-id="57a71-351">Ogni attributo ha una proprietà che ne controlla il contenuto e un'altra per disabilitarne la generazione, come illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="57a71-351">Each attribute has a property that control its content and another to disable its generation as shown in the following table:</span></span>

| <span data-ttu-id="57a71-352">Attributo</span><span class="sxs-lookup"><span data-stu-id="57a71-352">Attribute</span></span>                                                      | <span data-ttu-id="57a71-353">Gli</span><span class="sxs-lookup"><span data-stu-id="57a71-353">Property</span></span>               | <span data-ttu-id="57a71-354">Proprietà da disabilitare</span><span class="sxs-lookup"><span data-stu-id="57a71-354">Property to disable</span></span>                             |
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

<span data-ttu-id="57a71-355">Note:</span><span class="sxs-lookup"><span data-stu-id="57a71-355">Notes:</span></span>

- <span data-ttu-id="57a71-356">Per impostazione predefinita, `AssemblyVersion` e `FileVersion` usano il valore di `$(Version)` senza suffisso.</span><span class="sxs-lookup"><span data-stu-id="57a71-356">`AssemblyVersion` and `FileVersion` default is to take the value of `$(Version)` without suffix.</span></span> <span data-ttu-id="57a71-357">Se ad esempio `$(Version)` è `1.2.3-beta.4`, il valore sarà `1.2.3`.</span><span class="sxs-lookup"><span data-stu-id="57a71-357">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
- <span data-ttu-id="57a71-358">Il valore predefinito di `InformationalVersion` è `$(Version)`.</span><span class="sxs-lookup"><span data-stu-id="57a71-358">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
- <span data-ttu-id="57a71-359">A `InformationalVersion` viene aggiunto `$(SourceRevisionId)` se la proprietà è presente.</span><span class="sxs-lookup"><span data-stu-id="57a71-359">`InformationalVersion` has `$(SourceRevisionId)` appended if the property is present.</span></span> <span data-ttu-id="57a71-360">Può essere disabilitata usando `IncludeSourceRevisionInInformationalVersion`.</span><span class="sxs-lookup"><span data-stu-id="57a71-360">It can be disabled using `IncludeSourceRevisionInInformationalVersion`.</span></span>
- <span data-ttu-id="57a71-361">Le proprietà `Copyright` e `Description` vengono usate anche per i metadati NuGet.</span><span class="sxs-lookup"><span data-stu-id="57a71-361">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
- <span data-ttu-id="57a71-362">`Configuration` viene condivisa con tutto il processo di compilazione e impostata tramite il parametro `--configuration` dei comandi `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="57a71-362">`Configuration` is shared with all the build process and set via the `--configuration` parameter of `dotnet` commands.</span></span>

### <a name="generateassemblyinfo"></a><span data-ttu-id="57a71-363">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="57a71-363">GenerateAssemblyInfo</span></span>

<span data-ttu-id="57a71-364">Valore booleano che abilita o disabilita tutta la generazione di AssemblyInfo.</span><span class="sxs-lookup"><span data-stu-id="57a71-364">A Boolean that enable or disable all the AssemblyInfo generation.</span></span> <span data-ttu-id="57a71-365">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="57a71-365">The default value is `true`.</span></span>

### <a name="generatedassemblyinfofile"></a><span data-ttu-id="57a71-366">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="57a71-366">GeneratedAssemblyInfoFile</span></span>

<span data-ttu-id="57a71-367">Percorso del file di informazioni sull'assembly generato.</span><span class="sxs-lookup"><span data-stu-id="57a71-367">The path of the generated assembly info file.</span></span> <span data-ttu-id="57a71-368">L'impostazione predefinita è un file nella directory `$(IntermediateOutputPath)` (obj).</span><span class="sxs-lookup"><span data-stu-id="57a71-368">Default to a file in the `$(IntermediateOutputPath)` (obj) directory.</span></span>
