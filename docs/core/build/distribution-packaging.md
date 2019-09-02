---
title: Creazione di pacchetti di distribuzione di .NET Core
description: Informazione su come creare pacchetti e assegnare nome e versione ai pacchetti per la distribuzione di .NET Core.
author: tmds
ms.date: 03/02/2018
ms.custom: seodec18
ms.openlocfilehash: 5d23147c8a38fbeea9e88c0a18e1f220e854fec1
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2019
ms.locfileid: "70105421"
---
# <a name="net-core-distribution-packaging"></a>Creazione di pacchetti di distribuzione di .NET Core

Dato che .NET Core è disponibile in un numero sempre maggiore di piattaforme, è utile imparare a creare un pacchetto e assegnarvi un nome e una versione. In questo modo, coloro che si occupano della manutenzione dei pacchetti possono garantire un'esperienza coerente indipendentemente dalla piattaforma scelta dagli utenti per l'esecuzione di .NET. Questo articolo è utile per gli utenti che:

- Stanno cercando di compilare .NET Core dal codice sorgente.
- Vogliono apportare modifiche all'interfaccia della riga di comando di .NET Core che possono avere effetti sul layout risultante o sui pacchetti prodotti.

## <a name="disk-layout"></a>Layout su disco

Quando viene installato, .NET Core è costituito da diversi componenti che vengono disposti nel file system come segue:

```
.
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host
│   └── fxr
│       └── <fxr version>        (2)
├── sdk
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)
└── shared
    ├── Microsoft.NETCore.App
    │   └── <runtime version>    (5)
    └── Microsoft.AspNetCore.App
        └── <aspnetcore version> (6)
    └── Microsoft.AspNetCore.All
        └── <aspnetcore version> (7)
/
├─usr/share/man/man1
│       └── dotnet.1.gz          (9)
└─usr/bin
        └── dotnet               (10)
```

- (1) **dotnet** L'host, noto anche come "muxer", ha due ruoli distinti: attivare un runtime per avviare un'applicazione e attivare un SDK per inviare comandi all'applicazione. L'host è un file eseguibile nativo (`dotnet.exe`).

Benché sia presente un singolo host, la maggior parte degli altri componenti si trova in directory con versioni (2,3,5,6). Questo significa che nel sistema possono essere presenti più versioni installate side-by-side.

- (2) **host/fxr/\<versione fxr>** contiene la logica di risoluzione del framework usata dall'host. L'host usa la versione di hostfxr più recente installata. Hostfxr è responsabile della selezione del runtime appropriato durante l'esecuzione di un'applicazione .NET Core. Ad esempio, un'applicazione compilata per .NET Core 2.0.0 usa il runtime 2.0.5 quando è disponibile. Analogamente, hostfxr seleziona l'SDK appropriato durante lo sviluppo.

- (3) **sdk/\<versione sdk>** L'SDK, noto anche come "strumenti", è un set di strumenti gestiti che vengono usati per scrivere e compilare applicazioni e librerie .NET Core. L'SDK include l'interfaccia della riga di comando (CLI) di .NET Core, i compilatori di linguaggi gestiti, MSBuild, le attività di compilazione e le destinazioni associate, NuGet, nuovi modelli di progetto e così via.

- (4) **sdk/NuGetFallbackFolder** contiene una cache dei pacchetti NuGet usati da un SDK durante un'operazione di ripristino, come ad esempio l'esecuzione di `dotnet restore` o di `dotnet build /t:Restore`.

La cartella **shared** contiene i framework. Un framework condiviso offre un set di librerie in una posizione centrale per consentirne l'uso da parte di applicazioni diverse.

- (5) **shared/Microsoft.NETCore.App/\<versione runtime>** Questo framework contiene il runtime di .NET Core e il supporto delle librerie gestite.

- (6,7) **shared/Microsoft.AspNetCore.{App,All}/\<versione aspnetcore>** contiene le librerie ASP.NET Core. Le librerie in `Microsoft.AspNetCore.App` vengono sviluppate e supportate come parte del progetto .NET Core. Le librerie in `Microsoft.AspNetCore.All` sono un superset che contiene anche le librerie di terze parti.

- (8) **LICENSE.txt,ThirdPartyNotices.txt** sono rispettivamente le licenze di .NET Core e le licenze delle librerie di terze parti usate in .NET Core.

- (9,10) **dotnet.1.gz, dotnet** `dotnet.1.gz` è la pagina di manuale dotnet. `dotnet` è un collegamento simbolico all'host dotnet (1). Questi file vengono installati in percorsi ben noti per l'integrazione del sistema.

## <a name="recommended-packages"></a>Pacchetti consigliati

Il controllo delle versioni di .NET Core è basato sui numeri di versione `[major].[minor]` del componente di runtime.
La versione dell'SDK usa gli stessi elementi `[major].[minor]` e ha un elemento `[patch]` indipendente che combina la semantica della versione definitiva e della versione patch per l'SDK.
Ad esempio: la versione 2.2.302 dell'SDK è la seconda versione patch della terza versione definitiva dell'SDK che supporta il runtime 2.2. Per altre informazioni sul controllo delle versioni, vedere [Panoramica di come viene specificata la versione di .NET Core](../versions/index.md).

Alcuni pacchetti includono parte del numero di versione nel nome. Questo consente di installare una versione specifica.
La parte rimanente della versione non è inclusa nel nome della versione. Ciò consente alla gestione pacchetti del sistema operativo di aggiornare i pacchetti, ad esempio installando automaticamente le correzioni per la sicurezza. La gestione pacchetti supportata è specifica per Linux.

Nella tabella seguente sono riportati i pacchetti consigliati:

