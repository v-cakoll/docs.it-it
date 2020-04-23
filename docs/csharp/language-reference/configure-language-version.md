---
title: Controllo delle versioni del linguaggio C# - Guida a C#
description: Informazioni su come viene determinata la versione del linguaggio C'è determinato in base al progetto e i motivi alla base di tale scelta. Scopri come sostituire manualmente l'impostazione predefinita.
ms.date: 02/21/2020
ms.openlocfilehash: 850c4a860878593d80aaa3b7b38efaff9e003f43
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102658"
---
# <a name="c-language-versioning"></a>Controllo delle versioni del linguaggio C#

Il compilatore C# più recente determina la versione di un linguaggio predefinito in base ai framework di destinazione del progetto. Visual Studio non fornisce un'interfaccia utente per modificare il valore, ma è possibile modificarlo modificando il file *csproj.* La scelta di default assicura di utilizzare la versione della lingua più recente compatibile con il framework di destinazione. Approfittadellete dell'accesso alle più recenti funzionalità linguistiche compatibili con il target del progetto. Questa scelta predefinita garantisce inoltre di non usare un linguaggio che richiede tipi o comportamenti di runtime non disponibili nel framework di destinazione. La scelta di una versione della lingua più recente dell'impostazione predefinita può causare la diagnosi di errori di runtime e in fase di compilazione.

Le regole in questo articolo si applicano al compilatore fornito con Visual Studio 2019 o .NET Core 3.0 SDK. I compilatori C# che fanno parte dell'installazione di Visual Studio 2017 o di versioni precedenti di .NET Core SDK usano C# 7.0 come destinazione per impostazione predefinita.

La versione 8.0 (e successive) di Cè è supportata solo in .NET Core 3.x e versioni più recenti. Molte delle funzionalità più recenti richiedono funzionalità di libreria e runtime introdotte in .NET Core 3.x:

- L'implementazione predefinita dei membri di interfaccia richiede nuove funzionalità in .NET Core 3.0 CLR.
- I flussi asincroni <xref:System.IAsyncDisposable?displayProperty=nameWithType> <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>richiedono <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>i nuovi tipi , e .
- Gli indici e gli intervalli richiedono i nuovi tipi <xref:System.Index?displayProperty=nameWithType> e <xref:System.Range?displayProperty=nameWithType>.
- I tipi di riferimento nullable utilizzano diversi [attributi](attributes/nullable-analysis.md) per fornire avvisi migliori. Tali attributi sono stati aggiunti in .NET Core 3.0. Altri framework di destinazione non sono stati annotati con uno di questi attributi. Ciò significa che gli avvisi nullable potrebbero non riflettere accuratamente i potenziali problemi.

## <a name="defaults"></a>Valori predefiniti

Il compilatore determina un'impostazione predefinita in base a queste regole:

|Framework di destinazione|version|Impostazione predefinita della versione del linguaggio C#|
|----------------|-------|---------------------------|
|.NET Core|3.x|C# 8.0|
|.NET Core|2.x|C# 7.3|
|.NET Standard|2.1|C# 8.0|
|.NET Standard|2.0|C# 7.3|
|.NET Standard|1.x|C# 7.3|
|.NET Framework|all|C# 7.3|

Quando il progetto ha come destinazione un framework in anteprima con una versione del linguaggio in anteprima corrispondente, la versione del linguaggio usata è la versione del linguaggio in anteprima. Utilizzare le funzionalità più recenti con tale anteprima in qualsiasi ambiente, senza influire sui progetti destinati a una versione di .NET Core rilasciata.

## <a name="override-a-default"></a>Sostituire un valore predefinito

Se è necessario specificare in modo esplicito la versione di C#, è possibile farlo in diversi modi:

- Modificare manualmente il [file di progetto](#edit-the-project-file).
- Impostare la versione del linguaggio [per più progetti in una sottodirectory](#configure-multiple-projects).
- Configurare [ `-langversion` l'opzione del compilatore](compiler-options/langversion-compiler-option.md).

### <a name="edit-the-project-file"></a>Modificare il file di progetto

È possibile impostare la versione del linguaggio nel file di progetto. Ad esempio, se si vuole accedere esplicitamente alle funzionalità di anteprima, aggiungere un elemento simile a questo:

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

Il valore `preview` usa la versione del linguaggio C# in anteprima disponibile più recente supportata dal compilatore.

### <a name="configure-multiple-projects"></a>Configurare più progetti

Per configurare più progetti, è possibile creare un file `<LangVersion>` **Directory.Build.props** contenente l'elemento. Questa operazione viene in genere eseguita nella directory della soluzione. Aggiungere quanto segue a un file **Directory.Build.props** nella directory della soluzione:

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

Viene compilato in tutte le sottodirectory della directory che contiene tale file verrà utilizzata la versione di anteprima di C. Per altre informazioni, vedere l'articolo [Personalizzare la compilazione](/visualstudio/msbuild/customize-your-build).

## <a name="c-language-version-reference"></a>Informazioni di riferimento sulle versioni del linguaggio C#

La tabella seguente illustra tutte le versioni del linguaggio C# correnti. Il compilatore potrebbe non comprendere necessariamente ogni valore se è più vecchio. Se si installa .NET Core 3.0 o versione successiva, è possibile accedere a tutti gli elementi elencati.

|valore|Significato|
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
|ISO-2|Il compilatore accetta solo la sintassi inclusa in ISO/IEC 23270:2006 in C |
|ISO-1|Il compilatore accetta solo la sintassi inclusa in ISO/IEC 23270:2003 c'è (1.0/1.2). |
