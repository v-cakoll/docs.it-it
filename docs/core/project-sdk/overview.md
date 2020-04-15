---
title: Panoramica dell'SDK del progetto .NET Core
description: Informazioni sugli SDK del progetto .NET Core.Learn about the .NET Core project SDKs.
ms.date: 02/02/2020
ms.topic: conceptual
ms.openlocfilehash: d0ac01dca31dffea482745126e00c34b1da20774
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389663"
---
# <a name="net-core-project-sdks"></a><span data-ttu-id="a08f0-103">SDK del progetto .NET Core</span><span class="sxs-lookup"><span data-stu-id="a08f0-103">.NET Core project SDKs</span></span>

<span data-ttu-id="a08f0-104">I progetti .NET Core sono associati a un Software Development Kit (SDK).</span><span class="sxs-lookup"><span data-stu-id="a08f0-104">.NET Core projects are associated with a software development kit (SDK).</span></span> <span data-ttu-id="a08f0-105">Ogni SDK del *progetto* è un set di [destinazioni](/visualstudio/msbuild/msbuild-targets) MSBuild e [attività](/visualstudio/msbuild/msbuild-tasks) associate responsabili della compilazione, dell'imballaggio e della pubblicazione del codice.</span><span class="sxs-lookup"><span data-stu-id="a08f0-105">Each *project SDK* is a set of MSBuild [targets](/visualstudio/msbuild/msbuild-targets) and associated [tasks](/visualstudio/msbuild/msbuild-tasks) that are responsible for compiling, packing, and publishing code.</span></span> <span data-ttu-id="a08f0-106">Un progetto che fa riferimento a un SDK di progetto viene talvolta definito *progetto di tipo SDK.*</span><span class="sxs-lookup"><span data-stu-id="a08f0-106">A project that references a project SDK is sometimes referred to as an *SDK-style project*.</span></span>

## <a name="available-sdks"></a><span data-ttu-id="a08f0-107">SDK disponibili</span><span class="sxs-lookup"><span data-stu-id="a08f0-107">Available SDKs</span></span>

<span data-ttu-id="a08f0-108">Per .NET Core sono disponibili i seguenti SDK:</span><span class="sxs-lookup"><span data-stu-id="a08f0-108">The following SDKs are available for .NET Core:</span></span>

| <span data-ttu-id="a08f0-109">ID</span><span class="sxs-lookup"><span data-stu-id="a08f0-109">ID</span></span> | <span data-ttu-id="a08f0-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a08f0-110">Description</span></span> | <span data-ttu-id="a08f0-111">Repo</span><span class="sxs-lookup"><span data-stu-id="a08f0-111">Repo</span></span>|
| - | - | - |
| `Microsoft.NET.Sdk` | <span data-ttu-id="a08f0-112">The .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="a08f0-112">The .NET Core SDK</span></span> | https://github.com/dotnet/sdk |
| `Microsoft.NET.Sdk.Web` | <span data-ttu-id="a08f0-113">Web [SDK](/aspnet/core/razor-pages/web-sdk) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="a08f0-113">The .NET Core [Web SDK](/aspnet/core/razor-pages/web-sdk)</span></span> | https://github.com/aspnet/websdk |
| `Microsoft.NET.Sdk.Razor` | <span data-ttu-id="a08f0-114">SDK di .NET Core [Razor](/aspnet/core/razor-pages/sdk)</span><span class="sxs-lookup"><span data-stu-id="a08f0-114">The .NET Core [Razor SDK](/aspnet/core/razor-pages/sdk)</span></span> |
| `Microsoft.NET.Sdk.Worker` | <span data-ttu-id="a08f0-115">L'SDK del servizio di lavoro .NET Core</span><span class="sxs-lookup"><span data-stu-id="a08f0-115">The .NET Core Worker Service SDK</span></span> |
| `Microsoft.NET.Sdk.WindowsDesktop` | <span data-ttu-id="a08f0-116">WinForms e WPF SDK di .NET Core</span><span class="sxs-lookup"><span data-stu-id="a08f0-116">The .NET Core WinForms and WPF SDK</span></span> |

