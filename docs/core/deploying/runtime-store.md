---
title: Archivio pacchetti di runtime
description: Questo argomento illustra l'archivio pacchetti di runtime e i manifesti di destinazione usati da .NET Core.
keywords: .NET, .NET Core, archivio dotnet, archivio pacchetti di runtime
author: bleroy
ms.author: mairaw
ms.date: 08/12/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 9521d8b4-25fc-412b-a65b-4c975ebf6bfd
ms.openlocfilehash: 607f8259fa6d8488a7fccf3c7d90b6cf40d5f237
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="runtime-package-store"></a><span data-ttu-id="1e1a1-104">Archivio pacchetti di runtime</span><span class="sxs-lookup"><span data-stu-id="1e1a1-104">Runtime package store</span></span>

<span data-ttu-id="1e1a1-105">A partire da .NET Core 2.0, è possibile creare un pacchetto e distribuire le app su un set noto di pacchetti esistenti nell'ambiente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-105">Starting with .NET Core 2.0, it's possible to package and deploy apps against a known set of packages that exist in the target environment.</span></span> <span data-ttu-id="1e1a1-106">I vantaggi sono distribuzioni più veloci, utilizzo ridotto dello spazio su disco e, in alcuni casi, migliori prestazioni di avvio.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-106">The benefits are faster deployments, lower disk space use, and improved startup performance in some cases.</span></span>

<span data-ttu-id="1e1a1-107">Questa funzionalità viene implementata come *archivio pacchetti di runtime*, che è una directory su disco in cui vengono archiviati i pacchetti, in genere */usr/local/share/dotnet/store* in macOS/Linux e *C:/Program Files/dotnet/store* in Windows.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-107">This feature is implemented as a *runtime package store*, which is a directory on disk where packages are stored (typically at */usr/local/share/dotnet/store* on macOS/Linux and *C:/Program Files/dotnet/store* on Windows).</span></span> <span data-ttu-id="1e1a1-108">In questa directory sono disponibili le sottodirectory per le architetture e i [framework di destinazione](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1e1a1-108">Under this directory, there are subdirectories for architectures and [target frameworks](../../standard/frameworks.md).</span></span> <span data-ttu-id="1e1a1-109">Il layout dei file è simile a quello con cui gli [asset NuGet sono disposti su disco](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):</span><span class="sxs-lookup"><span data-stu-id="1e1a1-109">The file layout is similar to the way that [NuGet assets are laid out on disk](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):</span></span>

<span data-ttu-id="1e1a1-110">\dotnet</span><span class="sxs-lookup"><span data-stu-id="1e1a1-110">\dotnet</span></span>   
<span data-ttu-id="1e1a1-111">&nbsp;&nbsp;\store</span><span class="sxs-lookup"><span data-stu-id="1e1a1-111">&nbsp;&nbsp;\store</span></span>   
<span data-ttu-id="1e1a1-112">&nbsp;&nbsp;&nbsp;&nbsp;\x64</span><span class="sxs-lookup"><span data-stu-id="1e1a1-112">&nbsp;&nbsp;&nbsp;&nbsp;\x64</span></span>   
<span data-ttu-id="1e1a1-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="1e1a1-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\netcoreapp2.0</span></span>   
<span data-ttu-id="1e1a1-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.applicationinsights</span><span class="sxs-lookup"><span data-stu-id="1e1a1-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.applicationinsights</span></span>   
<span data-ttu-id="1e1a1-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.aspnetcore</span><span class="sxs-lookup"><span data-stu-id="1e1a1-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.aspnetcore</span></span>   
<span data-ttu-id="1e1a1-116">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...</span><span class="sxs-lookup"><span data-stu-id="1e1a1-116">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...</span></span>   
<span data-ttu-id="1e1a1-117">&nbsp;&nbsp;&nbsp;&nbsp;\x86</span><span class="sxs-lookup"><span data-stu-id="1e1a1-117">&nbsp;&nbsp;&nbsp;&nbsp;\x86</span></span>   
<span data-ttu-id="1e1a1-118">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="1e1a1-118">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\netcoreapp2.0</span></span>   
<span data-ttu-id="1e1a1-119">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.applicationinsights</span><span class="sxs-lookup"><span data-stu-id="1e1a1-119">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.applicationinsights</span></span>   
<span data-ttu-id="1e1a1-120">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.aspnetcore</span><span class="sxs-lookup"><span data-stu-id="1e1a1-120">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.aspnetcore</span></span>   
<span data-ttu-id="1e1a1-121">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...</span><span class="sxs-lookup"><span data-stu-id="1e1a1-121">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...</span></span>   

