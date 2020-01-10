---
title: Creazione di pacchetti di distribuzione di .NET Core
description: Informazione su come creare pacchetti e assegnare nome e versione ai pacchetti per la distribuzione di .NET Core.
author: tmds
ms.date: 10/09/2019
ms.openlocfilehash: cfd6003cfac5c00fc06ebc6195eccd55a0d7afe7
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740929"
---
# <a name="net-core-distribution-packaging"></a>Creazione di pacchetti di distribuzione di .NET Core

Dato che .NET Core è disponibile in un numero sempre maggiore di piattaforme, è utile imparare a creare un pacchetto e assegnarvi un nome e una versione. In questo modo, coloro che si occupano della manutenzione dei pacchetti possono garantire un'esperienza coerente indipendentemente dalla piattaforma scelta dagli utenti per l'esecuzione di .NET. Questo articolo è utile per gli utenti che:

- Stanno cercando di compilare .NET Core dal codice sorgente.
- Vogliono apportare modifiche all'interfaccia della riga di comando di .NET Core che possono avere effetti sul layout risultante o sui pacchetti prodotti.

## <a name="disk-layout"></a>Layout del disco

Quando viene installato, .NET Core è costituito da diversi componenti che vengono disposti nel file system come segue:

```
{dotnet_root}                                     (*)
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host                                          (*)
│   └── fxr                                       (*)
│       └── <fxr version>        (2)
├── sdk                                           (*)
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)              (*)
├── packs                                         (*)
│   ├── Microsoft.AspNetCore.App.Ref              (*)
│   │   └── <aspnetcore ref version>     (11)
│   ├── Microsoft.NETCore.App.Ref                 (*)
│   │   └── <netcore ref version>        (12)
│   ├── Microsoft.NETCore.App.Host.<rid>          (*)
│   │   └── <apphost version>            (13)
│   ├── Microsoft.WindowsDesktop.App.Ref          (*)
│   │   └── <desktop ref version>        (14)
│   └── NETStandard.Library.Ref                   (*)
│       └── <netstandard version>        (15)
├── shared                                        (*)
│   ├── Microsoft.NETCore.App                     (*)
│   │   └── <runtime version>     (5)
│   ├── Microsoft.AspNetCore.App                  (*)
│   │   └── <aspnetcore version>  (6)
│   ├── Microsoft.AspNetCore.All                  (*)
│   │   └── <aspnetcore version>  (6)
│   └── Microsoft.WindowsDesktop.App              (*)
│       └── <desktop app version> (7)
└── templates                                     (*)
│   └── <templates version>      (17)
/
├── etc/dotnet
│       └── install_location     (16)
├── usr/share/man/man1
│       └── dotnet.1.gz          (9)
└── usr/bin
        └── dotnet               (10)
```

- (1) **dotnet** L'host, noto anche come "muxer", ha due ruoli distinti: attivare un runtime per avviare un'applicazione e attivare un SDK per inviare comandi all'applicazione. L'host è un file eseguibile nativo (`dotnet.exe`).

Benché sia presente un singolo host, la maggior parte degli altri componenti si trova in directory con versioni (2,3,5,6). Questo significa che nel sistema possono essere presenti più versioni installate side-by-side.

- (2) **host/fxr/\<versione fxr>** contiene la logica di risoluzione del framework usata dall'host. L'host usa la versione di hostfxr più recente installata. Hostfxr è responsabile della selezione del runtime appropriato durante l'esecuzione di un'applicazione .NET Core. Ad esempio, un'applicazione compilata per .NET Core 2.0.0 usa il runtime 2.0.5 quando è disponibile. Analogamente, hostfxr seleziona l'SDK appropriato durante lo sviluppo.

- (3) **sdk/\<versione sdk>** L'SDK, noto anche come "strumenti", è un set di strumenti gestiti che vengono usati per scrivere e compilare applicazioni e librerie .NET Core. L'SDK include l'interfaccia della riga di comando (CLI) di .NET Core, i compilatori di linguaggi gestiti, MSBuild, le attività di compilazione e le destinazioni associate, NuGet, nuovi modelli di progetto e così via.

- (4) **sdk/NuGetFallbackFolder** contiene una cache dei pacchetti NuGet usati da un SDK durante un'operazione di ripristino, come ad esempio l'esecuzione di `dotnet restore` o di `dotnet build`. Questa cartella viene usata solo prima di .NET Core 3,0. Non può essere compilato dall'origine perché contiene risorse binarie predefinite da `nuget.org`.

