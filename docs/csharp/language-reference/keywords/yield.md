---
title: yield (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- yield
- yield_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
caps.latest.revision: 46
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: eb55fd5b1ade48316516cda83633935abbf8dcf9
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="yield-c-reference"></a><span data-ttu-id="bd4dc-102">yield (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="bd4dc-102">yield (C# Reference)</span></span>
<span data-ttu-id="bd4dc-103">Quando si utilizza la parola chiave `yield` in un'istruzione, si indica che il metodo, l'operatore o la funzione di accesso `get` in cui appare è un iteratore.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-103">When you use the `yield` keyword in a statement, you indicate that the method, operator, or `get` accessor in which it appears is an iterator.</span></span> <span data-ttu-id="bd4dc-104">Utilizzando `yield` per definire un iteratore, si elimina la necessità di una classe esplicita aggiuntiva (la classe che contiene lo stato per un'enumerazione, vedere <xref:System.Collections.Generic.IEnumerator%601> per un esempio) quando si implementano i modelli <xref:System.Collections.IEnumerable> e di <xref:System.Collections.IEnumerator> per un tipo di raccolta personalizzato.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-104">Using `yield` to define an iterator removes the need for an explicit extra class (the class that holds the state for an enumeration, see <xref:System.Collections.Generic.IEnumerator%601> for an example) when you implement the <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> pattern for a custom collection type.</span></span>  
  
 <span data-ttu-id="bd4dc-105">Nell'esempio seguente vengono illustrate le due forme dell'istruzione `yield`.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-105">The following example shows the two forms of the `yield` statement.</span></span>  
  
```csharp  
yield return <expression>;  
yield break;  
```  
  
## <a name="remarks"></a><span data-ttu-id="bd4dc-106">Note</span><span class="sxs-lookup"><span data-stu-id="bd4dc-106">Remarks</span></span>  
 <span data-ttu-id="bd4dc-107">Si utilizza un'istruzione `yield return` per restituire un elemento alla volta.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-107">You use a `yield return` statement to return each element one at a time.</span></span>  
  
 <span data-ttu-id="bd4dc-108">Viene usato un metodo iteratore se si usa un'istruzione [foreach](../../../csharp/language-reference/keywords/foreach-in.md) o una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-108">You consume an iterator method by using a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement or LINQ query.</span></span> <span data-ttu-id="bd4dc-109">Ogni iterazione del ciclo `foreach` chiama il metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-109">Each iteration of the `foreach` loop calls the iterator method.</span></span> <span data-ttu-id="bd4dc-110">Quando si raggiunge un'istruzione `yield return` nel metodo iteratore, viene restituito `expression` e viene mantenuta la posizione corrente nel codice.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-110">When a `yield return` statement is reached in the iterator method, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="bd4dc-111">L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-111">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="bd4dc-112">È possibile utilizzare un'istruzione `yield break` per terminare l'iterazione.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-112">You can use a `yield break` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="bd4dc-113">Per altre informazioni sugli iteratori, vedere [Iteratori](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="bd4dc-113">For more information about iterators, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="iterator-methods-and-get-accessors"></a><span data-ttu-id="bd4dc-114">Metodi e funzioni di accesso get dell'iteratore</span><span class="sxs-lookup"><span data-stu-id="bd4dc-114">Iterator Methods and get Accessors</span></span>  
 <span data-ttu-id="bd4dc-115">La dichiarazione di un iteratore deve soddisfare i seguenti requisiti:</span><span class="sxs-lookup"><span data-stu-id="bd4dc-115">The declaration of an iterator must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="bd4dc-116">Il tipo restituito deve essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-116">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
-   <span data-ttu-id="bd4dc-117">La dichiarazione non può avere parametri [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out.md).</span><span class="sxs-lookup"><span data-stu-id="bd4dc-117">The declaration can't have any [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) parameters.</span></span>  
  
 <span data-ttu-id="bd4dc-118">Il tipo `yield` di un iteratore che restituisce <xref:System.Collections.IEnumerable> o <xref:System.Collections.IEnumerator> è `object`.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-118">The `yield` type of an iterator that returns <xref:System.Collections.IEnumerable> or <xref:System.Collections.IEnumerator> is `object`.</span></span>  <span data-ttu-id="bd4dc-119">Se l'iteratore restituisce <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Collections.Generic.IEnumerator%601>, deve essere presente una conversione implicita dal tipo dell'espressione nell'istruzione `yield return` al parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-119">If the iterator returns <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.Generic.IEnumerator%601>, there must be an implicit conversion from the type of the expression in the `yield return` statement to the generic type parameter .</span></span>  
  
 <span data-ttu-id="bd4dc-120">Non è possibile includere un'istruzione `yield return` o `yield break` nei metodi che presentano le seguenti caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="bd4dc-120">You can't include a `yield return` or `yield break` statement in methods that have the following characteristics:</span></span>  
  
-   <span data-ttu-id="bd4dc-121">Metodi anonimi.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-121">Anonymous methods.</span></span> <span data-ttu-id="bd4dc-122">Per altre informazioni, vedere [Metodi anonimi](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="bd4dc-122">For more information, see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
-   <span data-ttu-id="bd4dc-123">Metodi contenenti blocchi unsafe.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-123">Methods that contain unsafe blocks.</span></span> <span data-ttu-id="bd4dc-124">Per altre informazioni, vedere [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="bd4dc-124">For more information, see [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="bd4dc-125">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="bd4dc-125">Exception Handling</span></span>  
 <span data-ttu-id="bd4dc-126">Un'istruzione `yield return` non può essere inclusa in un blocco try-catch.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-126">A `yield return` statement can't be located in a try-catch block.</span></span> <span data-ttu-id="bd4dc-127">Un'istruzione `yield return` può essere inclusa nel blocco try di un'istruzione try-finally.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-127">A `yield return` statement can be located in the try block of a try-finally statement.</span></span>  
  
 <span data-ttu-id="bd4dc-128">Un'istruzione `yield break` può essere inclusa in un blocco try o in un blocco catch ma non in un blocco finally.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-128">A `yield break` statement can be located in a try block or a catch block but not a finally block.</span></span>  
  
 <span data-ttu-id="bd4dc-129">Se il corpo di `foreach` (esterno al metodo iteratore) genera un'eccezione, viene eseguito un blocco `finally` nel metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-129">If the `foreach` body (outside of the iterator method) throws an exception, a `finally` block in the iterator method is executed.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="bd4dc-130">Implementazione tecnica</span><span class="sxs-lookup"><span data-stu-id="bd4dc-130">Technical Implementation</span></span>  
 <span data-ttu-id="bd4dc-131">Il codice seguente restituisce `IEnumerable<string>` da un metodo iteratore e quindi scorre i relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-131">The following code returns an `IEnumerable<string>` from an iterator method and then iterates through its elements.</span></span>  
  
```csharp  
IEnumerable<string> elements = MyIteratorMethod();  
foreach (string element in elements)  
{  
   ...  
}  
```  
  
 <span data-ttu-id="bd4dc-132">La chiamata a `MyIteratorMethod` non esegue il corpo del metodo.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-132">The call to `MyIteratorMethod` doesn't execute the body of the method.</span></span> <span data-ttu-id="bd4dc-133">La chiamata restituisce invece `IEnumerable<string>` nella variabile `elements`.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-133">Instead the call returns an `IEnumerable<string>` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="bd4dc-134">In un'iterazione del ciclo `foreach`, il metodo <xref:System.Collections.IEnumerator.MoveNext%2A> viene chiamato per `elements`.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-134">On an iteration of the `foreach` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="bd4dc-135">Questa chiamata esegue il corpo di `MyIteratorMethod` fino a quando non viene raggiunta l'istruzione `yield return` successiva.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-135">This call executes the body of `MyIteratorMethod` until the next `yield return` statement is reached.</span></span> <span data-ttu-id="bd4dc-136">L'espressione restituita dall'istruzione `yield return` determina non solo il valore della variabile `element` per l'utilizzo dal corpo del ciclo, ma anche la proprietà <xref:System.Collections.Generic.IEnumerator%601.Current%2A> degli elementi, ovvero `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-136">The expression returned by the `yield return` statement determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable<string>`.</span></span>  
  
 <span data-ttu-id="bd4dc-137">In ogni iterazione successiva del ciclo `foreach`, l'esecuzione del corpo dell'iteratore continua da dove è stata interrotta, fermandosi ancora quando raggiunge un'istruzione `yield return`.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-137">On each subsequent iteration of the `foreach` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="bd4dc-138">Il ciclo `foreach` termina quando si raggiunge la fine del metodo iteratore o un'istruzione `yield break`.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-138">The `foreach` loop completes when the end of the iterator method or a `yield break` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd4dc-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="bd4dc-139">Example</span></span>  
 <span data-ttu-id="bd4dc-140">L'esempio seguente contiene un'istruzione `yield return` all'interno di un ciclo `for`.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-140">The following example has a `yield return` statement that's inside a `for` loop.</span></span> <span data-ttu-id="bd4dc-141">Ogni iterazione del corpo dell'istruzione `foreach` in `Process` crea una chiamata alla funzione iteratore `Power`.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-141">Each iteration of the `foreach` statement body in `Process` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="bd4dc-142">Ogni chiamata alla funzione iteratore procede fino alla prossima esecuzione dell'istruzione `yield return`, che si verifica durante l'iterazione successiva del ciclo `for`.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-142">Each call to the iterator function proceeds to the next execution of the `yield return` statement, which occurs during the next iteration of the `for` loop.</span></span>  
  
 <span data-ttu-id="bd4dc-143">Il tipo restituito del metodo iteratore è <xref:System.Collections.IEnumerable>, ovvero un tipo di interfaccia iteratore.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-143">The return type of the iterator method is <xref:System.Collections.IEnumerable>, which is an iterator interface type.</span></span> <span data-ttu-id="bd4dc-144">Quando il metodo iteratore viene chiamato, restituisce un oggetto enumerabile che contiene le potenze di un numero.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-144">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 <span data-ttu-id="bd4dc-145">[!code-cs[csrefKeywordsContextual#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bd4dc-145">[!code-cs[csrefKeywordsContextual#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd4dc-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="bd4dc-146">Example</span></span>  
 <span data-ttu-id="bd4dc-147">Nell'esempio seguente viene illustrata una funzione di accesso `get` che è un iteratore.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-147">The following example demonstrates a `get` accessor that is an iterator.</span></span> <span data-ttu-id="bd4dc-148">Nell'esempio, ogni istruzione `yield return` restituisce un'istanza di una classe definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="bd4dc-148">In the example, each `yield return` statement returns an instance of a user-defined class.</span></span>  
  
 <span data-ttu-id="bd4dc-149">[!code-cs[csrefKeywordsContextual#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="bd4dc-149">[!code-cs[csrefKeywordsContextual#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="bd4dc-150">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="bd4dc-150">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bd4dc-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd4dc-151">See Also</span></span>  
 <span data-ttu-id="bd4dc-152">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bd4dc-152">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bd4dc-153">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bd4dc-153">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bd4dc-154">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span><span class="sxs-lookup"><span data-stu-id="bd4dc-154">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span></span>  
 [<span data-ttu-id="bd4dc-155">Iteratori</span><span class="sxs-lookup"><span data-stu-id="bd4dc-155">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)

