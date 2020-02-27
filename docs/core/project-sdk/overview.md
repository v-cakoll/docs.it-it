---
title: Panoramica dell'SDK del progetto .NET Core
description: Informazioni sugli SDK per progetti .NET Core.
ms.date: 02/02/2020
ms.topic: conceptual
ms.openlocfilehash: c41b25bf7933e7b1f6cb50da5e52dc0b312f5c74
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626249"
---
# <a name="net-core-project-sdks"></a><span data-ttu-id="53fc4-103">SDK per progetti .NET Core</span><span class="sxs-lookup"><span data-stu-id="53fc4-103">.NET Core project SDKs</span></span>

<span data-ttu-id="53fc4-104">I progetti .NET Core sono associati a un Software Development Kit (SDK).</span><span class="sxs-lookup"><span data-stu-id="53fc4-104">.NET Core projects are associated with a software development kit (SDK).</span></span> <span data-ttu-id="53fc4-105">Ogni SDK di progetto è un set di [destinazioni](/visualstudio/msbuild/msbuild-targets) MSBuild e [attività](/visualstudio/msbuild/msbuild-tasks) associate responsabili della compilazione, della compressione e della pubblicazione di codice.</span><span class="sxs-lookup"><span data-stu-id="53fc4-105">Each project SDK is a set of MSBuild [targets](/visualstudio/msbuild/msbuild-targets) and associated [tasks](/visualstudio/msbuild/msbuild-tasks) that are responsible for compiling, packing, and publishing code.</span></span>

## <a name="available-sdks"></a><span data-ttu-id="53fc4-106">SDK disponibili</span><span class="sxs-lookup"><span data-stu-id="53fc4-106">Available SDKs</span></span>

<span data-ttu-id="53fc4-107">Per .NET Core sono disponibili gli SDK seguenti:</span><span class="sxs-lookup"><span data-stu-id="53fc4-107">The following SDKs are available for .NET Core:</span></span>

| <span data-ttu-id="53fc4-108">ID</span><span class="sxs-lookup"><span data-stu-id="53fc4-108">ID</span></span> | <span data-ttu-id="53fc4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53fc4-109">Description</span></span> | <span data-ttu-id="53fc4-110">Repo</span><span class="sxs-lookup"><span data-stu-id="53fc4-110">Repo</span></span>|
| - | - | - |
| `Microsoft.NET.Sdk` | <span data-ttu-id="53fc4-111">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="53fc4-111">The .NET Core SDK</span></span> | https://github.com/dotnet/sdk |
| `Microsoft.NET.Sdk.Web` | <span data-ttu-id="53fc4-112">[SDK Web](/aspnet/core/razor-pages/web-sdk) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="53fc4-112">The .NET Core [Web SDK](/aspnet/core/razor-pages/web-sdk)</span></span> | https://github.com/aspnet/websdk |
| `Microsoft.NET.Sdk.Razor` | <span data-ttu-id="53fc4-113">.NET Core [Razor SDK](/aspnet/core/razor-pages/sdk)</span><span class="sxs-lookup"><span data-stu-id="53fc4-113">The .NET Core [Razor SDK](/aspnet/core/razor-pages/sdk)</span></span> |
| `Microsoft.NET.Sdk.Worker` | <span data-ttu-id="53fc4-114">SDK del servizio Worker di .NET Core</span><span class="sxs-lookup"><span data-stu-id="53fc4-114">The .NET Core Worker Service SDK</span></span> |
| `Microsoft.NET.Sdk.WindowsDesktop` | <span data-ttu-id="53fc4-115">.NET Core WinForms e WPF SDK</span><span class="sxs-lookup"><span data-stu-id="53fc4-115">The .NET Core WinForms and WPF SDK</span></span> |