La cartella **shared** contiene i framework. Un framework condiviso offre un set di librerie in una posizione centrale per consentirne l'uso da parte di applicazioni diverse.

- (5) **shared/Microsoft.NETCore.App/\<versione runtime>** Questo framework contiene il runtime di .NET Core e il supporto delle librerie gestite.

- (6) **Shared/Microsoft. AspNetCore. { App, all}/\<versione di aspnetcore >** contiene le librerie di ASP.NET Core. Le librerie in `Microsoft.AspNetCore.App` vengono sviluppate e supportate come parte del progetto .NET Core. Le librerie in `Microsoft.AspNetCore.All` sono un superset che contiene anche le librerie di terze parti.

- (7) la **versione dell'app desktop Shared/Microsoft. desktop. app/\<** contiene le librerie desktop di Windows. Questa operazione non è inclusa nelle piattaforme non Windows.

- (8) **LICENSE.txt,ThirdPartyNotices.txt** sono rispettivamente le licenze di .NET Core e le licenze delle librerie di terze parti usate in .NET Core.

- (9, 10) **dotnet. 1. gz, dotnet** `dotnet.1.gz` è la pagina manuale dotnet. `dotnet` è un collegamento simbolico all'host dotnet (1). Questi file vengono installati in percorsi ben noti per l'integrazione del sistema.

- (11, 12) **Microsoft. NETCore. app. Ref, Microsoft. AspNetCore. app. Ref** descrivono l'API di una versione `x.y` di .NET Core e ASP.NET Core rispettivamente. Questi pacchetti vengono usati durante la compilazione per le versioni di destinazione.

- (13) **Microsoft. NETCore. app. host.\<rid >** contiene un file binario nativo per `rid`della piattaforma. Questo file binario è un modello quando si compila un'applicazione .NET Core in un file binario nativo per tale piattaforma.

- (14) **Microsoft. WindowsDesktop. app. Ref** descrive l'API della versione `x.y` delle applicazioni desktop di Windows. Questi file vengono usati durante la compilazione per la destinazione. Questa opzione non è disponibile nelle piattaforme non Windows.

- (15) **NETStandard. Library. Ref** descrive l'API NETStandard `x.y`. Questi file vengono usati durante la compilazione per la destinazione.

- (16) **/etc/dotnet/install_location** è un file che contiene il percorso completo per `{dotnet_root}`. Il percorso può terminare con una nuova riga. Non è necessario aggiungere questo file quando viene `/usr/share/dotnet`la radice.

- (17) i **modelli** contengono i modelli usati dall'SDK. Ad esempio, `dotnet new` trova qui i modelli di progetto.

Le cartelle contrassegnate con `(*)` vengono utilizzate da più pacchetti. Alcuni formati di pacchetto (ad esempio `rpm`) richiedono una gestione speciale di tali cartelle. Il gestore del pacchetto deve occuparsi di questo.

## <a name="recommended-packages"></a>Pacchetti consigliati

Il controllo delle versioni di .NET Core è basato sui numeri di versione `[major].[minor]` del componente di runtime.
La versione dell'SDK usa gli stessi elementi `[major].[minor]` e ha un elemento `[patch]` indipendente che combina la semantica della versione definitiva e della versione patch per l'SDK.
Ad esempio, l'SDK versione 2.2.302 è la seconda versione della versione della terza funzionalità dell'SDK che supporta il runtime di 2,2. Per altre informazioni sul controllo delle versioni, vedere [Panoramica di come viene specificata la versione di .NET Core](../versions/index.md).

Alcuni pacchetti includono parte del numero di versione nel nome. Questo consente di installare una versione specifica.
La parte rimanente della versione non è inclusa nel nome della versione. Ciò consente alla gestione pacchetti del sistema operativo di aggiornare i pacchetti, ad esempio installando automaticamente le correzioni per la sicurezza. La gestione pacchetti supportata è specifica per Linux.

Di seguito sono elencati i pacchetti consigliati:

- `dotnet-sdk-[major].[minor]`-installa l'SDK più recente per un runtime specifico
  - **Versione:** \<versione runtime >
  - **Esempio:** DotNet-sdk-2,1
  - **Contiene:** (3), (4)
  - **Dipendenze:** `dotnet-runtime-[major].[minor]`, `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`

