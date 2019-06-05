---
title: Criteri attivi
description: Informazioni su come usare i modelli attivi per definire partizioni denominate che suddividono i dati di input di F# linguaggio di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: 25ab255574390d3761fe788aeb413c8ee04fda2a
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690416"
---
# <a name="active-patterns"></a><span data-ttu-id="9ffff-103">Criteri attivi</span><span class="sxs-lookup"><span data-stu-id="9ffff-103">Active Patterns</span></span>

<span data-ttu-id="9ffff-104">*Criteri attivi* consentono di definire partizioni denominate che suddividono i dati di input, in modo che è possibile usare questi nomi in un criterio di corrispondenza espressione esattamente come si farebbe per un'unione discriminata.</span><span class="sxs-lookup"><span data-stu-id="9ffff-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="9ffff-105">È possibile usare i criteri attivi per decomporre i dati in modo personalizzato per ogni partizione.</span><span class="sxs-lookup"><span data-stu-id="9ffff-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="9ffff-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ffff-106">Syntax</span></span>

```fsharp
// Active pattern of one choice.
let (|identifier|) [arguments] valueToMatch= expression

// Active Pattern with multiple choices.
// Uses a FSharp.Core.Choice<_,...,_> based on the number of case names. In F#, the limitation n <= 7 applies.
let (|identifer1|identifier2|...|) valueToMatch = expression

// Partial active pattern definition.
// Uses a FSharp.Core.option<_> to represent if the type is satisfied at the call site.
let (|identifier|_|) [arguments ] valueToMatch = expression
```

## <a name="remarks"></a><span data-ttu-id="9ffff-107">Note</span><span class="sxs-lookup"><span data-stu-id="9ffff-107">Remarks</span></span>

<span data-ttu-id="9ffff-108">Nella sintassi precedente, gli identificatori sono nomi per le partizioni dei dati di input che sono rappresentati da *argomenti*, o, in altre parole, i nomi per i subset del set di tutti i valori degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="9ffff-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="9ffff-109">In una definizione di criterio attivo possono essere presenti fino a sette partizioni.</span><span class="sxs-lookup"><span data-stu-id="9ffff-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="9ffff-110">Il *espressione* descrive la forma in cui si desidera scomporre i dati.</span><span class="sxs-lookup"><span data-stu-id="9ffff-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="9ffff-111">È possibile usare una definizione di criterio attivo per definire le regole per determinare quali partizioni denominate i valori forniti come argomenti appartengono a.</span><span class="sxs-lookup"><span data-stu-id="9ffff-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="9ffff-112">I (| e |) i simboli sono dette *banana clip* e viene chiamata la funzione creata da questo tipo di binding "Let" un' *riconoscimento active*.</span><span class="sxs-lookup"><span data-stu-id="9ffff-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="9ffff-113">Ad esempio, prendere in considerazione il seguente criterio attivo con un argomento.</span><span class="sxs-lookup"><span data-stu-id="9ffff-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="9ffff-114">È possibile usare il modello attivo in un criterio di corrispondenza espressione, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9ffff-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="9ffff-115">Come indicato di seguito è riportato l'output di questo programma:</span><span class="sxs-lookup"><span data-stu-id="9ffff-115">The output of this program is as follows:</span></span>

```
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="9ffff-116">Viene utilizzato un altro di criteri attivi per decomporre i tipi di dati in diversi modi, ad esempio quando gli stessi dati sottostanti dispongono di diverse rappresentazioni possibili.</span><span class="sxs-lookup"><span data-stu-id="9ffff-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="9ffff-117">Ad esempio, un `Color` oggetto può essere scomposto in una rappresentazione RGB o in una rappresentazione HSB.</span><span class="sxs-lookup"><span data-stu-id="9ffff-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="9ffff-118">Come indicato di seguito è riportato l'output del programma precedente:</span><span class="sxs-lookup"><span data-stu-id="9ffff-118">The output of the above program is as follows:</span></span>

```
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

<span data-ttu-id="9ffff-119">In combinazione, queste due modalità di utilizzo dei modelli attivi consentono alla partizione e decomporre i dati nel proprio form appropriato ed eseguire i calcoli appropriati sui dati appropriati nella forma più semplice per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="9ffff-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="9ffff-120">Le espressioni di corrispondenza risultante abilitare dati da scrivere in un modo pratico che è molto leggibili, semplificando notevolmente la diramazione potenzialmente complesso e il codice di analisi di dati.</span><span class="sxs-lookup"><span data-stu-id="9ffff-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="9ffff-121">Criteri attivi parziali</span><span class="sxs-lookup"><span data-stu-id="9ffff-121">Partial Active Patterns</span></span>