<span data-ttu-id="53fc4-116">Il .NET Core SDK è l'SDK di base per .NET Core.</span><span class="sxs-lookup"><span data-stu-id="53fc4-116">The .NET Core SDK is the base SDK for .NET Core.</span></span> <span data-ttu-id="53fc4-117">Gli altri SDK fanno riferimento al .NET Core SDK e i progetti associati agli altri SDK hanno tutte le proprietà di .NET Core SDK disponibili.</span><span class="sxs-lookup"><span data-stu-id="53fc4-117">The other SDKs reference the .NET Core SDK, and projects that are associated with the other SDKs have all the .NET Core SDK properties available to them.</span></span> <span data-ttu-id="53fc4-118">Il Web SDK, ad esempio, dipende dal .NET Core SDK e Razor SDK.</span><span class="sxs-lookup"><span data-stu-id="53fc4-118">The Web SDK, for example, depends on both the .NET Core SDK and the Razor SDK.</span></span>

<span data-ttu-id="53fc4-119">È anche possibile creare un proprio SDK che può essere distribuito tramite NuGet.</span><span class="sxs-lookup"><span data-stu-id="53fc4-119">You can also author your own SDK that can be distributed via NuGet.</span></span>

## <a name="project-files"></a><span data-ttu-id="53fc4-120">File di progetto</span><span class="sxs-lookup"><span data-stu-id="53fc4-120">Project files</span></span>

<span data-ttu-id="53fc4-121">I progetti .NET Core sono basati sul formato [MSBuild](/visualstudio/msbuild/msbuild) .</span><span class="sxs-lookup"><span data-stu-id="53fc4-121">.NET Core projects are based on the [MSBuild](/visualstudio/msbuild/msbuild) format.</span></span> <span data-ttu-id="53fc4-122">I file di progetto, che hanno estensioni come *. csproj* per C# i progetti e F# *. fsproj* per i progetti, sono in formato XML.</span><span class="sxs-lookup"><span data-stu-id="53fc4-122">Project files, which have extensions like *.csproj* for C# projects and *.fsproj* for F# projects, are in XML format.</span></span> <span data-ttu-id="53fc4-123">L'elemento radice di un file di progetto MSBuild è l'elemento [Project](/visualstudio/msbuild/project-element-msbuild) .</span><span class="sxs-lookup"><span data-stu-id="53fc4-123">The root element of an MSBuild project file is the [Project](/visualstudio/msbuild/project-element-msbuild) element.</span></span> <span data-ttu-id="53fc4-124">L'elemento `Project` dispone di un attributo `Sdk` facoltativo che specifica quale SDK (e versione) utilizzare.</span><span class="sxs-lookup"><span data-stu-id="53fc4-124">The `Project` element has an optional `Sdk` attribute that specifies which SDK (and version) to use.</span></span> <span data-ttu-id="53fc4-125">Per usare gli strumenti di .NET Core e compilare il codice, impostare l'attributo `Sdk` su uno degli ID nella tabella [SDK disponibili](#available-sdks) .</span><span class="sxs-lookup"><span data-stu-id="53fc4-125">To use the .NET Core tools and build your code, set the `Sdk` attribute to one of the IDs in the [Available SDKs](#available-sdks) table.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
</Project>
```

<span data-ttu-id="53fc4-126">Per specificare un SDK che deriva da NuGet, includere la versione alla fine del nome o specificare il nome e la versione nel file *Global. JSON* .</span><span class="sxs-lookup"><span data-stu-id="53fc4-126">To specify an SDK that comes from NuGet, include the version at the end of the name, or specify the name and version in the *global.json* file.</span></span>

```xml
<Project Sdk="MSBuild.Sdk.Extras/2.0.54">
  ...
</Project>
```

<span data-ttu-id="53fc4-127">Un altro modo per specificare l'SDK è con l'elemento dell' [SDK](/visualstudio/msbuild/sdk-element-msbuild) di primo livello:</span><span class="sxs-lookup"><span data-stu-id="53fc4-127">Another way to specify the SDK is with the top-level [Sdk](/visualstudio/msbuild/sdk-element-msbuild) element:</span></span>

```xml
<Project>
  <Sdk Name="Microsoft.NET.Sdk" />
  ...
