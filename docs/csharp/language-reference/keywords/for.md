---
title: for (Riferimenti per C#)
ms.date: 06/13/2018
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: beac7727c8ce83d8ea20f0fc578f80ceef3053e7
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208010"
---
# <a name="for-c-reference"></a><span data-ttu-id="832f6-102">for (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="832f6-102">for (C# reference)</span></span>

<span data-ttu-id="832f6-103">L'istruzione `for` esegue un'istruzione o un blocco di istruzioni mentre un'espressione booleana specificata restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="832f6-103">The `for` statement executes a statement or a block of statements while a specified boolean expression evaluates to `true`.</span></span>

<span data-ttu-id="832f6-104">In un punto qualsiasi all'interno del blocco dell'istruzione `for` è possibile uscire dal ciclo usando l'istruzione [break](break.md) o passare all'iterazione successiva nel ciclo con l'istruzione [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="832f6-104">At any point within the `for` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="832f6-105">Si può uscire da un ciclo `for` anche usando l'istruzione [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="832f6-105">You also can exit a `for` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>
  
## <a name="structure-of-the-for-statement"></a><span data-ttu-id="832f6-106">Struttura dell'istruzione `for`</span><span class="sxs-lookup"><span data-stu-id="832f6-106">Structure of the `for` statement</span></span>

<span data-ttu-id="832f6-107">L'istruzione `for` definisce le sezioni *inizializzatore*, *condizione* e *iteratore*:</span><span class="sxs-lookup"><span data-stu-id="832f6-107">The `for` statement defines *initializer*, *condition*, and *iterator* sections:</span></span>
  
```csharp
for (initializer; condition; iterator)  
    body  
```

<span data-ttu-id="832f6-108">Tutte le tre sezioni sono facoltative.</span><span class="sxs-lookup"><span data-stu-id="832f6-108">All three sections are optional.</span></span> <span data-ttu-id="832f6-109">Il corpo del ciclo è un'istruzione o un blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="832f6-109">The body of the loop is either a statement or a block of statements.</span></span>

<span data-ttu-id="832f6-110">L'esempio seguente illustra l'istruzione `for` con tutte le sezioni definite:</span><span class="sxs-lookup"><span data-stu-id="832f6-110">The following example shows the `for` statement with all of the sections defined:</span></span>

[!code-csharp-interactive[for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#5)]

### <a name="the-initializer-section"></a><span data-ttu-id="832f6-111">Sezione *inizializzatore*</span><span class="sxs-lookup"><span data-stu-id="832f6-111">The *initializer* section</span></span>

<span data-ttu-id="832f6-112">Le istruzioni nella sezione *inizializzatore* vengono eseguite una sola volta, prima dell'avvio del ciclo.</span><span class="sxs-lookup"><span data-stu-id="832f6-112">The statements in the *initializer* section are executed only once, before entering the loop.</span></span> <span data-ttu-id="832f6-113">La sezione *inizializzatore* può essere costituita da quanto segue:</span><span class="sxs-lookup"><span data-stu-id="832f6-113">The *initializer* section is either of the following:</span></span>

- <span data-ttu-id="832f6-114">Dichiarazione e inizializzazione di una variabile di ciclo locale, non accessibile dall'esterno del ciclo stesso.</span><span class="sxs-lookup"><span data-stu-id="832f6-114">The declaration and initialization of a local loop variable, which can't be accessed from outside the loop.</span></span>

- <span data-ttu-id="832f6-115">Zero o più istruzioni, ricavate dal seguente elenco, separate da virgole:</span><span class="sxs-lookup"><span data-stu-id="832f6-115">Zero or more statement expressions from the following list, separated by commas:</span></span>

  - <span data-ttu-id="832f6-116">Istruzione di [assegnazione](../operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="832f6-116">[assignment](../operators/assignment-operator.md) statement</span></span>

  - <span data-ttu-id="832f6-117">Chiamata di un metodo</span><span class="sxs-lookup"><span data-stu-id="832f6-117">invocation of a method</span></span>  

  - <span data-ttu-id="832f6-118">Espressione di [incremento](../operators/increment-operator.md) in forma prefissa o suffissa, ad esempio `++i` o `i++`</span><span class="sxs-lookup"><span data-stu-id="832f6-118">prefix or postfix [increment](../operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  

  - <span data-ttu-id="832f6-119">Espressione di [decremento](../operators/decrement-operator.md) in forma prefissa o suffissa, ad esempio `--i` o `i--`</span><span class="sxs-lookup"><span data-stu-id="832f6-119">prefix or postfix [decrement](../operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  

  - <span data-ttu-id="832f6-120">Creazione di un oggetto con la parola chiave [new](new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="832f6-120">creation of an object by using [new](new-operator.md) keyword</span></span>

  - <span data-ttu-id="832f6-121">Espressione [await](await.md)</span><span class="sxs-lookup"><span data-stu-id="832f6-121">[await](await.md) expression</span></span>

<span data-ttu-id="832f6-122">La sezione *inizializzatore* dell'esempio precedente dichiara e inizializza la variabile di ciclo locale `i`:</span><span class="sxs-lookup"><span data-stu-id="832f6-122">The *initializer* section in the example above declares and initializes the local loop variable `i`:</span></span>

```csharp
int i = 0
```

### <a name="the-condition-section"></a><span data-ttu-id="832f6-123">Sezione *condizione*</span><span class="sxs-lookup"><span data-stu-id="832f6-123">The *condition* section</span></span>

<span data-ttu-id="832f6-124">La sezione *condizione*, se presente, deve essere un'espressione booleana.</span><span class="sxs-lookup"><span data-stu-id="832f6-124">The *condition* section, if present, must be a boolean expression.</span></span> <span data-ttu-id="832f6-125">Tale espressione viene valutata prima di ogni iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="832f6-125">That expression is evaluated before every loop iteration.</span></span> <span data-ttu-id="832f6-126">Se la sezione *condizione* non è presente o l'espressione booleana restituisce `true`, viene eseguita la successiva iterazione del ciclo; in caso contrario, si esce dal ciclo.</span><span class="sxs-lookup"><span data-stu-id="832f6-126">If the *condition* section is not present or the boolean expression evaluates to `true`, the next loop iteration is executed; otherwise, the loop is exited.</span></span>

<span data-ttu-id="832f6-127">La sezione *condizione* dell'esempio precedente determina se il ciclo termina in base al valore della variabile di ciclo locale:</span><span class="sxs-lookup"><span data-stu-id="832f6-127">The *condition* section in the example above determines if the loop terminates based on the value of the local loop variable:</span></span>

```csharp
i < 5
```

### <a name="the-iterator-section"></a><span data-ttu-id="832f6-128">Sezione *iteratore*</span><span class="sxs-lookup"><span data-stu-id="832f6-128">The *iterator* section</span></span>

<span data-ttu-id="832f6-129">La sezione *iteratore* definisce cosa accade dopo ogni iterazione del corpo del ciclo.</span><span class="sxs-lookup"><span data-stu-id="832f6-129">The *iterator* section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="832f6-130">Questa sezione contiene zero o più delle espressioni di istruzione seguenti, separate da virgole:</span><span class="sxs-lookup"><span data-stu-id="832f6-130">The *iterator* section contains zero or more of the following statement expressions, separated by commas:</span></span>  

- <span data-ttu-id="832f6-131">Istruzione di [assegnazione](../operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="832f6-131">[assignment](../operators/assignment-operator.md) statement</span></span>

- <span data-ttu-id="832f6-132">Chiamata di un metodo</span><span class="sxs-lookup"><span data-stu-id="832f6-132">invocation of a method</span></span>  

- <span data-ttu-id="832f6-133">Espressione di [incremento](../operators/increment-operator.md) in forma prefissa o suffissa, ad esempio `++i` o `i++`</span><span class="sxs-lookup"><span data-stu-id="832f6-133">prefix or postfix [increment](../operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  

- <span data-ttu-id="832f6-134">Espressione di [decremento](../operators/decrement-operator.md) in forma prefissa o suffissa, ad esempio `--i` o `i--`</span><span class="sxs-lookup"><span data-stu-id="832f6-134">prefix or postfix [decrement](../operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  

- <span data-ttu-id="832f6-135">Creazione di un oggetto con la parola chiave [new](new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="832f6-135">creation of an object by using [new](new-operator.md) keyword</span></span>

- <span data-ttu-id="832f6-136">Espressione [await](await.md)</span><span class="sxs-lookup"><span data-stu-id="832f6-136">[await](await.md) expression</span></span>

<span data-ttu-id="832f6-137">La sezione *iteratore* dell'esempio precedente incrementa la variabile di ciclo locale:</span><span class="sxs-lookup"><span data-stu-id="832f6-137">The *iterator* section in the example above increments the local loop variable:</span></span>

```csharp
i++
```

## <a name="examples"></a><span data-ttu-id="832f6-138">Esempi</span><span class="sxs-lookup"><span data-stu-id="832f6-138">Examples</span></span>

<span data-ttu-id="832f6-139">L'esempio seguente illustra alcuni utilizzi meno comuni delle sezioni dell'istruzione `for`: assegnazione di un valore a una variabile di ciclo esterna nella sezione *inizializzatore*, chiamata di un metodo sia nella sezione *inizializzatore* che nella sezione *iteratore* e modifica dei valori di due variabili nella sezione *iteratore*.</span><span class="sxs-lookup"><span data-stu-id="832f6-139">The following example illustrates several less common usages of the `for` statement sections: assigning a value to an external loop variable in the *initializer* section, invoking a method in both the *initializer* and the *iterator* sections, and changing the values of two variables in the *iterator* section.</span></span> <span data-ttu-id="832f6-140">Selezionare **Esegui** per eseguire il codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="832f6-140">Select **Run** to run the example code.</span></span> <span data-ttu-id="832f6-141">Dopo l'esecuzione è possibile modificare il codice ed eseguirlo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="832f6-141">After that you can modify the code and run it again.</span></span>
  
[!code-csharp-interactive[not typical for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#6)]
  
<span data-ttu-id="832f6-142">L'esempio seguente definisce il ciclo `for` infinito:</span><span class="sxs-lookup"><span data-stu-id="832f6-142">The following example defines the infinite `for` loop:</span></span>
  
[!code-csharp[infinite for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#7)]
  
## <a name="c-language-specification"></a><span data-ttu-id="832f6-143">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="832f6-143">C# language specification</span></span>  

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]
  
## <a name="see-also"></a><span data-ttu-id="832f6-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="832f6-144">See also</span></span>

[<span data-ttu-id="832f6-145">Istruzione for (specifica del linguaggio C#)</span><span class="sxs-lookup"><span data-stu-id="832f6-145">The for statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-for-statement)  
[<span data-ttu-id="832f6-146">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="832f6-146">C# Reference</span></span>](../index.md)  
[<span data-ttu-id="832f6-147">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="832f6-147">C# Programming Guide</span></span>](../../programming-guide/index.md)  
[<span data-ttu-id="832f6-148">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="832f6-148">C# Keywords</span></span>](index.md)  
[<span data-ttu-id="832f6-149">foreach, in</span><span class="sxs-lookup"><span data-stu-id="832f6-149">foreach, in</span></span>](foreach-in.md)  
[<span data-ttu-id="832f6-150">Istruzione for (C++)</span><span class="sxs-lookup"><span data-stu-id="832f6-150">for Statement (C++)</span></span>](/cpp/cpp/for-statement-cpp)  
[<span data-ttu-id="832f6-151">Istruzioni di iterazione</span><span class="sxs-lookup"><span data-stu-id="832f6-151">Iteration Statements</span></span>](iteration-statements.md)
