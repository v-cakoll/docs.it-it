---
title: Novità di C# 7.1
description: Panoramica delle nuove funzionalità in C# 7.1.
ms.date: 04/09/2019
ms.openlocfilehash: a95111b6f217a2ca5c520c2d4d70efa0e23742f9
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "67347611"
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="b2393-103">Novità di C# 7.1</span><span class="sxs-lookup"><span data-stu-id="b2393-103">What's new in C# 7.1</span></span>

<span data-ttu-id="b2393-104">C# 7.1 è la prima versione intermedia del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="b2393-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="b2393-105">Indica una maggiore frequenza per il rilascio delle versioni del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="b2393-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="b2393-106">Le nuove funzionalità possono essere usate prima, idealmente non appena ognuna di esse è pronta.</span><span class="sxs-lookup"><span data-stu-id="b2393-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="b2393-107">C# 7.1 aggiunge la possibilità di configurare il compilatore in modo che corrisponda a una specifica versione del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="b2393-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="b2393-108">Questo consente di separare la decisione di eseguire l'aggiornamento di strumenti dalla decisione di eseguire l'aggiornamento delle versioni del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="b2393-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="b2393-109">C# 7.1 aggiunge l'elemento di configurazione per la [selezione della versione del linguaggio](../language-reference/configure-language-version.md), tre nuove funzionalità del linguaggio e il nuovo comportamento del compilatore.</span><span class="sxs-lookup"><span data-stu-id="b2393-109">C# 7.1 adds the [language version selection](../language-reference/configure-language-version.md) configuration element, three new language features, and new compiler behavior.</span></span>

<span data-ttu-id="b2393-110">Le nuove funzionalità relative al linguaggio in questa versione sono:</span><span class="sxs-lookup"><span data-stu-id="b2393-110">The new language features in this release are:</span></span>

