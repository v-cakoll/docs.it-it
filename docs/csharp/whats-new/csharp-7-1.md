---
title: Novità di C# 7.1
description: Panoramica delle nuove funzionalità in C# 7.1.
ms.date: 08/16/2017
ms.openlocfilehash: 565db102284424f9d8f6fa04ec9c74b52c9da0e6
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728654"
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="e1e91-103">Novità di C# 7.1</span><span class="sxs-lookup"><span data-stu-id="e1e91-103">What's new in C# 7.1</span></span>

<span data-ttu-id="e1e91-104">C# 7.1 è la prima versione intermedia del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="e1e91-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="e1e91-105">Indica una maggiore frequenza per il rilascio delle versioni del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="e1e91-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="e1e91-106">Le nuove funzionalità possono essere usate prima, idealmente non appena ognuna di esse è pronta.</span><span class="sxs-lookup"><span data-stu-id="e1e91-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="e1e91-107">C# 7.1 aggiunge la possibilità di configurare il compilatore in modo che corrisponda a una specifica versione del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="e1e91-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="e1e91-108">Questo consente di separare la decisione di eseguire l'aggiornamento di strumenti dalla decisione di eseguire l'aggiornamento delle versioni del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="e1e91-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="e1e91-109">C# 7.1 aggiunge l'elemento di configurazione per la [selezione della versione del linguaggio](../language-reference/configure-language-version.md), tre nuove funzionalità del linguaggio e il nuovo comportamento del compilatore.</span><span class="sxs-lookup"><span data-stu-id="e1e91-109">C# 7.1 adds the [language version selection](../language-reference/configure-language-version.md) configuration element, three new language features and new compiler behavior.</span></span>

<span data-ttu-id="e1e91-110">Le nuove funzionalità relative al linguaggio in questa versione sono:</span><span class="sxs-lookup"><span data-stu-id="e1e91-110">The new language features in this release are:</span></span>