<span data-ttu-id="a08f0-117">.NET Core SDK è l'SDK di base per .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a08f0-117">The .NET Core SDK is the base SDK for .NET Core.</span></span> <span data-ttu-id="a08f0-118">Gli altri SDK fanno riferimento a .NET Core SDK e i progetti associati agli altri SDK dispongono di tutte le proprietà di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="a08f0-118">The other SDKs reference the .NET Core SDK, and projects that are associated with the other SDKs have all the .NET Core SDK properties available to them.</span></span> <span data-ttu-id="a08f0-119">Il Web SDK, ad esempio, dipende sia da .NET Core SDK che da Razor SDK.</span><span class="sxs-lookup"><span data-stu-id="a08f0-119">The Web SDK, for example, depends on both the .NET Core SDK and the Razor SDK.</span></span>

<span data-ttu-id="a08f0-120">È anche possibile creare il proprio SDK che può essere distribuito tramite NuGet.You can also author your own SDK that can be distributed via NuGet.</span><span class="sxs-lookup"><span data-stu-id="a08f0-120">You can also author your own SDK that can be distributed via NuGet.</span></span>

## <a name="project-files"></a><span data-ttu-id="a08f0-121">File di progetto</span><span class="sxs-lookup"><span data-stu-id="a08f0-121">Project files</span></span>

<span data-ttu-id="a08f0-122">I progetti .NET Core sono basati sul formato [MSBuild.](/visualstudio/msbuild/msbuild)</span><span class="sxs-lookup"><span data-stu-id="a08f0-122">.NET Core projects are based on the [MSBuild](/visualstudio/msbuild/msbuild) format.</span></span> <span data-ttu-id="a08f0-123">I file di progetto, che dispongono di estensioni come *.csproj* per i progetti in C, e *.fsproj* per i progetti F , sono in formato XML.</span><span class="sxs-lookup"><span data-stu-id="a08f0-123">Project files, which have extensions like *.csproj* for C# projects and *.fsproj* for F# projects, are in XML format.</span></span> <span data-ttu-id="a08f0-124">L'elemento radice di un file di progetto MSBuild è l'elemento [Project.](/visualstudio/msbuild/project-element-msbuild)</span><span class="sxs-lookup"><span data-stu-id="a08f0-124">The root element of an MSBuild project file is the [Project](/visualstudio/msbuild/project-element-msbuild) element.</span></span> <span data-ttu-id="a08f0-125">L'elemento `Project` dispone `Sdk` di un attributo facoltativo che specifica l'SDK (e la versione) da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="a08f0-125">The `Project` element has an optional `Sdk` attribute that specifies which SDK (and version) to use.</span></span> <span data-ttu-id="a08f0-126">Per usare gli strumenti .NET Core e `Sdk` compilare il codice, impostare l'attributo su uno degli ID nella tabella [SDK disponibili.](#available-sdks)</span><span class="sxs-lookup"><span data-stu-id="a08f0-126">To use the .NET Core tools and build your code, set the `Sdk` attribute to one of the IDs in the [Available SDKs](#available-sdks) table.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
</Project>
```

<span data-ttu-id="a08f0-127">Per specificare un SDK proveniente da NuGet, includere la versione alla fine del nome oppure specificare il nome e la versione nel file *global.json.*</span><span class="sxs-lookup"><span data-stu-id="a08f0-127">To specify an SDK that comes from NuGet, include the version at the end of the name, or specify the name and version in the *global.json* file.</span></span>

```xml
<Project Sdk="MSBuild.Sdk.Extras/2.0.54">
  ...
