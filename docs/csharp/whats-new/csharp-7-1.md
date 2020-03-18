---
title: Novità di C# 7.1
description: Panoramica delle nuove funzionalità in C# 7.1.
ms.date: 04/09/2019
ms.openlocfilehash: 5d2d6f51b6422f5b4db5c6bd275b5ffce1f695f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399707"
---
# <a name="whats-new-in-c-71"></a>Novità di C# 7.1

C# 7.1 è la prima versione intermedia del linguaggio C#. Indica una maggiore frequenza per il rilascio delle versioni del linguaggio. Le nuove funzionalità possono essere usate prima, idealmente non appena ognuna di esse è pronta. C# 7.1 aggiunge la possibilità di configurare il compilatore in modo che corrisponda a una specifica versione del linguaggio. Questo consente di separare la decisione di eseguire l'aggiornamento di strumenti dalla decisione di eseguire l'aggiornamento delle versioni del linguaggio.

C# 7.1 aggiunge l'elemento di configurazione per la [selezione della versione del linguaggio](../language-reference/configure-language-version.md), tre nuove funzionalità del linguaggio e il nuovo comportamento del compilatore.

Le nuove funzionalità relative al linguaggio in questa versione sono:

- [`async``Main` metodo](#async-main)
  - Il punto di ingresso per un'applicazione può avere il modificatore `async`.
- [`default`espressioni letterali](#default-literal-expressions)
  - Quando è possibile dedurre il tipo di destinazione, si possono usare espressioni letterali predefinite nelle espressioni con valore predefinito.
- [Nomi di elemento di tupla dedotti](#inferred-tuple-element-names)
  - In molti casi i nomi degli elementi della tupla possono essere dedotti dall'inizializzazione tupla.
- [Criteri di ricerca su parametri di tipo generico](#pattern-matching-on-generic-type-parameters)
  - È possibile usare espressioni di criteri di ricerca sulle variabili in cui il tipo è un parametro di tipo generico.

Infine, il compilatore offre due opzioni `-refout` e `-refonly` che controllano la [generazione dell'assembly di riferimento](#reference-assembly-generation).

Per usare le funzionalità più recenti in una versione a punti, è necessario [configurare la versione in lingua del compilatore](../language-reference/configure-language-version.md) e selezionare la versione.

La parte restante di questo articolo illustra una panoramica di ogni funzionalità. Per ogni funzionalità verranno illustrati i concetti di base e si apprenderà la sintassi. È possibile esplorare queste funzionalità nell'ambiente in uso tramite lo strumento globale `dotnet try`:

1. Installare lo strumento globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).
1. Clonare il repository [dotnet/try-samples](https://github.com/dotnet/try-samples).
1. Impostare la directory corrente sulla sottodirectory *csharp7* per il repository *try-samples*.
1. Eseguire `dotnet try`.

## <a name="async-main"></a>Async main

Un metodo *async main* consente di usare `await` nel proprio metodo `Main`.
In precedenza sarebbe stato necessario scrivere:

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

Ora è possibile scrivere:

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

Se il programma non restituisce un codice di uscita, è possibile dichiarare un metodo `Main` che restituisce una classe <xref:System.Threading.Tasks.Task>:

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

Per altre informazioni dettagliate, leggere l'articolo [async main](../programming-guide/main-and-command-args/index.md) nella guida alla programmazione.

## <a name="default-literal-expressions"></a>Espressioni letterali predefinite

Le espressioni letterali predefinite rappresentano un miglioramento delle espressioni con valore predefinito.
Queste espressioni inizializzano una variabile sul valore predefinito. Mentre in precedenza si sarebbe scritto:

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

È ora possibile omettere il tipo sul lato destro dell'inizializzazione:

```csharp
Func<string, bool> whereClause = default;
```

Per altre informazioni, vedere la sezione [Valore letterale predefinito](../language-reference/operators/default.md#default-literal) dell'articolo [Operatore default](../language-reference/operators/default.md).

## <a name="inferred-tuple-element-names"></a>Nomi di elemento di tupla dedotti

Questa funzionalità costituisce un piccolo miglioramento alla funzionalità relativa alle tuple introdotta in C# 7.0. Molte volte, quando si inizializza una tupla, le variabili usate per il lato destro dell'assegnazione corrispondono esattamente ai nomi che si vorrebbero usare per gli elementi della tupla:

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

I nomi degli elementi della tupla possono essere dedotti dalle variabili usate per inizializzare la tupla in C# 7.1:

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

Informazioni più approfondite sulle tuple sono disponibili nell'articolo [Tuple](../tuples.md).

## <a name="pattern-matching-on-generic-type-parameters"></a>Criteri di ricerca su parametri di tipo generico

A partire da C# 7.1, l'espressione di criteri per `is` e il criterio di tipo `switch` possono avere il tipo di un parametro di tipo generico. Questo è particolarmente utile quando si esegue il controllo dei tipi che possono essere `struct` o `class` e si vuole evitare la conversione boxing.

## <a name="reference-assembly-generation"></a>Generazione assembly di riferimento

Sono disponibili due nuove opzioni del compilatore che generano gli *assembly di solo riferimento*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) e [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).
Gli articoli collegati illustrano in modo più dettagliato queste opzioni e gli assembly di riferimento.
