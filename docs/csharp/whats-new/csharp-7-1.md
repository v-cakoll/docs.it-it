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
# <a name="whats-new-in-c-71"></a><span data-ttu-id="4b95a-103">Novità di C# 7.1</span><span class="sxs-lookup"><span data-stu-id="4b95a-103">What's new in C# 7.1</span></span>

<span data-ttu-id="4b95a-104">C# 7.1 è la prima versione intermedia del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="4b95a-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="4b95a-105">Indica una maggiore frequenza per il rilascio delle versioni del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="4b95a-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="4b95a-106">Le nuove funzionalità possono essere usate prima, idealmente non appena ognuna di esse è pronta.</span><span class="sxs-lookup"><span data-stu-id="4b95a-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="4b95a-107">C# 7.1 aggiunge la possibilità di configurare il compilatore in modo che corrisponda a una specifica versione del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="4b95a-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="4b95a-108">Questo consente di separare la decisione di eseguire l'aggiornamento di strumenti dalla decisione di eseguire l'aggiornamento delle versioni del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="4b95a-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="4b95a-109">C# 7.1 aggiunge l'elemento di configurazione per la [selezione della versione del linguaggio](../language-reference/configure-language-version.md), tre nuove funzionalità del linguaggio e il nuovo comportamento del compilatore.</span><span class="sxs-lookup"><span data-stu-id="4b95a-109">C# 7.1 adds the [language version selection](../language-reference/configure-language-version.md) configuration element, three new language features, and new compiler behavior.</span></span>

<span data-ttu-id="4b95a-110">Le nuove funzionalità relative al linguaggio in questa versione sono:</span><span class="sxs-lookup"><span data-stu-id="4b95a-110">The new language features in this release are:</span></span>

