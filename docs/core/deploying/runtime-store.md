---
title: Archivio pacchetti di runtime
description: Informazioni su come usare l'archivio pacchetti di runtime per specificare come destinazione i manifesti usati da .NET Core.
ms.date: 08/12/2017
ms.openlocfilehash: 7a833ed95147608c6fb403f8f0dec179d2a73833
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77448958"
---
# <a name="runtime-package-store"></a>Archivio pacchetti di runtime

A partire da .NET Core 2.0, è possibile creare un pacchetto e distribuire le app su un set noto di pacchetti esistenti nell'ambiente di destinazione. I vantaggi sono distribuzioni più veloci, utilizzo ridotto dello spazio su disco e, in alcuni casi, migliori prestazioni di avvio.

Questa funzionalità viene implementata come *archivio pacchetti di runtime*, che è una directory su disco in cui vengono archiviati i pacchetti, in genere */usr/local/share/dotnet/store* in macOS/Linux e *C:/Program Files/dotnet/store* in Windows. In questa directory sono disponibili le sottodirectory per le architetture e i [framework di destinazione](../../standard/frameworks.md). Il layout dei file è simile a quello con cui gli [asset NuGet sono disposti su disco](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):

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

Un file *manifesto di destinazione* elenca i pacchetti nell'archivio pacchetti di runtime. Gli sviluppatori possono destinare questo manifesto quando pubblicano la propria applicazione. Il manifesto di destinazione viene fornito in genere dal proprietario dell'ambiente di produzione di destinazione.

## <a name="preparing-a-runtime-environment"></a>Preparazione di un ambiente di runtime

L'amministratore di un ambiente di runtime può ottimizzare le app per distribuzioni più veloci e utilizzo inferiore dello spazio su disco compilando un archivio di pacchetti di runtime e il manifesto di destinazione corrispondente.

Il primo passaggio consiste nel creare un *manifesto dell'archivio pacchetti* che elenca i pacchetti che compongono l'archivio pacchetti di runtime. Questo formato di file è compatibile con il formato di file del progetto (*csproj*).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="<NUGET_PACKAGE>" Version="<VERSION>" />
    <!-- Include additional packages here -->
  </ItemGroup>
</Project>
```

**Esempio**

Il manifesto dell'archivio pacchetti di esempio seguente (*packages.csproj*) viene usato per aggiungere [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) e [`Moq`](https://www.nuget.org/packages/moq/) a un archivio pacchetti di runtime:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.3" />
    <PackageReference Include="Moq" Version="4.7.63" />
  </ItemGroup>
</Project>
```

Eseguire il provisioning dell'archivio pacchetti di runtime eseguendo `dotnet store` con il manifesto dell'archivio pacchetti, il runtime e il framework:

```dotnetcli
dotnet store --manifest <PATH_TO_MANIFEST_FILE> --runtime <RUNTIME_IDENTIFIER> --framework <FRAMEWORK>
```

**Esempio**

```dotnetcli
dotnet store --manifest packages.csproj --runtime win10-x64 --framework netcoreapp2.0 --framework-version 2.0.0
```

È possibile passare più percorsi del [`dotnet store`](../tools/dotnet-store.md) manifesto dell'archivio pacchetti di destinazione a un singolo comando ripetendo l'opzione e il percorso nel comando.

Per impostazione predefinita, l'output del comando è un archivio pacchetti nella sottodirectory *.dotnet/store* del profilo utente. È possibile specificare un percorso diverso usando l'opzione `--output <OUTPUT_DIRECTORY>`. La directory radice dell'archivio contiene un file manifesto di destinazione *artifact.xml*. Questo file può essere reso disponibile per il download e usato dagli autori di app che intendono eseguire la destinazione di questo archivio durante la pubblicazione.

**Esempio**

Il file *artifact.xml* seguente viene generato dopo l'esecuzione dell'esempio precedente. Si [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) noti che `Moq`è una dipendenza di , pertanto viene incluso automaticamente e visualizzato nel file manifesto *artifacts.xml.*

```xml
<StoreArtifacts>
  <Package Id="Newtonsoft.Json" Version="10.0.3" />
  <Package Id="Castle.Core" Version="4.1.0" />
  <Package Id="Moq" Version="4.7.63" />
</StoreArtifacts>
```

## <a name="publishing-an-app-against-a-target-manifest"></a>Pubblicazione di un'app con un manifesto di destinazione

Se si dispone di un file manifesto di destinazione su disco, [`dotnet publish`](../tools/dotnet-publish.md) specificare il percorso del file quando si pubblica l'app con il comando:

```dotnetcli
dotnet publish --manifest <PATH_TO_MANIFEST_FILE>
```

**Esempio**

```dotnetcli
dotnet publish --manifest manifest.xml
```

Distribuire l'app pubblicata risultante in un ambiente contenente i pacchetti descritti nel manifesto di destinazione. In caso contrario, si verifica un errore di avvio dell'app.

Specificare più manifesti di destinazione quando si pubblica un'app ripetendo l'opzione e il percorso, ad esempio `--manifest manifest1.xml --manifest manifest2.xml`. Quando si esegue questa operazione, l'app viene rimossa per l'unione dei pacchetti specificati nei file manifesto di destinazione forniti al comando.