</Project>
```

<span data-ttu-id="a08f0-128">Un altro modo per specificare l'SDK è con l'elemento [Sdk](/visualstudio/msbuild/sdk-element-msbuild) di primo livello:</span><span class="sxs-lookup"><span data-stu-id="a08f0-128">Another way to specify the SDK is with the top-level [Sdk](/visualstudio/msbuild/sdk-element-msbuild) element:</span></span>

```xml
<Project>
  <Sdk Name="Microsoft.NET.Sdk" />
  ...
</Project>
```

<span data-ttu-id="a08f0-129">Il riferimento a un SDK in uno di questi modi semplifica notevolmente i file di progetto per .NET Core.Referening an SDK in one of these ways greatly simplifies project files for .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a08f0-129">Referencing an SDK in one of these ways greatly simplifies project files for .NET Core.</span></span> <span data-ttu-id="a08f0-130">Durante la valutazione del progetto, MSBuild `Sdk.props` aggiunge importazioni implicite `Sdk.targets` per all'inizio del file di progetto e nella parte inferiore.</span><span class="sxs-lookup"><span data-stu-id="a08f0-130">While evaluating the project, MSBuild adds implicit imports for `Sdk.props` at the top of the project file and `Sdk.targets` at the bottom.</span></span>

```xml
<Project>
  <!-- Implicit top import -->
  <Import Project="Sdk.props" Sdk="Microsoft.NET.Sdk" />
  ...
  <!-- Implicit bottom import -->
  <Import Project="Sdk.targets" Sdk="Microsoft.NET.Sdk" />
