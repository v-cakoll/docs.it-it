---
title: NuGet e librerie .NET
description: Procedure consigliate per la creazione di pacchetti con NuGet per le librerie .NET.
ms.date: 01/15/2019
ms.openlocfilehash: f1e8d39fe2988f11ce7fd351a4d6bee6d322f2b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79400519"
---
# <a name="nuget"></a>NuGet

NuGet è uno strumento di gestione pacchetti per l'ecosistema .NET e rappresenta il modo principale in cui gli sviluppatori individuano e acquisiscono librerie open source .NET. [NuGet.org](https://www.nuget.org/), un servizio gratuito fornito da Microsoft per l'hosting dei pacchetti NuGet, è l'host primario per i pacchetti NuGet pubblici, ma è possibile eseguire la pubblicazione in servizi NuGet personalizzati, come [MyGet](https://www.myget.org/) e [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/).

![Nuget](./media/nuget/nuget-logo.png "NuGet")

## <a name="create-a-nuget-package"></a>Creare un pacchetto NuGet

Un pacchetto NuGet (`*.nupkg`) è un file ZIP che contiene gli assembly .NET e i metadati associati.

Ci sono due modi principali per creare un pacchetto NuGet. Il modo più recente e consigliato consiste nel creare un pacchetto da un progetto in stile SDK (file di progetto il cui contenuto inizia con `<Project Sdk="Microsoft.NET.Sdk">`). Destinazioni e assembly vengono aggiunti automaticamente al pacchetto e i metadati rimanenti vengono aggiunti al file MSBuild, ad esempio numero di versione e nome del pacchetto. La compilazione [`dotnet pack`](../../core/tools/dotnet-pack.md) con il `*.nupkg` comando genera un file anziché gli assembly.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <AssemblyName>Contoso.Api</AssemblyName>
    <PackageVersion>1.1.0</PackageVersion>
    <Authors>John Doe</Authors>
  </PropertyGroup>
</Project>
```

Il modo meno recente per creare un pacchetto NuGet consiste nell'usare un file `*.nuspec` e lo strumento da riga di comando `nuget.exe`. Un file nuspec offre uno straordinario controllo, ma è necessario specificare attentamente quali assembly e destinazioni includere nel pacchetto NuGet finale. È facile commette un errore o dimenticarsi di aggiornare il file nuspec quando si apportano modifiche. Il vantaggio di un file nuspec è la possibilità di usarlo per creare pacchetti NuGet per framework che ancora non supportano un file di progetto in stile SDK.

✔️ VALUTARE l'uso di un file di progetto in stile SDK per creare il pacchetto NuGet.

## <a name="package-dependencies"></a>Dipendenze dei pacchetti

Le dipendenze dei pacchetti NuGet sono illustrate in dettaglio nell'articolo [Dipendenze](./dependencies.md).

## <a name="important-nuget-package-metadata"></a>Metadati importanti dei pacchetti NuGet

Un pacchetto NuGet supporta numerose [proprietà dei metadati](/nuget/reference/nuspec). La tabella seguente contiene i principali metadati che deve offrire ogni pacchetto in NuGet.org:

| Nome proprietà MSBuild              | Nome nuspec              | Descrizione  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | Identificatore di pacchetto. Un prefisso dell'identificatore può essere riservato se soddisfa i [criteri](/nuget/reference/id-prefix-reservation). |
| `PackageVersion`                   | `version`                  | Versione del pacchetto NuGet. Per altre informazioni, vedere [Versione dei pacchetti NuGet](./versioning.md#nuget-package-version).             |
| `Title`                            | `title`                    | Titolo descrittivo del pacchetto. Il valore predefinito è `PackageId`.             |
| `Description`                      | `description`              | Descrizione lunga del pacchetto visualizzata nell'interfaccia utente.             |
| `Authors`                          | `authors`                  | Elenco di autori del pacchetto delimitati da virgole, corrispondenti ai nomi dei profili in nuget.org.             |
| `PackageTags`                      | `tags`                     | Elenco di tag e parole chiave delimitati da spazi che descrivono il pacchetto. I tag vengono usati per la ricerca di pacchetti.             |
| `PackageIconUrl`                   | `iconUrl`                  | URL di un'immagine da usare come icona per il pacchetto. L'URL deve essere di tipo HTTPS e l'immagine deve avere dimensioni di 64x64 e uno sfondo trasparente.             |
| `PackageProjectUrl`                | `projectUrl`               | URL della home page del progetto o del repository di origine.             |
| `PackageLicenseExpression`         | `license`                  | [Identificatore SPDX](https://spdx.org/licenses/) della licenza del progetto. Solo le licenze con approvazione OSI e FSF possono usare un identificatore. Le altre licenze devono usare `PackageLicenseFile`. Ulteriori informazioni sui [ `license` metadati](/nuget/reference/nuspec#license). |

> [!IMPORTANT]
> Per un progetto senza una licenza viene applicato per impostazione predefinita il [copyright esclusivo](https://choosealicense.com/no-permission/), che ne impedisce a livello legale l'uso da parte di altre persone.

✔️ VALUTARE la scelta di un nome di pacchetto NuGet con un prefisso che soddisfi i [criteri](/nuget/reference/id-prefix-reservation) per riservare il prefisso NuGet.

✔️ USARE un attributo href HTTPS per l'icona del pacchetto.

> I siti come NuGet.org vengono eseguiti con il protocollo HTTPS abilitato e la visualizzazione di un'immagine non HTTPS comporta la generazione di un avviso di contenuto misto.

✔️ USARE un'immagine di icona del pacchetto con dimensioni di 64x64 e con uno sfondo trasparente per ottenere una migliore visualizzazione.

✔️ VALUTARE la configurazione del [collegamento all'origine](./sourcelink.md) per aggiungere metadati di controllo del codice sorgente agli assembly e al pacchetto NuGet.

> Il collegamento all'origine aggiunge automaticamente metadati `RepositoryUrl` e `RepositoryType` al pacchetto NuGet. Il collegamento all'origine aggiunge anche informazioni sul codice sorgente esatto da cui è stato compilato il pacchetto. Ad esempio, a un pacchetto creato da un repository Git verrà aggiunto l'hash commit come metadati.

## <a name="pre-release-packages"></a>Pacchetti in versione non definitiva

I pacchetti NuGet con un suffisso di versione sono considerati [versioni non definitive](/nuget/create-packages/prerelease-packages). Per impostazione predefinita, l'interfaccia utente di Gestione pacchetti NuGet mostra le versioni stabili, a meno che un utente non scelga esplicitamente pacchetti in versione non definitiva, ideali per test utente limitati.

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> Una pacchetto stabile non può dipendere da un pacchetto in versione non definitiva. È necessario impostare un pacchetto come versione non definitiva oppure fare in modo che dipenda da una versione stabile precedente.

![Dipendenza del pacchetto non definitivo NuGetNuGet pre-release package dependency](./media/nuget/nuget-prerelease-package.png "Dipendenza del pacchetto non definitivo NuGetNuGet pre-release package dependency")

✔️ PUBBLICARE un pacchetto in versione non definitiva a scopi di test, anteprima o sperimentazione.

✔️ PUBBLICARE un pacchetto stabile quando è pronto, in modo che altri pacchetti stabili possano farvi riferimento.

## <a name="symbol-packages"></a>Pacchetti di simboli

I file di simboli (`*.pdb`) vengono prodotti dal compilatore .NET insieme agli assembly. I file di simboli mappano le posizioni di esecuzione al codice sorgente originale, in modo che sia possibile esaminare il codice sorgente mentre è in esecuzione usando un debugger. NuGet supporta la [generazione di un pacchetto di simboli separato (`*.snupkg`)](/nuget/create-packages/symbol-packages-snupkg) contenente i file di simboli insieme al pacchetto principale che contiene gli assembly .NET. L'idea dei pacchetti di simboli è che siano ospitati in un server di simboli e scaricati solo da uno strumento come Visual Studio su richiesta.

NuGet.org ospita il proprio [repository del server dei simboli](/nuget/create-packages/symbol-packages-snupkg#nugetorg-symbol-server). Gli sviluppatori possono usare i simboli pubblicati nel server dei simboli di NuGet.org aggiungendo `https://symbols.nuget.org/download/symbols` alle loro origini di simboli[ in Visual Studio](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger).

