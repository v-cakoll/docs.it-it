---
title: Cross-platform targeting
description: Le procedure consigliate per la creazione di librerie .NET multipiattaforma.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 72fa891d5b1054af485a98d89b4efb11d6b0018b
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374893"
---
# <a name="cross-platform-targeting"></a>Cross-platform targeting

.NET moderne supporta più sistemi operativi e dispositivi. È importante per le librerie open source .NET supportare gli sviluppatori tanti possibili, che si stia creando un sito Web ASP.NET ospitate in Azure o in un gioco di .NET in Unity.

## <a name="net-standard"></a>.NET Standard

.NET standard è il modo migliore per aggiungere il supporto multipiattaforma per una libreria .NET. [.NET standard](../net-standard.md) è una specifica di API .NET che sono disponibili in tutte le implementazioni di .NET. Scelta di .NET Standard consente di creare librerie che sono vincolate a usare le API in una determinata versione di .NET Standard, che significa che è utilizzabile da tutte le piattaforme che implementano tale versione di .NET Standard.

![.NET standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")

Destinato a .NET Standard e completata la compilazione del progetto, non garantisce che la libreria verrà eseguita correttamente in tutte le piattaforme:

1. API specifiche della piattaforma avrà esito negativo su altre piattaforme. Ad esempio, <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> verrà eseguita correttamente in Windows e generare <xref:System.PlatformNotSupportedException> quando viene usato in qualsiasi altro sistema operativo.
2. Le API possono comportarsi in modo diverso. Ad esempio, la reflection API hanno diverse caratteristiche di prestazioni quando un'applicazione usa la compilazione ahead of time in iOS e UWP.

> [!TIP]
> Il team di .NET [offre un analizzatore Roslyn](../analyzers/api-analyzer.md) che consentono di individuare i possibili problemi.

**ESEGUIRE ✔️** iniziano con incluso un `netstandard2.0` destinazione.

> Le API di fuori di .NET Standard 2.0 non necessitano di più librerie di uso generico. .NET standard 2.0 è supportato da tutte le piattaforme moderne ed è il modo consigliato per supportare più piattaforme con una sola destinazione.

**Si consiglia di evitare ❌** tra cui un `netstandard1.x` destinazione.

> .NET standard 1.x viene distribuito come un set granulare dei pacchetti NuGet, che consente di creare un grafico di dipendenze di pacchetto di grandi dimensioni e determina gli sviluppatori di download di numerosi pacchetti durante la compilazione. Piattaforme .NET moderne, tra cui .NET Framework 4.6.1, UWP e Xamarin, tutte supportano .NET Standard 2.0. Necessario solo scegliere come destinazione .NET Standard 1.x se è necessario in modo specifico come destinazione una piattaforma meno recente.

**ESEGUIRE ✔️** includono un `netstandard2.0` di destinazione se è necessario un `netstandard1.x` destinazione.

> Tutte le piattaforme che supportano .NET Standard 2.0 useranno il `netstandard2.0` di destinazione e trarre vantaggio dall'avere un grafico di pacchetto più piccolo mentre piattaforme precedenti verranno comunque funzionare e cercare di usare il `netstandard1.x` destinazione.

**NON ❌** includono una destinazione .NET Standard, se la libreria si basa su un modello di app specifici della piattaforma.

> Ad esempio, una libreria del toolkit UWP controllo dipende da un modello di app che è disponibile solo in UWP. Specifico del modello App API non saranno disponibili in .NET Standard.

## <a name="multi-targeting"></a>Multitargeting

In alcuni casi è necessario accedere alle API specifiche del framework dalle librerie. Il modo migliore per chiamare le API specifiche del framework Usa il multitargeting, che compila il progetto per molte [Framework di destinazione .NET](../frameworks.md) invece che per uno solo.

Per proteggere i tuoi utenti di dover compilare per singoli Framework, è consigliabile avere un output di .NET Standard oltre a uno o più output specifico del framework. Con il multitargeting, tutti gli assembly vengono inseriti all'interno di un singolo pacchetto NuGet. I consumer possono quindi fare riferimento il pacchetto stesso e NuGet sceglierà l'implementazione appropriata. La libreria .NET Standard serve come libreria di fallback che viene utilizzato ovunque, tranne nei casi in cui il pacchetto NuGet offre un'implementazione specifica di framework. Il multitargeting consente di utilizzare la compilazione condizionale del codice e chiamare API specifiche del framework.

![Pacchetto NuGet con più assembly](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "pacchetto NuGet con più assembly")

**Provare a ✔️** come destinazione le implementazioni di .NET oltre a .NET Standard.

> Come destinazione le implementazioni di .NET consente di chiamare API specifiche della piattaforma che sono di fuori di .NET Standard.
>
> Non eliminare il supporto per .NET Standard quando si esegue questa operazione. Al contrario, generare rispetto all'implementazione e offrono funzionalità API. In questo modo, la libreria può essere usata ovunque e supporta runtime light-up delle funzionalità.

**Si consiglia di evitare ❌** usando più destinazioni con .NET Standard se il codice sorgente è lo stesso per tutte le destinazioni.

> L'assembly .NET Standard verrà utilizzato automaticamente da NuGet. Come destinazione le implementazioni di .NET singoli aumenta la `*.nupkg` dimensioni senza alcun vantaggio.

**✔️ si consiglia** aggiunta di una destinazione `net461` quando esegue offerta un `netstandard2.0` destinazione. 

> Uso di .NET Standard 2.0 da .NET Framework presenta alcuni problemi che sono stati risolti in .NET Framework 4.7.2. È possibile migliorare l'esperienza per gli sviluppatori che sono ancora disponibili su .NET Framework 4.6.1 - 4.7.1, offrendo loro un file binario viene compilato per .NET Framework 4.6.1.

**Eseguire operazioni ✔️** distribuire tua libreria tramite un pacchetto NuGet.

> NuGet verrà selezionare la destinazione migliore per gli sviluppatori e schermare li dover scegliere l'implementazione appropriata.

**Eseguire operazioni ✔️** usare un file di progetto `TargetFrameworks` proprietà in caso di multitargeting.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <!-- This project will output netstandard2.0 and net461 assemblies -->
    <TargetFrameworks>netstandard2.0;net461</TargetFrameworks>
  </PropertyGroup>
</Project>
```

**✔️ CONSIDERARE** usando [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) quando multitargeting per UWP e Xamarin poiché semplifica notevolmente il file di progetto.

## <a name="older-targets"></a>Destinazioni precedenti

.NET supporta le versioni di destinazione di .NET Framework lunghi da supporto, nonché le piattaforme non sono più comunemente usati. Anche se ha valore eseguendo il lavoro di libreria in come destinata a numerosi possibili, che sia necessario ovviare alla mancanza di API può aggiungere significativo sovraccarico. Crediamo che determinati Framework non sono più la pena di destinazione, prendere in considerazione la portata e le limitazioni.

**NON ❌** includono una destinazione di libreria di classi portabile (PCL). Ad esempio `portable-net45+win8+wpa81+wp8`.

> .NET standard è il modo moderni per lo sviluppo multipiattaforma .NET librerie di supporto e sostituisce librerie di classi portabili.

**NON ❌** includono le destinazioni per le piattaforme .NET che non sono più supportate. Ad esempio, `SL4`, `WP`.

>[!div class="step-by-step"]
[Precedente](./get-started.md)
[Successivo](./strong-naming.md)