<span data-ttu-id="1e1a1-122">Un file *manifesto di destinazione* elenca i pacchetti nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-122">A *target manifest* file lists the packages in the runtime package store.</span></span> <span data-ttu-id="1e1a1-123">Gli sviluppatori possono destinare questo manifesto quando pubblicano la propria applicazione.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-123">Developers can target this manifest when publishing their app.</span></span> <span data-ttu-id="1e1a1-124">Il manifesto di destinazione viene fornito in genere dal proprietario dell'ambiente di produzione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-124">The target manifest is typically provided by the owner of the targeted production environment.</span></span>

## <a name="preparing-a-runtime-environment"></a><span data-ttu-id="1e1a1-125">Preparazione di un ambiente di runtime</span><span class="sxs-lookup"><span data-stu-id="1e1a1-125">Preparing a runtime environment</span></span>

<span data-ttu-id="1e1a1-126">L'amministratore di un ambiente di runtime può ottimizzare le app per distribuzioni più veloci e utilizzo inferiore dello spazio su disco compilando un archivio di pacchetti di runtime e il manifesto di destinazione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-126">The administrator of a runtime environment can optimize apps for faster deployments and lower disk space use by building a runtime package store and the corresponding target manifest.</span></span>

<span data-ttu-id="1e1a1-127">Il primo passaggio consiste nel creare un *manifesto dell'archivio pacchetti* che elenca i pacchetti che compongono l'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-127">The first step is to create a *package store manifest* that lists the packages that compose the runtime package store.</span></span> <span data-ttu-id="1e1a1-128">Questo formato di file è compatibile con il formato di file del progetto (*csproj*).</span><span class="sxs-lookup"><span data-stu-id="1e1a1-128">This file format is compatible with the project file format (*csproj*).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="<NUGET_PACKAGE>" Version="<VERSION>" />
    <!-- Include additional packages here -->
  </ItemGroup>
</Project>
```

<span data-ttu-id="1e1a1-129">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="1e1a1-129">**Example**</span></span>

<span data-ttu-id="1e1a1-130">Il manifesto dell'archivio pacchetti di esempio seguente (*packages.csproj*) viene usato per aggiungere [ `Newtonsoft.Json` ](https://www.nuget.org/packages/Newtonsoft.Json/) e [ `Moq` ](https://www.nuget.org/packages/moq/) a un archivio pacchetti di runtime:</span><span class="sxs-lookup"><span data-stu-id="1e1a1-130">The following example package store manifest (*packages.csproj*) is used to add [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) and [`Moq`](https://www.nuget.org/packages/moq/) to a runtime package store:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.3" />
    <PackageReference Include="Moq" Version="4.7.63" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="1e1a1-131">Eseguire il provisioning dell'archivio pacchetti di runtime eseguendo `dotnet store` con il manifesto dell'archivio pacchetti, il runtime e il framework:</span><span class="sxs-lookup"><span data-stu-id="1e1a1-131">Provision the runtime package store by executing `dotnet store` with the package store manifest, runtime, and framework:</span></span>

```console
dotnet store --manifest <PATH_TO_MANIFEST_FILE> --runtime <RUNTIME_IDENTIFIER> --framework <FRAMEWORK>
```

<span data-ttu-id="1e1a1-132">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="1e1a1-132">**Example**</span></span>

```console
dotnet store --manifest packages.csproj --runtime win10-x64 --framework netcoreapp2.0 --framework-version 2.0.0
```

<span data-ttu-id="1e1a1-133">È possibile passare più percorsi del manifesto dell'archivio pacchetti di destinazione a un singolo comando [ `dotnet store` ](../tools/dotnet-store.md) ripetendo l'opzione e il percorso nel comando.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-133">You can pass multiple target package store manifest paths to a single [`dotnet store`](../tools/dotnet-store.md) command by repeating the option and path in the command.</span></span>

<span data-ttu-id="1e1a1-134">Per impostazione predefinita, l'output del comando è un archivio pacchetti nella sottodirectory *.dotnet/store* del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-134">By default, the output of the command is a package store under the *.dotnet/store* subdirectory of the user's profile.</span></span> <span data-ttu-id="1e1a1-135">È possibile specificare un percorso diverso usando l'opzione `--output <OUTPUT_DIRECTORY>`.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-135">You can specify a different location using the `--output <OUTPUT_DIRECTORY>` option.</span></span> <span data-ttu-id="1e1a1-136">La directory radice dell'archivio contiene un file manifesto di destinazione *artifact.xml*.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-136">The root directory of the store contains a target manifest *artifact.xml* file.</span></span> <span data-ttu-id="1e1a1-137">Questo file può essere reso disponibile per il download e usato dagli autori di app che intendono eseguire la destinazione di questo archivio durante la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-137">This file can be made available for download and be used by app authors who want to target this store when publishing.</span></span>

<span data-ttu-id="1e1a1-138">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="1e1a1-138">**Example**</span></span>

<span data-ttu-id="1e1a1-139">Il file *artifact.xml* seguente viene generato dopo l'esecuzione dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-139">The following *artifact.xml* file is produced after running the previous example.</span></span> <span data-ttu-id="1e1a1-140">Si noti che [ `Castle.Core` ](https://www.nuget.org/packages/Castle.Core/) è una dipendenza di `Moq` e viene quindi incluso automaticamente e visualizzato nel file manifesto *artifacts.xml*.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-140">Note that [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) is a dependency of `Moq`, so it's included automatically and appears in the *artifacts.xml* manifest file.</span></span>

```xml
<StoreArtifacts>
  <Package Id="Newtonsoft.Json" Version="10.0.3" />
  <Package Id="Castle.Core" Version="4.1.0" />
  <Package Id="Moq" Version="4.7.63" />
