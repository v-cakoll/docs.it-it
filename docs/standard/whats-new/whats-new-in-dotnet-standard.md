---
title: Novità di .NET Standard
description: Questo articolo riepiloga le nuove funzionalità e i miglioramenti disponibili in ogni nuova versione di .NET Standard.
ms.custom: updateeachrelease
ms.date: 04/12/2018
ms.technology: dotnet-standard
ms.openlocfilehash: a90df0360211c3b02f4f2d8697890180099c5807
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921064"
---
# <a name="whats-new-in-the-net-standard"></a>Novità di .NET Standard

.NET Standard è una specifica formale che definisce un set di API con versioni specifiche che devono essere disponibili nelle implementazioni .NET conformi a tale versione dello standard. .NET Standard è destinato agli sviluppatori di librerie. Una libreria che ha come destinazione una versione di .NET Standard è utilizzabile in qualsiasi implementazione di .NET Framework, .NET Core o Xamarin che supporta tale versione dello standard.

La versione più recente di .NET Standard è la versione 2.0. È incluso in .NET Core 2,0 SDK, nonché con Visual Studio 2017 versione 15,3 con il carico di lavoro di .NET Core installato.

## <a name="supported-net-implementations"></a>Implementazioni di .NET supportate

.NET Standard 2.0 è supportato dalle implementazioni .NET seguenti:

- .NET Core 2.0 o versioni successive
- .NET Framework 4.6.1 o versioni successive
- Mono 5.4 o versioni successive
- Xamarin.iOS 10.14 o versioni successive
- Xamarin.Mac 3.8 o versioni successive
- Xamarin.Android 8.0 o versioni successive
- Piattaforma UWP (Universal Windows Platform) 10.0.16299 o versioni successive

## <a name="whats-new-in-the-net-standard-20"></a>Novità di .NET Standard 2.0

.NET Standard 2.0 include le nuove funzionalità seguenti:

### <a name="a-vastly-expanded-set-of-apis"></a>Un set di API notevolmente ampliato

Nella versione 1.6 .NET Standard includeva un subset relativamente ridotto di API. Molte API escluse erano tra quelle comunemente usate in .NET Framework o Xamarin. Ciò rende lo sviluppo più complesso, poiché gli sviluppatori devono trovare sostituzioni appropriate per le API a loro ben note durante lo sviluppo di applicazioni e librerie destinate a più implementazioni .NET. .NET 2.0 Standard risolve questa limitazione rendendo disponibili più di 20.000 API rispetto a quelle disponibili in .NET Standard 1.6, la versione precedente. Per un elenco delle API aggiunte a .NET Standard 2.0, vedere [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md) (Confronto tra le versioni 2.0 e 1.6 di .NET Standard)

Ecco alcune delle funzionalità aggiunte allo spazio dei nomi <xref:System> in .NET 2.0 Standard:

- Supporto della classe <xref:System.AppDomain>.
- Supporto più efficiente dell'uso delle matrici da altri membri della classe <xref:System.Array>.
- Supporto più efficiente per l'uso degli attributi da altri membri della classe <xref:System.Attribute>.
- Supporto più efficiente del calendario e opzioni di formattazione aggiuntive per i valori <xref:System.DateTime>.
- Funzionalità di arrotondamento <xref:System.Decimal> aggiuntiva.
- Funzionalità aggiuntive nella classe <xref:System.Environment>.
- Miglioramento del controllo sul Garbage Collector tramite la classe <xref:System.GC>.
- Supporto più efficiente del confronto tra stringhe, dell'enumerazione e della normalizzazione nella classe <xref:System.String>.
- Supporto della rettifica relativa all'ora legale e dei tempi di transizione nelle classi <xref:System.TimeZoneInfo.AdjustmentRule> e <xref:System.TimeZoneInfo.TransitionTime>.
- Sensibile miglioramento delle funzionalità nella classe <xref:System.Type>.
- Supporto più efficiente della deserializzazione degli oggetti eccezione tramite l'aggiunta di un costruttore di eccezioni con parametri <xref:System.Runtime.Serialization.SerializationInfo> e <xref:System.Runtime.Serialization.StreamingContext>.

### <a name="support-for-net-framework-libraries"></a>Supporto delle librerie di .NET Framework

La stragrande maggioranza delle librerie è destinata a .NET Framework anziché a .NET Standard. La maggior parte delle chiamate in tali librerie, tuttavia, riguardano API incluse in .NET Standard 2.0. A partire da .NET Standard 2.0, è possibile accedere alle librerie .NET Framework da una libreria .NET Standard tramite uno [shim di compatibilità](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification). Questo livello di compatibilità è trasparente per gli sviluppatori. Non è necessario eseguire alcuna operazione per sfruttare i vantaggi delle librerie .NET Framework.

L'unico requisito è che le API chiamate dalla libreria di classi di .NET Framework siano incluse in .NET Standard 2.0.

### <a name="support-for-visual-basic"></a>Supporto per Visual Basic

È ora possibile sviluppare librerie .NET Standard in Visual Basic. Per Visual Basic sviluppatori che usano Visual Studio 2017 versione 15,3 o successiva con il carico di lavoro di .NET Core installato, Visual Studio ora include un modello di libreria di classi .NET Standard. Per gli sviluppatori Visual Basic che usano altri strumenti e ambienti di sviluppo, è possibile usare il comando [dotnet new](../../core/tools/dotnet-new.md) per creare un progetto di libreria .NET Standard. Per altre informazioni, vedere [Supporto degli strumenti per librerie .NET Standard](#tooling-support-for-net-standard-libraries).

### <a name="tooling-support-for-net-standard-libraries"></a>Supporto degli strumenti per librerie .NET Standard

Con il rilascio di .NET Core 2,0 e .NET Standard 2,0, sia Visual Studio 2017 che i [interfaccia della riga di comando di .NET Core](../../core/tools/index.md) includono il supporto degli strumenti per la creazione di librerie di .NET standard.

Se si installa Visual Studio con il carico di lavoro **Sviluppo multipiattaforma .NET Core**, è possibile creare un progetto di libreria .NET Standard 2.0 usando un modello di progetto, come illustrato nella figura seguente:

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[C#](#tab/csharp)

![Aggiungere un nuovo progetto di libreria .NET Standard](./media/std-project-cs.png)

Se si usa l'interfaccia della riga di comando di .NET Core, il comando [dotnet new](../../core/tools/dotnet-new.md) seguente crea un progetto di libreria di classi destinato a .NET Standard 2.0:

```dotnetcli
dotnet new classlib
```

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)

![Aggiungere un nuovo progetto di libreria .NET Standard](./media/std-project-vb.png)

Se si usa l'interfaccia della riga di comando di .NET Core, il comando [dotnet new](../../core/tools/dotnet-new.md) seguente crea un progetto di libreria di classi destinato a .NET Standard 2.0:

```dotnetcli
dotnet new classlib -lang vb
```

---

## <a name="see-also"></a>Vedere anche

- [.NET Standard](../net-standard.md)
- [Introducing .NET Standard](https://devblogs.microsoft.com/dotnet/introducing-net-standard/) (Introduzione a .NET Standard)
