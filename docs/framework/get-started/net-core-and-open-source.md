---
title: Componenti di base e open-source di .NET
description: Leggi una panoramica su .NET Core, un'implementazione di uso generico, modulare, multipiattaforma e open source del .NET Standard.
ms.date: 03/30/2017
ms.assetid: e6bd4655-ce37-4003-8462-468a6fe2c40f
ms.openlocfilehash: 08d30d047c25b3b6d681d72b46b81a0cb21f8e0a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622757"
---
# <a name="net-core-and-open-source"></a>.NET Core e open source

Questo articolo fornisce una breve panoramica di .NET Core e Mostra come è possibile trovare altre informazioni. Per trovare l'elenco completo della documentazione per .NET Core, vedere la [Guida di .NET Core](../../core/index.yml).

## <a name="what-is-net-core"></a>Informazioni su .NET Core  

.NET Core è un'implementazione generica, modulare, multipiattaforma e open source del .NET Standard. Contiene molte delle stesse API del .NET Framework (ma .NET Core è un set più piccolo) e include componenti di runtime, Framework, compilatore e strumenti che supportano un'ampia gamma di sistemi operativi e di destinazione chip. L'implementazione di .NET Core nasce dall'esigenza di gestire i carichi di lavoro di ASP.NET Core, ma anche dalla necessità di un'implementazione più moderna. Può essere usato in scenari di dispositivi, cloud e incorporate/Internet.  
  
Per iniziare a usare .NET Core, vedere l'esercitazione su .NET [Hello World in 10 minuti](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro).  
  
Di seguito sono riportate le caratteristiche principali di .NET Core:
  
- **Multi-piattaforma:** NET Core offre gli strumenti essenziali per implementare le funzioni dell'app necessarie e riusare il codice indipendentemente dalla piattaforma di destinazione. Attualmente supporta tre sistemi operativi principali: Windows, Linux e macOS. È possibile scrivere app e librerie in modo che vengano eseguite senza modifiche nei sistemi operativi supportati. Per visualizzare l'elenco dei sistemi operativi supportati, vedere [.NET Core roadmap](https://github.com/dotnet/core/blob/master/roadmap.md) (Roadmap di .NET Core).
  
- **Open source:** .NET Core è uno dei molti progetti sotto il controllo di [.NET Foundation](https://www.dotnetfoundation.org/) ed è disponibile in [GitHub](https://github.com/). Come progetto open source, .NET Core promuove un processo di sviluppo più trasparente e una community attiva e impegnata.  
  
- **Distribuzione flessibile:** esistono principalmente due modi per distribuire l'app, ovvero la distribuzione dipendente dal framework e la distribuzione autonoma. Con la distribuzione dipendente dal framework vengono installate solo l'app e le dipendenze di terze parti e l'app richiede che sia presente una versione a livello di sistema di .NET Core. Con la distribuzione autonoma, la versione di .NET Core usata per compilare l'applicazione viene distribuita insieme all'app e alle dipendenze di terze parti e può essere eseguita side-by-side con altre versioni. Per altre informazioni, vedere [distribuzione di applicazioni .NET Core](../../core/deploying/index.md).

- **Modulare:** .NET Core è modulare perché viene rilasciato tramite NuGet in pacchetti di assembly di dimensioni ridotte. Invece di un assembly di grandi dimensioni che contiene la maggior parte delle funzionalità di base, .NET Core viene reso disponibile come pacchetti più piccoli e incentrati sulle funzionalità. Questa modularità consente un modello di sviluppo più agile e consente di ottimizzare l'app in modo da includere solo i pacchetti NuGet necessari. Una riduzione della superficie occupata dall'app offre anche diversi vantaggi, tra cui una maggiore sicurezza, una riduzione delle esigenze di assistenza, un miglioramento delle prestazioni e una diminuzione dei costi in un modello di pagamento basato sul consumo effettivo.  
  
## <a name="the-net-core-platform"></a>Piattaforma .NET Core
  
La piattaforma .NET Core è costituita da diversi componenti, tra cui i compilatori gestiti, il runtime, le librerie di classi base e numerosi modelli di applicazione, ad esempio ASP.NET Core. Per altre informazioni sui diversi componenti, vedere i repository [GitHub](https://github.com/) seguenti:  
  
- [Home page di .NET Core](https://github.com/dotnet/core)  
  
- [Runtime-piattaforma e runtime di .NET Core](https://github.com/dotnet/runtime)  
  
- [CLI - .NET Core command-line tools (CLI - Strumenti della riga di comando di .NET Core)](https://github.com/dotnet/cli)  
  
- [Roslyn - .NET Compiler Platform (Roslyn - Piattaforma del compilatore .NET)](https://github.com/dotnet/roslyn)  
  
- [ASP.NET Core](https://github.com/dotnet/aspnetcore)  
  
## <a name="see-also"></a>Vedere anche

- [Esercitazione su .NET-Hello World tra 10 minuti](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro)
- [Guida a .NET Core](../../core/index.yml)
- [Documenti ASP.NET Core](/aspnet/core/)