</StoreArtifacts>
```

## <a name="publishing-an-app-against-a-target-manifest"></a><span data-ttu-id="1e1a1-141">Pubblicazione di un'app con un manifesto di destinazione</span><span class="sxs-lookup"><span data-stu-id="1e1a1-141">Publishing an app against a target manifest</span></span>

<span data-ttu-id="1e1a1-142">Se si dispone di un file manifesto di destinazione su disco, specificare il percorso del file durante la pubblicazione dell'app con il comando [ `dotnet publish` ](../tools/dotnet-publish.md):</span><span class="sxs-lookup"><span data-stu-id="1e1a1-142">If you have a target manifest file on disk, you specify the path to the file when publishing your app with the [`dotnet publish`](../tools/dotnet-publish.md) command:</span></span>

```console
dotnet publish --manifest <PATH_TO_MANIFEST_FILE>
```

<span data-ttu-id="1e1a1-143">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="1e1a1-143">**Example**</span></span>

```console
dotnet publish --manifest manifest.xml
```

<span data-ttu-id="1e1a1-144">Distribuire l'app pubblicata risultante in un ambiente contenente i pacchetti descritti nel manifesto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-144">You deploy the resulting published app to an environment that has the packages described in the target manifest.</span></span> <span data-ttu-id="1e1a1-145">In caso contrario, si verifica un errore di avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-145">Failing to do so results in the app failing to start.</span></span>

<span data-ttu-id="1e1a1-146">Specificare più manifesti di destinazione quando si pubblica un'app ripetendo l'opzione e il percorso, ad esempio `--manifest manifest1.xml --manifest manifest2.xml`.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-146">Specify multiple target manifests when publishing an app by repeating the option and path (for example, `--manifest manifest1.xml --manifest manifest2.xml`).</span></span> <span data-ttu-id="1e1a1-147">Quando si esegue questa operazione, l'app viene rimossa per l'unione dei pacchetti specificati nei file manifesto di destinazione forniti al comando.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-147">When you do so, the app is trimmed for the union of packages specified in the target manifest files provided to the command.</span></span>

## <a name="specifying-target-manifests-in-the-project-file"></a><span data-ttu-id="1e1a1-148">Specifica dei manifesti di destinazione nel file di progetto</span><span class="sxs-lookup"><span data-stu-id="1e1a1-148">Specifying target manifests in the project file</span></span>

<span data-ttu-id="1e1a1-149">Un'alternativa alla specifica di manifesti di destinazione con il comando [ `dotnet publish` ](../tools/dotnet-publish.md) è quella di specificarli nel file di progetto come elenco di percorsi delimitato da punto e virgola in un tag  **\<TargetManifestFiles>**.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-149">An alternative to specifying target manifests with the [`dotnet publish`](../tools/dotnet-publish.md) command is to specify them in the project file as a semicolon-separated list of paths under a **\<TargetManifestFiles>** tag.</span></span>

```xml
<PropertyGroup>
  <TargetManifestFiles>manifest1.xml;manifest2.xml</TargetManifestFiles>