</Project>
```

> [!TIP]
> <span data-ttu-id="a08f0-131">In un computer Windows, i file *Sdk.props* e *Sdk.targets* sono disponibili nella cartella *%ProgramFiles%\\*</span><span class="sxs-lookup"><span data-stu-id="a08f0-131">On a Windows machine, the *Sdk.props* and *Sdk.targets* files can be found in the *%ProgramFiles%\dotnet\sdk\\[version]\Sdks\Microsoft.NET.Sdk\Sdk* folder.</span></span>

### <a name="preprocess-the-project-file"></a><span data-ttu-id="a08f0-132">Pre-elaborare il file di progetto</span><span class="sxs-lookup"><span data-stu-id="a08f0-132">Preprocess the project file</span></span>

<span data-ttu-id="a08f0-133">È possibile visualizzare il progetto completamente espanso come MSBuild vede dopo `dotnet msbuild -preprocess` l'SDK e le relative destinazioni sono inclusi utilizzando il comando.</span><span class="sxs-lookup"><span data-stu-id="a08f0-133">You can see the fully expanded project as MSBuild sees it after the SDK and its targets are included by using the `dotnet msbuild -preprocess` command.</span></span> <span data-ttu-id="a08f0-134">L'opzione [`dotnet msbuild`](../tools/dotnet-msbuild.md) di [pre-elaborazione](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando mostra quali file vengono importati, le relative origini e i relativi contributi alla compilazione senza compilare effettivamente il progetto.</span><span class="sxs-lookup"><span data-stu-id="a08f0-134">The [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) switch of the [`dotnet msbuild`](../tools/dotnet-msbuild.md) command shows which files are imported, their sources, and their contributions to the build without actually building the project.</span></span>

<span data-ttu-id="a08f0-135">Se il progetto dispone di più framework di destinazione, spostare i risultati del comando su un solo framework specificandolo come proprietà MSBuild.</span><span class="sxs-lookup"><span data-stu-id="a08f0-135">If the project has multiple target frameworks, focus the results of the command on only one framework by specifying it as an MSBuild property.</span></span> <span data-ttu-id="a08f0-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a08f0-136">For example:</span></span>

`dotnet msbuild -property:TargetFramework=netcoreapp2.0 -preprocess:output.xml`

### <a name="default-compilation-includes"></a><span data-ttu-id="a08f0-137">La compilazione predefinita include</span><span class="sxs-lookup"><span data-stu-id="a08f0-137">Default compilation includes</span></span>

<span data-ttu-id="a08f0-138">L'impostazione predefinita include ed esclude per gli elementi di compilazione e le risorse incorporate sono definite nell'SDK.</span><span class="sxs-lookup"><span data-stu-id="a08f0-138">The default includes and excludes for compile items and embedded resources are defined in the SDK.</span></span> <span data-ttu-id="a08f0-139">A differenza dei progetti .NET Framework non SDK, non è necessario specificare questi elementi nel file di progetto, perché i valori predefiniti riguardano i casi d'uso più comuni.</span><span class="sxs-lookup"><span data-stu-id="a08f0-139">Unlike non-SDK .NET Framework projects, you don't need to specify these items in your project file, because the defaults cover most common use cases.</span></span> <span data-ttu-id="a08f0-140">Questo porta a file di progetto più piccoli che sono più facili da capire e modificare a mano, se necessario.</span><span class="sxs-lookup"><span data-stu-id="a08f0-140">This leads to smaller project files that are easier to understand as well as edit by hand, if needed.</span></span>

<span data-ttu-id="a08f0-141">Nella tabella seguente vengono illustrati l'elemento e i [glob](https://en.wikipedia.org/wiki/Glob_(programming)) inclusi ed esclusi in .NET Core SDK:</span><span class="sxs-lookup"><span data-stu-id="a08f0-141">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are included and excluded in the .NET Core SDK:</span></span>

| <span data-ttu-id="a08f0-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="a08f0-142">Element</span></span>           | <span data-ttu-id="a08f0-143">GLOB Include</span><span class="sxs-lookup"><span data-stu-id="a08f0-143">Include glob</span></span>                              | <span data-ttu-id="a08f0-144">GLOB Exclude</span><span class="sxs-lookup"><span data-stu-id="a08f0-144">Exclude glob</span></span>                                                  | <span data-ttu-id="a08f0-145">GLOB Remove</span><span class="sxs-lookup"><span data-stu-id="a08f0-145">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| <span data-ttu-id="a08f0-146">Compilazione</span><span class="sxs-lookup"><span data-stu-id="a08f0-146">Compile</span></span>           | <span data-ttu-id="a08f0-147">\*\*/\*.cs (o altre estensioni del linguaggio)</span><span class="sxs-lookup"><span data-stu-id="a08f0-147">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="a08f0-148">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="a08f0-148">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="a08f0-149">N/D</span><span class="sxs-lookup"><span data-stu-id="a08f0-149">N/A</span></span>                      |
| <span data-ttu-id="a08f0-150">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="a08f0-150">EmbeddedResource</span></span>  | <span data-ttu-id="a08f0-151">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="a08f0-151">\*\*/\*.resx</span></span>                              | <span data-ttu-id="a08f0-152">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="a08f0-152">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="a08f0-153">N/D</span><span class="sxs-lookup"><span data-stu-id="a08f0-153">N/A</span></span>                      |
| <span data-ttu-id="a08f0-154">nessuno</span><span class="sxs-lookup"><span data-stu-id="a08f0-154">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="a08f0-155">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="a08f0-155">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="a08f0-156">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="a08f0-156">\*\*/\*.cs; \*\*/\*.resx</span></span> |

> [!NOTE]
> <span data-ttu-id="a08f0-157">Le `./bin` `./obj` cartelle e, rappresentate `$(BaseOutputPath)` `$(BaseIntermediateOutputPath)` dalle proprietà e MSBuild, sono escluse dai glob per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a08f0-157">The `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, are excluded from the globs by default.</span></span> <span data-ttu-id="a08f0-158">Gli esclusi sono `$(DefaultItemExcludes)`rappresentati dalla proprietà .</span><span class="sxs-lookup"><span data-stu-id="a08f0-158">Excludes are represented by the property `$(DefaultItemExcludes)`.</span></span>

