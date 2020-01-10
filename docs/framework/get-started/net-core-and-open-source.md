---
title: .NET Core e open source
ms.date: 03/30/2017
ms.assetid: e6bd4655-ce37-4003-8462-468a6fe2c40f
ms.openlocfilehash: 4032ba771d917d25473c8de350cc752bd052f94d
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75752552"
---
# <a name="net-core-and-open-source"></a>.NET Core e open source

Questo articolo fornisce una breve panoramica di .NET Core e Mostra come è possibile trovare altre informazioni. Per trovare l'elenco completo della documentazione per .NET Core, vedere la [Guida di .NET Core](../../core/index.md).
  
<a name="BKMK_WhatisNETCore"></a>   
## <a name="what-is-net-core"></a>Informazioni su .NET Core  
 .NET Core è un'implementazione generica, modulare, multi-piattaforma e open source dello standard .NET. Contiene molte delle stesse API di .NET Framework (ma .NET Core è un set più piccolo) e include componenti runtime, framework, compilatore e strumenti che supportano un'ampia gamma di sistemi operativi e chip di destinazione. L'implementazione di .NET Core nasce dall'esigenza di gestire i carichi di lavoro di ASP.NET Core, ma anche dalla necessità di un'implementazione più moderna. Può essere usata in scenari di dispositivi, cloud e IoT/incorporati.  
  
 Per iniziare a usare .NET Core, vedere l'esercitazione su .NET [Hello World in 10 minuti](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro).  
  
Di seguito sono riportate le caratteristiche principali di .NET Core:
  
- **Multi-piattaforma:** NET Core offre gli strumenti essenziali per implementare le funzioni dell'app necessarie e riusare il codice indipendentemente dalla piattaforma di destinazione. Supporta attualmente tre sistemi operativi principali: Windows, Linux e macOS. È possibile scrivere app e librerie in modo che vengano eseguite senza modifiche nei sistemi operativi supportati. Per visualizzare l'elenco dei sistemi operativi supportati, vedere [.NET Core roadmap](https://github.com/dotnet/core/blob/master/roadmap.md) (Roadmap di .NET Core).
  
- **Open source:** .NET Core è uno dei molti progetti sotto il controllo di [.NET Foundation](https://www.dotnetfoundation.org/) ed è disponibile in [GitHub](https://github.com/).  La disponibilità di .NET Core come progetto open source favorisce un processo di sviluppo più trasparente e promuove una community più attiva e impegnata.  
  
- **Distribuzione flessibile:** esistono principalmente due modi per distribuire l'app, ovvero la distribuzione dipendente dal framework e la distribuzione autonoma. Con la distribuzione dipendente dal framework vengono installate solo l'app e le dipendenze di terze parti e l'app richiede che sia presente una versione a livello di sistema di .NET Core.  Con la distribuzione completa, insieme all'app e alle dipendenze di terze parti viene distribuita anche la versione di .NET Core usata per compilare l'applicazione. Questa distribuzione può essere eseguita side-by-side con altre versioni.    Per altre informazioni, vedere [Distribuzione di applicazioni .NET Core](../../core/deploying/index.md).

- **Modulare:** .NET Core è modulare perché viene rilasciato tramite NuGet in pacchetti di assembly di dimensioni ridotte. Invece di un unico assembly grande contenente la maggior parte delle funzionalità di base, .NET Core è disponibile sotto forma di pacchetti più piccoli incentrati sulle funzionalità. Questa struttura consente un modello di sviluppo più agile e offre agli utenti l'opportunità di ottimizzare le app includendo solo i pacchetti NuGet effettivamente necessari. Una riduzione della superficie occupata dall'app offre anche diversi vantaggi, tra cui una maggiore sicurezza, una riduzione delle esigenze di assistenza, un miglioramento delle prestazioni e una diminuzione dei costi in un modello di pagamento basato sul consumo effettivo.  
  
## <a name="the-net-core-platform"></a>Piattaforma .NET Core
  
La piattaforma .NET Core è costituita da diversi componenti, tra cui i compilatori gestiti, il runtime, le librerie di classi base e numerosi modelli di applicazione, ad esempio ASP.NET Core. Per altre informazioni sui diversi componenti, vedere i repository [GitHub](https://github.com/) seguenti:  
  
- [Home page di .NET Core](https://github.com/dotnet/core)  
  
- [Runtime-piattaforma e runtime di .NET Core](https://github.com/dotnet/runtime)  
  
- [CLI - .NET Core command-line tools](https://github.com/dotnet/cli) (CLI - Strumenti della riga di comando di .NET Core)  
  
- [Roslyn - .NET Compiler Platform](https://github.com/dotnet/roslyn) (Roslyn - Piattaforma del compilatore .NET)  
  
- [ASP.NET Core](https://github.com/dotnet/aspnetcore)  
  
## <a name="see-also"></a>Vedere anche

- [Esercitazione su .NET-Hello World tra 10 minuti](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro)
- [Guida a .NET Core](../../core/index.md)
- [Documenti ASP.NET Core](/aspnet/core/)
