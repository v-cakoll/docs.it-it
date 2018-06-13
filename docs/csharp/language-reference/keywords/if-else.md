---
title: if-else (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- if_CSharpKeyword
- else
- else_CSharpKeyword
- if
helpviewer_keywords:
- else keyword [C#]
- if keyword [C#]
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
ms.openlocfilehash: eb8fe4c3a02cab8f8c887ec37244bede04b8a663
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218754"
---
# <a name="if-else-c-reference"></a><span data-ttu-id="9128e-102">if-else (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="9128e-102">if-else (C# Reference)</span></span>
<span data-ttu-id="9128e-103">Un'istruzione `if` identifica quale istruzione eseguire in base al valore di un'espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="9128e-103">An `if` statement identifies which statement to run based on the value of a `Boolean` expression.</span></span> <span data-ttu-id="9128e-104">Nell'esempio seguente la variabile `Boolean` `result` viene impostata su `true` e quindi archiviata nell'istruzione `if` .</span><span class="sxs-lookup"><span data-stu-id="9128e-104">In the following example, the `Boolean` variable `result` is set to `true` and then checked in the `if` statement.</span></span> <span data-ttu-id="9128e-105">L'output è `The condition is true`.</span><span class="sxs-lookup"><span data-stu-id="9128e-105">The output is `The condition is true`.</span></span>  
  
 [!code-csharp[csrefKeywordsSelection#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_1.cs)]  
  
 <span data-ttu-id="9128e-106">È possibile eseguire gli esempi di questo argomento posizionandoli nel metodo `Main` di un'app console.</span><span class="sxs-lookup"><span data-stu-id="9128e-106">You can run the examples in this topic by placing them in the `Main` method of a console app.</span></span>  
  
 <span data-ttu-id="9128e-107">Un'istruzione `if` in C# può essere usata in due modi, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9128e-107">An `if` statement in C# can take two forms, as the following example shows.</span></span>  
  
```csharp  
// if-else statement  
if (condition)  
{  
    then-statement;  
}  
else  
{  
    else-statement;  
}  
// Next statement in the program.  
  
// if statement without an else  
if (condition)  
{  
    then-statement;  
}  
// Next statement in the program.  
```  
  
 <span data-ttu-id="9128e-108">In un'istruzione `if-else` se `condition` restituisce true, viene eseguito `then-statement` .</span><span class="sxs-lookup"><span data-stu-id="9128e-108">In an `if-else` statement, if `condition` evaluates to true, the `then-statement` runs.</span></span> <span data-ttu-id="9128e-109">Se `condition` è false, viene eseguito `else-statement` .</span><span class="sxs-lookup"><span data-stu-id="9128e-109">If `condition` is false, the `else-statement` runs.</span></span> <span data-ttu-id="9128e-110">Poiché `condition` non può essere contemporaneamente true e false, `then-statement` e `else-statement` di un'istruzione `if-else` non possono mai essere eseguiti insieme.</span><span class="sxs-lookup"><span data-stu-id="9128e-110">Because `condition` can’t be simultaneously true and false, the `then-statement` and the `else-statement` of an `if-else` statement can never both run.</span></span> <span data-ttu-id="9128e-111">Dopo l'esecuzione di `then-statement` o `else-statement` il controllo viene trasferito all'istruzione successiva dopo l'istruzione `if` .</span><span class="sxs-lookup"><span data-stu-id="9128e-111">After the `then-statement` or the `else-statement` runs, control is transferred to the next statement after the `if` statement.</span></span>  
  
 <span data-ttu-id="9128e-112">In un'istruzione `if` che non include un'istruzione `else` , se `condition` è true, viene eseguito `then-statement` .</span><span class="sxs-lookup"><span data-stu-id="9128e-112">In an `if` statement that doesn’t include an `else` statement, if `condition` is true, the `then-statement` runs.</span></span> <span data-ttu-id="9128e-113">Se `condition` è false, il controllo viene trasferito all'istruzione successiva dopo l'istruzione `if` .</span><span class="sxs-lookup"><span data-stu-id="9128e-113">If `condition` is false, control is transferred to the next statement after the `if` statement.</span></span>  
  
 <span data-ttu-id="9128e-114">`then-statement` e `else-statement` possono essere entrambi costituiti da una singola istruzione o da più istruzioni racchiuse tra parentesi graffe (`{}`).</span><span class="sxs-lookup"><span data-stu-id="9128e-114">Both the `then-statement` and the `else-statement` can consist of a single statement or multiple statements that are enclosed in braces (`{}`).</span></span> <span data-ttu-id="9128e-115">Per una singola istruzione le parentesi graffe sono facoltative ma consigliate.</span><span class="sxs-lookup"><span data-stu-id="9128e-115">For a single statement, the braces are optional but recommended.</span></span>  
  
 <span data-ttu-id="9128e-116">L'istruzione o le istruzioni in `then-statement` e `else-statement` possono essere di qualsiasi tipo, compresa un'altra istruzione `if` annidata all'interno dell'istruzione `if` originale.</span><span class="sxs-lookup"><span data-stu-id="9128e-116">The statement or statements in the `then-statement` and the `else-statement` can be of any kind, including another `if` statement nested inside the original `if` statement.</span></span> <span data-ttu-id="9128e-117">Nelle istruzioni `if` annidate ogni clausola `else` appartiene all'ultima istruzione `if` che non ha un'istruzione `else`corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9128e-117">In nested `if` statements, each `else` clause belongs to the last `if` that doesn’t have a corresponding `else`.</span></span> <span data-ttu-id="9128e-118">Nell'esempio seguente viene visualizzato `Result1` se `m > 10` e `n > 20` restituiscono entrambi true.</span><span class="sxs-lookup"><span data-stu-id="9128e-118">In the following example, `Result1` appears if both `m > 10` and `n > 20` evaluate to true.</span></span> <span data-ttu-id="9128e-119">Se `m > 10` è true ma `n > 20` è false, viene visualizzato `Result2` .</span><span class="sxs-lookup"><span data-stu-id="9128e-119">If `m > 10` is true but `n > 20` is false, `Result2` appears.</span></span>  
  
 [!code-csharp[csrefKeywordsSelection#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_2.cs)]  
  
 <span data-ttu-id="9128e-120">Se invece si vuole che venga visualizzato `Result2` quando `(m > 10)` è false, è possibile specificare tale associazione usando le parentesi graffe per stabilire l'inizio e la fine dell'istruzione `if` annidata, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9128e-120">If, instead, you want `Result2` to appear when `(m > 10)` is false, you can specify that association by using braces to establish the start and end of the nested `if` statement, as the following example shows.</span></span>  
  
 [!code-csharp[csrefKeywordsSelection#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_3.cs)]  
  
 <span data-ttu-id="9128e-121">`Result2` viene visualizzato se la condizione `(m > 10)` restituisce false.</span><span class="sxs-lookup"><span data-stu-id="9128e-121">`Result2` appears if the condition `(m > 10)` evaluates to false.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9128e-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="9128e-122">Example</span></span>  
 <span data-ttu-id="9128e-123">Nell'esempio seguente si immette un carattere dalla tastiera e il programma usa un'istruzione `if` annidata per determinare se il carattere di input è un carattere alfabetico.</span><span class="sxs-lookup"><span data-stu-id="9128e-123">In the following example, you enter a character from the keyboard, and the program uses a nested `if` statement to determine whether the input character is an alphabetic character.</span></span> <span data-ttu-id="9128e-124">Se il carattere di input è un carattere alfabetico, il programma verifica se il carattere di input è maiuscolo o minuscolo.</span><span class="sxs-lookup"><span data-stu-id="9128e-124">If the input character is an alphabetic character, the program checks whether the input character is lowercase or uppercase.</span></span> <span data-ttu-id="9128e-125">Viene visualizzato un messaggio per ogni situazione.</span><span class="sxs-lookup"><span data-stu-id="9128e-125">A message appears for each case.</span></span>  
  
 [!code-csharp[csrefKeywordsSelection#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_4.cs)]  
  
## <a name="example"></a><span data-ttu-id="9128e-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="9128e-126">Example</span></span>  
 <span data-ttu-id="9128e-127">È anche possibile annidare un'istruzione `if` all'interno di un blocco else, come illustrato nella parte di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="9128e-127">You also can nest an `if` statement inside an else block, as the following partial code shows.</span></span> <span data-ttu-id="9128e-128">Nell'esempio le istruzioni `if` vengono annidate all'interno di due blocchi else e di un blocco then.</span><span class="sxs-lookup"><span data-stu-id="9128e-128">The example nests `if` statements inside two else blocks and one then block.</span></span> <span data-ttu-id="9128e-129">I commenti specificano che le condizioni sono true o false in ogni blocco.</span><span class="sxs-lookup"><span data-stu-id="9128e-129">The comments specify which conditions are true or false in each block.</span></span>  
  
 [!code-csharp[csrefKeywordsSelection#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_5.cs)]  
  
## <a name="example"></a><span data-ttu-id="9128e-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="9128e-130">Example</span></span>  
 <span data-ttu-id="9128e-131">L'esempio seguente determina se un carattere di input è una lettera minuscola, una lettera maiuscola o un numero.</span><span class="sxs-lookup"><span data-stu-id="9128e-131">The following example determines whether an input character is a lowercase letter, an uppercase letter, or a number.</span></span> <span data-ttu-id="9128e-132">Se tutte e tre le condizioni sono false, il carattere non è un carattere alfanumerico.</span><span class="sxs-lookup"><span data-stu-id="9128e-132">If all three conditions are false, the character isn’t an alphanumeric character.</span></span> <span data-ttu-id="9128e-133">Nell'esempio viene visualizzato un messaggio per ogni situazione.</span><span class="sxs-lookup"><span data-stu-id="9128e-133">The example displays a message for each case.</span></span>  
  
 [!code-csharp[csrefKeywordsSelection#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_6.cs)]  
  
 <span data-ttu-id="9128e-134">Come per un'istruzione nel blocco else o nel blocco then è possibile usare qualsiasi istruzione valida, allo stesso modo per la condizione è possibile usare qualsiasi espressione booleana valida.</span><span class="sxs-lookup"><span data-stu-id="9128e-134">Just as a statement in the else block or the then block can be any valid statement, you can use any valid Boolean expression for the condition.</span></span> <span data-ttu-id="9128e-135">È possibile usare operatori logici quali [&&](../../../csharp/language-reference/operators/conditional-and-operator.md), [&](../../../csharp/language-reference/operators/and-operator.md), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), [&#124;](../../../csharp/language-reference/operators/or-operator.md) e [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span><span class="sxs-lookup"><span data-stu-id="9128e-135">You can use logical operators such as [&&](../../../csharp/language-reference/operators/conditional-and-operator.md), [&](../../../csharp/language-reference/operators/and-operator.md), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), [&#124;](../../../csharp/language-reference/operators/or-operator.md) and [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span></span> <span data-ttu-id="9128e-136">.</span><span class="sxs-lookup"><span data-stu-id="9128e-136">to make compound conditions.</span></span> <span data-ttu-id="9128e-137">Il codice seguente illustra alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="9128e-137">The following code shows examples.</span></span>  
  
```csharp  
// NOT  
bool result = true;  
if (!result)  
{  
    Console.WriteLine("The condition is true (result is false).");  
}  
else  
{  
    Console.WriteLine("The condition is false (result is true).");  
}  
  
// Short-circuit AND  
int m = 9;  
int n = 7;  
int p = 5;  
if (m >= n && m >= p)  
{  
    Console.WriteLine("Nothing is larger than m.");  
}  
  
// AND and NOT  
if (m >= n && !(p > m))  
{  
    Console.WriteLine("Nothing is larger than m.");  
}  
  
// Short-circuit OR  
if (m > n || m > p)  
{  
    Console.WriteLine("m isn't the smallest.");  
}  
  
// NOT and OR  
m = 4;  
if (!(m >= n || m >= p))  
{  
    Console.WriteLine("Now m is the smallest.");  
}  
// Output:  
// The condition is false (result is true).  
// Nothing is larger than m.  
// Nothing is larger than m.  
// m isn't the smallest.  
// Now m is the smallest.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="9128e-138">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="9128e-138">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9128e-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9128e-139">See Also</span></span>  
 [<span data-ttu-id="9128e-140">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="9128e-140">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9128e-141">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="9128e-141">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9128e-142">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="9128e-142">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="9128e-143">Operatore ?:</span><span class="sxs-lookup"><span data-stu-id="9128e-143">?: Operator</span></span>](../../../csharp/language-reference/operators/conditional-operator.md)  
 [<span data-ttu-id="9128e-144">Istruzione if-else (C++)</span><span class="sxs-lookup"><span data-stu-id="9128e-144">if-else Statement (C++)</span></span>](/cpp/cpp/if-else-statement-cpp)  
 [<span data-ttu-id="9128e-145">switch</span><span class="sxs-lookup"><span data-stu-id="9128e-145">switch</span></span>](../../../csharp/language-reference/keywords/switch.md)