<span data-ttu-id="a08f0-159">Se si definiscono in modo esplicito questi elementi nel file di progetto, è probabile che venga visualizzato il seguente errore:</span><span class="sxs-lookup"><span data-stu-id="a08f0-159">If you explicitly define these items in your project file, you're likely to get the following error:</span></span>

<span data-ttu-id="a08f0-160">**Sono stati inclusi elementi Compile duplicati. .NET SDK include gli elementi Compile dalla directory del progetto per impostazione predefinita. È possibile rimuovere questi elementi dal file di progetto o impostare la proprietà 'EnableDefaultCompileItems' su 'false' se si desidera includerli in modo esplicito nel file di progetto.**</span><span class="sxs-lookup"><span data-stu-id="a08f0-160">**Duplicate Compile items were included. The .NET SDK includes Compile items from your project directory by default. You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.**</span></span>

<span data-ttu-id="a08f0-161">Per risolvere l'errore, `Compile` rimuovere gli elementi espliciti che corrispondono a `EnableDefaultCompileItems` quelli `false`impliciti elencati nella tabella precedente oppure impostare la proprietà su , che disabilita l'inclusione implicita:</span><span class="sxs-lookup"><span data-stu-id="a08f0-161">To resolve the error, either remove the explicit `Compile` items that match the implicit ones listed on the previous table, or set the `EnableDefaultCompileItems` property to `false`, which disables implicit inclusion:</span></span>

```xml
<PropertyGroup>
  <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

<span data-ttu-id="a08f0-162">Se si desidera specificare, ad esempio, alcuni file da pubblicare con l'app, è comunque `Content` possibile usare i meccanismi MSBuild noti per tale file, ad esempio l'elemento.</span><span class="sxs-lookup"><span data-stu-id="a08f0-162">If you want to specify, for example, some files to get published with your app, you can still use the known MSBuild mechanisms for that, for example, the `Content` element.</span></span>

<span data-ttu-id="a08f0-163">`EnableDefaultCompileItems`disabilita solo `Compile` globs ma non influisce su altri glob, come il glob implicito `None` che si applica anche agli \*elementi .cs.</span><span class="sxs-lookup"><span data-stu-id="a08f0-163">`EnableDefaultCompileItems` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob that also applies to \*.cs items.</span></span> <span data-ttu-id="a08f0-164">Per questo, Esplora soluzioni \*in Visual Studio mostra gli elementi `None` con estensione cs come parte del progetto, inclusi come elementi.</span><span class="sxs-lookup"><span data-stu-id="a08f0-164">Because of that, Solution Explorer in Visual Studio shows \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="a08f0-165">Per disabilitare `None` il glob `false`implicito, impostare su `EnableDefaultNoneItems` :</span><span class="sxs-lookup"><span data-stu-id="a08f0-165">To disable the implicit `None` glob, set `EnableDefaultNoneItems` to `false`:</span></span>

```xml
<PropertyGroup>
  <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

<span data-ttu-id="a08f0-166">Per disabilitare *tutti i* glob impliciti, impostare la `EnableDefaultItems` proprietà su `false`:</span><span class="sxs-lookup"><span data-stu-id="a08f0-166">To disable *all* implicit globs, set the `EnableDefaultItems` property to `false`:</span></span>

