---
title: Novità di C# 7.1
description: Panoramica delle nuove funzionalità in C# 7.1.
ms.date: 08/16/2017
ms.openlocfilehash: 00baec45d7582d3ac12c7b0865241f5cd8159246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c-71"></a>Novità di C# 7.1

C# 7.1 è la prima versione intermedia del linguaggio C#. Indica una maggiore frequenza per il rilascio delle versioni del linguaggio. Le nuove funzionalità possono essere usate prima, idealmente non appena ognuna di esse è pronta. C# 7.1 aggiunge la possibilità di configurare il compilatore in modo che corrisponda a una specifica versione del linguaggio. Questo consente di separare la decisione di eseguire l'aggiornamento di strumenti dalla decisione di eseguire l'aggiornamento delle versioni del linguaggio.

C# 7.1 aggiunge l'elemento di configurazione per la [selezione della versione del linguaggio](#language-version-selection), tre nuove funzionalità del linguaggio e il nuovo comportamento del compilatore.

Le nuove funzionalità relative al linguaggio in questa versione sono:

* Metodo [`async` `Main` ](#async-main)
  - Il punto di ingresso per un'applicazione può avere il modificatore `async`.
* Espressioni letterali [`default` ](#default-literal-expressions)
  - Quando è possibile dedurre il tipo di destinazione, si possono usare espressioni letterali predefinite nelle espressioni con valore predefinito.
* [Nomi di elemento di tupla dedotti](#inferred-tuple-element-names)
  - In molti casi i nomi degli elementi della tupla possono essere dedotti dall'inizializzazione tupla.

Infine, il compilatore offre due opzioni `/refout` e `/refonly` che controllano la [generazione dell'assembly di riferimento](#reference-assembly-generation).

## <a name="language-version-selection"></a>Selezione della versione del linguaggio

Il compilatore C# supporta C# 7.1 a partire da Visual Studio 2017 versione 15.3 o .NET Core SDK 2.0. Le funzionalità della versione 7.1 sono tuttavia disattivate per impostazione predefinita. Per abilitare le funzionalità della versione 7.1, è necessario modificare l'impostazione della versione del linguaggio per il progetto.

In Visual Studio fare clic con il pulsante destro del mouse sul nodo del progetto in Esplora soluzioni e scegliere **Proprietà**. Selezionare la scheda **Compilazione** e quindi il pulsante **Avanzate**. Nell'elenco a discesa selezionare l'**Ultima versione secondaria di C# (più recente)** o la versione specifica **C# 7.1** come illustrato nell'immagine seguente. Il valore `latest` indica che si intende usare l'ultima versione secondaria nel computer corrente. Il valore `C# 7.1` indica che si intende usare C# 7.1 anche dopo il rilascio di versioni secondarie successive.

![Impostazione della versione del linguaggio](./media/csharp-7-1/advanced-build-settings.png)

In alternativa, è possibile modificare il file "csproj" e aggiungere o modificare le righe seguenti:

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> Se si usa l'IDE di Visual Studio per aggiornare i file csproj, l'IDE crea nodi separati per ogni configurazione della build. In genere si imposta lo stesso valore in tutte le configurazioni della build, ma è necessario impostarlo in modo esplicito per ogni configurazione della build o selezionare "Tutte le configurazioni" quando si modifica questa impostazione. Nel file csproj verrà visualizzato quanto segue:

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Le impostazioni valide per l'elemento `LangVersion` sono:

* `ISO-1`
* `ISO-2`
* `3`
* `4`
* `5`
* `6`
* `7`
* `7.1`
* `default`
* `latest`

Le stringhe speciali `default` e `latest` si risolvono rispettivamente nelle versioni principale e secondaria più recenti del linguaggio installate nel computer di compilazione.

Questa impostazione separa l'installazione delle nuove versioni di SDK e strumenti nell'ambiente di sviluppo dalla scelta di incorporare nuove funzionalità del linguaggio in un progetto. È possibile installare l'SDK e gli strumenti più recenti nel computer di compilazione. Ogni progetto può essere configurato per usare una versione specifica del linguaggio in base alla relativa build.

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

Per altre informazioni dettagliate, leggere l'argomento [async main](../programming-guide/main-and-command-args/index.md) nella guida alla programmazione.

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

Altre informazioni su questo miglioramento sono disponibili nell'argomento della Guida per programmatori C# relativo alle [espressioni con valore predefinito](../programming-guide/statements-expressions-operators/default-value-expressions.md).

Questo miglioramento modifica anche alcune delle regole di analisi per la [parola chiave default](../language-reference/keywords/default.md).

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

Informazioni più approfondite sulle tuple sono disponibili nell'argomento [Tuple](../tuples.md).

## <a name="reference-assembly-generation"></a>Generazione assembly di riferimento

Sono disponibili due nuove opzioni del compilatore che generano *gli assembly di solo riferimento* : [/refout](../language-reference/compiler-options/refout-compiler-option.md) e [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).
Gli argomenti collegati illustrano in modo più dettagliato queste opzioni e gli assembly di riferimento.
