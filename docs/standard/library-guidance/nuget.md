---
title: Librerie di NuGet e .NET
description: Le procedure consigliate per la creazione di pacchetti con NuGet per librerie .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: d0ea462a7f52dd9a6b2f14be9ed5770160bf66b1
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374502"
---
# <a name="nuget"></a>NuGet

NuGet è una gestione pacchetti per l'ecosistema .NET e agli sviluppatori il modo principale individuano e acquisire le librerie open source di .NET. [NuGet.org](https://www.nuget.org/), un servizio gratuito fornito da Microsoft per l'hosting dei pacchetti NuGet, è l'host primario per i pacchetti NuGet pubblici, ma è possibile pubblicare in servizi di NuGet personalizzati, ad esempio [MyGet](https://www.myget.org/) e [gli artefatti di Azure ](https://azure.microsoft.com/services/devops/artifacts/).

![NuGet](./media/nuget/nuget-logo.png "NuGet")

## <a name="create-a-nuget-package"></a>Creare un pacchetto NuGet

Un pacchetto NuGet (`*.nupkg`) è un file zip che contiene gli assembly .NET e i metadati associati.

Esistono due modi principali per creare un pacchetto NuGet. Il modo più recente e consigliato consiste nel creare un pacchetto da un progetto in stile SDK (file di progetto il cui contenuto viene avviato con `<Project Sdk="Microsoft.NET.Sdk">`). Obiettivi e gli assembly vengono aggiunti automaticamente al pacchetto e rimanente dei metadati viene aggiunto al file di MSBuild, ad esempio numero di nome e la versione del pacchetto. La compilazione con il [ `dotnet pack` ](../../core/tools/dotnet-pack.md) comando output un `*.nupkg` file anziché gli assembly.

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

È il modo meno recente di creazione di un pacchetto NuGet con un `*.nuspec` file e il `nuget.exe` lo strumento da riga di comando. Un file nuspec offre uno straordinario controllo ma è necessario specificare attentamente quali assembly e le destinazioni da includere nel pacchetto NuGet finale. È facile commette un errore o per un utente a dimenticare di aggiornare il file nuspec, quando si apportano modifiche. Il vantaggio di un file nuspec è consente di creare pacchetti NuGet per i framework che ancora non supportano un file di progetto basato su SDK.

**Provare a ✔️** utilizzando un file di progetto basato su SDK per creare il pacchetto NuGet.

**Provare a ✔️** configurazione SourceLink per aggiungere metadati di controllo di origine per l'assembly e il pacchetto NuGet.

## <a name="package-dependencies"></a>Dipendenze dei pacchetti

Dipendenze dei pacchetti NuGet sono trattate in dettaglio nel [dipendenze](./dependencies.md) articolo.

## <a name="important-nuget-package-metadata"></a>Metadati del pacchetto NuGet importanti

Un pacchetto NuGet supporta molte [le proprietà dei metadati](/nuget/reference/nuspec). Nella tabella seguente contiene i metadati di core che devono fornire tutti i progetti open source:

| Nome della proprietà di MSBuild              | Nome del file Nuspec              | Descrizione  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | L'identificatore del pacchetto. Un prefisso dall'identificatore può essere riservato se soddisfa le [criteri](/nuget/reference/id-prefix-reservation). |
| `PackageVersion`                   | `version`                  | Versione del pacchetto NuGet. Per altre informazioni, vedere [versione del pacchetto NuGet](./versioning.md#nuget-package-version).             |
| `Title`                            | `title`                    | Un titolo Converto del pacchetto. Per impostazione predefinita il `PackageId`.             |
| `Description`                      | `description`              | Descrizione lunga del pacchetto visualizzato nell'interfaccia utente.             |
| `Authors`                          | `authors`                  | Elenco delimitato dalla virgola di autori di pacchetti, corrispondenti ai nomi di profilo in nuget.org.             |
| `PackageTags`                      | `tags`                     | Elenco delimitato da spazi di tag e parole chiave che descrivono il pacchetto. I tag vengono usati durante la ricerca di pacchetti.             |
| `PackageIconUrl`                   | `iconUrl`                  | Un URL di un'immagine da usare come icona per il pacchetto. L'URL deve essere HTTPS e l'immagine deve essere di 64 x 64 e uno sfondo trasparente.             |
| `PackageProjectUrl`                | `projectUrl`               | Un URL per il repository di origine o della home page del progetto.             |
| `PackageLicenseUrl`                | `licenseUrl`               | Un URL della licenza di progetto. Può essere l'URL per il `LICENSE` file nel controllo del codice sorgente.             |

**Provare a ✔️** scegliendo un nome del pacchetto NuGet con un prefisso che soddisfi prenotazione del prefisso di NuGet [criteri](/nuget/reference/id-prefix-reservation).

**✔️ si consiglia** usando il `LICENSE` file nel controllo del codice sorgente come il `LicenseUrl`. Ad esempio, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).

> [!IMPORTANT]
> Un progetto senza una licenza per impostazione predefinita [copyright esclusivo](https://choosealicense.com/no-permission/), rendendo impossibile la uso ad altri utenti.

**Eseguire operazioni ✔️** usano un href HTTPS per l'icona del pacchetto.

> Siti come NuGet.org eseguano con abilitato per HTTPS e la visualizzazione di un'immagine non HTTPS creerà un avviso di contenuto misto.

**Eseguire operazioni ✔️** usare un'immagine icona pacchetto 64 x 64 e con uno sfondo trasparente per ottenere una migliore visualizzazione.

## <a name="pre-release-packages"></a>Pacchetti in versione non definitiva

I pacchetti NuGet con un suffisso di versione sono considerati [definitive](/nuget/create-packages/prerelease-packages). Per impostazione predefinita, la UI Gestione pacchetti NuGet Mostra versioni stabili, a meno che un utente sceglie di versioni non definitive dei pacchetti, pacchetti di versioni non definitive le rendono ideali per i test di utente con limitazioni.

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> Una stabile del pacchetto non può dipendere da un versione preliminare del pacchetto. È necessario verificare che il proprio pacchetto di versioni non definitive o dipendono da una versione stabile precedente.

![Dipendenza del pacchetto di versioni non definitive NuGet](./media/nuget/nuget-prerelease-package.png "dipendenza versione preliminare del pacchetto NuGet")

**Eseguire operazioni ✔️** pubblicare un versione preliminare del pacchetto durante la verifica, la visualizzazione in anteprima o la sperimentazione.

**Eseguire operazioni ✔️** pubblicare un pacchetto stabile quando pronto in modo gli altri pacchetti stabili possono farvi riferimento.

## <a name="symbol-packages"></a>Pacchetti di simboli

NuGet supporta [generazione di un pacchetto di simboli separati](/nuget/create-packages/symbol-packages) contenente il debug di file PDB insieme al pacchetto principale che contiene gli assembly .NET. L'idea di pacchetti di simboli è che siano ospitate in un server di simboli e vengono scaricati solo da uno strumento come Visual Studio su richiesta.

Attualmente l'host pubblica principale per i simboli - [SymbolSource](http://www.symbolsource.org/) -non supporta i file PDB portatili creato dallo stile di SDK progetti e pacchetti di simboli non sono utili.

**Provare a ✔️** incorporamento di PDB nel pacchetto NuGet principale.

**Si consiglia di evitare ❌** creazione di un pacchetto di simboli che contiene i file PDB.

>[!div class="step-by-step"]
[Precedente](./strong-naming.md)
[Successivo](./dependencies.md)
