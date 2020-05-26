---
title: Controllo delle versioni del linguaggio C# - Guida a C#
description: Informazioni su come la versione del linguaggio C# viene determinata in base al progetto e ai motivi alla base di tale scelta. Informazioni su come eseguire manualmente l'override del valore predefinito.
ms.date: 05/20/2020
ms.openlocfilehash: bbe5b12e378cf47b7c9b2c8576088e949e526a9a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803012"
---
# <a name="c-language-versioning"></a>Controllo delle versioni del linguaggio C#

Il compilatore C# più recente determina la versione di un linguaggio predefinito in base ai framework di destinazione del progetto. Visual Studio non fornisce un'interfaccia utente per modificare il valore, ma è possibile modificarlo modificando il file *csproj* . La scelta del valore predefinito consente di usare la versione più recente del linguaggio compatibile con il Framework di destinazione. È possibile trarre vantaggio dall'accesso alle funzionalità più recenti del linguaggio compatibili con la destinazione del progetto. Questa scelta predefinita garantisce anche di non usare un linguaggio che richiede tipi o comportamenti di runtime non disponibili nel Framework di destinazione. La scelta di una versione della lingua più recente di quella predefinita può causare difficoltà nella diagnosi degli errori di runtime e della fase di compilazione.

Le regole in questo articolo si applicano al compilatore fornito con Visual Studio 2019 o .NET Core 3,0 SDK. I compilatori C# che fanno parte dell'installazione di Visual Studio 2017 o di versioni precedenti di .NET Core SDK usano C# 7.0 come destinazione per impostazione predefinita.

C# 8,0 (e versioni successive) è supportato solo in .NET Core 3. x e versioni successive. Molte delle funzionalità più recenti richiedono la libreria e le funzionalità di runtime introdotte in .NET Core 3. x:

- L' [implementazione dell'interfaccia predefinita](../whats-new/csharp-8.md#default-interface-methods) richiede nuove funzionalità in CLR di .net core 3,0.
- I [flussi asincroni](../whats-new/csharp-8.md#asynchronous-streams) richiedono i nuovi tipi <xref:System.IAsyncDisposable?displayProperty=nameWithType> , <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> e <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType> .
- Per gli [indici e gli intervalli](../whats-new/csharp-8.md#indices-and-ranges) sono necessari i nuovi tipi <xref:System.Index?displayProperty=nameWithType> e <xref:System.Range?displayProperty=nameWithType> .
- I [tipi di riferimento Nullable](../whats-new/csharp-8.md#nullable-reference-types) fanno uso di diversi [attributi](attributes/nullable-analysis.md) per fornire avvisi migliori. Questi attributi sono stati aggiunti in .NET Core 3,0. Altri Framework di destinazione non sono stati annotati con nessuno di questi attributi. Questo significa che gli avvisi Nullable potrebbero non riflettere accuratamente i potenziali problemi.

## <a name="defaults"></a>Valori predefiniti

Il compilatore determina un'impostazione predefinita in base a queste regole:

| Framework di destinazione | version | Impostazione predefinita della versione del linguaggio C# |
|------------------|---------|-----------------------------|
| .NET Core        | 3.x     | C# 8.0                      |
| .NET Core        | 2.x     | C# 7.3                      |
| .NET Standard    | 2.1     | C# 8.0                      |
| .NET Standard    | 2.0     | C# 7.3                      |
| .NET Standard    | 1.x     | C# 7.3                      |
| .NET Framework   | all     | C# 7.3                      |

Quando il progetto ha come destinazione un framework in anteprima con una versione del linguaggio in anteprima corrispondente, la versione del linguaggio usata è la versione del linguaggio in anteprima. Si usano le funzionalità più recenti con questa anteprima in qualsiasi ambiente, senza influire sui progetti destinati a una versione di .NET Core rilasciata.

## <a name="override-a-default"></a>Sostituire un valore predefinito

Se è necessario specificare in modo esplicito la versione di C#, è possibile farlo in diversi modi:

- Modificare manualmente il [file di progetto](#edit-the-project-file).
- Impostare la versione del linguaggio [per più progetti in una sottodirectory](#configure-multiple-projects).
- Configurare l' [ `-langversion` opzione del compilatore](compiler-options/langversion-compiler-option.md).

### <a name="edit-the-project-file"></a>Modificare il file di progetto

È possibile impostare la versione del linguaggio nel file di progetto. Ad esempio, se si vuole accedere esplicitamente alle funzionalità di anteprima, aggiungere un elemento simile a questo:

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

Il valore `preview` usa la versione del linguaggio C# in anteprima disponibile più recente supportata dal compilatore.

### <a name="configure-multiple-projects"></a>Configurare più progetti

Per configurare più progetti, è possibile creare un file **Directory. Build. props** che contiene l' `<LangVersion>` elemento. Questa operazione viene in genere eseguita nella directory della soluzione. Aggiungere il codice seguente a un file **Directory. Build. props** nella directory della soluzione:

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

Compilazioni in tutte le sottodirectory della directory che contiene il file utilizzerà la versione di anteprima C#. Per altre informazioni, vedere l'articolo [Personalizzare la compilazione](/visualstudio/msbuild/customize-your-build).

## <a name="c-language-version-reference"></a>Informazioni di riferimento sulle versioni del linguaggio C#

La tabella seguente illustra tutte le versioni del linguaggio C# correnti. Il compilatore potrebbe non comprendere necessariamente ogni valore se è meno recente. Se si installa .NET Core 3,0 o versione successiva, è possibile accedere a tutti gli elementi elencati.

[!INCLUDE [langversion-table](includes/langversion-table.md)]

> [!TIP]
> Aprire il [prompt dei comandi per gli sviluppatori per Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md)ed eseguire il comando seguente per visualizzare l'elenco delle versioni della lingua disponibili nel computer.
>
> ```CMD
> csc -langversion:?
> ```
>
> Se si sta interrogando l'opzione di compilazione [-langversion](compiler-options/langversion-compiler-option.md) , verrà stampato un valore simile al seguente:
>
> ```CMD
> Supported language versions:
> default
> 1
> 2
> 3
> 4
> 5
> 6
> 7.0
> 7.1
> 7.2
> 7.3
> 8.0 (default)
> latestmajor
> preview
> latest
> ```