| nome                                    | Esempio                | Caso d'uso: Installare...           | Contiene           | Dipendenze                                   | Versione            |
|-----------------------------------------|------------------------|---------------------------------|--------------------|------------------------------------------------|--------------------|
| dotnet-sdk-[major]                      | dotnet-sdk-2           | Sdk più recente per runtime major    |                    | dotnet-sdk-[major].[latestminor]               | \<versione SDK>     |
| dotnet-sdk-[major].[minor]              | dotnet-sdk-2.1         | Sdk più recente per runtime specifico |                    | dotnet-sdk-[major].[minor].[latest sdk feat]xx | \<versione SDK>     |
| dotnet-sdk-[major].[minor].[sdk feat]xx | dotnet-sdk-2.1.3xx     | Versione definitiva sdk specifico    | (3),(4)            | aspnetcore-runtime-[major].[minor]             | \<versione SDK>     |
| aspnetcore-runtime-[major].[minor]      | aspnetcore-runtime-2.1 | Runtime di ASP.NET Core specifico   | (6),[(7)]          | dotnet-runtime-[major].[minor]                 | \<versione runtime> |
| dotnet-runtime-[major].[minor]          | dotnet-runtime-2.1     | Runtime specifico                | (5)                | host-fxr:\<versione runtime>+                   | \<versione runtime> |
| dotnet-host-fxr                         | dotnet-host-fxr        | _dipendenza_                    | (2)                | host:\<versione runtime>+                       | \<versione runtime> |
| dotnet-host                             | dotnet-host            | _dipendenza_                    | (1),(8),(9),(10)   |                                                | \<versione runtime> |

Per la maggior parte delle distribuzioni è necessario che tutti gli elementi vengano compilati dall'origine. Questo ha un certo impatto sui pacchetti:

- Le librerie di terze parti in `shared/Microsoft.AspNetCore.All` non possono essere compilate facilmente dal codice sorgente. Quindi la cartella viene omessa dal pacchetto `aspnetcore-runtime`.

- `NuGetFallbackFolder` viene popolato usando elementi binari da `nuget.org`. Deve rimanere vuoto.

Più pacchetti `dotnet-sdk` possono contenere gli stessi file per `NuGetFallbackFolder`. Per evitare problemi con la gestione pacchetti, questi file devono essere identici (checksum, data di modifica e così via).

### <a name="preview-versions"></a>Versioni di anteprima

I responsabili della manutenzione dei pacchetti possono decidere di rendere disponibili versioni di anteprima del framework condiviso e dell'SDK. Le versioni di anteprima possono essere messe a disposizione usando i pacchetti `dotnet-sdk-[major].[minor].[sdk feat]xx`, `aspnetcore-runtime-[major].[minor]` o `dotnet-runtime-[major].[minor]`. Per le versioni di anteprima, è necessario impostare la versione major del pacchetto su zero. In questo modo la versione finale viene installata come aggiornamento del pacchetto.

### <a name="patch-packages"></a>Pacchetti di patch

Poiché la versione della patch di un pacchetto può causare una modifica importante, è consigliabile che il responsabile della manutenzione del pacchetto renda disponibili dei _pacchetti di patch_. Questi pacchetti consentono di installare una versione specifica della patch che non viene aggiornata automaticamente. Usare i pacchetti di patch solo in rare circostanze poiché non vengono aggiornati con correzioni per la sicurezza.

Nella tabella seguente sono riportati i pacchetti consigliati e i **pacchetti di patch**:

| nome                                           | Esempio                  | Contiene         | Dipendenze                                              |
|------------------------------------------------|--------------------------|------------------|-----------------------------------------------------------|
| dotnet-sdk-[major]                             | dotnet-sdk-2             |                  | dotnet-sdk-[major].[latest sdk minor]                     |
| dotnet-sdk-[major].[minor]                     | dotnet-sdk-2.1           |                  | dotnet-sdk-[major].[minor].[latest sdk feat]xx            |
| dotnet-sdk-[major].[minor].[sdk feat]xx        | dotnet-sdk-2.1.3xx       |                  | dotnet-sdk-[major].[minor].[latest sdk patch]             |
| **dotnet-sdk-[major].[minor].[patch]**         | dotnet-sdk-2.1.300       | (3),(4)          | aspnetcore-runtime-[major].[minor].[sdk runtime patch]    |
| aspnetcore-runtime-[major].[minor]             | aspnetcore-runtime-2.1   |                  | aspnetcore-runtime-[major].[minor].[latest runtime patch] |
| **aspnetcore-runtime-[major].[minor].[patch]** | aspnetcore-runtime-2.1.0 | (6),[(7)]        | dotnet-runtime-[major].[minor].[patch]                    |
| dotnet-runtime-[major].[minor]                 | dotnet-runtime-2.1       |                  | dotnet-runtime-[major].[minor].[latest runtime patch]     |
| **dotnet-runtime-[major].[minor].[patch]**     | dotnet-runtime-2.1.0     | (5)              | host-fxr:\<versione runtime>+                              |
| dotnet-host-fxr                                | dotnet-host-fxr          | (2)              | host:\<versione runtime>+                                  |
| dotnet-host                                    | dotnet-host              | (1),(8),(9),(10) |                                                           |

Un'alternativa all'uso dei pacchetti di patch è _aggiungere_ i pacchetti a una versione specifica usando Gestione pacchetti. Per evitare di influire su altri utenti o applicazioni, è possibile compilare e distribuire le applicazioni in un contenitore.

## <a name="building-packages"></a>Compilazione dei pacchetti

Il repository [dotnet/source-build](https://github.com/dotnet/source-build) contiene istruzioni su come compilare un file tarball di origine di .NET Core SDK e tutti i relativi componenti. L'output del repository di compilazione dell'origine corrisponde al layout descritto nella prima sezione di questo articolo.
