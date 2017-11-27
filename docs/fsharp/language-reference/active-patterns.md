---
title: Modelli attivi (F#)
description: 'Informazioni su come usare i criteri attivi per definire partizioni denominate che suddividono i dati di input nel linguaggio di programmazione F #.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 11a724ff-f9ff-4056-b5e0-87e9ed986f4a
ms.openlocfilehash: 845184e6150cf0b93393038ca3d39f0e6d898a2e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="active-patterns"></a><span data-ttu-id="9c9a5-104">Criteri attivi</span><span class="sxs-lookup"><span data-stu-id="9c9a5-104">Active Patterns</span></span>

<span data-ttu-id="9c9a5-105">*Criteri attivi* consentono di definire partizioni denominate che suddividono i dati di input, in modo che è possibile utilizzare questi nomi in un'espressione come se trattasse di un'unione discriminata.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-105">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="9c9a5-106">È possibile usare i criteri attivi per decomporre i dati in modo personalizzato per ogni partizione.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-106">You can use active patterns to decompose data in a customized manner for each partition.</span></span>


## <a name="syntax"></a><span data-ttu-id="9c9a5-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c9a5-107">Syntax</span></span>

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a><span data-ttu-id="9c9a5-108">Note</span><span class="sxs-lookup"><span data-stu-id="9c9a5-108">Remarks</span></span>
<span data-ttu-id="9c9a5-109">Nella sintassi precedente, gli identificatori sono nomi per le partizioni di dati di input sono rappresentati da *argomenti*, o, in altre parole, i nomi per sottoinsiemi del set di tutti i valori degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-109">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="9c9a5-110">In una definizione di tipo (modello attivo) possono essere presenti fino a sette partizioni.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-110">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="9c9a5-111">Il *espressione* descrive il form in cui scomporre i dati.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-111">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="9c9a5-112">È possibile utilizzare una definizione (modello attivo) per definire le regole per determinare quali partizioni denominate i valori forniti come argomenti appartengono a.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-112">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="9c9a5-113">Il (| e |) i simboli sono detti *banana clip* e viene chiamata la funzione creata da questo tipo di associazione consentono un *riconoscimento attivo*.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-113">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="9c9a5-114">Ad esempio, si consideri il seguente (modello attivo) con un argomento.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-114">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="9c9a5-115">È possibile utilizzare il modello attivo in un'espressione, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-115">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="9c9a5-116">L'output di questo programma è come segue:</span><span class="sxs-lookup"><span data-stu-id="9c9a5-116">The output of this program is as follows:</span></span>

```
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="9c9a5-117">Viene utilizzato un altro di criteri attivi per scomporre i tipi di dati in più modi, ad esempio quando gli stessi dati sottostanti dispongono di varie rappresentazioni possibili.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-117">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="9c9a5-118">Ad esempio, un `Color` oggetto può essere scomposta in una rappresentazione RGB o in una rappresentazione HSB.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-118">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="9c9a5-119">L'output del programma precedente è come segue:</span><span class="sxs-lookup"><span data-stu-id="9c9a5-119">The output of the above program is as follows:</span></span>

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

<span data-ttu-id="9c9a5-120">In combinazione, queste due modalità di utilizzo di criteri attivi consentono di partizione e scomporre i dati in formato appena appropriato ed eseguire i calcoli appropriati sui dati appropriati nella forma più semplice per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-120">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="9c9a5-121">Le espressioni di corrispondenza risultante abilitare dati deve essere scritto in un modo pratico è molto leggibili, semplificando notevolmente la diramazione potenzialmente complesse e codice di analisi di dati.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-121">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>


## <a name="partial-active-patterns"></a><span data-ttu-id="9c9a5-122">Criteri attivi parziali</span><span class="sxs-lookup"><span data-stu-id="9c9a5-122">Partial Active Patterns</span></span>
<span data-ttu-id="9c9a5-123">In alcuni casi, è necessario partizionare solo una parte dello spazio di input.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-123">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="9c9a5-124">In tal caso, scrivere un set di modelli parziali, ognuno dei quali corrisponde alcuni input ma non altri input.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-124">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="9c9a5-125">Criteri attivi che non producono sempre un valore sono detti *criteri attivi parziali*; hanno un valore restituito è un tipo di opzione.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-125">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="9c9a5-126">Per definire un modello attivo parziale, utilizzare un carattere jolly (_) alla fine dell'elenco di modelli interni banana clip.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-126">To define a partial active pattern, you use a wildcard character (_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="9c9a5-127">Il codice seguente viene illustrato l'utilizzo di un modello attivo parziale.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-127">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="9c9a5-128">L'output dell'esempio precedente è come segue:</span><span class="sxs-lookup"><span data-stu-id="9c9a5-128">The output of the previous example is as follows:</span></span>

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="9c9a5-129">Quando si utilizza criteri attivi parziali, talvolta singole scelte possono essere contigui o si escludono a vicenda, ma è necessario.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-129">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="9c9a5-130">Nell'esempio seguente, il criterio Square e il modello di cubo non sono non contigui, perché alcuni numeri sono quadrati e cubi, ad esempio 64.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-130">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="9c9a5-131">Il seguente programma stampa tutti i valori interi fino a 1000000 quadrati e cubi.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-131">The following program prints out all integers up to 1000000 that are both squares and cubes.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="9c9a5-132">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9c9a5-132">The output is as follows:</span></span>

```
1
64
729
4096
15625
46656
117649
262144
531441
1000000
```

## <a name="parameterized-active-patterns"></a><span data-ttu-id="9c9a5-133">Criteri attivi con parametri</span><span class="sxs-lookup"><span data-stu-id="9c9a5-133">Parameterized Active Patterns</span></span>
<span data-ttu-id="9c9a5-134">Modelli attivi accettano sempre almeno un argomento per l'elemento viene cercata la corrispondenza, ma possono accettare argomenti aggiuntivi nonché, nel qual caso il nome *con parametri (modello attivo)* si applica.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="9c9a5-135">Gli argomenti aggiuntivi consentono un criterio generale specializzati.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="9c9a5-136">Ad esempio, i criteri attivi che usano espressioni regolari per analizzare le stringhe spesso includono l'espressione regolare come parametro aggiuntivo, come illustrato nel codice seguente, che utilizza anche il modello attivo parziale `Integer` definito nell'esempio di codice precedente.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="9c9a5-137">In questo esempio, le stringhe che utilizzano espressioni regolari per vari formati di data vengono fornite per personalizzare l'attivo generale ParseRegex.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="9c9a5-138">Il modello attivo Integer viene utilizzato per convertire le stringhe corrispondenti in numeri interi che possono essere passati al costruttore DateTime.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="9c9a5-139">L'output del codice precedente è come segue:</span><span class="sxs-lookup"><span data-stu-id="9c9a5-139">The output of the previous code is as follows:</span></span>

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="9c9a5-140">Criteri attivi non sono limitati solo a espressioni di corrispondenza di schema, è possibile utilizzare anche in consentono di associazioni.</span><span class="sxs-lookup"><span data-stu-id="9c9a5-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="9c9a5-141">L'output del codice precedente è come segue:</span><span class="sxs-lookup"><span data-stu-id="9c9a5-141">The output of the previous code is as follows:</span></span>

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="9c9a5-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c9a5-142">See Also</span></span>
[<span data-ttu-id="9c9a5-143">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="9c9a5-143">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="9c9a5-144">Espressioni match</span><span class="sxs-lookup"><span data-stu-id="9c9a5-144">Match Expressions</span></span>](match-expressions.md)

