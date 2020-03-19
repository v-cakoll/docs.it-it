---
title: Criteri attivi
description: Informazioni su come usare i modelli attivi per definire le partizioni denominate che suddividono i dati di input nel linguaggio di programmazione F .
ms.date: 05/16/2016
ms.openlocfilehash: 898ef201369683bfd49d53e863e86f919f5837fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187065"
---
# <a name="active-patterns"></a><span data-ttu-id="ce7c4-103">Criteri attivi</span><span class="sxs-lookup"><span data-stu-id="ce7c4-103">Active Patterns</span></span>

<span data-ttu-id="ce7c4-104">*I modelli attivi* consentono di definire partizioni denominate che suddividono i dati di input, in modo da poter utilizzare questi nomi in un'espressione di criteri di ricerca come per un'unione discriminata.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="ce7c4-105">È possibile usare i criteri attivi per decomporre i dati in modo personalizzato per ogni partizione.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="ce7c4-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce7c4-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="ce7c4-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ce7c4-107">Remarks</span></span>

<span data-ttu-id="ce7c4-108">Nella sintassi precedente, gli identificatori sono nomi per le partizioni dei dati di input rappresentati da *argomenti*o, in altre parole, i nomi per i sottoinsiemi del set di tutti i valori degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="ce7c4-109">In una definizione di modello attivo possono essere presenti fino a sette partizioni.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="ce7c4-110">*L'espressione* descrive la forma in cui scomporre i dati.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="ce7c4-111">È possibile usare una definizione di modello attivo per definire le regole per determinare a quali partizioni denominate appartengono i valori assegnati come argomenti.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="ce7c4-112">I simboli (sezione e ) sono detti clip di *banana* e la funzione creata da questo tipo di rilegatura let è chiamata *sistema di riconoscimento attivo.*</span><span class="sxs-lookup"><span data-stu-id="ce7c4-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="ce7c4-113">Ad esempio, si consideri il seguente modello attivo con un argomento.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="ce7c4-114">È possibile utilizzare il modello attivo in un'espressione di criteri di ricerca, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="ce7c4-115">L'output di questo programma è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ce7c4-115">The output of this program is as follows:</span></span>

```console
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="ce7c4-116">Un altro utilizzo dei modelli attivi consiste nel scomporre i tipi di dati in più modi, ad esempio quando gli stessi dati sottostanti hanno diverse rappresentazioni possibili.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="ce7c4-117">Ad esempio, `Color` un oggetto può essere scomposto in una rappresentazione RGB o HSB.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="ce7c4-118">L'output del programma di cui sopra è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ce7c4-118">The output of the above program is as follows:</span></span>

```console
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

<span data-ttu-id="ce7c4-119">In combinazione, questi due modi di utilizzare i modelli attivi consentono di partizionare e scomporre i dati nel formato appropriato ed eseguire i calcoli appropriati sui dati appropriati nella forma più conveniente per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="ce7c4-120">Le espressioni di criteri di ricerca risultanti consentono di scrivere i dati in modo pratico e molto leggibile e che semplifica notevolmente il codice di analisi dei dati e di diramazione potenzialmente complesso.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="ce7c4-121">Modelli attivi parziali</span><span class="sxs-lookup"><span data-stu-id="ce7c4-121">Partial Active Patterns</span></span>

<span data-ttu-id="ce7c4-122">A volte, è necessario partizionare solo una parte dello spazio di input.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="ce7c4-123">In tal caso, si scrive un set di modelli parziali ognuno dei quali corrisponde ad alcuni input ma non corrisponde ad altri input.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="ce7c4-124">I modelli attivi che non sempre producono un valore sono detti *modelli attivi parziali*; hanno un valore restituito che è un tipo di opzione.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="ce7c4-125">Per definire un modello attivo parziale,\_si utilizza un carattere jolly ( ) alla fine dell'elenco dei motivi all'interno delle clip di banana.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="ce7c4-126">Il codice seguente illustra l'uso di un modello attivo parziale.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="ce7c4-127">L'output dell'esempio precedente è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ce7c4-127">The output of the previous example is as follows:</span></span>

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="ce7c4-128">Quando si usano modelli attivi parziali, a volte le singole scelte possono essere disgiunte o che si escludono a vicenda, ma non è necessario esserlo.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="ce7c4-129">Nell'esempio seguente, il modello Square e il modello Cube non sono disgiunti, perché alcuni numeri sono entrambi quadrati e cubi, ad esempio 64.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="ce7c4-130">Il programma seguente utilizza il modello AND per combinare i modelli Square e Cube.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="ce7c4-131">Stampa tutti i numeri interi fino a 1000 che sono sia quadrati che cubi, così come quelli che sono solo cubi.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-131">It prints out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="ce7c4-132">L'output è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ce7c4-132">The output is as follows:</span></span>

```console
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

## <a name="parameterized-active-patterns"></a><span data-ttu-id="ce7c4-133">Modelli attivi con parametriParameterized Active Patterns</span><span class="sxs-lookup"><span data-stu-id="ce7c4-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="ce7c4-134">I modelli attivi accettano sempre almeno un argomento per l'elemento corrispondente, ma possono accettare anche argomenti aggiuntivi, nel qual caso si applica il *modello attivo* con parametri name.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="ce7c4-135">Argomenti aggiuntivi consentono di specializzata in un modello generale.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="ce7c4-136">Ad esempio, i modelli attivi che usano espressioni regolari per analizzare le stringhe spesso includono l'espressione `Integer` regolare come parametro aggiuntivo, come nel codice seguente, che usa anche il modello attivo parziale definito nell'esempio di codice precedente.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="ce7c4-137">In questo esempio vengono fornite stringhe che utilizzano espressioni regolari per vari formati di data per personalizzare il modello attivo ParseRegex generale.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="ce7c4-138">Il modello attivo Integer viene utilizzato per convertire le stringhe corrispondenti in numeri interi che possono essere passati al costruttore DateTime.The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="ce7c4-139">L'output del codice precedente è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ce7c4-139">The output of the previous code is as follows:</span></span>

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="ce7c4-140">I modelli attivi non sono limitati solo alle espressioni di criteri di ricerca, è anche possibile usarli nelle let-bindings.</span><span class="sxs-lookup"><span data-stu-id="ce7c4-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="ce7c4-141">L'output del codice precedente è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ce7c4-141">The output of the previous code is as follows:</span></span>

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="ce7c4-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce7c4-142">See also</span></span>

- [<span data-ttu-id="ce7c4-143">Guida di riferimento al linguaggio F</span><span class="sxs-lookup"><span data-stu-id="ce7c4-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="ce7c4-144">Espressioni match</span><span class="sxs-lookup"><span data-stu-id="ce7c4-144">Match Expressions</span></span>](match-expressions.md)
