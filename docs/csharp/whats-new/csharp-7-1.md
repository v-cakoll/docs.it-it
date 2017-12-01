---
title: "Novità di c# 7.1"
description: "Panoramica delle nuove funzionalità in c# 7.1."
keywords: Progettazione del linguaggio c#, 7.1, Visual Studio 2017,
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 02f1f8fc8f0a3221e00e2a3c43ce06423ca43672
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="whats-new-in-c-71"></a>Novità di c# 7.1

C# 7.1 è il primo punto di rilascio del linguaggio c#. Contrassegna un rilasci maggiore per la lingua. È possibile utilizzare le nuove funzionalità prima, idealmente quando ogni nuova funzionalità è pronta. 7.1 c# aggiunge la possibilità di configurare il compilatore in modo che corrisponda a una versione specifica del linguaggio. Che consente di separare la decisione di eseguire l'aggiornamento di strumenti della decisione di eseguire l'aggiornamento di versioni in lingue diverse.

7.1 c# aggiunge il [selezione della lingua versione](#language-version-selection) elemento di configurazione, tre nuove funzionalità del linguaggio e il nuovo comportamento del compilatore.

Le nuove funzionalità del linguaggio in questa versione sono:

* [`async``Main` (metodo)](#async-main)
  - Il punto di ingresso per un'applicazione può avere il `async` modificatore.
* [`default`espressioni letterali](#default-literal-expressions)
  - Quando è possibile dedurre il tipo di destinazione, è possibile utilizzare espressioni letterali predefinite nelle espressioni di valori predefinito.
* [Nomi di elemento dedotto tupla](#inferred-tuple-element-names)
  - I nomi degli elementi di tupla possono essere dedotto dall'inizializzazione tupla in molti casi.

Infine, il compilatore è disponibili due opzioni `/refout` e `/refonly` tale controllo [la generazione di assembly di riferimento](#reference-assembly-generation).

## <a name="language-version-selection"></a>Selezione della lingua della versione

Il compilatore c# supporta 7.1 c# a partire da Visual Studio 2017 versione 15.3 o .NET Core SDK 2.0. Tuttavia, le 7.1 funzionalità sono disattivate per impostazione predefinita. Per abilitare le 7.1 funzionalità, è necessario modificare l'impostazione della versione di lingua per il progetto.

In Visual Studio, fare clic sul nodo del progetto in Esplora soluzioni e selezionare **proprietà**. Selezionare il **compilare** e selezionare il **avanzate** pulsante. Nell'elenco a discesa, selezionare **c# versione secondaria più recente (versione più recente)**, o la versione **c# 7.1** come illustrato nella seguente immagine. Il `latest` valore indica che si desidera utilizzare la versione secondaria più recente nel computer corrente. Il `C# 7.1` significa che si desidera utilizzare c# 7.1, anche dopo che vengono rilasciate le versioni secondarie successive.

![Impostazione della versione di lingua](./media/csharp-7-1/advanced-build-settings.png)

In alternativa, è possibile modificare il file "csproj" e aggiungere o modificare le righe seguenti:

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> Se si utilizza l'IDE di Visual Studio di aggiornare i file csproj, l'IDE crea nodi diversi per ogni configurazione di compilazione. È in genere imposta il valore lo stesso in tutte le configurazioni di compilazione, ma è necessario impostarlo in modo esplicito per ogni configurazione di compilazione o selezionare "Tutte le configurazioni" quando si modifica questa impostazione. Nel file csproj, verrà visualizzato quanto segue:

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Le impostazioni valide per il `LangVersion` elemento sono:

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

Le stringhe speciali `default` e `latest` risolvere per le versioni in lingua principale e secondaria più recente installate nel computer di compilazione, rispettivamente.

Questa impostazione separa l'installazione di nuove versioni del SDK e strumenti nell'ambiente di sviluppo dalla scelta di incorporare nuove funzionalità del linguaggio in un progetto. È possibile installare il SDK e strumenti più recenti nel computer di compilazione. Ogni progetto può essere configurato per utilizzare una versione specifica del linguaggio per la compilazione.

## <a name="async-main"></a>Async principale

Un *async principale* metodo consente di utilizzare `await` nel `Main` metodo.
In precedenza, è necessario scrivere:

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

Se il programma non restituisce un codice di uscita, è possibile dichiarare un `Main` metodo che restituisce un <xref:System.Threading.Tasks.Task>:

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

È possibile leggere informazioni sui dettagli nel [async principale](../programming-guide/main-and-command-args/index.md) argomento nella Guida di programmazione.

## <a name="default-literal-expressions"></a>Espressioni letterali predefinito

Le espressioni letterali predefinito rappresentano un progresso espressioni di valori predefiniti.
Queste espressioni di inizializzare una variabile sul valore predefinito. In cui in precedenza scrivere:

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

È ora possibile omettere il tipo sul lato destro dell'inizializzazione:

```csharp
Func<string, bool> whereClause = default;
```

Maggiori informazioni su questa funzionalità avanzata nell'argomento della Guida per programmatori c# in [predefinito espressioni valore](../programming-guide/statements-expressions-operators/default-value-expressions.md).

Questa funzionalità avanzata modifica anche alcune delle regole di analisi per il [parola chiave default](../language-reference/keywords/default.md).

## <a name="inferred-tuple-element-names"></a>Nomi di elemento dedotto tupla

Questa funzionalità è un piccolo miglioramento alla funzionalità tuple introdotta in c# 7.0. Molte volte quando l'inizializzazione di una tupla, le variabili utilizzate per il lato destro dell'assegnazione sono gli stessi nomi di cui che si desidera usare gli elementi della tupla:

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

I nomi degli elementi di tupla possono essere dedotto da variabili utilizzate per inizializzare la tupla in c# 7.1:

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

Per ulteriori informazioni su questa funzionalità in informazioni di [Tuple](../tuples.md) argomento.

## <a name="reference-assembly-generation"></a>Generazione di assembly di riferimento

Sono disponibili due nuove opzioni del compilatore che generano *gli assembly di riferimento sola*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) e [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).
Gli argomenti collegati illustrano queste opzioni e gli assembly di riferimento in modo più dettagliato.