</Project>
```

<span data-ttu-id="53fc4-128">Il riferimento a un SDK in uno di questi modi semplifica notevolmente i file di progetto per .NET Core.</span><span class="sxs-lookup"><span data-stu-id="53fc4-128">Referencing an SDK in one of these ways greatly simplifies project files for .NET Core.</span></span> <span data-ttu-id="53fc4-129">Durante la valutazione del progetto, MSBuild aggiunge le importazioni implicite per `Sdk.props` all'inizio del file di progetto e `Sdk.targets` nella parte inferiore.</span><span class="sxs-lookup"><span data-stu-id="53fc4-129">While evaluating the project, MSBuild adds implicit imports for `Sdk.props` at the top of the project file and `Sdk.targets` at the bottom.</span></span>

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
> <span data-ttu-id="53fc4-130">In un computer Windows, i file *SDK. props* e *SDK. targets* si trovano nella cartella *%ProgramFiles%\dotnet\sdk\\[Version] \Sdks\Microsoft.NET.Sdk\Sdk*</span><span class="sxs-lookup"><span data-stu-id="53fc4-130">On a Windows machine, the *Sdk.props* and *Sdk.targets* files can be found in the *%ProgramFiles%\dotnet\sdk\\[version]\Sdks\Microsoft.NET.Sdk\Sdk* folder.</span></span>

### <a name="preprocess-the-project-file"></a><span data-ttu-id="53fc4-131">Pre-elaborare il file di progetto</span><span class="sxs-lookup"><span data-stu-id="53fc4-131">Preprocess the project file</span></span>

<span data-ttu-id="53fc4-132">È possibile visualizzare il progetto completamente espanso poiché MSBuild lo rileva dopo che l'SDK e le relative destinazioni sono inclusi usando il comando `dotnet msbuild -preprocess`.</span><span class="sxs-lookup"><span data-stu-id="53fc4-132">You can see the fully expanded project as MSBuild sees it after the SDK and its targets are included by using the `dotnet msbuild -preprocess` command.</span></span> <span data-ttu-id="53fc4-133">L'opzione di [pre-elaborazione](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando [`dotnet msbuild`](../tools/dotnet-msbuild.md) Mostra i file che vengono importati, le relative origini e i relativi contributi alla compilazione senza compilare effettivamente il progetto.</span><span class="sxs-lookup"><span data-stu-id="53fc4-133">The [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) switch of the [`dotnet msbuild`](../tools/dotnet-msbuild.md) command shows which files are imported, their sources, and their contributions to the build without actually building the project.</span></span>

<span data-ttu-id="53fc4-134">Se il progetto dispone di più framework di destinazione, concentrare i risultati del comando su un solo Framework specificandone il risultato come proprietà di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="53fc4-134">If the project has multiple target frameworks, focus the results of the command on only one framework by specifying it as an MSBuild property.</span></span> <span data-ttu-id="53fc4-135">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="53fc4-135">For example:</span></span>

`dotnet msbuild -property:TargetFramework=netcoreapp2.0 -preprocess:output.xml`

### <a name="default-compilation-includes"></a><span data-ttu-id="53fc4-136">La compilazione predefinita include</span><span class="sxs-lookup"><span data-stu-id="53fc4-136">Default compilation includes</span></span>

<span data-ttu-id="53fc4-137">Le impostazioni predefinite include ed Escludi per gli elementi di compilazione e le risorse incorporate sono definite nell'SDK.</span><span class="sxs-lookup"><span data-stu-id="53fc4-137">The default includes and excludes for compile items and embedded resources are defined in the SDK.</span></span> <span data-ttu-id="53fc4-138">A differenza dei progetti non SDK .NET Framework, non è necessario specificare questi elementi nel file di progetto, perché i valori predefiniti coprono i casi d'uso più comuni.</span><span class="sxs-lookup"><span data-stu-id="53fc4-138">Unlike non-SDK .NET Framework projects, you don't need to specify these items in your project file, because the defaults cover most common use cases.</span></span> <span data-ttu-id="53fc4-139">In questo modo, i file di progetto più piccoli risultano più facili da comprendere e modificati manualmente, se necessario.</span><span class="sxs-lookup"><span data-stu-id="53fc4-139">This leads to smaller project files that are easier to understand as well as edit by hand, if needed.</span></span>

<span data-ttu-id="53fc4-140">La tabella seguente mostra l'elemento e i [glob](https://en.wikipedia.org/wiki/Glob_(programming)) che vengono inclusi ed esclusi nella .NET Core SDK:</span><span class="sxs-lookup"><span data-stu-id="53fc4-140">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are included and excluded in the .NET Core SDK:</span></span>

| <span data-ttu-id="53fc4-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="53fc4-141">Element</span></span>           | <span data-ttu-id="53fc4-142">GLOB Include</span><span class="sxs-lookup"><span data-stu-id="53fc4-142">Include glob</span></span>                              | <span data-ttu-id="53fc4-143">GLOB Exclude</span><span class="sxs-lookup"><span data-stu-id="53fc4-143">Exclude glob</span></span>                                                  | <span data-ttu-id="53fc4-144">GLOB Remove</span><span class="sxs-lookup"><span data-stu-id="53fc4-144">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| <span data-ttu-id="53fc4-145">Compile</span><span class="sxs-lookup"><span data-stu-id="53fc4-145">Compile</span></span>           | <span data-ttu-id="53fc4-146">\*\*/\*.cs (o altre estensioni del linguaggio)</span><span class="sxs-lookup"><span data-stu-id="53fc4-146">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="53fc4-147">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="53fc4-147">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="53fc4-148">N/D</span><span class="sxs-lookup"><span data-stu-id="53fc4-148">N/A</span></span>                      |
| <span data-ttu-id="53fc4-149">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="53fc4-149">EmbeddedResource</span></span>  | <span data-ttu-id="53fc4-150">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="53fc4-150">\*\*/\*.resx</span></span>                              | <span data-ttu-id="53fc4-151">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="53fc4-151">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="53fc4-152">N/D</span><span class="sxs-lookup"><span data-stu-id="53fc4-152">N/A</span></span>                      |
| <span data-ttu-id="53fc4-153">None</span><span class="sxs-lookup"><span data-stu-id="53fc4-153">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="53fc4-154">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="53fc4-154">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="53fc4-155">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="53fc4-155">\*\*/\*.cs; \*\*/\*.resx</span></span> |

> [!NOTE]
> <span data-ttu-id="53fc4-156">Per impostazione predefinita, le cartelle `./bin` e `./obj`, rappresentate dalle proprietà `$(BaseOutputPath)` e `$(BaseIntermediateOutputPath)` MSBuild, sono escluse dai glob.</span><span class="sxs-lookup"><span data-stu-id="53fc4-156">The `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, are excluded from the globs by default.</span></span> <span data-ttu-id="53fc4-157">Le esclusioni sono rappresentate dalla proprietà `$(DefaultItemExcludes)`.</span><span class="sxs-lookup"><span data-stu-id="53fc4-157">Excludes are represented by the property `$(DefaultItemExcludes)`.</span></span>