<span data-ttu-id="9ffff-122">In alcuni casi, è necessario partizionare solo una parte dello spazio di input.</span><span class="sxs-lookup"><span data-stu-id="9ffff-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="9ffff-123">In tal caso, è scrivere un set di modelli parziali, ognuno dei quali corrisponde a una serie di dati e non agli altri input.</span><span class="sxs-lookup"><span data-stu-id="9ffff-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="9ffff-124">Criteri attivi che non producono sempre un valore sono detti *parziali modelli attivi*; hanno un valore restituito che è un tipo di opzione.</span><span class="sxs-lookup"><span data-stu-id="9ffff-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="9ffff-125">Per definire un modello attivo parziale, si utilizza un carattere jolly (\_) alla fine dell'elenco di modelli interni banana clip.</span><span class="sxs-lookup"><span data-stu-id="9ffff-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="9ffff-126">Il codice seguente illustra l'uso di un modello attivo parziale.</span><span class="sxs-lookup"><span data-stu-id="9ffff-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="9ffff-127">Come indicato di seguito è riportato l'output dell'esempio precedente:</span><span class="sxs-lookup"><span data-stu-id="9ffff-127">The output of the previous example is as follows:</span></span>

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="9ffff-128">Quando si usano i modelli attivi parziali, in alcuni casi le singole scelte possono essere contigui o si escludono a vicenda, ma non è necessario.</span><span class="sxs-lookup"><span data-stu-id="9ffff-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="9ffff-129">Nell'esempio seguente, il quadrato di modello e il modello di cubo non sono non contigui, perché alcuni numeri sono entrambi quadrati e cubi, ad esempio 64.</span><span class="sxs-lookup"><span data-stu-id="9ffff-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="9ffff-130">Il programma seguente usa il modello AND per combinare i modelli quadrato e il cubo.</span><span class="sxs-lookup"><span data-stu-id="9ffff-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="9ffff-131">Vengono stampati tutti i numeri interi fino a 1000 che sono entrambi quadrati e cubi, nonché quelle che sono soltanto i cubi.</span><span class="sxs-lookup"><span data-stu-id="9ffff-131">It print out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span> 

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="9ffff-132">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ffff-132">The output is as follows:</span></span>

```
1 is a cube and a square
8 is a cube
27 is a cube
64 is a cube and a square
125 is a cube
216 is a cube
343 is a cube
512 is a cube
729 is a cube and a square
1000 is a cube
```

## <a name="parameterized-active-patterns"></a><span data-ttu-id="9ffff-133">Criteri attivi con parametri</span><span class="sxs-lookup"><span data-stu-id="9ffff-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="9ffff-134">Criteri attivi hanno sempre almeno un argomento per l'elemento di soddisfazione, ma possono accettare argomenti aggiuntivi, nel qual caso il nome *con parametri (modello attivo)* si applica.</span><span class="sxs-lookup"><span data-stu-id="9ffff-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="9ffff-135">Argomenti aggiuntivi consentono un modello generale essere specializzata.</span><span class="sxs-lookup"><span data-stu-id="9ffff-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="9ffff-136">Ad esempio, i modelli attivi che usano le espressioni regolari per analizzare le stringhe spesso includono l'espressione regolare come parametro aggiuntivo, come nel codice seguente, che usa anche il modello attivo parziale `Integer` definito nell'esempio di codice precedente.</span><span class="sxs-lookup"><span data-stu-id="9ffff-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="9ffff-137">In questo esempio, le stringhe che utilizzano le espressioni regolari per i diversi formati di data vengono fornite per personalizzare l'attivo generale ParseRegex.</span><span class="sxs-lookup"><span data-stu-id="9ffff-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="9ffff-138">Consente di convertire le stringhe corrispondenti in numeri interi che possono essere passati al costruttore DateTime (modello attivo) l'intero.</span><span class="sxs-lookup"><span data-stu-id="9ffff-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="9ffff-139">Come indicato di seguito è riportato l'output del codice precedente:</span><span class="sxs-lookup"><span data-stu-id="9ffff-139">The output of the previous code is as follows:</span></span>

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="9ffff-140">Criteri attivi non sono limitati solo a espressioni corrispondente con il criterio, è possibile usare anche nelle ti permettono di associazioni.</span><span class="sxs-lookup"><span data-stu-id="9ffff-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="9ffff-141">Come indicato di seguito è riportato l'output del codice precedente:</span><span class="sxs-lookup"><span data-stu-id="9ffff-141">The output of the previous code is as follows:</span></span>

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="9ffff-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ffff-142">See also</span></span>

- [<span data-ttu-id="9ffff-143">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="9ffff-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="9ffff-144">Espressioni match</span><span class="sxs-lookup"><span data-stu-id="9ffff-144">Match Expressions</span></span>](match-expressions.md)
