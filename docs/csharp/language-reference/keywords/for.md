---
title: istruzione for-riferimenti per C#
ms.date: 06/13/2018
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: db7cecc697a9cc9e5ff6b94b78747b799ed7e505
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401901"
---
# <a name="for-c-reference"></a><span data-ttu-id="70394-102">for (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="70394-102">for (C# reference)</span></span>

<span data-ttu-id="70394-103">L'istruzione `for` esegue un'istruzione o un blocco di istruzioni mentre un'espressione booleana specificata restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="70394-103">The `for` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span>

<span data-ttu-id="70394-104">In un punto qualsiasi all'interno del blocco dell'istruzione `for` è possibile uscire dal ciclo usando l'istruzione [break](break.md) o passare all'iterazione successiva nel ciclo con l'istruzione [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="70394-104">At any point within the `for` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="70394-105">È anche possibile uscire `for` da un ciclo tramite le istruzioni [goto](goto.md), [return](return.md)o [throw](throw.md) .</span><span class="sxs-lookup"><span data-stu-id="70394-105">You can also exit a `for` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="structure-of-the-for-statement"></a><span data-ttu-id="70394-106">Struttura dell'istruzione `for`</span><span class="sxs-lookup"><span data-stu-id="70394-106">Structure of the `for` statement</span></span>

<span data-ttu-id="70394-107">L'istruzione `for` definisce le sezioni *inizializzatore*, *condizione* e *iteratore*:</span><span class="sxs-lookup"><span data-stu-id="70394-107">The `for` statement defines *initializer*, *condition*, and *iterator* sections:</span></span>

```csharp
for (initializer; condition; iterator)
    body
```

<span data-ttu-id="70394-108">Le tre sezioni sono facoltative.</span><span class="sxs-lookup"><span data-stu-id="70394-108">All three sections are optional.</span></span> <span data-ttu-id="70394-109">Il corpo del ciclo è un'istruzione o un blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="70394-109">The body of the loop is either a statement or a block of statements.</span></span>

<span data-ttu-id="70394-110">L'esempio seguente illustra l'istruzione `for` con tutte le sezioni definite:</span><span class="sxs-lookup"><span data-stu-id="70394-110">The following example shows the `for` statement with all of the sections defined:</span></span>

