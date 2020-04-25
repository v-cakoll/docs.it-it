---
title: Archivio pacchetti di runtime
description: Informazioni su come usare l'archivio pacchetti di runtime per specificare come destinazione i manifesti usati da .NET Core.
ms.date: 08/12/2017
ms.openlocfilehash: 4395370c3bb2d97511d549a63813022fb8cac4b7
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158290"
---
# <a name="runtime-package-store"></a><span data-ttu-id="abada-103">Archivio pacchetti di runtime</span><span class="sxs-lookup"><span data-stu-id="abada-103">Runtime package store</span></span>

<span data-ttu-id="abada-104">A partire da .NET Core 2.0, è possibile creare un pacchetto e distribuire le app su un set noto di pacchetti esistenti nell'ambiente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="abada-104">Starting with .NET Core 2.0, it's possible to package and deploy apps against a known set of packages that exist in the target environment.</span></span> <span data-ttu-id="abada-105">I vantaggi sono distribuzioni più veloci, utilizzo ridotto dello spazio su disco e, in alcuni casi, migliori prestazioni di avvio.</span><span class="sxs-lookup"><span data-stu-id="abada-105">The benefits are faster deployments, lower disk space usage, and improved startup performance in some cases.</span></span>

<span data-ttu-id="abada-106">Questa funzionalità viene implementata come *archivio pacchetti di runtime*, che è una directory su disco in cui vengono archiviati i pacchetti, in genere */usr/local/share/dotnet/store* in macOS/Linux e *C:/Program Files/dotnet/store* in Windows.</span><span class="sxs-lookup"><span data-stu-id="abada-106">This feature is implemented as a *runtime package store*, which is a directory on disk where packages are stored (typically at */usr/local/share/dotnet/store* on macOS/Linux and *C:/Program Files/dotnet/store* on Windows).</span></span> <span data-ttu-id="abada-107">In questa directory sono disponibili le sottodirectory per le architetture e i [framework di destinazione](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="abada-107">Under this directory, there are subdirectories for architectures and [target frameworks](../../standard/frameworks.md).</span></span> <span data-ttu-id="abada-108">Il layout dei file è simile a quello con cui gli [asset NuGet sono disposti su disco](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):</span><span class="sxs-lookup"><span data-stu-id="abada-108">The file layout is similar to the way that [NuGet assets are laid out on disk](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):</span></span>

```
\dotnet
    \store
        \x64
            \netcoreapp2.0
                \microsoft.applicationinsights
                \microsoft.aspnetcore
                ...
        \x86
            \netcoreapp2.0
                \microsoft.applicationinsights
                \microsoft.aspnetcore
                ...
```

<span data-ttu-id="abada-109">Un file *manifesto di destinazione* elenca i pacchetti nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="abada-109">A *target manifest* file lists the packages in the runtime package store.</span></span> <span data-ttu-id="abada-110">Gli sviluppatori possono destinare questo manifesto quando pubblicano la propria applicazione.</span><span class="sxs-lookup"><span data-stu-id="abada-110">Developers can target this manifest when publishing their app.</span></span> <span data-ttu-id="abada-111">Il manifesto di destinazione viene fornito in genere dal proprietario dell'ambiente di produzione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="abada-111">The target manifest is typically provided by the owner of the targeted production environment.</span></span>

## <a name="preparing-a-runtime-environment"></a><span data-ttu-id="abada-112">Preparazione di un ambiente di runtime</span><span class="sxs-lookup"><span data-stu-id="abada-112">Preparing a runtime environment</span></span>

<span data-ttu-id="abada-113">L'amministratore di un ambiente di runtime può ottimizzare le app per distribuzioni più veloci e utilizzo inferiore dello spazio su disco compilando un archivio di pacchetti di runtime e il manifesto di destinazione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="abada-113">The administrator of a runtime environment can optimize apps for faster deployments and lower disk space use by building a runtime package store and the corresponding target manifest.</span></span>

<span data-ttu-id="abada-114">Il primo passaggio consiste nel creare un *manifesto dell'archivio pacchetti* che elenca i pacchetti che compongono l'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="abada-114">The first step is to create a *package store manifest* that lists the packages that compose the runtime package store.</span></span> <span data-ttu-id="abada-115">Questo formato di file è compatibile con il formato di file del progetto (*csproj*).</span><span class="sxs-lookup"><span data-stu-id="abada-115">This file format is compatible with the project file format (*csproj*).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="NUGET_PACKAGE" Version="VERSION" />
    <!-- Include additional packages here -->
  </ItemGroup>
</Project>
```

<span data-ttu-id="abada-116">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="abada-116">**Example**</span></span>

<span data-ttu-id="abada-117">Il manifesto dell'archivio pacchetti di esempio seguente (*packages.csproj*) viene usato per aggiungere [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) e [`Moq`](https://www.nuget.org/packages/moq/) a un archivio pacchetti di runtime:</span><span class="sxs-lookup"><span data-stu-id="abada-117">The following example package store manifest (*packages.csproj*) is used to add [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) and [`Moq`](https://www.nuget.org/packages/moq/) to a runtime package store:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.3" />
    <PackageReference Include="Moq" Version="4.7.63" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="abada-118">Eseguire il provisioning dell'archivio pacchetti di runtime eseguendo `dotnet store` con il manifesto dell'archivio pacchetti, il runtime e il framework:</span><span class="sxs-lookup"><span data-stu-id="abada-118">Provision the runtime package store by executing `dotnet store` with the package store manifest, runtime, and framework:</span></span>

```dotnetcli
dotnet store --manifest <PATH_TO_MANIFEST_FILE> --runtime <RUNTIME_IDENTIFIER> --framework <FRAMEWORK>
```

<span data-ttu-id="abada-119">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="abada-119">**Example**</span></span>

```dotnetcli
dotnet store --manifest packages.csproj --runtime win10-x64 --framework netcoreapp2.0 --framework-version 2.0.0
```

<span data-ttu-id="abada-120">È possibile passare più percorsi del manifesto dell'archivio pacchetti di destinazione [`dotnet store`](../tools/dotnet-store.md) a un singolo comando ripetendo l'opzione e il percorso nel comando.</span><span class="sxs-lookup"><span data-stu-id="abada-120">You can pass multiple target package store manifest paths to a single [`dotnet store`](../tools/dotnet-store.md) command by repeating the option and path in the command.</span></span>

<span data-ttu-id="abada-121">Per impostazione predefinita, l'output del comando è un archivio pacchetti nella sottodirectory *.dotnet/store* del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="abada-121">By default, the output of the command is a package store under the *.dotnet/store* subdirectory of the user's profile.</span></span> <span data-ttu-id="abada-122">È possibile specificare un percorso diverso usando l'opzione `--output <OUTPUT_DIRECTORY>`.</span><span class="sxs-lookup"><span data-stu-id="abada-122">You can specify a different location using the `--output <OUTPUT_DIRECTORY>` option.</span></span> <span data-ttu-id="abada-123">La directory radice dell'archivio contiene un file manifesto di destinazione *artifact.xml*.</span><span class="sxs-lookup"><span data-stu-id="abada-123">The root directory of the store contains a target manifest *artifact.xml* file.</span></span> <span data-ttu-id="abada-124">Questo file può essere reso disponibile per il download e usato dagli autori di app che intendono eseguire la destinazione di questo archivio durante la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="abada-124">This file can be made available for download and be used by app authors who want to target this store when publishing.</span></span>

<span data-ttu-id="abada-125">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="abada-125">**Example**</span></span>

<span data-ttu-id="abada-126">Il file *artifact.xml* seguente viene generato dopo l'esecuzione dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="abada-126">The following *artifact.xml* file is produced after running the previous example.</span></span> <span data-ttu-id="abada-127">Si noti [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) che è una dipendenza `Moq`di, pertanto viene inclusa automaticamente e visualizzata nel file manifesto *artefatts. XML* .</span><span class="sxs-lookup"><span data-stu-id="abada-127">Note that [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) is a dependency of `Moq`, so it's included automatically and appears in the *artifacts.xml* manifest file.</span></span>

```xml
<StoreArtifacts>
  <Package Id="Newtonsoft.Json" Version="10.0.3" />
  <Package Id="Castle.Core" Version="4.1.0" />
  <Package Id="Moq" Version="4.7.63" />
</StoreArtifacts>
```

## <a name="publishing-an-app-against-a-target-manifest"></a><span data-ttu-id="abada-128">Pubblicazione di un'app con un manifesto di destinazione</span><span class="sxs-lookup"><span data-stu-id="abada-128">Publishing an app against a target manifest</span></span>

<span data-ttu-id="abada-129">Se si dispone di un file manifesto di destinazione su disco, specificare il percorso del file quando si pubblica l'app con [`dotnet publish`](../tools/dotnet-publish.md) il comando:</span><span class="sxs-lookup"><span data-stu-id="abada-129">If you have a target manifest file on disk, you specify the path to the file when publishing your app with the [`dotnet publish`](../tools/dotnet-publish.md) command:</span></span>

```dotnetcli
dotnet publish --manifest <PATH_TO_MANIFEST_FILE>
```

<span data-ttu-id="abada-130">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="abada-130">**Example**</span></span>

```dotnetcli
dotnet publish --manifest manifest.xml
```

<span data-ttu-id="abada-131">Distribuire l'app pubblicata risultante in un ambiente contenente i pacchetti descritti nel manifesto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="abada-131">You deploy the resulting published app to an environment that has the packages described in the target manifest.</span></span> <span data-ttu-id="abada-132">In caso contrario, si verifica un errore di avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="abada-132">Failing to do so results in the app failing to start.</span></span>

<span data-ttu-id="abada-133">Specificare più manifesti di destinazione quando si pubblica un'app ripetendo l'opzione e il percorso, ad esempio `--manifest manifest1.xml --manifest manifest2.xml`.</span><span class="sxs-lookup"><span data-stu-id="abada-133">Specify multiple target manifests when publishing an app by repeating the option and path (for example, `--manifest manifest1.xml --manifest manifest2.xml`).</span></span> <span data-ttu-id="abada-134">Quando si esegue questa operazione, l'app viene rimossa per l'unione dei pacchetti specificati nei file manifesto di destinazione forniti al comando.</span><span class="sxs-lookup"><span data-stu-id="abada-134">When you do so, the app is trimmed for the union of packages specified in the target manifest files provided to the command.</span></span>

<span data-ttu-id="abada-135">Se si distribuisce un'applicazione con una dipendenza del manifesto che è presente nella distribuzione (l'assembly si trova nella cartella *bin*), l'archivio pacchetti di runtime *non viene usato* nell'host per tale assembly.</span><span class="sxs-lookup"><span data-stu-id="abada-135">If you deploy an application with a manifest dependency that's present in the deployment (the assembly is present in the *bin* folder), the runtime package store *isn't used* on the host for that assembly.</span></span> <span data-ttu-id="abada-136">L'assembly della cartella *bin* viene usato indipendentemente dalla sua presenza nell'archivio pacchetti di runtime nell'host.</span><span class="sxs-lookup"><span data-stu-id="abada-136">The *bin* folder assembly is used regardless of its presence in the runtime package store on the host.</span></span>

<span data-ttu-id="abada-137">La versione della dipendenza indicata nel manifesto deve corrispondere alla versione della dipendenza nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="abada-137">The version of the dependency indicated in the manifest must match the version of the dependency in the runtime package store.</span></span> <span data-ttu-id="abada-138">In caso di mancata corrispondenza tra la dipendenza nel manifesto di destinazione e la versione esistente nell'archivio pacchetti di runtime e se l'app non include la versione necessaria del pacchetto nella relativa distribuzione, l'app non verrà avviata.</span><span class="sxs-lookup"><span data-stu-id="abada-138">If you have a version mismatch between the dependency in the target manifest and the version that exists in the runtime package store and the app doesn't include the required version of the package in its deployment, the app fails to start.</span></span> <span data-ttu-id="abada-139">L'eccezione include il nome del manifesto di destinazione chiamato per assembly dell'archivio pacchetti di runtime e questa informazione è utile per risolvere la mancata corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="abada-139">The exception includes the name of the target manifest that called for the runtime package store assembly, which helps you troubleshoot the mismatch.</span></span>

<span data-ttu-id="abada-140">Quando la distribuzione viene *tagliata* nella pubblicazione, solo le versioni specifiche dei pacchetti del manifesto indicate vengono trattenute dall'output pubblicato.</span><span class="sxs-lookup"><span data-stu-id="abada-140">When the deployment is *trimmed* on publish, only the specific versions of the manifest packages you indicate are withheld from the published output.</span></span> <span data-ttu-id="abada-141">I pacchetti nelle versioni indicate devono essere presenti nell'host per consentire l'avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="abada-141">The packages at the versions indicated must be present on the host for the app to start.</span></span>

## <a name="specifying-target-manifests-in-the-project-file"></a><span data-ttu-id="abada-142">Specifica dei manifesti di destinazione nel file di progetto</span><span class="sxs-lookup"><span data-stu-id="abada-142">Specifying target manifests in the project file</span></span>

<span data-ttu-id="abada-143">Un'alternativa alla specifica dei manifesti di destinazione [`dotnet publish`](../tools/dotnet-publish.md) con il comando consiste nel specificarli nel file di progetto come un elenco delimitato da punti e virgola di percorsi sotto un \*\* \<TargetManifestFiles>\*\* tag.</span><span class="sxs-lookup"><span data-stu-id="abada-143">An alternative to specifying target manifests with the [`dotnet publish`](../tools/dotnet-publish.md) command is to specify them in the project file as a semicolon-separated list of paths under a **\<TargetManifestFiles>** tag.</span></span>

```xml
<PropertyGroup>
  <TargetManifestFiles>manifest1.xml;manifest2.xml</TargetManifestFiles>
</PropertyGroup>
```

<span data-ttu-id="abada-144">Specificare i manifesti di destinazione nel file di progetto solo quando l'ambiente di destinazione per l'app è noto, come per i progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="abada-144">Specify the target manifests in the project file only when the target environment for the app is well-known, such as for .NET Core projects.</span></span> <span data-ttu-id="abada-145">Non è il caso di progetti open source.</span><span class="sxs-lookup"><span data-stu-id="abada-145">This isn't the case for open-source projects.</span></span> <span data-ttu-id="abada-146">Gli utenti di un progetto open source in genere lo distribuiscono in ambienti di produzione diversi.</span><span class="sxs-lookup"><span data-stu-id="abada-146">The users of an open-source project typically deploy it to different production environments.</span></span> <span data-ttu-id="abada-147">In genere questi ambienti di produzione includono diversi set di pacchetti pre-installati.</span><span class="sxs-lookup"><span data-stu-id="abada-147">These production environments generally have different sets of packages pre-installed.</span></span> <span data-ttu-id="abada-148">Non è possibile creare presupposti sul manifesto di destinazione in tali ambienti, pertanto è necessario usare `--manifest` l'opzione [`dotnet publish`](../tools/dotnet-publish.md)di.</span><span class="sxs-lookup"><span data-stu-id="abada-148">You can't make assumptions about the target manifest in such environments, so you should use the `--manifest` option of [`dotnet publish`](../tools/dotnet-publish.md).</span></span>

## <a name="aspnet-core-implicit-store-net-core-20-only"></a><span data-ttu-id="abada-149">ASP.NET Core archivio implicito (solo .NET Core 2,0)</span><span class="sxs-lookup"><span data-stu-id="abada-149">ASP.NET Core implicit store (.NET Core 2.0 only)</span></span>

<span data-ttu-id="abada-150">L'archivio implicito di ASP.NET Core è valido solo per ASP.NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="abada-150">The ASP.NET Core implicit store applies only to ASP.NET Core 2.0.</span></span> <span data-ttu-id="abada-151">È consigliabile che le applicazioni usino ASP.NET Core 2.1 e versioni successive, che **non** usano l'archivio implicito.</span><span class="sxs-lookup"><span data-stu-id="abada-151">We strongly recommend applications use ASP.NET Core 2.1 and later, which does **not** use the implicit store.</span></span> <span data-ttu-id="abada-152">ASP.NET Core 2.1 e versioni successive usano il framework condiviso.</span><span class="sxs-lookup"><span data-stu-id="abada-152">ASP.NET Core 2.1 and later use the shared framework.</span></span>

<span data-ttu-id="abada-153">Per .NET Core 2,0, la funzionalità di archivio pacchetti di runtime viene usata in modo implicito da un'app ASP.NET Core quando l'app viene distribuita come app di [distribuzione dipendente dal runtime](index.md#publish-runtime-dependent) .</span><span class="sxs-lookup"><span data-stu-id="abada-153">For .NET Core 2.0, the runtime package store feature is used implicitly by an ASP.NET Core app when the app is deployed as a [runtime-dependent deployment](index.md#publish-runtime-dependent) app.</span></span> <span data-ttu-id="abada-154">Le destinazioni in [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) includono manifesti che fanno riferimento all'archivio pacchetti implicito nel sistema di destinazione.</span><span class="sxs-lookup"><span data-stu-id="abada-154">The targets in [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) include manifests referencing the implicit package store on the target system.</span></span> <span data-ttu-id="abada-155">Inoltre, qualsiasi app dipendente dal runtime che dipende dal `Microsoft.AspNetCore.All` pacchetto restituisce un'app pubblicata che contiene solo l'app e le relative risorse e non i pacchetti elencati nel `Microsoft.AspNetCore.All` metapacchetto.</span><span class="sxs-lookup"><span data-stu-id="abada-155">Additionally, any runtime-dependent app that depends on the `Microsoft.AspNetCore.All` package results in a published app that contains only the app and its assets and not the packages listed in the `Microsoft.AspNetCore.All` metapackage.</span></span> <span data-ttu-id="abada-156">Si presuppone che questi pacchetti siano presenti nel sistema di destinazione.</span><span class="sxs-lookup"><span data-stu-id="abada-156">It's assumed that those packages are present on the target system.</span></span>

<span data-ttu-id="abada-157">L'archivio pacchetti di runtime viene installato nell'host quando viene installato .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="abada-157">The runtime package store is installed on the host when the .NET Core SDK is installed.</span></span> <span data-ttu-id="abada-158">Altri programmi di installazione possono fornire l'archivio pacchetti di runtime, incluse le installazioni di Zip/tarball di SDK .NET Core, `apt-get`, Red Hat Yum, il bundle di .NET Core Windows Server Hosting e le installazioni manuali di archivi pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="abada-158">Other installers may provide the runtime package store, including Zip/tarball installations of the .NET Core SDK, `apt-get`, Red Hat Yum, the .NET Core Windows Server Hosting bundle, and manual runtime package store installations.</span></span>

<span data-ttu-id="abada-159">Quando si distribuisce un'app di [distribuzione dipendente dal runtime](index.md#publish-runtime-dependent) , verificare che nell'ambiente di destinazione sia installato il .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="abada-159">When deploying a [runtime-dependent deployment](index.md#publish-runtime-dependent) app, make sure that the target environment has the .NET Core SDK installed.</span></span> <span data-ttu-id="abada-160">Se l'app viene distribuita in un ambiente che non include ASP.NET Core, è possibile rifiutare esplicitamente l'archivio implicito specificando \*\* \<PublishWithAspNetCoreTargetManifest>\*\* impostato su `false` nel file di progetto come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="abada-160">If the app is deployed to an environment that doesn't include ASP.NET Core, you can opt out of the implicit store by specifying  **\<PublishWithAspNetCoreTargetManifest>** set to `false` in the project file as in the following example:</span></span>

```xml
<PropertyGroup>
  <PublishWithAspNetCoreTargetManifest>false</PublishWithAspNetCoreTargetManifest>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="abada-161">Per le app di [distribuzione](index.md#publish-self-contained) indipendenti, si presuppone che il sistema di destinazione non contenga necessariamente i pacchetti manifesto richiesti.</span><span class="sxs-lookup"><span data-stu-id="abada-161">For [self-contained deployment](index.md#publish-self-contained) apps, it's assumed that the target system doesn't necessarily contain the required manifest packages.</span></span> <span data-ttu-id="abada-162">Di conseguenza \*\* \<\*\* , non è possibile impostare PublishWithAspNetCoreTargetManifest `true`>su per un'app autonoma.</span><span class="sxs-lookup"><span data-stu-id="abada-162">Therefore, **\<PublishWithAspNetCoreTargetManifest>** cannot be set to `true` for an self-contained app.</span></span>

## <a name="see-also"></a><span data-ttu-id="abada-163">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="abada-163">See also</span></span>

- [<span data-ttu-id="abada-164">dotnet-publish</span><span class="sxs-lookup"><span data-stu-id="abada-164">dotnet-publish</span></span>](../tools/dotnet-publish.md)
- [<span data-ttu-id="abada-165">dotnet-store</span><span class="sxs-lookup"><span data-stu-id="abada-165">dotnet-store</span></span>](../tools/dotnet-store.md)