</PropertyGroup>
```

<span data-ttu-id="1e1a1-150">Specificare i manifesti di destinazione nel file di progetto solo quando l'ambiente di destinazione per l'app è noto, come per i progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-150">Specify the target manifests in the project file only when the target environment for the app is well-known, such as for .NET Core projects.</span></span> <span data-ttu-id="1e1a1-151">Non è il caso di progetti open source.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-151">This isn't the case for open-source projects.</span></span> <span data-ttu-id="1e1a1-152">Gli utenti di un progetto open source in genere lo distribuiscono in ambienti di produzione diversi.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-152">The users of an open-source project typically deploy it to different production environments.</span></span> <span data-ttu-id="1e1a1-153">In genere questi ambienti di produzione includono diversi set di pacchetti pre-installati.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-153">These production environments generally have different sets of packages pre-installed.</span></span> <span data-ttu-id="1e1a1-154">Non è possibile fare ipotesi sul manifesto di destinazione presente in tali ambienti ed è quindi necessario usare l'opzione `--manifest` di [`dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="1e1a1-154">You can't make assumptions about the target manifest in such environments, so you should use the `--manifest` option of [`dotnet publish`](../tools/dotnet-publish.md).</span></span>

## <a name="aspnet-core-implicit-store"></a><span data-ttu-id="1e1a1-155">Archivio implicito di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1e1a1-155">ASP.NET Core implicit store</span></span>