- `aspnetcore-runtime-[major].[minor]`-installa un runtime di ASP.NET Core specifico
  - **Versione:** \<versione runtime aspnetcore >
  - **Esempio:** aspnetcore-runtime-2,1
  - **Contiene:** (6)
  - **Dipendenze:** `dotnet-runtime-[major].[minor]`

- `dotnet-runtime-deps-[major].[minor]` _(facoltativo)_ : installa le dipendenze per l'esecuzione di applicazioni autosufficienti
  - **Versione:** \<versione runtime >
  - **Esempio:** DotNet-Runtime-deps-2,1
  - **Dipendenze:** _dipendenze specifiche della distribuzione_

- `dotnet-runtime-[major].[minor]`-installa un runtime specifico
  - **Versione:** \<versione runtime >
  - **Esempio:** DotNet-runtime-2,1
  - **Contiene:** (5)
  - **Dipendenze:** `dotnet-hostfxr-[major].[minor]`, `dotnet-runtime-deps-[major].[minor]`

- dipendenza da `dotnet-hostfxr-[major].[minor]`
  - **Versione:** \<versione runtime >
  - **Esempio:** DotNet-hostfxr-3,0
  - **Contiene:** (2)
  - **Dipendenze:** `dotnet-host`

- dipendenza da `dotnet-host`
  - **Versione:** \<versione runtime >
  - **Esempio:** DotNet-host
  - **Contiene:** (1), (8), (9), (10), (16)

- dipendenza da `dotnet-apphost-pack-[major].[minor]`
  - **Versione:** \<versione runtime >
  - **Contiene:** (13)

- `dotnet-targeting-pack-[major].[minor]`: consente la destinazione di un runtime non più recente
  - **Versione:** \<versione runtime >
  - **Contiene:** (12)

- `aspnetcore-targeting-pack-[major].[minor]`: consente la destinazione di un runtime non più recente
  - **Versione:** \<versione runtime aspnetcore >
  - **Contiene:** (11)

- `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`: consente la destinazione di una versione di netstandard
  - **Versione:** \<versione SDK >
  - **Contiene:** (15)

- `dotnet-templates-[major].[minor]`
  - **Versione:** \<versione SDK >
  - **Contiene:** (15)

Per la `dotnet-runtime-deps-[major].[minor]` è necessario comprendere le _dipendenze specifiche della distribuzione_. Poiché il sistema di compilazione della distribuzione potrebbe essere in grado di derivare automaticamente questo valore, il pacchetto è facoltativo, nel qual caso queste dipendenze vengono aggiunte direttamente al pacchetto `dotnet-runtime-[major].[minor]`.

Quando il contenuto del pacchetto si trova in una cartella con versione, il nome del pacchetto `[major].[minor]` corrisponde al nome della cartella con versione. Per tutti i pacchetti, ad eccezione del `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, questo corrisponde anche alla versione di .NET Core.

Le dipendenze tra i pacchetti devono usare un requisito _di versione uguale o maggiore di_ . Ad esempio, `dotnet-sdk-2.2:2.2.401` richiede `aspnetcore-runtime-2.2 >= 2.2.6`. In questo modo, l'utente può aggiornare l'installazione tramite un pacchetto radice, ad esempio `dnf update dotnet-sdk-2.2`.

Per la maggior parte delle distribuzioni è necessario che tutti gli elementi vengano compilati dall'origine. Questo ha un certo impatto sui pacchetti:

- Le librerie di terze parti in `shared/Microsoft.AspNetCore.All` non possono essere compilate facilmente dal codice sorgente. Quindi la cartella viene omessa dal pacchetto `aspnetcore-runtime`.

- `NuGetFallbackFolder` viene popolato usando elementi binari da `nuget.org`. Deve rimanere vuoto.

Più pacchetti `dotnet-sdk` possono contenere gli stessi file per `NuGetFallbackFolder`. Per evitare problemi con la gestione pacchetti, questi file devono essere identici (checksum, data di modifica e così via).

## <a name="building-packages"></a>Compilazione dei pacchetti

Il repository [dotnet/source-build](https://github.com/dotnet/source-build) contiene istruzioni su come compilare un file tarball di origine di .NET Core SDK e tutti i relativi componenti. L'output del repository di compilazione dell'origine corrisponde al layout descritto nella prima sezione di questo articolo.