## <a name="specifying-target-manifests-in-the-project-file"></a>Specifica dei manifesti di destinazione nel file di progetto

Un'alternativa alla specifica dei [`dotnet publish`](../tools/dotnet-publish.md) manifesti di destinazione con il comando consiste nel specificarli nel file di progetto come elenco di percorsi separati da punto e virgola in un ** \<tag>TargetManifestFiles.An** alternative to specifying target manifests with the command is to specify them in the project file as a semi-separated list of paths under a TargetManifestFiles>tag.

```xml
<PropertyGroup>
  <TargetManifestFiles>manifest1.xml;manifest2.xml</TargetManifestFiles>
</PropertyGroup>
```

Specificare i manifesti di destinazione nel file di progetto solo quando l'ambiente di destinazione per l'app è noto, come per i progetti .NET Core. Non è il caso di progetti open source. Gli utenti di un progetto open source in genere lo distribuiscono in ambienti di produzione diversi. In genere questi ambienti di produzione includono diversi set di pacchetti pre-installati. Non è possibile fare supposizioni sul manifesto di destinazione `--manifest` in [`dotnet publish`](../tools/dotnet-publish.md)tali ambienti, pertanto è consigliabile utilizzare l'opzione di .

## <a name="aspnet-core-implicit-store"></a>Archivio implicito di ASP.NET Core

L'archivio implicito di ASP.NET Core è valido solo per ASP.NET Core 2.0. È consigliabile che le applicazioni usino ASP.NET Core 2.1 e versioni successive, che **non** usano l'archivio implicito. ASP.NET Core 2.1 e versioni successive usano il framework condiviso.

La funzionalità di archivio pacchetti di runtime viene usata in modo implicito da un'app ASP.NET Core quando l'app viene distribuita come app con [distribuzione dipendente da framework (FDD, Framework-Dependent Deployment)](index.md#publish-runtime-dependent). Le destinazioni in [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) includere i manifesti che fanno riferimento all'archivio pacchetti implicito nel sistema di destinazione. Inoltre, qualsiasi app con distribuzione dipendente da framework (FDD, Framework-Dependent Deployment) dipende dal pacchetto `Microsoft.AspNetCore.All` genera un'app pubblicata che contiene solo l'app e gli asset e non i pacchetti elencati nel metapacchetto `Microsoft.AspNetCore.All`. Si presuppone che questi pacchetti siano presenti nel sistema di destinazione.

L'archivio pacchetti di runtime viene installato nell'host quando viene installato .NET Core SDK. Altri programmi di installazione possono fornire l'archivio pacchetti di runtime, incluse le installazioni di Zip/tarball di SDK .NET Core, `apt-get`, Red Hat Yum, il bundle di .NET Core Windows Server Hosting e le installazioni manuali di archivi pacchetti di runtime.

Quando si distribuisce un'app con [distribuzione dipendente da framework (FDD, Framework-Dependent Deployment)](index.md#publish-runtime-dependent), verificare che nell'ambiente di destinazione sia installato .NET Core SDK. Se l'app viene distribuita in un ambiente che non include ASP.NET Core, puoi rifiutare esplicitamente l'archivio implicito specificando ** \<PublishWithAspNetCoreTargetManifest>** impostato su `false` nel file di progetto come nell'esempio seguente:

```xml
<PropertyGroup>
  <PublishWithAspNetCoreTargetManifest>false</PublishWithAspNetCoreTargetManifest>
</PropertyGroup>
```

> [!NOTE]
> Per le app con [distribuzione indipendente (SCD, Self-Contained Deployment)](index.md#publish-self-contained), si presuppone che il sistema di destinazione non contenga necessariamente i pacchetti del manifesto necessari. Pertanto, ** \<PublishWithAspNetCoreTargetManifest>** `true` non può essere impostato su per un'app SCD.

Se si distribuisce un'applicazione con una dipendenza del manifesto che è presente nella distribuzione (l'assembly si trova nella cartella *bin*), l'archivio pacchetti di runtime *non viene usato* nell'host per tale assembly. L'assembly della cartella *bin* viene usato indipendentemente dalla sua presenza nell'archivio pacchetti di runtime nell'host.

La versione della dipendenza indicata nel manifesto deve corrispondere alla versione della dipendenza nell'archivio pacchetti di runtime. In caso di mancata corrispondenza tra la dipendenza nel manifesto di destinazione e la versione esistente nell'archivio pacchetti di runtime e se l'app non include la versione necessaria del pacchetto nella relativa distribuzione, l'app non verrà avviata. L'eccezione include il nome del manifesto di destinazione chiamato per assembly dell'archivio pacchetti di runtime e questa informazione è utile per risolvere la mancata corrispondenza.

Quando la distribuzione viene *tagliata* nella pubblicazione, solo le versioni specifiche dei pacchetti del manifesto indicate vengono trattenute dall'output pubblicato. I pacchetti nelle versioni indicate devono essere presenti nell'host per consentire l'avvio dell'app.

## <a name="see-also"></a>Vedere anche

- [dotnet-publish](../tools/dotnet-publish.md)
- [dotnet-store](../tools/dotnet-store.md)