<span data-ttu-id="1e1a1-156">La funzionalità di archivio pacchetti di runtime viene usata in modo implicito da un'app ASP.NET Core quando l'app viene distribuita come app con [distribuzione dipendente da framework (FDD, Framework-Dependent Deployment)](index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="1e1a1-156">The runtime package store feature is used implicitly by an ASP.NET Core app when the app is deployed as a [framework-dependent deployment (FDD)](index.md#framework-dependent-deployments-fdd) app.</span></span> <span data-ttu-id="1e1a1-157">Le destinazioni in [ `Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) includono manifesti che fanno riferimento all'archivio pacchetti implicito nel sistema di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-157">The targets in [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) include manifests referencing the implicit package store on the target system.</span></span> <span data-ttu-id="1e1a1-158">Inoltre, qualsiasi app con distribuzione dipendente da framework (FDD, Framework-Dependent Deployment) dipende dal pacchetto `Microsoft.AspNetCore.All` genera un'app pubblicata che contiene solo l'app e gli asset e non i pacchetti elencati nel metapacchetto `Microsoft.AspNetCore.All`.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-158">Additionally, any FDD app that depends on the `Microsoft.AspNetCore.All` package results in a published app that contains only the app and its assets and not the packages listed in the `Microsoft.AspNetCore.All` metapackage.</span></span> <span data-ttu-id="1e1a1-159">Si presuppone che questi pacchetti siano presenti nel sistema di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-159">It's assumed that those packages are present on the target system.</span></span>

<span data-ttu-id="1e1a1-160">L'archivio pacchetti di runtime viene installato nell'host quando viene installato .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-160">The runtime package store is installed on the host when the .NET Core SDK is installed.</span></span> <span data-ttu-id="1e1a1-161">Altri programmi di installazione possono fornire l'archivio pacchetti di runtime, incluse le installazioni di Zip/tarball di SDK .NET Core, `apt-get`, Red Hat Yum, il bundle di .NET Core Windows Server Hosting e le installazioni manuali di archivi pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-161">Other installers may provide the runtime package store, including Zip/tarball installations of the .NET Core SDK, `apt-get`, Red Hat Yum, the .NET Core Windows Server Hosting bundle, and manual runtime package store installations.</span></span>

<span data-ttu-id="1e1a1-162">Quando si distribuisce un'app con [distribuzione dipendente da framework (FDD, Framework-Dependent Deployment)](index.md#framework-dependent-deployments-fdd), verificare che nell'ambiente di destinazione sia installato .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-162">When deploying a [framework-dependent deployment (FDD)](index.md#framework-dependent-deployments-fdd) app, make sure that the target environment has the .NET Core SDK installed.</span></span> <span data-ttu-id="1e1a1-163">Se l'app viene distribuita in un ambiente che non include ASP.NET Core, è possibile rifiutare esplicitamente l'archivio implicito specificando **\<PublishWithAspNetCoreTargetManifest >** impostato su `false` nel file di progetto, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1e1a1-163">If the app is deployed to an environment that doesn't include ASP.NET Core, you can opt out of the implicit store by specifying  **\<PublishWithAspNetCoreTargetManifest>** set to `false` in the project file as in the following example:</span></span>

```xml
<PropertyGroup>
  <PublishWithAspNetCoreTargetManifest>false</PublishWithAspNetCoreTargetManifest>
</PropertyGroup>
```

> [!NOTE] 
> <span data-ttu-id="1e1a1-164">Per le app con [distribuzione indipendente (SCD, Self-Contained Deployment)](index.md#self-contained-deployments-scd), si presuppone che il sistema di destinazione non contenga necessariamente i pacchetti del manifesto necessari.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-164">For [self-contained deployment (SCD)](index.md#self-contained-deployments-scd) apps, it's assumed that the target system doesn't necessarily contain the required manifest packages.</span></span> <span data-ttu-id="1e1a1-165">Pertanto,  **\<PublishWithAspNetCoreTargetManifest >** non può essere impostato su `true` per un'app con distribuzione indipendente (SCD, Self-Contained Deployment).</span><span class="sxs-lookup"><span data-stu-id="1e1a1-165">Therefore, **\<PublishWithAspNetCoreTargetManifest>** cannot be set to `true` for an SCD app.</span></span>

<span data-ttu-id="1e1a1-166">Se si distribuisce un'applicazione con una dipendenza del manifesto che è presente nella distribuzione (l'assembly si trova nella cartella *bin*), l'archivio pacchetti di runtime *non viene usato* nell'host per tale assembly.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-166">If you deploy an application with a manifest dependency that's present in the deployment (the assembly is present in the *bin* folder), the runtime package store *isn't used* on the host for that assembly.</span></span> <span data-ttu-id="1e1a1-167">L'assembly della cartella *bin* viene usato indipendentemente dalla sua presenza nell'archivio pacchetti di runtime nell'host.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-167">The *bin* folder assembly is used regardless of its presence in the runtime package store on the host.</span></span>

<span data-ttu-id="1e1a1-168">La versione della dipendenza indicata nel manifesto deve corrispondere alla versione della dipendenza nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-168">The version of the dependency indicated in the manifest must match the version of the dependency in the runtime package store.</span></span> <span data-ttu-id="1e1a1-169">In caso di mancata corrispondenza tra la dipendenza nel manifesto di destinazione e la versione esistente nell'archivio pacchetti di runtime e se l'app non include la versione necessaria del pacchetto nella relativa distribuzione, l'app non verrà avviata.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-169">If you have a version mismatch between the dependency in the target manifest and the version that exists in the runtime package store and the app doesn't include the required version of the package in its deployment, the app fails to start.</span></span> <span data-ttu-id="1e1a1-170">L'eccezione include il nome del manifesto di destinazione chiamato per assembly dell'archivio pacchetti di runtime e questa informazione è utile per risolvere la mancata corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-170">The exception includes the name of the target manifest that called for the runtime package store assembly, which helps you troubleshoot the mismatch.</span></span>

<span data-ttu-id="1e1a1-171">Quando la distribuzione viene *tagliata* nella pubblicazione, solo le versioni specifiche dei pacchetti del manifesto indicate vengono trattenute dall'output pubblicato.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-171">When the deployment is *trimmed* on publish, only the specific versions of the manifest packages you indicate are withheld from the published output.</span></span> <span data-ttu-id="1e1a1-172">I pacchetti nelle versioni indicate devono essere presenti nell'host per consentire l'avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="1e1a1-172">The packages at the versions indicated must be present on the host for the app to start.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e1a1-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e1a1-173">See also</span></span>
 [<span data-ttu-id="1e1a1-174">dotnet-publish</span><span class="sxs-lookup"><span data-stu-id="1e1a1-174">dotnet-publish</span></span>](../tools/dotnet-publish.md)  
 [<span data-ttu-id="1e1a1-175">dotnet-store</span><span class="sxs-lookup"><span data-stu-id="1e1a1-175">dotnet-store</span></span>](../tools/dotnet-store.md)  
