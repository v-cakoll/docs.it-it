---
title: Specifica di destinazioni multipiattaforma per librerie .NET
description: Procedure consigliate per la creazione di librerie .NET multipiattaforma.
ms.date: 08/12/2019
ms.openlocfilehash: 61adff3759984554bb83531b4f9d8a49e29c929c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "76731453"
---
# <a name="cross-platform-targeting"></a>Specifica di destinazioni multipiattaforma

Il software .NET moderno supporta più sistemi operativi e dispositivi. È importante che le librerie open source .NET offrano supporto per il maggior numero possibile di sviluppatori, che stiano creando un sito Web ASP.NET ospitato in Azure o un gioco .NET in Unity.

## <a name="net-standard"></a>.NET Standard

L'uso di .NET Standard è il modo migliore per aggiungere il supporto multipiattaforma a una libreria .NET. [.NET Standard](../net-standard.md) è una specifica delle API .NET disponibili in tutte le implementazioni .NET. Scegliendo come destinazione .NET Standard è possibile creare librerie vincolate all'uso delle API di una determinata versione di .NET Standard, che possono quindi essere usate da tutte le piattaforme che implementano tale versione di .NET Standard.

![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")

La scelta di .NET Standard come destinazione e la corretta compilazione del progetto non garantiscono che la libreria verrà eseguita correttamente in tutte le piattaforme:

1. Le API specifiche della piattaforma avranno esito negativo nelle altre piattaforme. Ad esempio, l'esecuzione di <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> avverrà correttamente in Windows e genererà un'eccezione <xref:System.PlatformNotSupportedException> in qualsiasi altro sistema operativo.
2. Le API possono avere comportamenti diversi. Ad esempio, le API reflection hanno caratteristiche di prestazioni diverse quando un'applicazione usa la compilazione Ahead Of Time in iOS o nella piattaforma UWP.

> [!TIP]
> Il team di .NET [offre un analizzatore Roslyn](../analyzers/api-analyzer.md) che consente di individuare i possibili problemi.

✔️ INIZIARE includendo una destinazione `netstandard2.0`.

> La maggior parte delle librerie per utilizzo generico non necessita di API al di fuori di .NET Standard 2.0. .NET standard 2.0 è supportato da tutte le piattaforme moderne ed è il modo consigliato per supportare più piattaforme con una sola destinazione.

❌AVOID che `netstandard1.x` include un bersaglio.

> .NET standard 1.x è distribuito come set granulare di pacchetti NuGet, che crea un grafo delle dipendenze dei pacchetti di grandi dimensioni e obbliga gli sviluppatori a scaricare numerosi pacchetti durante la compilazione. Le moderne piattaforme .NET, tra cui .NET Framework 4.6.1, la piattaforma UWP e Xamarin, supportano tutte .NET Standard 2.0. Scegliere come destinazione .NET Standard 1.x solo se è necessaria una piattaforma di destinazione meno recente.

✔️ INCLUDERE una destinazione `netstandard2.0` se è necessaria una destinazione `netstandard1.x`.

> Tutte le piattaforme che supportano .NET Standard 2.0 useranno la destinazione `netstandard2.0` con il vantaggio di avere un grafo dei pacchetti più piccolo, mentre le piattaforme precedenti continueranno a funzionare ed eseguiranno il fallback alla destinazione `netstandard1.x`.

❌NON includere una destinazione .NET Standard se la libreria si basa su un modello di app specifico della piattaforma.

> Una libreria di toolkit di controlli della piattaforma UWP, ad esempio, dipende da un modello di app che è disponibile solo nella piattaforma UWP. Le API specifiche del modello di app non saranno disponibili in .NET Standard.

## <a name="multi-targeting"></a>Multitargeting

In alcuni casi è necessario accedere alle API specifiche del framework dalle librerie. Il modo migliore per chiamare le API specifiche del framework consiste nell'usare il multitargeting, che compila il progetto per numerosi [framework di destinazione .NET](../frameworks.md) invece che per uno solo.

Per evitare ai consumer di dover eseguire la compilazione per i singoli framework, è consigliabile cercare di avere un output .NET Standard e uno o più output specifici del framework. Con il multitargeting, tutti gli assembly vengono inseriti all'interno di un singolo pacchetto NuGet. I consumer possono quindi fare riferimento allo stesso pacchetto NuGet e scegliere l'implementazione appropriata. La libreria .NET Standard serve come libreria di fallback usata in tutti i casi ad eccezione di quelli in cui il pacchetto NuGet offre un'implementazione specifica del framework. Il multitargeting consente di usare la compilazione condizionale nel codice e chiamare API specifiche del framework.

![Pacchetto NuGet con più assemblyNuGet package with multiple assemblies](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "Pacchetto NuGet con più assemblyNuGet package with multiple assemblies")

✔️ Valutare la scelta delle implementazioni .NET come destinazione in aggiunta a .NET Standard.

> La scelta delle implementazioni .NET come destinazione consente di chiamare API specifiche della piattaforma al di fuori di .NET Standard.
>
> Quando si esegue questa operazione, non eliminare il supporto per .NET Standard. Eseguire invece la generazione dall'implementazione e offrire API per le funzionalità. In questo modo, la libreria può essere usata ovunque e supporta l'abilitazione delle funzionalità in fase di esecuzione.

```csharp
public static class GpsLocation
{
    // This project uses multi-targeting to expose device-specific APIs to .NET Standard.
    public static async Task<(double latitude, double longitude)> GetCoordinatesAsync()
    {
#if NET461
        return CallDotNetFramworkApi();
#elif WINDOWS_UWP
        return CallUwpApi();
#else
        throw new PlatformNotSupportedException();
#endif
    }

    // Allows callers to check without having to catch PlatformNotSupportedException
    // or replicating the OS check.
    public static bool IsSupported
    {
        get
        {
#if NET461 || WINDOWS_UWP
            return true;
#else
            return false;
#endif
        }
    }
}
```

❌AVOID multi-targeting e targeting .NET Standard, se il codice sorgente è lo stesso per tutte le destinazioni.

> L'assembly .NET Standard verrà usato automaticamente da NuGet. La scelta come destinazione di singole implementazioni .NET comporta un aumento delle dimensioni di `*.nupkg` senza offrire alcun vantaggio.

✔️ VALUTARE l'aggiunta di una destinazione per `net461` quando si offre una destinazione `netstandard2.0`.

> L'uso di .NET Standard 2.0 da .NET Framework presenta alcuni problemi che sono stati risolti in .NET Framework 4.7.2. È possibile migliorare l'esperienza per gli sviluppatori che usano ancora .NET Framework 4.6.1-4.7.1 offrendo loro un file binario compilato per .NET Framework 4.6.1.

✔️ DA FARE Distribuire la libreria usando un pacchetto NuGet.

> NuGet selezionerà la destinazione migliore per lo sviluppatore evitandogli di dover scegliere l'implementazione appropriata.

✔️ USARE la proprietà `TargetFrameworks` di un file di progetto quando si usa il multitargeting.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <!-- This project will output netstandard2.0 and net461 assemblies -->
    <TargetFrameworks>netstandard2.0;net461</TargetFrameworks>
  </PropertyGroup>
</Project>
```

✔️ VALUTARE l'uso di [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) con il multitargeting per la piattaforma UWP e Xamarin in quanto semplifica notevolmente il file di progetto.

## <a name="older-targets"></a>Destinazioni precedenti

.NET consente di scegliere come destinazione versioni di .NET Framework per le quali non è più disponibile il supporto e piattaforme non più comunemente usate. In questo modo, la libreria funzionerà con il maggior numero di destinazioni possibili, tuttavia sarà necessario lavoro aggiuntivo per trovare una soluzione alternativa per le API mancanti. Considerando la copertura e le limitazioni, non vale più la pena scegliere come destinazione determinati framework.

❌NON includere una destinazione libreria di classi portabile (PCL). Ad esempio: `portable-net45+win8+wpa81+wp8`.

> .NET standard è il modo moderno per supportare le librerie .NET multipiattaforma e sostituisce le librerie di classi portabili.

❌DO NOT includere destinazioni per le piattaforme .NET che non sono più supportate. Ad esempio, `SL4`, `WP`.

>[!div class="step-by-step"]
>[Successivo](get-started.md)
>[precedente](strong-naming.md)
