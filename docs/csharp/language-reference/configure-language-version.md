---
title: Controllo delle versioni del linguaggio C# - Guida a C#
description: Informazioni sul modo in C# cui la versione della lingua viene determinata in base al progetto e ai motivi alla base di tale scelta. Informazioni su come eseguire manualmente l'override del valore predefinito.
ms.date: 02/21/2020
ms.openlocfilehash: 2be76fdac471a7175b661d896b0da2910b3609f3
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626764"
---
# <a name="c-language-versioning"></a>Controllo delle versioni del linguaggio C#

Il compilatore C# più recente determina la versione di un linguaggio predefinito in base ai framework di destinazione del progetto. Visual Studio non fornisce un'interfaccia utente per modificare il valore, ma è possibile modificarlo modificando il file *csproj* . La scelta del valore predefinito consente di usare la versione più recente del linguaggio compatibile con il Framework di destinazione. È possibile trarre vantaggio dall'accesso alle funzionalità più recenti del linguaggio compatibili con la destinazione del progetto. Questa scelta predefinita garantisce anche di non usare un linguaggio che richiede tipi o comportamenti di runtime non disponibili nel Framework di destinazione. La scelta di una versione della lingua più recente di quella predefinita può causare difficoltà nella diagnosi degli errori di runtime e della fase di compilazione.

C#8,0 (e versioni successive) è supportato solo in .NET Core 3. x e versioni successive. Molte delle funzionalità più recenti richiedono la libreria e le funzionalità di runtime introdotte in .NET Core 3. x:

- L'implementazione del membro di interfaccia predefinito richiede nuove funzionalità in CLR di .NET Core 3,0.
- I flussi asincroni richiedono i nuovi tipi <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>e <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.
- Per gli indici e gli intervalli sono necessari i nuovi tipi <xref:System.Index?displayProperty=nameWithType> e <xref:System.Range?displayProperty=nameWithType>.
- I tipi di riferimento Nullable fanno uso di diversi [attributi](../nullable-attributes.md) per fornire avvisi migliori. Questi attributi sono stati aggiunti in .NET Core 3,0. Altri Framework di destinazione non sono stati annotati con nessuno di questi attributi. Questo significa che gli avvisi Nullable potrebbero non riflettere accuratamente i potenziali problemi.

## <a name="defaults"></a>Impostazioni predefinite

Il compilatore determina un'impostazione predefinita in base a queste regole:

|Framework di destinazione|version|Impostazione predefinita della versione del linguaggio C#|
|----------------|-------|---------------------------|
|.NET Core|3.x|C# 8.0|
|.NET Core|2.x|C# 7.3|
|.NET Standard|2.1|C# 8.0|
|.NET Standard|2.0|C# 7.3|
|.NET Standard|1.x|C# 7.3|
|.NET Framework|all|C# 7.3|

Quando il progetto ha come destinazione un framework in anteprima con una versione del linguaggio in anteprima corrispondente, la versione del linguaggio usata è la versione del linguaggio in anteprima. Si usano le funzionalità più recenti con questa anteprima in qualsiasi ambiente, senza influire sui progetti destinati a una versione di .NET Core rilasciata.

## <a name="override-a-default"></a>Sostituire un valore predefinito

Se è necessario specificare in modo esplicito la versione di C#, è possibile farlo in diversi modi:

- Modificare manualmente il [file di progetto](#edit-the-project-file).
- Impostare la versione del linguaggio [per più progetti in una sottodirectory](#configure-multiple-projects).
- Configurare l'[opzione del compilatore `-langversion`](compiler-options/langversion-compiler-option.md).

### <a name="edit-the-project-file"></a>Modificare il file di progetto

È possibile impostare la versione del linguaggio nel file di progetto. Ad esempio, se si vuole accedere esplicitamente alle funzionalità di anteprima, aggiungere un elemento simile a questo:

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

Il valore `preview` usa la versione del linguaggio C# in anteprima disponibile più recente supportata dal compilatore.

### <a name="configure-multiple-projects"></a>Configurare più progetti

Per configurare più progetti, è possibile creare un file **Directory. Build. props** che contiene l'elemento `<LangVersion>`. Questa operazione viene in genere eseguita nella directory della soluzione. Aggiungere il codice seguente a un file **Directory.Build.props** nella directory della soluzione:

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

Compilazioni in tutte le sottodirectory della directory che contiene il file utilizzerà C# la versione di anteprima. Per altre informazioni, vedere l'articolo [Personalizzare la compilazione](/visualstudio/msbuild/customize-your-build).

## <a name="c-language-version-reference"></a>Informazioni di riferimento sulle versioni del linguaggio C#

La tabella seguente illustra tutte le versioni del linguaggio C# correnti. Il compilatore potrebbe non comprendere necessariamente ogni valore se è meno recente. Se si installa .NET Core 3,0 o versione successiva, è possibile accedere a tutti gli elementi elencati.

|Valore|Significato|
|------------|-------------|
|preview|Il compilatore accetta tutte le sintassi di linguaggio valide dalla versione di anteprima più recente.|
|più recenti|Il compilatore accetta la sintassi dalla versione rilasciata più recente del compilatore (inclusa la versione secondaria).|
|latestMajor|Il compilatore accetta la sintassi dalla versione principale più recente rilasciata del compilatore.|
|8.0|Il compilatore accetta solo la sintassi inclusa in C# 8.0 o versione precedente.|
|7.3|Il compilatore accetta solo la sintassi inclusa in C# 7.3 o versione precedente.|
|7.2|Il compilatore accetta solo la sintassi inclusa in C# 7.2 o versione precedente.|
|7.1|Il compilatore accetta solo la sintassi inclusa in C# 7.1 o versione precedente.|
|7|Il compilatore accetta solo la sintassi inclusa in C# 7.0 o versione precedente.|
|6|Il compilatore accetta solo la sintassi inclusa in C# 6.0 o versione precedente.|
|5|Il compilatore accetta solo la sintassi inclusa in C# 5.0 o versione precedente.|
|4|Il compilatore accetta solo la sintassi inclusa in C# 4.0 o versione precedente.|
|3|Il compilatore accetta solo la sintassi inclusa in C# 3.0 o versione precedente.|
|ISO-2|Il compilatore accetta solo la sintassi inclusa in ISO/IEC 23270:2006 C# (2,0). |
|ISO-1|Il compilatore accetta solo la sintassi inclusa in ISO/IEC 23270:2003 C# (1.0/1.2). |
