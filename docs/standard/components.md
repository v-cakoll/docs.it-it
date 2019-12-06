---
title: Componenti dell'architettura .NET
description: Descrive i componenti dell'architettura .NET, ad esempio .NET Standard, le implementazioni di .NET, i runtime .NET e gli strumenti.
author: cartermp
ms.author: mairaw
ms.date: 08/23/2017
ms.technology: dotnet-standard
ms.openlocfilehash: 543f05cd52e62166b8a5ee318a588dee1e8ef76a
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838195"
---
# <a name="net-architectural-components"></a>Componenti dell'architettura .NET

Un'app .NET viene sviluppata per e viene eseguita in una o più *implementazioni di .NET*.  Le implementazioni di .NET includono .NET Framework, .NET Core e Mono. .NET Standard è una specifica di API comune a tutte le implementazioni di .NET. Questo articolo fornisce una breve introduzione di questi concetti.

## <a name="net-standard"></a>.NET Standard

.NET Standard è un set di API implementate dalla libreria di classi base di un'implementazione di .NET. In termini più formali, si tratta di una specifica di API .NET che costituiscono un set di contratti in base a cui viene compilato il codice. Questi contratti vengono implementati in ogni implementazione di .NET. Questo consente la portabilità tra diverse implementazioni di .NET, consentendo di eseguire il codice su qualsiasi piattaforma.