* <span data-ttu-id="b2393-111">Metodo [`async` `Main` ](#async-main)</span><span class="sxs-lookup"><span data-stu-id="b2393-111">[`async` `Main` method](#async-main)</span></span>
  - <span data-ttu-id="b2393-112">Il punto di ingresso per un'applicazione può avere il modificatore `async`.</span><span class="sxs-lookup"><span data-stu-id="b2393-112">The entry point for an application can have the `async` modifier.</span></span>
* <span data-ttu-id="b2393-113">Espressioni letterali [`default` ](#default-literal-expressions)</span><span class="sxs-lookup"><span data-stu-id="b2393-113">[`default` literal expressions](#default-literal-expressions)</span></span>
  - <span data-ttu-id="b2393-114">Quando è possibile dedurre il tipo di destinazione, si possono usare espressioni letterali predefinite nelle espressioni con valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="b2393-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="b2393-115">Nomi di elemento di tupla dedotti</span><span class="sxs-lookup"><span data-stu-id="b2393-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="b2393-116">In molti casi i nomi degli elementi della tupla possono essere dedotti dall'inizializzazione tupla.</span><span class="sxs-lookup"><span data-stu-id="b2393-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>
* [<span data-ttu-id="b2393-117">Criteri di ricerca su parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="b2393-117">Pattern matching on generic type parameters</span></span>](#pattern-matching-on-generic-type-parameters)
  - <span data-ttu-id="b2393-118">È possibile usare espressioni di criteri di ricerca sulle variabili in cui il tipo è un parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="b2393-118">You can use pattern match expressions on variables whose type is a generic type parameter.</span></span>

<span data-ttu-id="b2393-119">Infine, il compilatore offre due opzioni `-refout` e `-refonly` che controllano la [generazione dell'assembly di riferimento](#reference-assembly-generation).</span><span class="sxs-lookup"><span data-stu-id="b2393-119">Finally, the compiler has two options `-refout` and `-refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

<span data-ttu-id="b2393-120">Per usare le funzionalità più recenti in una versione intermedia, è necessario [configurare la versione in lingua del compilatore](../language-reference/configure-language-version.md) e selezionare la versione.</span><span class="sxs-lookup"><span data-stu-id="b2393-120">To use the latest features in a point release, you need to [configure the compiler language version](../language-reference/configure-language-version.md) and select the version.</span></span>

<span data-ttu-id="b2393-121">La parte restante di questo articolo illustra una panoramica di ogni funzionalità.</span><span class="sxs-lookup"><span data-stu-id="b2393-121">The remainder of this article provides an overview of each feature.</span></span> <span data-ttu-id="b2393-122">Per ogni funzionalità verranno illustrati i concetti di base</span><span class="sxs-lookup"><span data-stu-id="b2393-122">For each feature, you'll learn the reasoning behind it.</span></span> <span data-ttu-id="b2393-123">e si apprenderà la sintassi.</span><span class="sxs-lookup"><span data-stu-id="b2393-123">You'll learn the syntax.</span></span> <span data-ttu-id="b2393-124">È possibile esplorare queste funzionalità nell'ambiente in uso tramite lo strumento globale `dotnet try`:</span><span class="sxs-lookup"><span data-stu-id="b2393-124">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="b2393-125">Installare lo strumento globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).</span><span class="sxs-lookup"><span data-stu-id="b2393-125">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="b2393-126">Clonare il repository [dotnet/try-samples](https://github.com/dotnet/try-samples).</span><span class="sxs-lookup"><span data-stu-id="b2393-126">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="b2393-127">Impostare la directory corrente sulla sottodirectory *csharp7* per il repository *try-samples*.</span><span class="sxs-lookup"><span data-stu-id="b2393-127">Set the current directory to the *csharp7* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="b2393-128">Eseguire `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="b2393-128">Run `dotnet try`.</span></span>

## <a name="async-main"></a><span data-ttu-id="b2393-129">Async main</span><span class="sxs-lookup"><span data-stu-id="b2393-129">Async main</span></span>

<span data-ttu-id="b2393-130">Un metodo *async main* consente di usare `await` nel proprio metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="b2393-130">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="b2393-131">In precedenza sarebbe stato necessario scrivere:</span><span class="sxs-lookup"><span data-stu-id="b2393-131">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="b2393-132">Ora è possibile scrivere:</span><span class="sxs-lookup"><span data-stu-id="b2393-132">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="b2393-133">Se il programma non restituisce un codice di uscita, è possibile dichiarare un metodo `Main` che restituisce una classe <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="b2393-133">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="b2393-134">Per altre informazioni dettagliate, leggere l'articolo [async main](../programming-guide/main-and-command-args/index.md) nella guida alla programmazione.</span><span class="sxs-lookup"><span data-stu-id="b2393-134">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) article in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="b2393-135">Espressioni letterali predefinite</span><span class="sxs-lookup"><span data-stu-id="b2393-135">Default literal expressions</span></span>

<span data-ttu-id="b2393-136">Le espressioni letterali predefinite rappresentano un miglioramento delle espressioni con valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="b2393-136">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="b2393-137">Queste espressioni inizializzano una variabile sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="b2393-137">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="b2393-138">Mentre in precedenza si sarebbe scritto:</span><span class="sxs-lookup"><span data-stu-id="b2393-138">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="b2393-139">È ora possibile omettere il tipo sul lato destro dell'inizializzazione:</span><span class="sxs-lookup"><span data-stu-id="b2393-139">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="b2393-140">Altre informazioni su questo miglioramento sono disponibili nell'articolo della Guida per programmatori C# relativo alle [espressioni con valore predefinito](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="b2393-140">You can learn more about this enhancement in the C# Programming Guide article on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="b2393-141">Questo miglioramento modifica anche alcune delle regole di analisi per la [parola chiave default](../language-reference/keywords/default.md).</span><span class="sxs-lookup"><span data-stu-id="b2393-141">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="b2393-142">Nomi di elemento di tupla dedotti</span><span class="sxs-lookup"><span data-stu-id="b2393-142">Inferred tuple element names</span></span>

<span data-ttu-id="b2393-143">Questa funzionalità costituisce un piccolo miglioramento alla funzionalità relativa alle tuple introdotta in C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="b2393-143">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="b2393-144">Molte volte, quando si inizializza una tupla, le variabili usate per il lato destro dell'assegnazione corrispondono esattamente ai nomi che si vorrebbero usare per gli elementi della tupla:</span><span class="sxs-lookup"><span data-stu-id="b2393-144">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="b2393-145">I nomi degli elementi della tupla possono essere dedotti dalle variabili usate per inizializzare la tupla in C# 7.1:</span><span class="sxs-lookup"><span data-stu-id="b2393-145">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="b2393-146">Informazioni più approfondite sulle tuple sono disponibili nell'articolo [Tuple](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="b2393-146">You can learn more about this feature in the [Tuples](../tuples.md) article.</span></span>

## <a name="pattern-matching-on-generic-type-parameters"></a><span data-ttu-id="b2393-147">Criteri di ricerca su parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="b2393-147">Pattern matching on generic type parameters</span></span>

<span data-ttu-id="b2393-148">A partire da C# 7.1, l'espressione di criteri per `is` e il criterio di tipo `switch` possono avere il tipo di un parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="b2393-148">Beginning with C# 7.1, the pattern expression for `is` and the `switch` type pattern may have the type of a generic type parameter.</span></span> <span data-ttu-id="b2393-149">Questo è particolarmente utile quando si esegue il controllo dei tipi che possono essere `struct` o `class` e si vuole evitare la conversione boxing.</span><span class="sxs-lookup"><span data-stu-id="b2393-149">This can be most useful when checking types that may be either `struct` or `class` types, and you want to avoid boxing.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="b2393-150">Generazione assembly di riferimento</span><span class="sxs-lookup"><span data-stu-id="b2393-150">Reference assembly generation</span></span>

<span data-ttu-id="b2393-151">Sono disponibili due nuove opzioni del compilatore che generano gli *assembly di solo riferimento*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) e [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="b2393-151">There are two new compiler options that generate *reference-only assemblies*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) and [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="b2393-152">Gli articoli collegati illustrano in modo più dettagliato queste opzioni e gli assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="b2393-152">The linked articles explain these options and reference assemblies in more detail.</span></span>