```xml
<PropertyGroup>
  <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="customize-the-build"></a><span data-ttu-id="a08f0-167">Personalizzare la build</span><span class="sxs-lookup"><span data-stu-id="a08f0-167">Customize the build</span></span>

<span data-ttu-id="a08f0-168">Esistono vari modi per [personalizzare una compilazione](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="a08f0-168">There are various ways to [customize a build](/visualstudio/msbuild/customize-your-build).</span></span> <span data-ttu-id="a08f0-169">È possibile eseguire l'override di una proprietà passandola come argomento a un comando [msbuild](/visualstudio/msbuild/msbuild-command-line-reference) o [dotnet.](../tools/index.md)</span><span class="sxs-lookup"><span data-stu-id="a08f0-169">You may want to override a property by passing it as an argument to an [msbuild](/visualstudio/msbuild/msbuild-command-line-reference) or [dotnet](../tools/index.md) command.</span></span> <span data-ttu-id="a08f0-170">È inoltre possibile aggiungere la proprietà al file di progetto o a un file *Directory.Build.props.*</span><span class="sxs-lookup"><span data-stu-id="a08f0-170">You can also add the property to the project file or to a *Directory.Build.props* file.</span></span> <span data-ttu-id="a08f0-171">Per un elenco di proprietà utili per i progetti .NET Core, vedere Proprietà MSBuild per i [progetti .NET Core SDK](msbuild-props.md).</span><span class="sxs-lookup"><span data-stu-id="a08f0-171">For a list of useful properties for .NET Core projects, see [MSBuild properties for .NET Core SDK projects](msbuild-props.md).</span></span>

### <a name="custom-targets"></a><span data-ttu-id="a08f0-172">Destinazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="a08f0-172">Custom targets</span></span>

<span data-ttu-id="a08f0-173">I progetti .NET Core possono creare pacchetti di destinazioni e proprietà MSBuild personalizzate per l'utilizzo da parte di progetti che utilizzano il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a08f0-173">.NET Core projects can package custom MSBuild targets and properties for use by projects that consume the package.</span></span> <span data-ttu-id="a08f0-174">Utilizzare questo tipo di estendibilità quando si desidera:</span><span class="sxs-lookup"><span data-stu-id="a08f0-174">Use this type of extensibility when you want to:</span></span>

- <span data-ttu-id="a08f0-175">Estendere il processo di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a08f0-175">Extend the build process.</span></span>
- <span data-ttu-id="a08f0-176">Accedere agli elementi del processo di compilazione, ad esempio i file generati.</span><span class="sxs-lookup"><span data-stu-id="a08f0-176">Access artifacts of the build process, such as generated files.</span></span>
- <span data-ttu-id="a08f0-177">Esaminare la configurazione in cui viene richiamata la compilazione.</span><span class="sxs-lookup"><span data-stu-id="a08f0-177">Inspect the configuration under which the build is invoked.</span></span>

<span data-ttu-id="a08f0-178">È possibile aggiungere proprietà o destinazioni `<package_id>.targets` di `<package_id>.props` compilazione `Contoso.Utility.UsefulStuff.targets`personalizzate inserendo i file nel formato o (ad esempio) nella cartella di *compilazione* del progetto.</span><span class="sxs-lookup"><span data-stu-id="a08f0-178">You add custom build targets or properties by placing files in the form `<package_id>.targets` or `<package_id>.props` (for example, `Contoso.Utility.UsefulStuff.targets`) in the *build* folder of the project.</span></span>

<span data-ttu-id="a08f0-179">Il codice XML seguente è un frammento di [`dotnet pack`](../tools/dotnet-pack.md) codice da un file con estensione *csproj* che indica al comando cosa creare un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a08f0-179">The following XML is a snippet from a *.csproj* file that instructs the [`dotnet pack`](../tools/dotnet-pack.md) command what to package.</span></span> <span data-ttu-id="a08f0-180">L'elemento `<ItemGroup Label="dotnet pack instructions">` inserisce i file di destinazione nella cartella di *compilazione* all'interno del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a08f0-180">The `<ItemGroup Label="dotnet pack instructions">` element places the targets files into the *build* folder inside the package.</span></span> <span data-ttu-id="a08f0-181">L'elemento `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` inserisce gli assembly e i file *json* nella cartella di *compilazione.*</span><span class="sxs-lookup"><span data-stu-id="a08f0-181">The `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` element places the assemblies and *.json* files into the *build* folder.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  ...
  <ItemGroup Label="dotnet pack instructions">
    <Content Include="build\*.targets">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">
    <!-- Collect these items inside a target that runs after build but before packaging. -->
    <ItemGroup>
      <Content Include="$(OutputPath)\*.dll;$(OutputPath)\*.json">
        <Pack>true</Pack>
        <PackagePath>build\</PackagePath>
      </Content>
    </ItemGroup>
  </Target>
  ...
  
</Project>
```