.NET Standard è anche un [framework di destinazione](glossary.md#target-framework). Se il codice ha come destinazione una versione di .NET Standard, può essere eseguito in qualsiasi implementazione di .NET che supporta tale versione di .NET Standard.

Per altre informazioni su .NET Standard e su come specificarla come destinazione, vedere l'argomento [.NET Standard](net-standard.md).

## <a name="net-implementations"></a>Implementazioni di .NET

Ogni implementazione di .NET include i componenti seguenti:

- Uno o più runtime. Esempi: CLR per .NET Framework, CoreCLR e CoreRT per .NET Core.
- Una libreria di classi che implementa .NET Standard e può implementare API aggiuntive. Esempi: libreria di classi base .NET Framework, libreria di classi base .NET Core.
- Facoltativamente, uno o più framework applicazione. Esempi: [ASP.NET](https://www.asp.net/), [Windows Forms](../framework/winforms/windows-forms-overview.md)e [Windows Presentation Foundation (WPF)](../framework/wpf/index.md) sono inclusi nei .NET Framework e in .NET Core.
- Facoltativamente, strumenti di sviluppo. Alcuni strumenti di sviluppo sono condivisi tra più implementazioni.

Microsoft sviluppa e gestisce attivamente quattro implementazioni di .NET principali, ovvero .NET Core, .NET Framework, Mono e piattaforma UWP.

### <a name="net-core"></a>.NET Core

.NET core è un'implementazione multipiattaforma di .NET ed è progettato per gestire i carichi di lavoro di server e cloud su larga scala. Viene eseguito in Windows, macOS e Linux. Implementa .NET Standard, pertanto qualsiasi codice che ha come destinazione .NET Standard può essere eseguito su .NET Core. [ASP.NET Core](https://dotnet.microsoft.com/learn/aspnet/what-is-aspnet-core), [Windows Forms](../framework/winforms/windows-forms-overview.md) e [Windows Presentation Foundation (WPF)](../framework/wpf/index.md) sono tutti supportati in .NET Core.

Per altre informazioni su .NET Core, vedere la [Guida a .NET Core](../core/index.md) e [Scelta di .NET Core o .NET Framework per le app server](choosing-core-framework-server.md).

### <a name="net-framework"></a>.NET Framework

.NET Framework è l'implementazione originale di .NET, introdotta nel 2002. È lo stesso .NET Framework che gli sviluppatori .NET hanno sempre usato. Le versioni 4.5 e successive implementano .NET Standard, quindi il codice che ha come destinazione .NET Standard può essere eseguito in tali versioni di .NET Framework. Contiene API aggiuntive specifiche di Windows, ad esempio API per lo sviluppo di applicazioni desktop di Windows con Windows Forms e WPF. .NET Framework è ottimizzato per la compilazione di applicazioni desktop di Windows.

Per altre informazioni su .NET Framework, vedere [Guida a .NET Framework](../framework/index.md).

### <a name="mono"></a>Mono

Mono è un'implementazione di .NET usata principalmente quando è necessario un runtime di dimensioni ridotte. Si tratta del runtime su cui si basano le applicazioni Xamarin in Android, Mac, iOS, tvOS e watchOS ed è incentrato principalmente su un footprint ridotto. Mono inoltre consente di compilare giochi tramite il motore Unity.

Supporta tutte le versioni attualmente pubblicate di .NET Standard.

In precedenza, Mono implementava le API di dimensioni maggiori di .NET Framework ed emulava alcune delle funzionalità più diffuse su Unix. Viene a volte usato per eseguire applicazioni .NET che si basano su tali funzionalità in Unix.

Mono viene in genere usato con un compilatore JIT, ma include anche un compilatore statico completo (compilazione Ahead Of Time), usato in piattaforme quali iOS.

Per altre informazioni su Mono, vedere la [documentazione Mono](https://www.mono-project.com/docs/).

### <a name="universal-windows-platform-uwp"></a>Piattaforma UWP (Universal Windows Platform)

La piattaforma UWP è un'implementazione di .NET usata per la creazione di applicazioni Windows moderne e abilitate per il tocco e di software per Internet delle cose. È stata progettata per unificare i diversi tipi di dispositivi da specificare come destinazione, ad esempio computer, tablet, phablet, telefoni e anche Xbox. La piattaforma UWP offre molti servizi, ad esempio un App Store centralizzato, un ambiente di esecuzione (AppContainer) e un set di API di Windows da usare invece di Win32 (WinRT). Le app possono essere scritte in C++, C#, VB.NET e JavaScript. Quando si usano C# e VB.NET, le API .NET vengono fornite da .NET Core.

Per altre informazioni sulla piattaforma UWP, vedere [Introduzione alla piattaforma UWP (Universal Windows Platform)](/windows/uwp/get-started/universal-application-platform-guide).

## <a name="net-runtimes"></a>Runtime .NET

Un runtime è l'ambiente di esecuzione per un programma gestito. Il sistema operativo è parte dell'ambiente di runtime, ma non del runtime di .NET. Ecco alcuni esempi di runtime di .NET:

- CRL (Common Language Runtime) per .NET Framework
- CoreCLR (Core Common Language Runtime) per .NET Core
- .NET Native per la piattaforma UWP 
- Runtime di Mono per Xamarin.iOS, Xamarin.Android, Xamarin.Mac e per il framework desktop di Mono

## <a name="net-tooling-and-common-infrastructure"></a>Strumenti .NET e infrastruttura comune

È possibile accedere a un ampio set di strumenti e di componenti di infrastruttura che possono essere usati con qualsiasi implementazione di .NET, ad esempio:

- Linguaggi .NET e relativi compilatori
- Sistema del progetto .NET (basato su file con estensione *csproj*, *vbproj* e *fsproj*)
- [MSBuild](/visualstudio/msbuild/msbuild), il motore di compilazione usato per compilare i progetti
- [NuGet](/nuget/), il gestore di pacchetti Microsoft per .NET
- Strumenti open source di orchestrazione della compilazione, ad esempio [CAKE](https://cakebuild.net/) e [FAKE](https://fake.build/)

## <a name="applicable-standards"></a>Standard applicabili

Il C# linguaggio e le specifiche dell'interfaccia Common Language Infrastructure della riga di comando (CLI) sono standardizzati tramite [ECMA International®](https://www.ecma-international.org/). Le prime edizioni di questi standard sono state pubblicate da ECMA nel 2001 dicembre.

Le revisioni successive degli standard sono state sviluppate dai gruppi di attivitàC#TC49-TG2 () e TC49-TG3 (CLI) nel comitato tecnico dei linguaggi di programmazione ([TC49](https://www.ecma-international.org/memento/tc49.htm)) e sono state adottate dall'assembly generale ECMA e successivamente da ISO/IEC JTC 1 tramite il processo di rilevamento rapido ISO.

### <a name="latest-standards"></a>Standard più recenti

I documenti ECMA ufficiali seguenti sono disponibili per [C#](http://www.ecma-international.org/publications/standards/Ecma-334.htm) e l' [interfaccia](http://www.ecma-international.org/publications/standards/Ecma-335.htm) della riga di comando ([TR-84](http://www.ecma-international.org/publications/techreports/E-TR-084.htm)):

- **Standard C# del linguaggio (versione 5,0)** : [ECMA-334. pdf](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf)
- **Il Common Language Infrastructure**: è disponibile in formato [PDF](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-335.pdf) e modulo [zip](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-335.zip) .
- **Informazioni derivate dal file XML della partizione IV**: disponibile nei formati [PDF](https://www.ecma-international.org/publications/files/ECMA-TR/ECMA%20TR-084.pdf) e [zip](https://www.ecma-international.org/publications/files/ECMA-TR/TR-084.zip) .
 
I documenti ISO/IEC ufficiali sono disponibili nella pagina standard ISO/IEC [disponibili pubblicamente](https://standards.iso.org/ittf/PubliclyAvailableStandards/) . Questi collegamenti sono diretti da questa pagina:

- **Information Technology-linguaggi di programmazione C#-** : [ISO/IEC 23270:2018](https://standards.iso.org/ittf/PubliclyAvailableStandards/c075178_ISO_IEC_23270_2018.zip)
- **Information Technology-Common Language Infrastructure (CLI) partizioni da I a vi**: [ISO/IEC 23271:2012](https://standards.iso.org/ittf/PubliclyAvailableStandards/c058046_ISO_IEC_23271_2012(E).zip)
- **Information Technology-Common Language Infrastructure (CLI)-report tecnico sulle informazioni derivate dal file XML della partizione IV**: [ISO/IEC TR 23272:2011](https://standards.iso.org/ittf/PubliclyAvailableStandards/c057955_ISO_IEC_TR_23272_2011.zip)

## <a name="see-also"></a>Vedere anche

- [Scelta di .NET Core o .NET Framework per le app server](choosing-core-framework-server.md)
- [.NET Standard](net-standard.md)
- [Guida a .NET Core](../core/index.md)
- [Guida a .NET Framework](../framework/index.md)
- [Guida a C#](../csharp/index.yml)
- [Guida a F#](../fsharp/index.yml)
- [Guida a VB.NET](../visual-basic/index.yml)