- [<span data-ttu-id="4b95a-111">`async``Main` metodo</span><span class="sxs-lookup"><span data-stu-id="4b95a-111">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="4b95a-112">Il punto di ingresso per un'applicazione può avere il modificatore `async`.</span><span class="sxs-lookup"><span data-stu-id="4b95a-112">The entry point for an application can have the `async` modifier.</span></span>
- [<span data-ttu-id="4b95a-113">`default`espressioni letterali</span><span class="sxs-lookup"><span data-stu-id="4b95a-113">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="4b95a-114">Quando è possibile dedurre il tipo di destinazione, si possono usare espressioni letterali predefinite nelle espressioni con valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="4b95a-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
- [<span data-ttu-id="4b95a-115">Nomi di elemento di tupla dedotti</span><span class="sxs-lookup"><span data-stu-id="4b95a-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="4b95a-116">In molti casi i nomi degli elementi della tupla possono essere dedotti dall'inizializzazione tupla.</span><span class="sxs-lookup"><span data-stu-id="4b95a-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>
- [<span data-ttu-id="4b95a-117">Criteri di ricerca su parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="4b95a-117">Pattern matching on generic type parameters</span></span>](#pattern-matching-on-generic-type-parameters)
  - <span data-ttu-id="4b95a-118">È possibile usare espressioni di criteri di ricerca sulle variabili in cui il tipo è un parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="4b95a-118">You can use pattern match expressions on variables whose type is a generic type parameter.</span></span>

<span data-ttu-id="4b95a-119">Infine, il compilatore offre due opzioni `-refout` e `-refonly` che controllano la [generazione dell'assembly di riferimento](#reference-assembly-generation).</span><span class="sxs-lookup"><span data-stu-id="4b95a-119">Finally, the compiler has two options `-refout` and `-refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

<span data-ttu-id="4b95a-120">Per usare le funzionalità più recenti in una versione a punti, è necessario [configurare la versione in lingua del compilatore](../language-reference/configure-language-version.md) e selezionare la versione.</span><span class="sxs-lookup"><span data-stu-id="4b95a-120">To use the latest features in a point release, you need to [configure the compiler language version](../language-reference/configure-language-version.md) and select the version.</span></span>

<span data-ttu-id="4b95a-121">La parte restante di questo articolo illustra una panoramica di ogni funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4b95a-121">The remainder of this article provides an overview of each feature.</span></span> <span data-ttu-id="4b95a-122">Per ogni funzionalità verranno illustrati i concetti di base</span><span class="sxs-lookup"><span data-stu-id="4b95a-122">For each feature, you'll learn the reasoning behind it.</span></span> <span data-ttu-id="4b95a-123">e si apprenderà la sintassi.</span><span class="sxs-lookup"><span data-stu-id="4b95a-123">You'll learn the syntax.</span></span> <span data-ttu-id="4b95a-124">È possibile esplorare queste funzionalità nell'ambiente in uso tramite lo strumento globale `dotnet try`:</span><span class="sxs-lookup"><span data-stu-id="4b95a-124">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="4b95a-125">Installare lo strumento globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).</span><span class="sxs-lookup"><span data-stu-id="4b95a-125">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="4b95a-126">Clonare il repository [dotnet/try-samples](https://github.com/dotnet/try-samples).</span><span class="sxs-lookup"><span data-stu-id="4b95a-126">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="4b95a-127">Impostare la directory corrente sulla sottodirectory *csharp7* per il repository *try-samples*.</span><span class="sxs-lookup"><span data-stu-id="4b95a-127">Set the current directory to the *csharp7* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="4b95a-128">Eseguire `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="4b95a-128">Run `dotnet try`.</span></span>

## <a name="async-main"></a><span data-ttu-id="4b95a-129">Async main</span><span class="sxs-lookup"><span data-stu-id="4b95a-129">Async main</span></span>

<span data-ttu-id="4b95a-130">Un metodo *async main* consente di usare `await` nel proprio metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="4b95a-130">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="4b95a-131">In precedenza sarebbe stato necessario scrivere:</span><span class="sxs-lookup"><span data-stu-id="4b95a-131">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="4b95a-132">Ora è possibile scrivere:</span><span class="sxs-lookup"><span data-stu-id="4b95a-132">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="4b95a-133">Se il programma non restituisce un codice di uscita, è possibile dichiarare un metodo `Main` che restituisce una classe <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="4b95a-133">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="4b95a-134">Per altre informazioni dettagliate, leggere l'articolo [async main](../programming-guide/main-and-command-args/index.md) nella guida alla programmazione.</span><span class="sxs-lookup"><span data-stu-id="4b95a-134">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) article in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="4b95a-135">Espressioni letterali predefinite</span><span class="sxs-lookup"><span data-stu-id="4b95a-135">Default literal expressions</span></span>

<span data-ttu-id="4b95a-136">Le espressioni letterali predefinite rappresentano un miglioramento delle espressioni con valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="4b95a-136">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="4b95a-137">Queste espressioni inizializzano una variabile sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="4b95a-137">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="4b95a-138">Mentre in precedenza si sarebbe scritto:</span><span class="sxs-lookup"><span data-stu-id="4b95a-138">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="4b95a-139">È ora possibile omettere il tipo sul lato destro dell'inizializzazione:</span><span class="sxs-lookup"><span data-stu-id="4b95a-139">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="4b95a-140">Per altre informazioni, vedere la sezione [Valore letterale predefinito](../language-reference/operators/default.md#default-literal) dell'articolo [Operatore default](../language-reference/operators/default.md).</span><span class="sxs-lookup"><span data-stu-id="4b95a-140">For more information, see the [default literal](../language-reference/operators/default.md#default-literal) section of the [default operator](../language-reference/operators/default.md) article.</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="4b95a-141">Nomi di elemento di tupla dedotti</span><span class="sxs-lookup"><span data-stu-id="4b95a-141">Inferred tuple element names</span></span>

<span data-ttu-id="4b95a-142">Questa funzionalità costituisce un piccolo miglioramento alla funzionalità relativa alle tuple introdotta in C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="4b95a-142">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="4b95a-143">Molte volte, quando si inizializza una tupla, le variabili usate per il lato destro dell'assegnazione corrispondono esattamente ai nomi che si vorrebbero usare per gli elementi della tupla:</span><span class="sxs-lookup"><span data-stu-id="4b95a-143">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="4b95a-144">I nomi degli elementi della tupla possono essere dedotti dalle variabili usate per inizializzare la tupla in C# 7.1:</span><span class="sxs-lookup"><span data-stu-id="4b95a-144">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="4b95a-145">Informazioni più approfondite sulle tuple sono disponibili nell'articolo [Tuple](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="4b95a-145">You can learn more about this feature in the [Tuples](../tuples.md) article.</span></span>

## <a name="pattern-matching-on-generic-type-parameters"></a><span data-ttu-id="4b95a-146">Criteri di ricerca su parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="4b95a-146">Pattern matching on generic type parameters</span></span>

<span data-ttu-id="4b95a-147">A partire da C# 7.1, l'espressione di criteri per `is` e il criterio di tipo `switch` possono avere il tipo di un parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="4b95a-147">Beginning with C# 7.1, the pattern expression for `is` and the `switch` type pattern may have the type of a generic type parameter.</span></span> <span data-ttu-id="4b95a-148">Questo è particolarmente utile quando si esegue il controllo dei tipi che possono essere `struct` o `class` e si vuole evitare la conversione boxing.</span><span class="sxs-lookup"><span data-stu-id="4b95a-148">This can be most useful when checking types that may be either `struct` or `class` types, and you want to avoid boxing.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="4b95a-149">Generazione assembly di riferimento</span><span class="sxs-lookup"><span data-stu-id="4b95a-149">Reference assembly generation</span></span>

<span data-ttu-id="4b95a-150">Sono disponibili due nuove opzioni del compilatore che generano gli *assembly di solo riferimento*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) e [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="4b95a-150">There are two new compiler options that generate *reference-only assemblies*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) and [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="4b95a-151">Gli articoli collegati illustrano in modo più dettagliato queste opzioni e gli assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="4b95a-151">The linked articles explain these options and reference assemblies in more detail.</span></span>