* <span data-ttu-id="e1e91-111">Metodo [`async` `Main` ](#async-main)</span><span class="sxs-lookup"><span data-stu-id="e1e91-111">[`async` `Main` method](#async-main)</span></span>
  - <span data-ttu-id="e1e91-112">Il punto di ingresso per un'applicazione può avere il modificatore `async`.</span><span class="sxs-lookup"><span data-stu-id="e1e91-112">The entry point for an application can have the `async` modifier.</span></span>
* <span data-ttu-id="e1e91-113">Espressioni letterali [`default` ](#default-literal-expressions)</span><span class="sxs-lookup"><span data-stu-id="e1e91-113">[`default` literal expressions](#default-literal-expressions)</span></span>
  - <span data-ttu-id="e1e91-114">Quando è possibile dedurre il tipo di destinazione, si possono usare espressioni letterali predefinite nelle espressioni con valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="e1e91-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="e1e91-115">Nomi di elemento di tupla dedotti</span><span class="sxs-lookup"><span data-stu-id="e1e91-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="e1e91-116">In molti casi i nomi degli elementi della tupla possono essere dedotti dall'inizializzazione tupla.</span><span class="sxs-lookup"><span data-stu-id="e1e91-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>

<span data-ttu-id="e1e91-117">Infine, il compilatore offre due opzioni `/refout` e `/refonly` che controllano la [generazione dell'assembly di riferimento](#reference-assembly-generation).</span><span class="sxs-lookup"><span data-stu-id="e1e91-117">Finally, the compiler has two options `/refout` and `/refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

<span data-ttu-id="e1e91-118">Per usare le funzionalità più recenti in una versione intermedia, è necessario [configurare la versione in lingua del compilatore](../language-reference/configure-language-version.md) e selezionare la versione.</span><span class="sxs-lookup"><span data-stu-id="e1e91-118">To use the latest features in a point release, you need to [configure the compiler language version](../language-reference/configure-language-version.md) and select the version.</span></span>

## <a name="async-main"></a><span data-ttu-id="e1e91-119">Async main</span><span class="sxs-lookup"><span data-stu-id="e1e91-119">Async main</span></span>

<span data-ttu-id="e1e91-120">Un metodo *async main* consente di usare `await` nel proprio metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="e1e91-120">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="e1e91-121">In precedenza sarebbe stato necessario scrivere:</span><span class="sxs-lookup"><span data-stu-id="e1e91-121">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="e1e91-122">Ora è possibile scrivere:</span><span class="sxs-lookup"><span data-stu-id="e1e91-122">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="e1e91-123">Se il programma non restituisce un codice di uscita, è possibile dichiarare un metodo `Main` che restituisce una classe <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="e1e91-123">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="e1e91-124">Per altre informazioni dettagliate, leggere l'argomento [async main](../programming-guide/main-and-command-args/index.md) nella guida alla programmazione.</span><span class="sxs-lookup"><span data-stu-id="e1e91-124">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) topic in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="e1e91-125">Espressioni letterali predefinite</span><span class="sxs-lookup"><span data-stu-id="e1e91-125">Default literal expressions</span></span>

<span data-ttu-id="e1e91-126">Le espressioni letterali predefinite rappresentano un miglioramento delle espressioni con valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="e1e91-126">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="e1e91-127">Queste espressioni inizializzano una variabile sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="e1e91-127">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="e1e91-128">Mentre in precedenza si sarebbe scritto:</span><span class="sxs-lookup"><span data-stu-id="e1e91-128">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="e1e91-129">È ora possibile omettere il tipo sul lato destro dell'inizializzazione:</span><span class="sxs-lookup"><span data-stu-id="e1e91-129">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="e1e91-130">Altre informazioni su questo miglioramento sono disponibili nell'argomento della Guida per programmatori C# relativo alle [espressioni con valore predefinito](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e1e91-130">You can learn more about this enhancement in the C# Programming Guide topic on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="e1e91-131">Questo miglioramento modifica anche alcune delle regole di analisi per la [parola chiave default](../language-reference/keywords/default.md).</span><span class="sxs-lookup"><span data-stu-id="e1e91-131">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="e1e91-132">Nomi di elemento di tupla dedotti</span><span class="sxs-lookup"><span data-stu-id="e1e91-132">Inferred tuple element names</span></span>

<span data-ttu-id="e1e91-133">Questa funzionalità costituisce un piccolo miglioramento alla funzionalità relativa alle tuple introdotta in C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="e1e91-133">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="e1e91-134">Molte volte, quando si inizializza una tupla, le variabili usate per il lato destro dell'assegnazione corrispondono esattamente ai nomi che si vorrebbero usare per gli elementi della tupla:</span><span class="sxs-lookup"><span data-stu-id="e1e91-134">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="e1e91-135">I nomi degli elementi della tupla possono essere dedotti dalle variabili usate per inizializzare la tupla in C# 7.1:</span><span class="sxs-lookup"><span data-stu-id="e1e91-135">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="e1e91-136">Informazioni più approfondite sulle tuple sono disponibili nell'argomento [Tuple](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="e1e91-136">You can learn more about this feature in the [Tuples](../tuples.md) topic.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="e1e91-137">Generazione assembly di riferimento</span><span class="sxs-lookup"><span data-stu-id="e1e91-137">Reference assembly generation</span></span>

<span data-ttu-id="e1e91-138">Sono disponibili due nuove opzioni del compilatore che generano *gli assembly di solo riferimento* : [/refout](../language-reference/compiler-options/refout-compiler-option.md) e [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="e1e91-138">There are two new compiler options that generate *reference-only assemblies*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) and [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="e1e91-139">Gli argomenti collegati illustrano in modo più dettagliato queste opzioni e gli assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e1e91-139">The linked topics explain these options and reference assemblies in more detail.</span></span>
