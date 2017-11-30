---
title: "Novità di .NET Standard"
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
ms.##devlang: dotnet
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e938c009b79af3b2f36094bbb74f4d38baeeac0b
ms.sourcegitcommit: 281070dee88db86ec3bb4634d5f558d1a4e159dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2017
---
# <a name="whats-new-in-the-net-standard"></a>Novità di .NET Standard

.NET Standard è una specifica formale che definisce un set di API che devono essere disponibile nelle implementazioni .NET conformi con tale versione dello standard con controllo delle versioni. .NET Standard è destinato agli sviluppatori di librerie. Una libreria che ha come destinazione una versione .NET Standard è utilizzabile in qualsiasi implementazione di .NET Framework, .NET Core o Xamarin che supporta tale versione dello standard.

La versione più recente di .NET Standard è 2.0. È inclusa con il SDK 2.0 di .NET Core e con versione 15.3 2017 di Visual Studio con il carico di lavoro di .NET Core installato.

## <a name="supported-net-implementations"></a>Implementazioni di .NET supportate

Standard di .NET 2.0 è supportata tramite le implementazioni .NET seguenti:

- .NET core 2.0
- .NET Framework 4.6.1
- Mono 5.4
- Xamarin 10.14
- 3.8 Xamarin.Mac
- Xamarin 8.0
- Piattaforma Windows universale 10.0.16299

## <a name="whats-new-in-the-net-standard-20"></a>Novità di .NET 2.0 Standard
 
Standard di .NET 2.0 include le nuove funzionalità seguenti:

**Un vasto set di API**

Alla versione 1.6, .NET Standard incluso un subset relativamente ridotto di API. Tra quelli esclusi sono state molte API comunemente usati in .NET Framework o Xamarin. Ciò complica lo sviluppo, poiché richiede che gli sviluppatori troveranno sostituzioni appropriate per le API familiarità durante lo sviluppo di applicazioni e librerie destinate a più implementazioni di .NET. .NET 2.0 Standard risolve questa limitazione aggiungendo le API più oltre 20.000 che erano disponibili in .NET Standard 1.6, la versione precedente dello standard. Per un elenco delle API che sono stati aggiunti a Standard di .NET 2.0, vedere [Visual Studio .NET 2.0 Standard 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md). 

Alcune delle aggiunte di <xref:System> dello spazio dei nomi .NET 2.0 Standard includono:

- Supporto per la <xref:System.AppDomain> classe.
- Supporto migliorato per l'utilizzo di matrici da altri membri di <xref:System.Array> classe.
- Supporto migliorato per lavorare con gli attributi da altri membri di <xref:System.Attribute> classe.
- Calendario migliore supporto e le opzioni di formattazione aggiuntive per <xref:System.DateTime> valori.
- Ulteriori <xref:System.Decimal> arrotondamento funzionalità.
- Funzionalità aggiuntive di <xref:System.Environment> classe.
- Il controllo tramite il garbage collector tramite avanzato di <xref:System.GC> classe.
- Supporto migliorato per confronto tra stringhe, enumerazione e la normalizzazione nel <xref:System.String> classe.
- Supporto per legale rettifiche e tempi di transizione nel <xref:System.TimeZoneInfo.AdjustmentRule> e <xref:System.TimeZoneInfo.TransitionTime> classi.
- Sensibilmente migliorata e ora funzionalità di <xref:System.Type> classe.
- Supporto migliorato per la deserializzazione di oggetti eccezione mediante l'aggiunta di un costruttore di eccezione con <xref:System.Runtime.Serialization.SerializationInfo> e <xref:System.Runtime.Serialization.StreamingContext> parametri.

**Supporto per le librerie .NET Framework**

La maggior parte delle librerie di destinazione di .NET Framework anziché .NET Standard. Tuttavia, la maggior parte delle chiamate in tali raccolte sono alle API incluse in .NET 2.0 Standard. A partire da .NET 2.0 Standard, è possibile accedere alle librerie .NET Framework da una libreria .NET Standard con un [shim di compatibilità](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification). Questo livello di compatibilità è trasparente per gli sviluppatori; non è necessario eseguire alcuna operazione per sfruttare i vantaggi delle librerie .NET Framework.

L'unico requisito è che le API chiamate dalla libreria di classi .NET Framework devono essere incluso in .NET 2.0 Standard.

**Supporto per Visual Basic**

È ora possibile sviluppare le librerie Standard di .NET in Visual Basic. Per gli sviluppatori di Visual Basic in Visual Studio 2017 versione 15.3 o versioni successive con il carico di lavoro di .NET Core installata, Visual Studio ora include un modello di libreria di classi .NET Standard. Per gli sviluppatori di Visual Basic che utilizzano altri strumenti di sviluppo e gli ambienti, è possibile utilizzare il [dotnet nuovo](../../core/tools/dotnet-new.md) comando per creare un progetto di libreria Standard di .NET. Per ulteriori informazioni, vedere il [gli strumenti di supporto per le librerie .NET Standard](#tooling).

<a name="tooling" />**Strumenti di supporto per le librerie .NET Standard**

Con la versione di .NET Core 2.0 e .NET 2.0 Standard, entrambi 2017 Studio Visual e [.NET Core interfaccia della riga di comando (CLI)](../../core/tools/index.md) includono gli strumenti di supporto per la creazione di librerie .NET Standard. 

Se si installa Visual Studio con il **lo sviluppo multipiattaforma con .NET Core** carico di lavoro, è possibile creare un progetto di libreria .NET 2.0 Standard utilizzando un modello di progetto, come illustrato nella figura seguente. 

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
![Aggiungere il progetto di libreria Standard di nuovo .NET](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![Aggiungere il progetto di libreria Standard di nuovo .NET](./media/std-project-vb.png)
---

Se si utilizza l'interfaccia CLI Core .NET, le operazioni seguenti [dotnet nuovo](../../core/tools/dotnet-new.md) comando crea un progetto libreria di classi destinate a .NET 2.0 Standard.

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a>Vedere anche
[.NET standard](../net-standard.md)
[Introduzione a .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)
