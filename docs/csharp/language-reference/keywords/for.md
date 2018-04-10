---
title: for (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
caps.latest.revision: 39
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cb7e83733fe026658f502b430975a0f8a27e9df3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="for-c-reference"></a><span data-ttu-id="8bc58-102">for (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="8bc58-102">for (C# Reference)</span></span>
<span data-ttu-id="8bc58-103">Usando un ciclo `for`, è possibile eseguire ripetutamente un'istruzione o un blocco di istruzioni fino a quando un'espressione specificata restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="8bc58-103">By using a `for` loop, you can run a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="8bc58-104">Questo tipo di ciclo è utile per eseguire l'iterazione su matrici e per altre applicazioni in cui si conosce in anticipo quante volte il ciclo deve eseguire l'iterazione.</span><span class="sxs-lookup"><span data-stu-id="8bc58-104">This kind of loop is useful for iterating over arrays and for other applications in which you know in advance how many times you want the loop to iterate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8bc58-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="8bc58-105">Example</span></span>  
 <span data-ttu-id="8bc58-106">Nell'esempio seguente il valore `i` viene scritto nella console e viene incrementato di 1 durante ogni iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="8bc58-106">In the following example, the value of `i` is written to the console and incremented by 1 during each iteration of the loop.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]  
  
 <span data-ttu-id="8bc58-107">L'istruzione `for` nell'esempio precedente esegue le azioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8bc58-107">The `for` statement in the previous example performs the following actions.</span></span>  
  
1.  <span data-ttu-id="8bc58-108">Prima viene stabilito il valore iniziale della variabile `i`.</span><span class="sxs-lookup"><span data-stu-id="8bc58-108">First, the initial value of variable `i` is established.</span></span> <span data-ttu-id="8bc58-109">Questo passaggio viene eseguito una sola volta, indipendentemente da quante volte viene ripetuto il ciclo.</span><span class="sxs-lookup"><span data-stu-id="8bc58-109">This step happens only once, regardless of how many times the loop repeats.</span></span> <span data-ttu-id="8bc58-110">È possibile pensare all'inizializzazione come a un'operazione che viene eseguita all'esterno del processo di ciclo.</span><span class="sxs-lookup"><span data-stu-id="8bc58-110">You can think of this initialization as happening outside the looping process.</span></span>  
  
2.  <span data-ttu-id="8bc58-111">Per valutare la condizione (`i <= 5`), il valore di `i` viene confrontato con 5.</span><span class="sxs-lookup"><span data-stu-id="8bc58-111">To evaluate the condition (`i <= 5`), the value of `i` is compared to 5.</span></span>  
  
    -   <span data-ttu-id="8bc58-112">Se `i` è minore o uguale a 5, la condizione restituisce `true` e si verificano le azioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8bc58-112">If `i` is less than or equal to 5, the condition evaluates to `true`, and the following actions occur.</span></span>  
  
        1.  <span data-ttu-id="8bc58-113">L'istruzione `Console.WriteLine` nel corpo del ciclo visualizza il valore di `i`.</span><span class="sxs-lookup"><span data-stu-id="8bc58-113">The `Console.WriteLine` statement in the body of the loop displays the value of `i`.</span></span>  
  
        2.  <span data-ttu-id="8bc58-114">Il valore di `i` viene incrementato di 1.</span><span class="sxs-lookup"><span data-stu-id="8bc58-114">The value of `i` is incremented by 1.</span></span>  
  
        3.  <span data-ttu-id="8bc58-115">Il ciclo ritorna all'inizio del passaggio 2 per valutare nuovamente la condizione.</span><span class="sxs-lookup"><span data-stu-id="8bc58-115">The loop returns to the start of step 2 to evaluate the condition again.</span></span>  
  
    -   <span data-ttu-id="8bc58-116">Se `i` è maggiore di 5, la condizione restituisce `false` e si esce dal ciclo.</span><span class="sxs-lookup"><span data-stu-id="8bc58-116">If `i` is greater than 5, the condition evaluates to `false`, and you exit the loop.</span></span>  
  
 <span data-ttu-id="8bc58-117">Si noti che, se il valore iniziale di `i` è maggiore di 5, il corpo del ciclo non viene eseguito neppure una volta.</span><span class="sxs-lookup"><span data-stu-id="8bc58-117">Note that, if the initial value of `i` is greater than 5, the body of the loop doesn't run even once.</span></span>  
  
 <span data-ttu-id="8bc58-118">Ogni istruzione `for` definisce le sezioni di inizializzatore, condizione e iteratore.</span><span class="sxs-lookup"><span data-stu-id="8bc58-118">Every `for` statement defines initializer, condition, and iterator sections.</span></span> <span data-ttu-id="8bc58-119">In queste sezioni viene solitamente definito quante volte il ciclo esegue l'iterazione.</span><span class="sxs-lookup"><span data-stu-id="8bc58-119">These sections usually determine how many times the loop iterates.</span></span>  
  
```csharp  
for (initializer; condition; iterator)  
    body  
```  
  
 <span data-ttu-id="8bc58-120">Gli scopi delle sezioni sono i seguenti.</span><span class="sxs-lookup"><span data-stu-id="8bc58-120">The sections serve the following purposes.</span></span>  
  
-   <span data-ttu-id="8bc58-121">Nella sezione dell'inizializzatore vengono impostate le condizioni iniziali.</span><span class="sxs-lookup"><span data-stu-id="8bc58-121">The initializer section sets the initial conditions.</span></span> <span data-ttu-id="8bc58-122">Le istruzioni in questa sezione sono eseguite una sola volta, prima che inizi il ciclo.</span><span class="sxs-lookup"><span data-stu-id="8bc58-122">The statements in this section run only once, before you enter the loop.</span></span> <span data-ttu-id="8bc58-123">Questa sezione può contenere solo una delle due opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8bc58-123">The section can contain only one of the following two options.</span></span>  
  
    -   <span data-ttu-id="8bc58-124">Dichiarazione e inizializzazione di una variabile di ciclo locale, come illustrato nel primo esempio (`int i = 1`).</span><span class="sxs-lookup"><span data-stu-id="8bc58-124">The declaration and initialization of a local loop variable, as the first example shows (`int i = 1`).</span></span> <span data-ttu-id="8bc58-125">La variabile è locale rispetto al ciclo e non è possibile accedervi dall'esterno del ciclo.</span><span class="sxs-lookup"><span data-stu-id="8bc58-125">The variable is local to the loop and can't be accessed from outside the loop.</span></span>  
  
    -   <span data-ttu-id="8bc58-126">Zero o più istruzioni, ricavate dal seguente elenco, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="8bc58-126">Zero or more statement expressons from the following list, separated by commas.</span></span>  
  
        -   <span data-ttu-id="8bc58-127">Istruzione di [assegnazione](../../../csharp/language-reference/operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="8bc58-127">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
        -   <span data-ttu-id="8bc58-128">Chiamata di un metodo</span><span class="sxs-lookup"><span data-stu-id="8bc58-128">invocation of a method</span></span>  
  
        -   <span data-ttu-id="8bc58-129">Espressione di [incremento](../../../csharp/language-reference/operators/increment-operator.md) in forma prefissa o suffissa, ad esempio `++i` o `i++`</span><span class="sxs-lookup"><span data-stu-id="8bc58-129">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
        -   <span data-ttu-id="8bc58-130">Espressione di [decremento](../../../csharp/language-reference/operators/decrement-operator.md) in forma prefissa o suffissa, ad esempio `--i` o `i--`</span><span class="sxs-lookup"><span data-stu-id="8bc58-130">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
        -   <span data-ttu-id="8bc58-131">Creazione di un oggetto con [new](../../../csharp/language-reference/keywords/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="8bc58-131">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
        -   <span data-ttu-id="8bc58-132">Espressione [await](../../../csharp/language-reference/keywords/await.md)</span><span class="sxs-lookup"><span data-stu-id="8bc58-132">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="8bc58-133">La sezione della condizione contiene un'espressione booleana valutata per determinare se uscire dal ciclo oppure ripeterlo.</span><span class="sxs-lookup"><span data-stu-id="8bc58-133">The condition section contains a boolean expression that’s evaluated to determine whether the loop should exit or should run again.</span></span>  
  
-   <span data-ttu-id="8bc58-134">Nella sezione dell'iteratore viene definito cosa accade dopo ogni iterazione del corpo del ciclo.</span><span class="sxs-lookup"><span data-stu-id="8bc58-134">The iterator section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="8bc58-135">Questa sezione contiene zero o più delle espressioni di istruzioni seguenti, separate da virgole:</span><span class="sxs-lookup"><span data-stu-id="8bc58-135">The iterator section contains zero or more of the following statement expressions, separated by commas:</span></span>  
  
    -   <span data-ttu-id="8bc58-136">Istruzione di [assegnazione](../../../csharp/language-reference/operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="8bc58-136">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
    -   <span data-ttu-id="8bc58-137">Chiamata di un metodo</span><span class="sxs-lookup"><span data-stu-id="8bc58-137">invocation of a method</span></span>  
  
    -   <span data-ttu-id="8bc58-138">Espressione di [incremento](../../../csharp/language-reference/operators/increment-operator.md) in forma prefissa o suffissa, ad esempio `++i` o `i++`</span><span class="sxs-lookup"><span data-stu-id="8bc58-138">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
    -   <span data-ttu-id="8bc58-139">Espressione di [decremento](../../../csharp/language-reference/operators/decrement-operator.md) in forma prefissa o suffissa, ad esempio `--i` o `i--`</span><span class="sxs-lookup"><span data-stu-id="8bc58-139">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
    -   <span data-ttu-id="8bc58-140">Creazione di un oggetto con [new](../../../csharp/language-reference/keywords/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="8bc58-140">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
    -   <span data-ttu-id="8bc58-141">Espressione [await](../../../csharp/language-reference/keywords/await.md)</span><span class="sxs-lookup"><span data-stu-id="8bc58-141">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="8bc58-142">Il corpo del ciclo è costituito da un'istruzione, un'istruzione vuota o un blocco di istruzioni, creato racchiudendo tra parentesi zero o più istruzioni.</span><span class="sxs-lookup"><span data-stu-id="8bc58-142">The body of the loop consists of a statement, an empty statement, or a block of statements, which you create by enclosing zero or more statements in braces.</span></span>  
  
     <span data-ttu-id="8bc58-143">È possibile interrompere un ciclo `for` con la parola chiave [break](../../../csharp/language-reference/keywords/break.md) oppure è possibile usare la parola chiave [continue](../../../csharp/language-reference/keywords/continue.md) per passare all'iterazione successiva.</span><span class="sxs-lookup"><span data-stu-id="8bc58-143">You can break out of a `for` loop by using the [break](../../../csharp/language-reference/keywords/break.md) keyword, or you can step to the next iteration by using the [continue](../../../csharp/language-reference/keywords/continue.md) keyword.</span></span> <span data-ttu-id="8bc58-144">Si può uscire da un ciclo anche usando l'istruzione [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md).</span><span class="sxs-lookup"><span data-stu-id="8bc58-144">You also can exit any loop by using a [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement.</span></span>  
  
 <span data-ttu-id="8bc58-145">Nel primo esempio di questo argomento viene illustrato il tipo di ciclo `for` più comune, che definisce le opzioni seguenti per le sezioni.</span><span class="sxs-lookup"><span data-stu-id="8bc58-145">The first example in this topic shows the most typical kind of `for` loop, which makes the following choices for the sections.</span></span>  
  
-   <span data-ttu-id="8bc58-146">L'inizializzatore dichiara e inizializza una variabile di ciclo locale, `i`, che conta le iterazioni del ciclo.</span><span class="sxs-lookup"><span data-stu-id="8bc58-146">The initializer declares and initializes a local loop variable, `i`, that maintains a count of the iterations of the loop.</span></span>  
  
-   <span data-ttu-id="8bc58-147">La condizione confronta il valore della variabile del ciclo con il valore finale noto 5.</span><span class="sxs-lookup"><span data-stu-id="8bc58-147">The condition checks the value of the loop variable against a known final value, 5.</span></span>  
  
-   <span data-ttu-id="8bc58-148">Nella sezione dell'iteratore viene usata un'istruzione d'incremento in forma suffissa, `i++`, per calcolare ogni iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="8bc58-148">The iterator section uses a postfix increment statement, `i++`, to tally each iteration of the loop.</span></span>  
  
 <span data-ttu-id="8bc58-149">L'esempio seguente illustra alcuni opzioni meno comuni: assegnazione di un valore a una variabile di ciclo esterno nella sezione dell'inizializzatore, chiamata del metodo `Console.WriteLine` nella sezione dell'inizializzatore e in quella dell'iteratore e modifica dei valori di due variabili nella sezione dell'iteratore.</span><span class="sxs-lookup"><span data-stu-id="8bc58-149">The following example illustrates several less common choices: assigning a value to an external loop variable in the initializer section,  invoking the `Console.WriteLine` method in both the initializer and the iterator sections, and changing the values of two variables in the iterator section.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]  
  
 <span data-ttu-id="8bc58-150">Tutte le espressioni che definiscono un'istruzione `for` sono facoltative.</span><span class="sxs-lookup"><span data-stu-id="8bc58-150">All of the expressions that define a `for` statement are optional.</span></span> <span data-ttu-id="8bc58-151">Ad esempio, l'istruzione seguente crea un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="8bc58-151">For example, the following statement creates an infinite loop.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8bc58-152">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="8bc58-152">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8bc58-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bc58-153">See Also</span></span>  
 [<span data-ttu-id="8bc58-154">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="8bc58-154">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8bc58-155">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="8bc58-155">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8bc58-156">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="8bc58-156">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="8bc58-157">foreach, in</span><span class="sxs-lookup"><span data-stu-id="8bc58-157">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
 [<span data-ttu-id="8bc58-158">Istruzione for (C++)</span><span class="sxs-lookup"><span data-stu-id="8bc58-158">for Statement (C++)</span></span>](/cpp/cpp/for-statement-cpp)  
 [<span data-ttu-id="8bc58-159">Istruzioni di iterazione</span><span class="sxs-lookup"><span data-stu-id="8bc58-159">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
