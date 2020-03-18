---
title: Parola chiave contestuale yield - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- yield
- yield_CSharpKeyword
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
ms.openlocfilehash: e3c9e37e7b543eaddae837a85604c4ba91fbc744
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712780"
---
# <a name="yield-c-reference"></a><span data-ttu-id="ab7fe-102">yield (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="ab7fe-102">yield (C# Reference)</span></span>

<span data-ttu-id="ab7fe-103">Quando si usa la  [parola chiave contestuale](index.md#contextual-keywords)`yield` in un'istruzione, si indica che il metodo, l'operatore o la funzione di accesso `get` in cui appare è un iteratore.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-103">When you use the `yield` [contextual keyword](index.md#contextual-keywords) in a statement, you indicate that the method, operator, or `get` accessor in which it appears is an iterator.</span></span> <span data-ttu-id="ab7fe-104">Utilizzando `yield` per definire un iteratore, si elimina la necessità di una classe esplicita aggiuntiva (la classe che contiene lo stato per un'enumerazione, vedere <xref:System.Collections.Generic.IEnumerator%601> per un esempio) quando si implementano i modelli <xref:System.Collections.IEnumerable> e di <xref:System.Collections.IEnumerator> per un tipo di raccolta personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-104">Using `yield` to define an iterator removes the need for an explicit extra class (the class that holds the state for an enumeration, see <xref:System.Collections.Generic.IEnumerator%601> for an example) when you implement the <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> pattern for a custom collection type.</span></span>

<span data-ttu-id="ab7fe-105">Nell'esempio seguente vengono illustrate le due forme dell'istruzione `yield`.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-105">The following example shows the two forms of the `yield` statement.</span></span>

```csharp
yield return <expression>;
yield break;
```

## <a name="remarks"></a><span data-ttu-id="ab7fe-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ab7fe-106">Remarks</span></span>

<span data-ttu-id="ab7fe-107">Si utilizza un'istruzione `yield return` per restituire un elemento alla volta.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-107">You use a `yield return` statement to return each element one at a time.</span></span>

<span data-ttu-id="ab7fe-108">La sequenza restituita da un metodo iteratore può essere usata con un'istruzione [foreach](foreach-in.md) o una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-108">The sequence returned from an iterator method can be consumed by using a [foreach](foreach-in.md) statement or LINQ query.</span></span> <span data-ttu-id="ab7fe-109">Ogni iterazione del ciclo `foreach` chiama il metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-109">Each iteration of the `foreach` loop calls the iterator method.</span></span> <span data-ttu-id="ab7fe-110">Quando si raggiunge un'istruzione `yield return` nel metodo iteratore, viene restituito `expression` e viene mantenuta la posizione corrente nel codice.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-110">When a `yield return` statement is reached in the iterator method, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="ab7fe-111">L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-111">Execution is restarted from that location the next time that the iterator function is called.</span></span>

<span data-ttu-id="ab7fe-112">È possibile utilizzare un'istruzione `yield break` per terminare l'iterazione.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-112">You can use a `yield break` statement to end the iteration.</span></span>

<span data-ttu-id="ab7fe-113">Per altre informazioni sugli iteratori, vedere [Iteratori](../../iterators.md).</span><span class="sxs-lookup"><span data-stu-id="ab7fe-113">For more information about iterators, see [Iterators](../../iterators.md).</span></span>

## <a name="iterator-methods-and-get-accessors"></a><span data-ttu-id="ab7fe-114">Metodi e funzioni di accesso get dell'iteratore</span><span class="sxs-lookup"><span data-stu-id="ab7fe-114">Iterator methods and get accessors</span></span>

<span data-ttu-id="ab7fe-115">La dichiarazione di un iteratore deve soddisfare i seguenti requisiti:</span><span class="sxs-lookup"><span data-stu-id="ab7fe-115">The declaration of an iterator must meet the following requirements:</span></span>

- <span data-ttu-id="ab7fe-116">Il tipo restituito deve essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-116">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

- <span data-ttu-id="ab7fe-117">La dichiarazione non può avere parametri [in](in-parameter-modifier.md) [ref](ref.md) o [out](out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="ab7fe-117">The declaration can't have any [in](in-parameter-modifier.md) [ref](ref.md) or [out](out-parameter-modifier.md) parameters.</span></span>

<span data-ttu-id="ab7fe-118">Il tipo `yield` di un iteratore che restituisce <xref:System.Collections.IEnumerable> o <xref:System.Collections.IEnumerator> è `object`.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-118">The `yield` type of an iterator that returns <xref:System.Collections.IEnumerable> or <xref:System.Collections.IEnumerator> is `object`.</span></span>  <span data-ttu-id="ab7fe-119">Se l'iteratore restituisce <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Collections.Generic.IEnumerator%601>, deve essere presente una conversione implicita dal tipo dell'espressione nell'istruzione `yield return` al parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-119">If the iterator returns <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.Generic.IEnumerator%601>, there must be an implicit conversion from the type of the expression in the `yield return` statement to the generic type parameter .</span></span>

<span data-ttu-id="ab7fe-120">Non è possibile includere un'istruzione `yield return` o `yield break` in:</span><span class="sxs-lookup"><span data-stu-id="ab7fe-120">You can't include a `yield return` or `yield break` statement in:</span></span>

- <span data-ttu-id="ab7fe-121">[Espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) e [metodi anonimi](../operators/delegate-operator.md).</span><span class="sxs-lookup"><span data-stu-id="ab7fe-121">[Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) and [anonymous methods](../operators/delegate-operator.md).</span></span>

- <span data-ttu-id="ab7fe-122">Metodi contenenti blocchi unsafe.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-122">Methods that contain unsafe blocks.</span></span> <span data-ttu-id="ab7fe-123">Per altre informazioni, vedere [unsafe](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="ab7fe-123">For more information, see [unsafe](unsafe.md).</span></span>

## <a name="exception-handling"></a><span data-ttu-id="ab7fe-124">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="ab7fe-124">Exception handling</span></span>

<span data-ttu-id="ab7fe-125">Un'istruzione `yield return` non può essere inclusa in un blocco try-catch.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-125">A `yield return` statement can't be located in a try-catch block.</span></span> <span data-ttu-id="ab7fe-126">Un'istruzione `yield return` può essere inclusa nel blocco try di un'istruzione try-finally.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-126">A `yield return` statement can be located in the try block of a try-finally statement.</span></span>

<span data-ttu-id="ab7fe-127">Un'istruzione `yield break` può essere inclusa in un blocco try o in un blocco catch ma non in un blocco finally.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-127">A `yield break` statement can be located in a try block or a catch block but not a finally block.</span></span>

<span data-ttu-id="ab7fe-128">Se il corpo di `foreach` (esterno al metodo iteratore) genera un'eccezione, viene eseguito un blocco `finally` nel metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-128">If the `foreach` body (outside of the iterator method) throws an exception, a `finally` block in the iterator method is executed.</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="ab7fe-129">Implementazione tecnica</span><span class="sxs-lookup"><span data-stu-id="ab7fe-129">Technical implementation</span></span>

<span data-ttu-id="ab7fe-130">Il codice seguente restituisce `IEnumerable<string>` da un metodo iteratore e quindi scorre i relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-130">The following code returns an `IEnumerable<string>` from an iterator method and then iterates through its elements.</span></span>

```csharp
IEnumerable<string> elements = MyIteratorMethod();
foreach (string element in elements)
{
   ...
}
```

<span data-ttu-id="ab7fe-131">La chiamata a `MyIteratorMethod` non esegue il corpo del metodo.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-131">The call to `MyIteratorMethod` doesn't execute the body of the method.</span></span> <span data-ttu-id="ab7fe-132">La chiamata restituisce invece `IEnumerable<string>` nella variabile `elements`.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-132">Instead the call returns an `IEnumerable<string>` into the `elements` variable.</span></span>

<span data-ttu-id="ab7fe-133">In un'iterazione del ciclo `foreach`, il metodo <xref:System.Collections.IEnumerator.MoveNext%2A> viene chiamato per `elements`.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-133">On an iteration of the `foreach` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="ab7fe-134">Questa chiamata esegue il corpo di `MyIteratorMethod` fino a quando non viene raggiunta l'istruzione `yield return` successiva.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-134">This call executes the body of `MyIteratorMethod` until the next `yield return` statement is reached.</span></span> <span data-ttu-id="ab7fe-135">L'espressione restituita dall'istruzione `yield return` determina non solo il valore della variabile `element` per l'utilizzo da parte del corpo del ciclo, ma anche la proprietà <xref:System.Collections.Generic.IEnumerator%601.Current%2A> di `elements`, che è `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-135">The expression returned by the `yield return` statement determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of `elements`, which is an `IEnumerable<string>`.</span></span>

<span data-ttu-id="ab7fe-136">In ogni iterazione successiva del ciclo `foreach`, l'esecuzione del corpo dell'iteratore continua da dove è stata interrotta, fermandosi ancora quando raggiunge un'istruzione `yield return`.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-136">On each subsequent iteration of the `foreach` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="ab7fe-137">Il ciclo `foreach` termina quando si raggiunge la fine del metodo iteratore o un'istruzione `yield break`.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-137">The `foreach` loop completes when the end of the iterator method or a `yield break` statement is reached.</span></span>

## <a name="example"></a><span data-ttu-id="ab7fe-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="ab7fe-138">Example</span></span>

<span data-ttu-id="ab7fe-139">L'esempio seguente contiene un'istruzione `yield return` all'interno di un ciclo `for`.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-139">The following example has a `yield return` statement that's inside a `for` loop.</span></span> <span data-ttu-id="ab7fe-140">Ogni iterazione del corpo dell'istruzione `foreach` nel metodo `Main` crea una chiamata alla funzione iteratore `Power`.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-140">Each iteration of the `foreach` statement body in the `Main` method creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="ab7fe-141">Ogni chiamata alla funzione iteratore procede fino alla prossima esecuzione dell'istruzione `yield return`, che si verifica durante l'iterazione successiva del ciclo `for`.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-141">Each call to the iterator function proceeds to the next execution of the `yield return` statement, which occurs during the next iteration of the `for` loop.</span></span>

<span data-ttu-id="ab7fe-142">Il tipo restituito del metodo iteratore è <xref:System.Collections.IEnumerable>, ovvero un tipo di interfaccia iteratore.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-142">The return type of the iterator method is <xref:System.Collections.IEnumerable>, which is an iterator interface type.</span></span> <span data-ttu-id="ab7fe-143">Quando il metodo iteratore viene chiamato, restituisce un oggetto enumerabile che contiene le potenze di un numero.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-143">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>

[!code-csharp[csrefKeywordsContextual#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#5)]

## <a name="example"></a><span data-ttu-id="ab7fe-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="ab7fe-144">Example</span></span>

<span data-ttu-id="ab7fe-145">Nell'esempio seguente viene illustrata una funzione di accesso `get` che è un iteratore.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-145">The following example demonstrates a `get` accessor that is an iterator.</span></span> <span data-ttu-id="ab7fe-146">Nell'esempio, ogni istruzione `yield return` restituisce un'istanza di una classe definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ab7fe-146">In the example, each `yield return` statement returns an instance of a user-defined class.</span></span>

[!code-csharp[csrefKeywordsContextual#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#21)]

## <a name="c-language-specification"></a><span data-ttu-id="ab7fe-147">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="ab7fe-147">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ab7fe-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab7fe-148">See also</span></span>

- [<span data-ttu-id="ab7fe-149">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="ab7fe-149">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="ab7fe-150">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ab7fe-150">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ab7fe-151">foreach, in</span><span class="sxs-lookup"><span data-stu-id="ab7fe-151">foreach, in</span></span>](foreach-in.md)
- [<span data-ttu-id="ab7fe-152">Iteratori</span><span class="sxs-lookup"><span data-stu-id="ab7fe-152">Iterators</span></span>](../../iterators.md)