<span data-ttu-id="a08f0-182">Per usare una destinazione personalizzata `PackageReference` nel progetto, aggiungere un elemento che punta al pacchetto e alla relativa versione.</span><span class="sxs-lookup"><span data-stu-id="a08f0-182">To consume a custom target in your project, add a `PackageReference` element that points to the package and its version.</span></span> <span data-ttu-id="a08f0-183">A differenza degli strumenti, il pacchetto di destinazioni personalizzate è incluso nella chiusura delle dipendenze del progetto consumer.</span><span class="sxs-lookup"><span data-stu-id="a08f0-183">Unlike the tools, the custom targets package is included in the consuming project's dependency closure.</span></span>

<span data-ttu-id="a08f0-184">È possibile configurare la modalità di utilizzo della destinazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a08f0-184">You can configure how to use the custom target.</span></span> <span data-ttu-id="a08f0-185">Poiché si tratta di una destinazione MSBuild, può dipendere da una determinata destinazione, eseguirla dopo un'altra destinazione o essere richiamata manualmente tramite il `dotnet msbuild -t:<target-name>` comando.</span><span class="sxs-lookup"><span data-stu-id="a08f0-185">Since it's an MSBuild target, it can depend on a given target, run after another target, or be manually invoked by using the `dotnet msbuild -t:<target-name>` command.</span></span> <span data-ttu-id="a08f0-186">Tuttavia, per offrire un'esperienza utente migliore, è possibile combinare strumenti per progetto e destinazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="a08f0-186">However, to provide a better user experience, you can combine per-project tools and custom targets.</span></span> <span data-ttu-id="a08f0-187">In questo scenario, lo strumento per progetto accetta i parametri necessari [`dotnet msbuild`](../tools/dotnet-msbuild.md) e lo converte nella chiamata richiesta che esegue la destinazione.</span><span class="sxs-lookup"><span data-stu-id="a08f0-187">In this scenario, the per-project tool accepts whatever parameters are needed and translates that into the required [`dotnet msbuild`](../tools/dotnet-msbuild.md) invocation that executes the target.</span></span> <span data-ttu-id="a08f0-188">È possibile visualizzare un esempio di questo tipo di sinergia nel repository degli [esempi di MVP Summit 2016 Hackathon](https://github.com/dotnet/MVPSummitHackathon2016) nel progetto [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer).</span><span class="sxs-lookup"><span data-stu-id="a08f0-188">You can see a sample of this kind of synergy on the [MVP Summit 2016 Hackathon samples](https://github.com/dotnet/MVPSummitHackathon2016) repo in the [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) project.</span></span>

## <a name="see-also"></a><span data-ttu-id="a08f0-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a08f0-189">See also</span></span>

- [<span data-ttu-id="a08f0-190">Installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="a08f0-190">Install .NET Core</span></span>](../install/index.md)
- [<span data-ttu-id="a08f0-191">Come utilizzare gli SDK del progetto MSBuildHow to use MSBuild project SDK</span><span class="sxs-lookup"><span data-stu-id="a08f0-191">How to use MSBuild project SDKs</span></span>](/visualstudio/msbuild/how-to-use-project-sdk)
- [<span data-ttu-id="a08f0-192">Creare il pacchetto di destinazioni e oggetti di scena MSBuild personalizzati con NuGetPackage custom MSBuild targets and props with NuGet</span><span class="sxs-lookup"><span data-stu-id="a08f0-192">Package custom MSBuild targets and props with NuGet</span></span>](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package)
