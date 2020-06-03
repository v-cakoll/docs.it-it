---
title: Confronto tra project.json e csproj
description: Vedere il mapping tra gli elementi project.json e csproj.
author: natemcmaster
ms.date: 03/13/2017
ms.openlocfilehash: a997b48f645ed58d15610a68aee7c67411f9763f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205838"
---
# <a name="a-mapping-between-projectjson-and-csproj-properties"></a><span data-ttu-id="8b3b5-103">Mapping tra le proprietà di project.json e csproj</span><span class="sxs-lookup"><span data-stu-id="8b3b5-103">A mapping between project.json and csproj properties</span></span>

<span data-ttu-id="8b3b5-104">di [Nate McMaster](https://github.com/natemcmaster)</span><span class="sxs-lookup"><span data-stu-id="8b3b5-104">By [Nate McMaster](https://github.com/natemcmaster)</span></span>

<span data-ttu-id="8b3b5-105">Durante lo sviluppo degli strumenti di .NET Core, è stata apportata una modifica importante che non supporta più i file *project.json* e sposta invece i progetti .NET Core nel formato MSBuild/csproj.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-105">During the development of the .NET Core tooling, an important design change was made to no longer support *project.json* files and instead move the .NET Core projects to the MSBuild/csproj format.</span></span>

<span data-ttu-id="8b3b5-106">Questo articolo illustra come vengono rappresentate le impostazioni di *project.json* nel formato MSBuild/csproj, offre informazioni sull'uso del nuovo formato e consente di capire le modifiche apportate dagli strumenti di migrazione quando si aggiorna un progetto alla nuova versione degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-106">This article shows how the settings in *project.json* are represented in the MSBuild/csproj format so you can learn how to use the new format and understand the changes made by the migration tools when you're upgrading your project to the latest version of the tooling.</span></span>

## <a name="the-csproj-format"></a><span data-ttu-id="8b3b5-107">Formato csproj</span><span class="sxs-lookup"><span data-stu-id="8b3b5-107">The csproj format</span></span>

<span data-ttu-id="8b3b5-108">Il nuovo formato, \*.csproj, è un formato basato su XML.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-108">The new format, \*.csproj, is an XML-based format.</span></span> <span data-ttu-id="8b3b5-109">L'esempio seguente illustra il nodo radice di un progetto .NET Core usando `Microsoft.NET.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-109">The following example shows the root node of a .NET Core project using the `Microsoft.NET.Sdk`.</span></span> <span data-ttu-id="8b3b5-110">Per i progetti Web, l'SDK usato è `Microsoft.NET.Sdk.Web`.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-110">For web projects, the SDK used is `Microsoft.NET.Sdk.Web`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
...
</Project>
```

## <a name="common-top-level-properties"></a><span data-ttu-id="8b3b5-111">Proprietà comuni di livello superiore</span><span class="sxs-lookup"><span data-stu-id="8b3b5-111">Common top-level properties</span></span>

### <a name="name"></a><span data-ttu-id="8b3b5-112">name</span><span class="sxs-lookup"><span data-stu-id="8b3b5-112">name</span></span>

```json
{
  "name": "MyProjectName"
}
```

<span data-ttu-id="8b3b5-113">Non più supportata.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-113">No longer supported.</span></span> <span data-ttu-id="8b3b5-114">In csproj è determinato dal nome del file di progetto, che in genere corrisponde al nome della directory.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-114">In csproj, this is determined by the project filename, which usually matches the directory name.</span></span> <span data-ttu-id="8b3b5-115">Ad esempio: `MyProjectName.csproj`.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-115">For example, `MyProjectName.csproj`.</span></span>

<span data-ttu-id="8b3b5-116">Per impostazione predefinita, il nome del file di progetto specifica anche il valore delle proprietà `<AssemblyName>` e `<PackageId>`.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-116">By default, the project filename also specifies the value of the `<AssemblyName>` and `<PackageId>` properties.</span></span>

```xml
<PropertyGroup>
  <AssemblyName>MyProjectName</AssemblyName>
  <PackageId>MyProjectName</PackageId>
</PropertyGroup>
```

<span data-ttu-id="8b3b5-117">La proprietà `<AssemblyName>` avrà un valore diverso da `<PackageId>` se la proprietà `buildOptions\outputName` è stata definita in project.json.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-117">The `<AssemblyName>` will have a different value than `<PackageId>` if `buildOptions\outputName` property was defined in project.json.</span></span>
<span data-ttu-id="8b3b5-118">Per altre informazioni, vedere [Altre opzioni comuni di compilazione](#other-common-build-options).</span><span class="sxs-lookup"><span data-stu-id="8b3b5-118">For more information, see [Other common build options](#other-common-build-options).</span></span>

### <a name="version"></a><span data-ttu-id="8b3b5-119">version</span><span class="sxs-lookup"><span data-stu-id="8b3b5-119">version</span></span>

```json
{
  "version": "1.0.0-alpha-*"
}
```

<span data-ttu-id="8b3b5-120">Usare le proprietà `VersionPrefix` e `VersionSuffix`:</span><span class="sxs-lookup"><span data-stu-id="8b3b5-120">Use the `VersionPrefix` and `VersionSuffix` properties:</span></span>

```xml
<PropertyGroup>
  <VersionPrefix>1.0.0</VersionPrefix>
  <VersionSuffix>alpha</VersionSuffix>
</PropertyGroup>
```

<span data-ttu-id="8b3b5-121">È anche possibile usare la proprietà `Version`, ma questa operazione potrebbe causare la sovrascrittura delle impostazioni della versione durante la creazione di pacchetti:</span><span class="sxs-lookup"><span data-stu-id="8b3b5-121">You can also use the `Version` property, but this may override version settings during packaging:</span></span>

```xml
<PropertyGroup>
  <Version>1.0.0-alpha</Version>
</PropertyGroup>
```

### <a name="other-common-root-level-options"></a><span data-ttu-id="8b3b5-122">Altre opzioni comuni a livello radice</span><span class="sxs-lookup"><span data-stu-id="8b3b5-122">Other common root-level options</span></span>

```json
{
  "authors": [ "Anne", "Bob" ],
  "company": "Contoso",
  "language": "en-US",
  "title": "My library",
  "description": "This is my library.\r\nAnd it's really great!",
  "copyright": "Nugetizer 3000",
  "userSecretsId": "xyz123"
}
```

```xml
<PropertyGroup>
  <Authors>Anne;Bob</Authors>
  <Company>Contoso</Company>
  <NeutralLanguage>en-US</NeutralLanguage>
  <AssemblyTitle>My library</AssemblyTitle>
  <Description>This is my library.
And it's really great!</Description>
  <Copyright>Nugetizer 3000</Copyright>
  <UserSecretsId>xyz123</UserSecretsId>
</PropertyGroup>
```

## <a name="frameworks"></a><span data-ttu-id="8b3b5-123">frameworks</span><span class="sxs-lookup"><span data-stu-id="8b3b5-123">frameworks</span></span>

### <a name="one-target-framework"></a><span data-ttu-id="8b3b5-124">Un solo framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="8b3b5-124">One target framework</span></span>

```json
{
  "frameworks": {
    "netcoreapp1.0": {}
  }
}
```

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp1.0</TargetFramework>
</PropertyGroup>
```

### <a name="multiple-target-frameworks"></a><span data-ttu-id="8b3b5-125">Più framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="8b3b5-125">Multiple target frameworks</span></span>

```json
{
  "frameworks": {
    "netcoreapp1.0": {},
    "net451": {}
  }
}
```

<span data-ttu-id="8b3b5-126">Usare la proprietà `TargetFrameworks` per definire l'elenco dei framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-126">Use the `TargetFrameworks` property to define your list of target frameworks.</span></span> <span data-ttu-id="8b3b5-127">Usare un punto e virgola per separare più valori di framework.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-127">Use semi-colon to separate multiple framework values.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp1.0;net451</TargetFrameworks>
</PropertyGroup>
```

## <a name="dependencies"></a><span data-ttu-id="8b3b5-128">dipendenze</span><span class="sxs-lookup"><span data-stu-id="8b3b5-128">dependencies</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b3b5-129">Se la dipendenza è un **progetto** e non un pacchetto, il formato è diverso.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-129">If the dependency is a **project** and not a package, the format is different.</span></span>
> <span data-ttu-id="8b3b5-130">Per altre informazioni, vedere la sezione [Tipo di dipendenza](#dependency-type).</span><span class="sxs-lookup"><span data-stu-id="8b3b5-130">For more information, see the [dependency type](#dependency-type) section.</span></span>

### <a name="netstandardlibrary-metapackage"></a><span data-ttu-id="8b3b5-131">Metapacchetto NETStandard.Library</span><span class="sxs-lookup"><span data-stu-id="8b3b5-131">NETStandard.Library metapackage</span></span>

```json
{
  "dependencies": {
    "NETStandard.Library": "1.6.0"
  }
}
```

```xml
<PropertyGroup>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

### <a name="microsoftnetcoreapp-metapackage"></a><span data-ttu-id="8b3b5-132">Metapacchetto Microsoft.NETCore.App</span><span class="sxs-lookup"><span data-stu-id="8b3b5-132">Microsoft.NETCore.App metapackage</span></span>

```json
{
  "dependencies": {
    "Microsoft.NETCore.App": "1.0.0"
  }
}
```

```xml
<PropertyGroup>
  <RuntimeFrameworkVersion>1.0.3</RuntimeFrameworkVersion>
</PropertyGroup>
```

<span data-ttu-id="8b3b5-133">Il `<RuntimeFrameworkVersion>` valore nel progetto migrato è determinato dalla versione dell'SDK installata.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-133">The `<RuntimeFrameworkVersion>` value in the migrated project is determined by the version of SDK that's installed.</span></span>

### <a name="top-level-dependencies"></a><span data-ttu-id="8b3b5-134">Dipendenze di livello superiore</span><span class="sxs-lookup"><span data-stu-id="8b3b5-134">Top-level dependencies</span></span>

```json
{
  "dependencies": {
    "Microsoft.AspNetCore": "1.1.0"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore" Version="1.1.0" />
</ItemGroup>
```

### <a name="per-framework-dependencies"></a><span data-ttu-id="8b3b5-135">Dipendenze per framework</span><span class="sxs-lookup"><span data-stu-id="8b3b5-135">Per-framework dependencies</span></span>

```json
{
  "framework": {
    "net451": {
      "dependencies": {
        "System.Collections.Immutable": "1.3.1"
      }
    },
    "netstandard1.5": {
      "dependencies": {
        "Newtonsoft.Json": "9.0.1"
      }
    }
  }
}
```

```xml
<ItemGroup Condition="'$(TargetFramework)'=='net451'">
  <PackageReference Include="System.Collections.Immutable" Version="1.3.1" />
</ItemGroup>

<ItemGroup Condition="'$(TargetFramework)'=='netstandard1.5'">
  <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
</ItemGroup>
```

### <a name="imports"></a><span data-ttu-id="8b3b5-136">importazioni</span><span class="sxs-lookup"><span data-stu-id="8b3b5-136">imports</span></span>

```json
{
  "dependencies": {
    "YamlDotNet": "4.0.1-pre309"
  },
  "frameworks": {
    "netcoreapp1.0": {
      "imports": [
        "dnxcore50",
        "dotnet"
      ]
    }
  }
}
```

```xml
<PropertyGroup>
  <PackageTargetFallback>dnxcore50;dotnet</PackageTargetFallback>
</PropertyGroup>
<ItemGroup>
  <PackageReference Include="YamlDotNet" Version="4.0.1-pre309" />
</ItemGroup>
```

### <a name="dependency-type"></a><span data-ttu-id="8b3b5-137">Tipo di dipendenza</span><span class="sxs-lookup"><span data-stu-id="8b3b5-137">dependency type</span></span>

#### <a name="type-project"></a><span data-ttu-id="8b3b5-138">Tipo: progetto</span><span class="sxs-lookup"><span data-stu-id="8b3b5-138">type: project</span></span>

```json
{
  "dependencies": {
    "MyOtherProject": "1.0.0-*",
    "AnotherProject": {
      "type": "project"
    }
  }
}
```

```xml
<ItemGroup>
  <ProjectReference Include="..\MyOtherProject\MyOtherProject.csproj" />
  <ProjectReference Include="..\AnotherProject\AnotherProject.csproj" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="8b3b5-139">Questa operazione interrompe il modo in cui `dotnet pack --version-suffix $suffix` determina la versione di dipendenza di un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-139">This will break the way that `dotnet pack --version-suffix $suffix` determines the dependency version of a project reference.</span></span>

#### <a name="type-build"></a><span data-ttu-id="8b3b5-140">Tipo: compilazione</span><span class="sxs-lookup"><span data-stu-id="8b3b5-140">type: build</span></span>

```json
{
  "dependencies": {
    "Microsoft.EntityFrameworkCore.Design": {
      "version": "1.1.0",
      "type": "build"
    }
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.EntityFrameworkCore.Design" Version="1.1.0" PrivateAssets="All" />
</ItemGroup>
```

#### <a name="type-platform"></a><span data-ttu-id="8b3b5-141">Tipo: piattaforma</span><span class="sxs-lookup"><span data-stu-id="8b3b5-141">type: platform</span></span>

```json
{
  "dependencies": {
    "Microsoft.NETCore.App": {
      "version": "1.1.0",
      "type": "platform"
    }
  }
}
```

<span data-ttu-id="8b3b5-142">Non è disponibile nessuna opzione equivalente in csproj.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-142">There is no equivalent in csproj.</span></span>

## <a name="runtimes"></a><span data-ttu-id="8b3b5-143">runtimes</span><span class="sxs-lookup"><span data-stu-id="8b3b5-143">runtimes</span></span>

```json
{
  "runtimes": {
    "win7-x64": {},
    "osx.10.11-x64": {},
    "ubuntu.16.04-x64": {}
  }
}
```

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win7-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="standalone-apps-self-contained-deployment"></a><span data-ttu-id="8b3b5-144">App indipendenti (distribuzione autonoma)</span><span class="sxs-lookup"><span data-stu-id="8b3b5-144">Standalone apps (self-contained deployment)</span></span>

<span data-ttu-id="8b3b5-145">In project.json, la definizione di una sezione `runtimes` indica che l'app era indipendente durante la compilazione e la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-145">In project.json, defining a `runtimes` section means the app was standalone during build and publish.</span></span>
<span data-ttu-id="8b3b5-146">In MSBuild, tutti i progetti sono *portatili* durante la creazione, ma possono essere pubblicati come autonomi.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-146">In MSBuild, all projects are *portable* during build, but can be published as standalone.</span></span>

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

<span data-ttu-id="8b3b5-147">Per altre informazioni, vedere [Distribuzioni autonome (SCD)](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="8b3b5-147">For more information, see [Self-contained deployments (SCD)](../deploying/index.md#publish-self-contained).</span></span>

## <a name="tools"></a><span data-ttu-id="8b3b5-148">tools</span><span class="sxs-lookup"><span data-stu-id="8b3b5-148">tools</span></span>

```json
{
  "tools": {
    "Microsoft.EntityFrameworkCore.Tools.DotNet": "1.0.0-*"
  }
}
```

```xml
<ItemGroup>
  <DotNetCliToolReference Include="Microsoft.EntityFrameworkCore.Tools.DotNet" Version="1.0.0" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="8b3b5-149">Gli `imports` sugli strumenti non sono supportati in csproj.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-149">`imports` on tools are not supported in csproj.</span></span> <span data-ttu-id="8b3b5-150">Gli strumenti che hanno bisogno di imports non funzionano con il nuovo `Microsoft.NET.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-150">Tools that need imports will not work with the new `Microsoft.NET.Sdk`.</span></span>

## <a name="buildoptions"></a><span data-ttu-id="8b3b5-151">buildOptions</span><span class="sxs-lookup"><span data-stu-id="8b3b5-151">buildOptions</span></span>

<span data-ttu-id="8b3b5-152">Vedere anche [Files](#files).</span><span class="sxs-lookup"><span data-stu-id="8b3b5-152">See also [Files](#files).</span></span>

### <a name="emitentrypoint"></a><span data-ttu-id="8b3b5-153">emitEntryPoint</span><span class="sxs-lookup"><span data-stu-id="8b3b5-153">emitEntryPoint</span></span>

```json
{
  "buildOptions": {
    "emitEntryPoint": true
  }
}
```

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="8b3b5-154">Se `emitEntryPoint` fosse `false`, il valore di `OutputType` verrebbe convertito in `Library`, ovvero il valore predefinito:</span><span class="sxs-lookup"><span data-stu-id="8b3b5-154">If `emitEntryPoint` was `false`, the value of `OutputType` is converted to `Library`, which is the default value:</span></span>

```json
{
  "buildOptions": {
    "emitEntryPoint": false
  }
}
```

```xml
<PropertyGroup>
  <OutputType>Library</OutputType>
  <!-- or, omit altogether. It defaults to 'Library' -->
</PropertyGroup>
```

### <a name="keyfile"></a><span data-ttu-id="8b3b5-155">keyFile</span><span class="sxs-lookup"><span data-stu-id="8b3b5-155">keyFile</span></span>

```json
{
  "buildOptions": {
    "keyFile": "MyKey.snk"
  }
}
```

<span data-ttu-id="8b3b5-156">L'elemento `keyFile` si espande a tre proprietà in MSBuild:</span><span class="sxs-lookup"><span data-stu-id="8b3b5-156">The `keyFile` element expands to three properties in MSBuild:</span></span>

```xml
<PropertyGroup>
  <AssemblyOriginatorKeyFile>MyKey.snk</AssemblyOriginatorKeyFile>
  <SignAssembly>true</SignAssembly>
  <PublicSign Condition="'$(OS)' != 'Windows_NT'">true</PublicSign>
</PropertyGroup>
```

### <a name="other-common-build-options"></a><span data-ttu-id="8b3b5-157">Altre opzioni comuni di compilazione</span><span class="sxs-lookup"><span data-stu-id="8b3b5-157">Other common build options</span></span>

```json
{
  "buildOptions": {
    "warningsAsErrors": true,
    "nowarn": ["CS0168", "CS0219"],
    "xmlDoc": true,
    "preserveCompilationContext": true,
    "outputName": "Different.AssemblyName",
    "debugType": "portable",
    "allowUnsafe": true,
    "define": ["TEST", "OTHERCONDITION"]
  }
}
```

```xml
<PropertyGroup>
  <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
  <NoWarn>$(NoWarn);CS0168;CS0219</NoWarn>
  <GenerateDocumentationFile>true</GenerateDocumentationFile>
  <PreserveCompilationContext>true</PreserveCompilationContext>
  <AssemblyName>Different.AssemblyName</AssemblyName>
  <DebugType>portable</DebugType>
  <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  <DefineConstants>$(DefineConstants);TEST;OTHERCONDITION</DefineConstants>
</PropertyGroup>
```

## <a name="packoptions"></a><span data-ttu-id="8b3b5-158">packOptions</span><span class="sxs-lookup"><span data-stu-id="8b3b5-158">packOptions</span></span>

<span data-ttu-id="8b3b5-159">Vedere anche [Files](#files).</span><span class="sxs-lookup"><span data-stu-id="8b3b5-159">See also [Files](#files).</span></span>

### <a name="common-pack-options"></a><span data-ttu-id="8b3b5-160">Opzioni comuni di pacchetto</span><span class="sxs-lookup"><span data-stu-id="8b3b5-160">Common pack options</span></span>

```json
{
  "packOptions": {
    "summary": "numl is a machine learning library intended to ease the use of using standard modeling techniques for both prediction and clustering.",
    "tags": ["machine learning", "framework"],
    "releaseNotes": "Version 0.9.12-beta",
    "iconUrl": "http://numl.net/images/ico.png",
    "projectUrl": "http://numl.net",
    "licenseUrl": "https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md",
    "requireLicenseAcceptance": false,
    "repository": {
      "type": "git",
      "url": "https://raw.githubusercontent.com/sethjuarez/numl"
    },
    "owners": ["Seth Juarez"]
  }
}
```

```xml
<PropertyGroup>
  <!-- summary is not migrated from project.json, but you can use the <Description> property for that if needed. -->
  <PackageTags>machine learning;framework</PackageTags>
  <PackageReleaseNotes>Version 0.9.12-beta</PackageReleaseNotes>
  <PackageIconUrl>http://numl.net/images/ico.png</PackageIconUrl>
  <PackageProjectUrl>http://numl.net</PackageProjectUrl>
  <PackageLicenseUrl>https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md</PackageLicenseUrl>
  <PackageRequireLicenseAcceptance>false</PackageRequireLicenseAcceptance>
  <RepositoryType>git</RepositoryType>
  <RepositoryUrl>https://raw.githubusercontent.com/sethjuarez/numl</RepositoryUrl>
  <!-- owners is not supported in MSBuild -->
</PropertyGroup>
```

<span data-ttu-id="8b3b5-161">Non è disponibile nessuna opzione equivalente per l'elemento `owners` in MSBuild.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-161">There is no equivalent for the `owners` element in MSBuild.</span></span> <span data-ttu-id="8b3b5-162">Per `summary` , è possibile usare la `<Description>` Proprietà MSBuild.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-162">For `summary`, you can use the MSBuild `<Description>` property.</span></span> <span data-ttu-id="8b3b5-163">Il valore di `summary` non viene migrato automaticamente a tale proprietà, dal momento che tale proprietà è mappata all' [`description`](#other-common-root-level-options) elemento.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-163">The value of `summary` is not migrated automatically to that property, since that property is mapped to the [`description`](#other-common-root-level-options) element.</span></span>

## <a name="scripts"></a><span data-ttu-id="8b3b5-164">script</span><span class="sxs-lookup"><span data-stu-id="8b3b5-164">scripts</span></span>

```json
{
  "scripts": {
    "precompile": "generateCode.cmd",
    "postpublish": [ "obfuscate.cmd", "removeTempFiles.cmd" ]
  }
}
```

<span data-ttu-id="8b3b5-165">Gli equivalenti in MSBuild sono [targets](/visualstudio/msbuild/msbuild-targets):</span><span class="sxs-lookup"><span data-stu-id="8b3b5-165">Their equivalents in MSBuild are [targets](/visualstudio/msbuild/msbuild-targets):</span></span>

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="generateCode.cmd" />
</Target>

<Target Name="MyPostCompileTarget" AfterTargets="Publish">
  <Exec Command="obfuscate.cmd" />
  <Exec Command="removeTempFiles.cmd" />
</Target>
```

## <a name="runtimeoptions"></a><span data-ttu-id="8b3b5-166">runtimeOptions</span><span class="sxs-lookup"><span data-stu-id="8b3b5-166">runtimeOptions</span></span>

```json
{
  "runtimeOptions": {
    "configProperties": {
      "System.GC.Server": true,
      "System.GC.Concurrent": true,
      "System.GC.RetainVM": true,
      "System.Threading.ThreadPool.MinThreads": 4,
      "System.Threading.ThreadPool.MaxThreads": 25
    }
  }
}
```

<span data-ttu-id="8b3b5-167">Tutte le impostazioni in questo gruppo, ad eccezione della `System.GC.Server` proprietà, vengono inserite in un file denominato *runtimeconfig. template. JSON* nella cartella del progetto, con le opzioni sollevate dall'oggetto radice durante il processo di migrazione:</span><span class="sxs-lookup"><span data-stu-id="8b3b5-167">All settings in this group, except for the `System.GC.Server` property, are placed into a file called *runtimeconfig.template.json* in the project folder, with options lifted to the root object during the migration process:</span></span>

```json
{
  "configProperties": {
    "System.GC.Concurrent": true,
    "System.GC.RetainVM": true,
    "System.Threading.ThreadPool.MinThreads": 4,
    "System.Threading.ThreadPool.MaxThreads": 25
  }
}
```

<span data-ttu-id="8b3b5-168">`System.GC.Server`Viene eseguita la migrazione della proprietà nel file csproj:</span><span class="sxs-lookup"><span data-stu-id="8b3b5-168">The `System.GC.Server` property is migrated into the csproj file:</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

<span data-ttu-id="8b3b5-169">È possibile tuttavia impostare tutti questi valori nel file csproj e anche nelle proprietà di MSBuild:</span><span class="sxs-lookup"><span data-stu-id="8b3b5-169">However, you can set all those values in the csproj as well as MSBuild properties:</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
  <ConcurrentGarbageCollection>true</ConcurrentGarbageCollection>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
</PropertyGroup>
```

## <a name="shared"></a><span data-ttu-id="8b3b5-170">shared</span><span class="sxs-lookup"><span data-stu-id="8b3b5-170">shared</span></span>

```json
{
  "shared": "shared/**/*.cs"
}
```

<span data-ttu-id="8b3b5-171">Non supportato in csproj.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-171">Not supported in csproj.</span></span> <span data-ttu-id="8b3b5-172">Al contrario, creare file di contenuto di inclusione nel file con *estensione NuSpec* .</span><span class="sxs-lookup"><span data-stu-id="8b3b5-172">Instead, create include content files in your *.nuspec* file.</span></span>
<span data-ttu-id="8b3b5-173">Per altre informazioni, vedere [Including content files](/nuget/schema/nuspec#including-content-files) (Includere i file di contenuto).</span><span class="sxs-lookup"><span data-stu-id="8b3b5-173">For more information, see [Including content files](/nuget/schema/nuspec#including-content-files).</span></span>

## <a name="files"></a><span data-ttu-id="8b3b5-174">files</span><span class="sxs-lookup"><span data-stu-id="8b3b5-174">files</span></span>

<span data-ttu-id="8b3b5-175">In *project.json*, la compilazione e la creazione di pacchetti possono essere estese per compilare e incorporare da cartelle diverse.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-175">In *project.json*, build and pack could be extended to compile and embed from different folders.</span></span>
<span data-ttu-id="8b3b5-176">In MSBuild, questa operazione viene eseguita tramite [items](/visualstudio/msbuild/common-msbuild-project-items).</span><span class="sxs-lookup"><span data-stu-id="8b3b5-176">In MSBuild, this is done using [items](/visualstudio/msbuild/common-msbuild-project-items).</span></span> <span data-ttu-id="8b3b5-177">L'esempio seguente illustra una conversione comune:</span><span class="sxs-lookup"><span data-stu-id="8b3b5-177">The following example is a common conversion:</span></span>

```json
{
  "buildOptions": {
    "compile": {
      "copyToOutput": "notes.txt",
      "include": "../Shared/*.cs",
      "exclude": "../Shared/Not/*.cs"
    },
    "embed": {
      "include": "../Shared/*.resx"
    }
  },
  "packOptions": {
    "include": "Views/",
    "mappings": {
      "some/path/in/project.txt": "in/package.txt"
    }
  },
  "publishOptions": {
    "include": [
      "files/",
      "publishnotes.txt"
    ]
  }
}
```

```xml
<ItemGroup>
  <Compile Include="..\Shared\*.cs" Exclude="..\Shared\Not\*.cs" />
  <EmbeddedResource Include="..\Shared\*.resx" />
  <Content Include="Views\**\*" PackagePath="%(Identity)" />
  <None Include="some/path/in/project.txt" Pack="true" PackagePath="in/package.txt" />
  
  <None Include="notes.txt" CopyToOutputDirectory="Always" />
  <!-- CopyToOutputDirectory = { Always, PreserveNewest, Never } -->

  <Content Include="files\**\*" CopyToPublishDirectory="PreserveNewest" />
  <None Include="publishnotes.txt" CopyToPublishDirectory="Always" />
  <!-- CopyToPublishDirectory = { Always, PreserveNewest, Never } -->
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="8b3b5-178">Molti dei [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) predefiniti vengono aggiunti automaticamente da .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-178">Many of the default [globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are added automatically by the .NET Core SDK.</span></span> <span data-ttu-id="8b3b5-179">Per ulteriori informazioni, vedere la pagina relativa alla [compilazione predefinita](../project-sdk/overview.md#default-compilation-includes).</span><span class="sxs-lookup"><span data-stu-id="8b3b5-179">For more information, see [Default compilation includes](../project-sdk/overview.md#default-compilation-includes).</span></span>

<span data-ttu-id="8b3b5-180">Tutti gli elementi `ItemGroup` di MSBuild supportano `Include`, `Exclude` e `Remove`.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-180">All MSBuild `ItemGroup` elements support `Include`, `Exclude`, and `Remove`.</span></span>

<span data-ttu-id="8b3b5-181">Il layout del pacchetto all'interno di .nupkg può essere modificato con `PackagePath="path"`.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-181">Package layout inside the .nupkg can be modified with `PackagePath="path"`.</span></span>

<span data-ttu-id="8b3b5-182">Ad eccezione di `Content`, la maggior parte dei gruppi di elementi richiedono in modo esplicito l'aggiunta di `Pack="true"` nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-182">Except for `Content`, most item groups require explicitly adding `Pack="true"` to be included in the package.</span></span> <span data-ttu-id="8b3b5-183">`Content` verrà incluso nella cartella *content* in un pacchetto poiché la proprietà `<IncludeContentInPack>` di MSBuild è impostata su `true` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-183">`Content` will be put in the *content* folder in a package since the MSBuild `<IncludeContentInPack>` property is set to `true` by default.</span></span>
<span data-ttu-id="8b3b5-184">Per altre informazioni, vedere [Including content in a package](/nuget/schema/msbuild-targets#including-content-in-a-package) (Includere contenuto in un pacchetto).</span><span class="sxs-lookup"><span data-stu-id="8b3b5-184">For more information, see [Including content in a package](/nuget/schema/msbuild-targets#including-content-in-a-package).</span></span>

<span data-ttu-id="8b3b5-185">`PackagePath="%(Identity)"` è un modo breve di impostare il percorso di un pacchetto sul percorso del file relativo al progetto.</span><span class="sxs-lookup"><span data-stu-id="8b3b5-185">`PackagePath="%(Identity)"` is a short way of setting package path to the project-relative file path.</span></span>

## <a name="testrunner"></a><span data-ttu-id="8b3b5-186">testRunner</span><span class="sxs-lookup"><span data-stu-id="8b3b5-186">testRunner</span></span>

### <a name="xunit"></a><span data-ttu-id="8b3b5-187">xUnit</span><span class="sxs-lookup"><span data-stu-id="8b3b5-187">xUnit</span></span>

```json
{
  "testRunner": "xunit",
  "dependencies": {
    "dotnet-test-xunit": "<any>"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-*" />
  <PackageReference Include="xunit" Version="2.2.0-*" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0-*" />
</ItemGroup>
```

### <a name="mstest"></a><span data-ttu-id="8b3b5-188">MSTest</span><span class="sxs-lookup"><span data-stu-id="8b3b5-188">MSTest</span></span>

```json
{
  "testRunner": "mstest",
  "dependencies": {
    "dotnet-test-mstest": "<any>"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-*" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.12-*" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.11-*" />
</ItemGroup>
```

## <a name="see-also"></a><span data-ttu-id="8b3b5-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b3b5-189">See also</span></span>

- <span data-ttu-id="8b3b5-190">[High-level overview of changes in CLI](cli-msbuild-architecture.md) (Panoramica generale sulle modifiche nell'interfaccia della riga di comando)</span><span class="sxs-lookup"><span data-stu-id="8b3b5-190">[High-level overview of changes in CLI](cli-msbuild-architecture.md)</span></span>