> [!IMPORTANT]
> Il server di simboli NuGet.org supporta solo`*.pdb`i nuovi file di [simboli portabili](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) ( ) creati da progetti in stile SDK.
>
> Per usare il server di simboli NuGet.org durante il debug di una libreria .NET, gli sviluppatori devono disporre di Visual Studio 2017 versione 15.9 o successiva.

Un'alternativa alla creazione di un pacchetto di simboli è incorporare i file di simboli nel pacchetto NuGet principale. Il pacchetto NuGet principale è di dimensioni maggiori, tuttavia, grazie ai file di simboli incorporati gli sviluppatori non devono configurare il server di simboli NuGet.org. Se si sta creando un pacchetto NuGet usando un progetto in stile SDK, è possibile incorporare i file di simboli impostando la proprietà `AllowedOutputExtensionsInPackageBuildOutputFolder`:

```xml
<Project Sdk="Microsoft.NET.Sdk">
 <PropertyGroup>
    <!-- Include symbol files (*.pdb) in the built .nupkg -->
    <AllowedOutputExtensionsInPackageBuildOutputFolder>$(AllowedOutputExtensionsInPackageBuildOutputFolder);.pdb</AllowedOutputExtensionsInPackageBuildOutputFolder>
  </PropertyGroup>
</Project>
```

Lo svantaggio dell'incorporamento di file di simboli è che aumentano le dimensioni del pacchetto di circa il 30% per le librerie .NET compilate con i progetti di tipo SDK. Se le dimensioni del pacchetto costituiscono un problema, i simboli dovranno essere pubblicati in un pacchetto di simboli.

✔️ VALUTARE di pubblicare i simboli come un pacchetto di simboli (`*.snupkg`) in NuGet.org

> I pacchetti di simboli (`*.snupkg`) rappresentano una buona esperienza di debug on demand per gli sviluppatori perché non fanno aumentare le dimensioni del pacchetto principale né interferiscono con le prestazioni del ripristino per gli utenti che non intendono eseguire il debug del pacchetto NuGet.
>
> L'avvertenza è che gli utenti potrebbero avere bisogno di trovare e configurare il server di simboli NuGet nel loro IDE (come un'installazione una tantera) per ottenere i file di simboli. Visual Studio 2019 versione 16.1 ha aggiunto il server di simboli di NuGet.org all'elenco dei server di simboli predefiniti.

>[!div class="step-by-step"]
>[Successivo](strong-naming.md)
>[precedente](dependencies.md)
