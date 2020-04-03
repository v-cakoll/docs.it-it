---
title: Componenti di base e open-source di .NET
ms.date: 03/30/2017
ms.assetid: e6bd4655-ce37-4003-8462-468a6fe2c40f
ms.openlocfilehash: bed5bb6aad5f3e651f7c4c0651a2365f17eb8a0b
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635298"
---
# <a name="net-core-and-open-source"></a>.NET Core e open source

Questo articolo fornisce una breve panoramica di .NET Core e viene illustrato come trovare ulteriori informazioni. Per trovare l'elenco completo della documentazione relativa a .NET Core, visitare la [guida .NET Core](../../core/index.yml).

## <a name="what-is-net-core"></a>Informazioni su .NET Core  

.NET Core è un'implementazione di .NET Core per scopi generali, modulari, multipiattaforma e open source. Contiene molte delle stesse API di .NET Framework (ma .NET Core è un set più piccolo) e include componenti di runtime, framework, compilatore e strumenti che supportano un'ampia gamma di sistemi operativi e destinazioni di chip. L'implementazione di .NET Core nasce dall'esigenza di gestire i carichi di lavoro di ASP.NET Core, ma anche dalla necessità di un'implementazione più moderna. Può essere usato in scenari di dispositivi, cloud e embedded/IoT.  
  
Per iniziare a utilizzare .NET Core, visitare l'esercitazione di .NET [Hello World in 10 minuti.](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro)  
  
Le caratteristiche principali di .NET Core sono:
  
- **Multi-piattaforma:** NET Core offre gli strumenti essenziali per implementare le funzioni dell'app necessarie e riusare il codice indipendentemente dalla piattaforma di destinazione. Attualmente supporta tre sistemi operativi principali: Windows, Linux e macOS. È possibile scrivere app e librerie in modo che vengano eseguite senza modifiche nei sistemi operativi supportati. Per visualizzare l'elenco dei sistemi operativi supportati, vedere [.NET Core roadmap](https://github.com/dotnet/core/blob/master/roadmap.md) (Roadmap di .NET Core).
  
- **Open source:** .NET Core è uno dei molti progetti sotto il controllo di [.NET Foundation](https://www.dotnetfoundation.org/) ed è disponibile in [GitHub](https://github.com/).  La disponibilità di .NET Core come progetto open source favorisce un processo di sviluppo più trasparente e promuove una community più attiva e impegnata.  
  
- **Distribuzione flessibile:** esistono principalmente due modi per distribuire l'app, ovvero la distribuzione dipendente dal framework e la distribuzione autonoma. Con la distribuzione dipendente dal framework vengono installate solo l'app e le dipendenze di terze parti e l'app richiede che sia presente una versione a livello di sistema di .NET Core. Con la distribuzione completa, insieme all'app e alle dipendenze di terze parti viene distribuita anche la versione di .NET Core usata per compilare l'applicazione. Questa distribuzione può essere eseguita side-by-side con altre versioni. Per ulteriori informazioni, vedere [Distribuzione di applicazioni .NET Core](../../core/deploying/index.md).

- **Modulare:** .NET Core è modulare perché viene rilasciato tramite NuGet in pacchetti di assembly di dimensioni ridotte. Anziché un assembly di grandi dimensioni che contiene la maggior parte delle funzionalità di base, .NET Core viene reso disponibile come pacchetti più piccoli e incentrati sulle funzionalità. Questa modularità consente un modello di sviluppo più agile per noi e consente di ottimizzare l'app per includere solo i pacchetti NuGet necessari. Una riduzione della superficie occupata dall'app offre anche diversi vantaggi, tra cui una maggiore sicurezza, una riduzione delle esigenze di assistenza, un miglioramento delle prestazioni e una diminuzione dei costi in un modello di pagamento basato sul consumo effettivo.  
  
## <a name="the-net-core-platform"></a>La piattaforma .NET Core
  
The .NET Core platform is made up of several components, including the managed compilers, the runtime, the base class libraries, and numerous application models, such as ASP.NET Core. È possibile ottenere ulteriori informazioni sui diversi componenti e impegnarsi visitando i seguenti repository [GitHub:](https://github.com/)  
  
- [Casa .NET Core](https://github.com/dotnet/core)  
  
- [Runtime - Piattaforma e runtime .NET Core](https://github.com/dotnet/runtime)  
  
- [CLI - .NET Core command-line tools (CLI - Strumenti della riga di comando di .NET Core)](https://github.com/dotnet/cli)  
  
- [Roslyn - .NET Compiler Platform (Roslyn - Piattaforma del compilatore .NET)](https://github.com/dotnet/roslyn)  
  
- [ASP.NET Core](https://github.com/dotnet/aspnetcore)  
  
## <a name="see-also"></a>Vedere anche

- [Esercitazione su .NET - Hello World in 10 minuti](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro)
- [Guida a .NET Core](../../core/index.yml)
- [Documenti di ASP.NET Core](/aspnet/core/)
