---
title: Creazione di pacchetti di distribuzione di .NET Core
description: Informazione su come creare pacchetti e assegnare nome e versione ai pacchetti per la distribuzione di .NET Core.
author: tmds
ms.date: 10/09/2019
ms.openlocfilehash: 1b5adf761a51e006f8309e1f326fc0a9c12aab7a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76748503"
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

- (4) **sdk/NuGetFallbackFolder** contiene una cache dei pacchetti NuGet usati da un SDK durante un'operazione di ripristino, come ad esempio l'esecuzione di `dotnet restore` o di `dotnet build`. This folder is only used prior to .NET Core 3.0. It can't be built from source, because it contains prebuilt binary assets from `nuget.org`.

La cartella **shared** contiene i framework. Un framework condiviso offre un set di librerie in una posizione centrale per consentirne l'uso da parte di applicazioni diverse.

- (5) **shared/Microsoft.NETCore.App/\<versione runtime>** Questo framework contiene il runtime di .NET Core e il supporto delle librerie gestite.

- (6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** contains the ASP.NET Core libraries. Le librerie in `Microsoft.AspNetCore.App` vengono sviluppate e supportate come parte del progetto .NET Core. Le librerie in `Microsoft.AspNetCore.All` sono un superset che contiene anche le librerie di terze parti.

- (7) **shared/Microsoft.Desktop.App/\<desktop app version>** contains the Windows desktop libraries. This isn't included on non-Windows platforms.

- (8) **LICENSE.txt,ThirdPartyNotices.txt** sono rispettivamente le licenze di .NET Core e le licenze delle librerie di terze parti usate in .NET Core.

- (9,10) **dotnet.1.gz, dotnet** `dotnet.1.gz` is the dotnet manual page. `dotnet` è un collegamento simbolico all'host dotnet (1). These files are installed at well-known locations for system integration.

- (11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** describe the API of an `x.y` version of .NET Core and ASP.NET Core respectively. These packs are used when compiling for those target versions.

- (13) **Microsoft.NETCore.App.Host.\<rid>** contains a native binary for platform `rid`. This binary is a template when compiling a .NET Core application into a native binary for that platform.

- (14) **Microsoft.WindowsDesktop.App.Ref** describes the API of `x.y` version of Windows Desktop applications. These files are used when compiling for that target. This isn't provided on non-Windows platforms.

- (15) **NETStandard.Library.Ref** describes the netstandard `x.y` API. These files are used when compiling for that target.

- (16) **/etc/dotnet/install_location** is a file that contains the full path for `{dotnet_root}`. The path may end with a newline. It's not necessary to add this file when the root is `/usr/share/dotnet`.

- (17) **templates** contains the templates used by the SDK. For example, `dotnet new` finds project templates here.

The folders marked with `(*)` are used by multiple packages. Some package formats (for example, `rpm`) require special handling of such folders. The package maintainer must take care of this.

## <a name="recommended-packages"></a>Pacchetti consigliati

Il controllo delle versioni di .NET Core è basato sui numeri di versione `[major].[minor]` del componente di runtime.
La versione dell'SDK usa gli stessi elementi `[major].[minor]` e ha un elemento `[patch]` indipendente che combina la semantica della versione definitiva e della versione patch per l'SDK.
For example: SDK version 2.2.302 is the second patch release of the third feature release of the SDK that supports the 2.2 runtime. Per altre informazioni sul controllo delle versioni, vedere [Panoramica di come viene specificata la versione di .NET Core](./versions/index.md).

Alcuni pacchetti includono parte del numero di versione nel nome. Questo consente di installare una versione specifica.
La parte rimanente della versione non è inclusa nel nome della versione. Ciò consente alla gestione pacchetti del sistema operativo di aggiornare i pacchetti, ad esempio installando automaticamente le correzioni per la sicurezza. La gestione pacchetti supportata è specifica per Linux.

The following lists the recommended packages:

- `dotnet-sdk-[major].[minor]` - Installs the latest sdk for specific runtime
  - **Version:** \<runtime version>
  - **Example:** dotnet-sdk-2.1
  - **Contains:** (3),(4)
  - **Dependencies:** `dotnet-runtime-[major].[minor]`, `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`

- `aspnetcore-runtime-[major].[minor]` - Installs a specific ASP.NET Core runtime
  - **Version:** \<aspnetcore runtime version>
  - **Example:** aspnetcore-runtime-2.1
  - **Contains:** (6)
  - **Dependencies:** `dotnet-runtime-[major].[minor]`

- `dotnet-runtime-deps-[major].[minor]` _(Optional)_ - Installs the dependencies for running self-contained applications
  - **Version:** \<runtime version>
  - **Example:** dotnet-runtime-deps-2.1
  - **Dependencies:** _distribution-specific dependencies_

- `dotnet-runtime-[major].[minor]` - Installs a specific runtime
  - **Version:** \<runtime version>
  - **Example:** dotnet-runtime-2.1
  - **Contains:** (5)
  - **Dependencies:** `dotnet-hostfxr-[major].[minor]`, `dotnet-runtime-deps-[major].[minor]`

- `dotnet-hostfxr-[major].[minor]` - dependency
  - **Version:** \<runtime version>
  - **Example:** dotnet-hostfxr-3.0
  - **Contains:** (2)
  - **Dependencies:** `dotnet-host`

- `dotnet-host` - dependency
  - **Version:** \<runtime version>
  - **Example:** dotnet-host
  - **Contains:** (1),(8),(9),(10),(16)

- `dotnet-apphost-pack-[major].[minor]` - dependency
  - **Version:** \<runtime version>
  - **Contains:** (13)

- `dotnet-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime
  - **Version:** \<runtime version>
  - **Contains:** (12)

- `aspnetcore-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime
  - **Version:** \<aspnetcore runtime version>
  - **Contains:** (11)

- `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]` - Allows targeting a netstandard version
  - **Version:** \<sdk version>
  - **Contains:** (15)

- `dotnet-templates-[major].[minor]`
  - **Version:** \<sdk version>
  - **Contains:** (15)

The `dotnet-runtime-deps-[major].[minor]` requires understanding the _distro-specific dependencies_. Because the distro build system may be able to derive this automatically, the package is optional, in which case these dependencies are added directly to the `dotnet-runtime-[major].[minor]` package.

When package content is under a versioned folder, the package name `[major].[minor]` match the versioned folder name. For all packages, except the `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, this also matches with the .NET Core version.

Dependencies between packages should use an _equal or greater than_ version requirement. For example, `dotnet-sdk-2.2:2.2.401` requires `aspnetcore-runtime-2.2 >= 2.2.6`. This makes it possible for the user to upgrade their installation via a root package (for example, `dnf update dotnet-sdk-2.2`).

Per la maggior parte delle distribuzioni è necessario che tutti gli elementi vengano compilati dall'origine. Questo ha un certo impatto sui pacchetti:

- Le librerie di terze parti in `shared/Microsoft.AspNetCore.All` non possono essere compilate facilmente dal codice sorgente. Quindi la cartella viene omessa dal pacchetto `aspnetcore-runtime`.

- `NuGetFallbackFolder` viene popolato usando elementi binari da `nuget.org`. Deve rimanere vuoto.

Più pacchetti `dotnet-sdk` possono contenere gli stessi file per `NuGetFallbackFolder`. Per evitare problemi con la gestione pacchetti, questi file devono essere identici (checksum, data di modifica e così via).

## <a name="building-packages"></a>Compilazione dei pacchetti

Il repository [dotnet/source-build](https://github.com/dotnet/source-build) contiene istruzioni su come compilare un file tarball di origine di .NET Core SDK e tutti i relativi componenti. L'output del repository di compilazione dell'origine corrisponde al layout descritto nella prima sezione di questo articolo.