[!code-csharp-interactive[for loop example](snippets/IterationKeywordsExamples.cs#5)]

### <a name="the-initializer-section"></a><span data-ttu-id="70394-111">Sezione *inizializzatore*</span><span class="sxs-lookup"><span data-stu-id="70394-111">The *initializer* section</span></span>

<span data-ttu-id="70394-112">Le istruzioni nella sezione *inizializzatore* vengono eseguite una sola volta, prima dell'avvio del ciclo.</span><span class="sxs-lookup"><span data-stu-id="70394-112">The statements in the *initializer* section are executed only once, before entering the loop.</span></span> <span data-ttu-id="70394-113">La sezione *inizializzatore* può essere costituita da quanto segue:</span><span class="sxs-lookup"><span data-stu-id="70394-113">The *initializer* section is either of the following:</span></span>

- <span data-ttu-id="70394-114">Dichiarazione e inizializzazione di una variabile di ciclo locale, non accessibile dall'esterno del ciclo stesso.</span><span class="sxs-lookup"><span data-stu-id="70394-114">The declaration and initialization of a local loop variable, which can't be accessed from outside the loop.</span></span>

- <span data-ttu-id="70394-115">Zero o più istruzioni, ricavate dal seguente elenco, separate da virgole:</span><span class="sxs-lookup"><span data-stu-id="70394-115">Zero or more statement expressions from the following list, separated by commas:</span></span>

  - <span data-ttu-id="70394-116">Istruzione di [assegnazione](../operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="70394-116">[assignment](../operators/assignment-operator.md) statement</span></span>

  - <span data-ttu-id="70394-117">Chiamata di un metodo</span><span class="sxs-lookup"><span data-stu-id="70394-117">invocation of a method</span></span>

  - <span data-ttu-id="70394-118">Espressione di [incremento](../operators/arithmetic-operators.md#increment-operator-) in forma prefissa o suffissa, ad esempio `++i` o `i++`</span><span class="sxs-lookup"><span data-stu-id="70394-118">prefix or postfix [increment](../operators/arithmetic-operators.md#increment-operator-) expression, such as `++i` or `i++`</span></span>

  - <span data-ttu-id="70394-119">Espressione di [decremento](../operators/arithmetic-operators.md#decrement-operator---) in forma prefissa o suffissa, ad esempio `--i` o `i--`</span><span class="sxs-lookup"><span data-stu-id="70394-119">prefix or postfix [decrement](../operators/arithmetic-operators.md#decrement-operator---) expression, such as `--i` or `i--`</span></span>

  - <span data-ttu-id="70394-120">Creazione di un oggetto con l'operatore [new](../operators/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="70394-120">creation of an object by using the [new](../operators/new-operator.md) operator</span></span>

  - <span data-ttu-id="70394-121">Espressione [await](../operators/await.md)</span><span class="sxs-lookup"><span data-stu-id="70394-121">[await](../operators/await.md) expression</span></span>

<span data-ttu-id="70394-122">La sezione *inizializzatore* dell'esempio precedente dichiara e inizializza la variabile di ciclo locale `i`:</span><span class="sxs-lookup"><span data-stu-id="70394-122">The *initializer* section in the example above declares and initializes the local loop variable `i`:</span></span>

```csharp
int i = 0
```

### <a name="the-condition-section"></a><span data-ttu-id="70394-123">Sezione *condizione*</span><span class="sxs-lookup"><span data-stu-id="70394-123">The *condition* section</span></span>

<span data-ttu-id="70394-124">La sezione *condizione*, se presente, deve essere un'espressione booleana.</span><span class="sxs-lookup"><span data-stu-id="70394-124">The *condition* section, if present, must be a boolean expression.</span></span> <span data-ttu-id="70394-125">Tale espressione viene valutata prima di ogni iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="70394-125">That expression is evaluated before every loop iteration.</span></span> <span data-ttu-id="70394-126">Se la sezione *condizione* non è presente o l'espressione booleana restituisce `true`, viene eseguita la successiva iterazione del ciclo; in caso contrario, si esce dal ciclo.</span><span class="sxs-lookup"><span data-stu-id="70394-126">If the *condition* section is not present or the boolean expression evaluates to `true`, the next loop iteration is executed; otherwise, the loop is exited.</span></span>

<span data-ttu-id="70394-127">La sezione *condizione* dell'esempio precedente determina se il ciclo termina in base al valore della variabile di ciclo locale:</span><span class="sxs-lookup"><span data-stu-id="70394-127">The *condition* section in the example above determines if the loop terminates based on the value of the local loop variable:</span></span>

```csharp
i < 5
```

### <a name="the-iterator-section"></a><span data-ttu-id="70394-128">Sezione *iteratore*</span><span class="sxs-lookup"><span data-stu-id="70394-128">The *iterator* section</span></span>

<span data-ttu-id="70394-129">La sezione *iteratore* definisce cosa accade dopo ogni iterazione del corpo del ciclo.</span><span class="sxs-lookup"><span data-stu-id="70394-129">The *iterator* section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="70394-130">La sezione dell' *iteratore* contiene zero o più delle espressioni di istruzione seguenti, separate da virgole:</span><span class="sxs-lookup"><span data-stu-id="70394-130">The *iterator* section contains zero or more of the following statement expressions, separated by commas:</span></span>

- <span data-ttu-id="70394-131">Istruzione di [assegnazione](../operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="70394-131">[assignment](../operators/assignment-operator.md) statement</span></span>

- <span data-ttu-id="70394-132">Chiamata di un metodo</span><span class="sxs-lookup"><span data-stu-id="70394-132">invocation of a method</span></span>

- <span data-ttu-id="70394-133">Espressione di [incremento](../operators/arithmetic-operators.md#increment-operator-) in forma prefissa o suffissa, ad esempio `++i` o `i++`</span><span class="sxs-lookup"><span data-stu-id="70394-133">prefix or postfix [increment](../operators/arithmetic-operators.md#increment-operator-) expression, such as `++i` or `i++`</span></span>

- <span data-ttu-id="70394-134">Espressione di [decremento](../operators/arithmetic-operators.md#decrement-operator---) in forma prefissa o suffissa, ad esempio `--i` o `i--`</span><span class="sxs-lookup"><span data-stu-id="70394-134">prefix or postfix [decrement](../operators/arithmetic-operators.md#decrement-operator---) expression, such as `--i` or `i--`</span></span>

- <span data-ttu-id="70394-135">Creazione di un oggetto con l'operatore [new](../operators/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="70394-135">creation of an object by using the [new](../operators/new-operator.md) operator</span></span>

- <span data-ttu-id="70394-136">Espressione [await](../operators/await.md)</span><span class="sxs-lookup"><span data-stu-id="70394-136">[await](../operators/await.md) expression</span></span>

<span data-ttu-id="70394-137">La sezione *iteratore* dell'esempio precedente incrementa la variabile di ciclo locale:</span><span class="sxs-lookup"><span data-stu-id="70394-137">The *iterator* section in the example above increments the local loop variable:</span></span>

```csharp
i++
```

## <a name="examples"></a><span data-ttu-id="70394-138">Esempi</span><span class="sxs-lookup"><span data-stu-id="70394-138">Examples</span></span>

<span data-ttu-id="70394-139">L'esempio seguente illustra alcuni utilizzi meno comuni delle sezioni dell'istruzione `for`: assegnazione di un valore a una variabile di ciclo esterna nella sezione *inizializzatore*, chiamata di un metodo sia nella sezione *inizializzatore* che nella sezione *iteratore* e modifica dei valori di due variabili nella sezione *iteratore*.</span><span class="sxs-lookup"><span data-stu-id="70394-139">The following example illustrates several less common usages of the `for` statement sections: assigning a value to an external loop variable in the *initializer* section, invoking a method in both the *initializer* and the *iterator* sections, and changing the values of two variables in the *iterator* section.</span></span> <span data-ttu-id="70394-140">Selezionare **Esegui** per eseguire il codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="70394-140">Select **Run** to run the example code.</span></span> <span data-ttu-id="70394-141">Dopo l'esecuzione è possibile modificare il codice ed eseguirlo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="70394-141">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[not typical for loop example](snippets/IterationKeywordsExamples.cs#6)]

<span data-ttu-id="70394-142">L'esempio seguente definisce il ciclo `for` infinito:</span><span class="sxs-lookup"><span data-stu-id="70394-142">The following example defines the infinite `for` loop:</span></span>

[!code-csharp[infinite for loop example](snippets/IterationKeywordsExamples.cs#7)]

## <a name="c-language-specification"></a><span data-ttu-id="70394-143">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="70394-143">C# language specification</span></span>

<span data-ttu-id="70394-144">Per altre informazioni, vedere la sezione [L'istruzione for](~/_csharplang/spec/statements.md#the-for-statement) della [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="70394-144">For more information, see [The for statement](~/_csharplang/spec/statements.md#the-for-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="70394-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70394-145">See also</span></span>

- [<span data-ttu-id="70394-146">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="70394-146">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="70394-147">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="70394-147">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="70394-148">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="70394-148">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="70394-149">foreach, in</span><span class="sxs-lookup"><span data-stu-id="70394-149">foreach, in</span></span>](foreach-in.md)