<span data-ttu-id="53fc4-158">Se si definiscono in modo esplicito questi elementi nel file di progetto, è probabile che si ottenga l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="53fc4-158">If you explicitly define these items in your project file, you're likely to get the following error:</span></span>

<span data-ttu-id="53fc4-159">**Sono stati inclusi elementi di compilazione duplicati. .NET SDK include gli elementi di compilazione dalla directory del progetto per impostazione predefinita. È possibile rimuovere questi elementi dal file di progetto o impostare la proprietà' EnableDefaultCompileItems ' su' false ' se si desidera includerli in modo esplicito nel file di progetto.**</span><span class="sxs-lookup"><span data-stu-id="53fc4-159">**Duplicate Compile items were included. The .NET SDK includes Compile items from your project directory by default. You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.**</span></span>

<span data-ttu-id="53fc4-160">Per risolvere l'errore, rimuovere gli elementi `Compile` espliciti che corrispondono a quelli impliciti elencati nella tabella precedente oppure impostare la proprietà `EnableDefaultCompileItems` su `false`, che disabilita l'inclusione implicita:</span><span class="sxs-lookup"><span data-stu-id="53fc4-160">To resolve the error, either remove the explicit `Compile` items that match the implicit ones listed on the previous table, or set the `EnableDefaultCompileItems` property to `false`, which disables implicit inclusion:</span></span>

```xml
<PropertyGroup>
  <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

<span data-ttu-id="53fc4-161">Se si vuole specificare, ad esempio, alcuni file da pubblicare con l'app, è comunque possibile usare i meccanismi MSBuild noti per tale elemento, ad esempio l'elemento `Content`.</span><span class="sxs-lookup"><span data-stu-id="53fc4-161">If you want to specify, for example, some files to get published with your app, you can still use the known MSBuild mechanisms for that, for example, the `Content` element.</span></span>

<span data-ttu-id="53fc4-162">`EnableDefaultCompileItems` Disabilita solo i glob `Compile` ma non influisce su altri glob, ad esempio il glob `None` implicito che si applica anche agli elementi \*. cs.</span><span class="sxs-lookup"><span data-stu-id="53fc4-162">`EnableDefaultCompileItems` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob that also applies to \*.cs items.</span></span> <span data-ttu-id="53fc4-163">Per questo motivo, Esplora soluzioni in Visual Studio Visualizza gli elementi \*. cs come parte del progetto, inclusi come elementi di `None`.</span><span class="sxs-lookup"><span data-stu-id="53fc4-163">Because of that, Solution Explorer in Visual Studio shows \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="53fc4-164">Per disabilitare il glob implicito `None`, impostare `EnableDefaultNoneItems` su `false`:</span><span class="sxs-lookup"><span data-stu-id="53fc4-164">To disable the implicit `None` glob, set `EnableDefaultNoneItems` to `false`:</span></span>

```xml
<PropertyGroup>
  <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

<span data-ttu-id="53fc4-165">Per disabilitare *tutti* i glob impliciti, impostare la proprietà `EnableDefaultItems` su `false`:</span><span class="sxs-lookup"><span data-stu-id="53fc4-165">To disable *all* implicit globs, set the `EnableDefaultItems` property to `false`:</span></span>

```xml
<PropertyGroup>
  <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="customize-the-build"></a><span data-ttu-id="53fc4-166">Personalizzare la compilazione</span><span class="sxs-lookup"><span data-stu-id="53fc4-166">Customize the build</span></span>

<span data-ttu-id="53fc4-167">Esistono diversi modi per [personalizzare una compilazione](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="53fc4-167">There are various ways to [customize a build](/visualstudio/msbuild/customize-your-build).</span></span> <span data-ttu-id="53fc4-168">Potrebbe essere necessario eseguire l'override di una proprietà passandola come argomento a un comando [MSBuild](/visualstudio/msbuild/msbuild-command-line-reference) o [DotNet](../tools/index.md) .</span><span class="sxs-lookup"><span data-stu-id="53fc4-168">You may want to override a property by passing it as an argument to an [msbuild](/visualstudio/msbuild/msbuild-command-line-reference) or [dotnet](../tools/index.md) command.</span></span> <span data-ttu-id="53fc4-169">È anche possibile aggiungere la proprietà al file di progetto o a un file *Directory. Build. props* .</span><span class="sxs-lookup"><span data-stu-id="53fc4-169">You can also add the property to the project file or to a *Directory.Build.props* file.</span></span> <span data-ttu-id="53fc4-170">Per un elenco di proprietà utili per i progetti .NET Core, vedere [Proprietà MSBuild per progetti .NET Core SDK](msbuild-props.md).</span><span class="sxs-lookup"><span data-stu-id="53fc4-170">For a list of useful properties for .NET Core projects, see [MSBuild properties for .NET Core SDK projects](msbuild-props.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="53fc4-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53fc4-171">See also</span></span>

- [<span data-ttu-id="53fc4-172">Installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="53fc4-172">Install .NET Core</span></span>](../install/index.md)
- [<span data-ttu-id="53fc4-173">Come usare gli SDK di progetto MSBuild</span><span class="sxs-lookup"><span data-stu-id="53fc4-173">How to use MSBuild project SDKs</span></span>](/visualstudio/msbuild/how-to-use-project-sdk)
