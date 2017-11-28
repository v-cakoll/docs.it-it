---
title: Modificatore del parametro out (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.assetid: 3fce0dc5-03f4-4faa-bd61-36c41bc6baf1
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 68ef554f95fe71f925cfa22cc49758cec3da237e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="3d374-102">Modificatore del parametro out (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3d374-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="3d374-103">La parola chiave `out` fa sì che gli argomenti vengono passati per riferimento.</span><span class="sxs-lookup"><span data-stu-id="3d374-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="3d374-104">È come la parola chiave [ref](../../../csharp/language-reference/keywords/ref.md), con la differenza che `ref` richiede l'inizializzazione della variabile prima di essere passato.</span><span class="sxs-lookup"><span data-stu-id="3d374-104">It is like the [ref](../../../csharp/language-reference/keywords/ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="3d374-105">Per usare un parametro `out`, la definizione del metodo e il metodo chiamante devono usare in modo esplicito la parola chiave `out`.</span><span class="sxs-lookup"><span data-stu-id="3d374-105">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="3d374-106">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3d374-106">For example:</span></span>  
  
 [!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]  

> [!NOTE] 
> <span data-ttu-id="3d374-107">La parola chiave `out` può essere usata anche con un parametro di tipo generico per specificare che il parametro tipo è covariante.</span><span class="sxs-lookup"><span data-stu-id="3d374-107">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="3d374-108">Per altre informazioni sull'uso della parola chiave `out` in questo contesto, vedere [out (Modificatore generico)](../../../csharp/language-reference/keywords/out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="3d374-108">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](../../../csharp/language-reference/keywords/out-generic-modifier.md).</span></span>
  
 <span data-ttu-id="3d374-109">Le variabili passate come argomenti `out` non devono essere inizializzate prima di essere passate in una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="3d374-109">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="3d374-110">È necessario tuttavia che il metodo chiamato assegni un valore prima della restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="3d374-110">However, the called method is required to assign a value before the method returns.</span></span>  
  
 <span data-ttu-id="3d374-111">Nonostante le parole chiave `ref` e `out` determinino un comportamento differente in fase di esecuzione, non sono considerate parte della firma del metodo in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="3d374-111">Although the `ref` and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="3d374-112">Non è quindi possibile eseguirne l'overload se l'unica differenza è che un metodo accetta un argomento `ref` e l'altro un argomento `out`.</span><span class="sxs-lookup"><span data-stu-id="3d374-112">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="3d374-113">Il codice seguente, ad esempio, non verrà compilato:</span><span class="sxs-lookup"><span data-stu-id="3d374-113">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="3d374-114">L'overload può essere eseguito, tuttavia, se un metodo accetta un argomento `ref` o `out` e l'altro non ne usa, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3d374-114">Overloading is legal, however, if one method takes a `ref` or `out` argument and the other uses neither, like this:</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]  
  
 <span data-ttu-id="3d374-115">Le proprietà non sono variabili e quindi non possono essere passate come parametri `out`.</span><span class="sxs-lookup"><span data-stu-id="3d374-115">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>  
  
 <span data-ttu-id="3d374-116">Per informazioni sul passaggio di matrici, vedere [Passaggio di matrici mediante ref e out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="3d374-116">For information about passing arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="3d374-117">Non è possibile usare le parole chiave `ref` e `out` per i seguenti tipi di metodi:</span><span class="sxs-lookup"><span data-stu-id="3d374-117">You can't use the `ref` and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="3d374-118">Metodi asincroni definiti usando il modificatore [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="3d374-118">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="3d374-119">Metodi iteratori che includono un'istruzione [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="3d374-119">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-arguments"></a><span data-ttu-id="3d374-120">Dichiarazione di argomenti `out`</span><span class="sxs-lookup"><span data-stu-id="3d374-120">Declaring `out` arguments</span></span>   

 <span data-ttu-id="3d374-121">La dichiarazione di un metodo con argomenti `out` è utile quando si vuole che un metodo restituisca più valori.</span><span class="sxs-lookup"><span data-stu-id="3d374-121">Declaring a method with `out` arguments is useful when you want a method to return multiple values.</span></span> <span data-ttu-id="3d374-122">Nell'esempio seguente viene usato `out` per restituire tre variabili con una sola chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="3d374-122">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="3d374-123">Notare che il terzo argomento è assegnato a null.</span><span class="sxs-lookup"><span data-stu-id="3d374-123">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="3d374-124">In questo modo i metodi restituiscono i valori facoltativamente.</span><span class="sxs-lookup"><span data-stu-id="3d374-124">This enables methods to return values optionally.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]  

 <span data-ttu-id="3d374-125">Il [modello Try](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) prevede la restituzione di `bool` per indicare se l'operazione è riuscita e la restituzione del valore prodotto dall'operazione in un argomento `out`.</span><span class="sxs-lookup"><span data-stu-id="3d374-125">The [Try pattern](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) involves returning a `bool` to indicate whether an operation succeeded and failed, and returning the value produced by the operation in an `out` argument.</span></span> <span data-ttu-id="3d374-126">Numerosi metodi di analisi, ad esempio il metodo [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)), usano questo modello.</span><span class="sxs-lookup"><span data-stu-id="3d374-126">A number of parsing methods, such as the [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) method, use this pattern.</span></span>
   
## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="3d374-127">Chiamata a un metodo con un argomento `out`</span><span class="sxs-lookup"><span data-stu-id="3d374-127">Calling a method with an `out` argument</span></span>

<span data-ttu-id="3d374-128">In C# 6 e nelle versioni precedenti è necessario dichiarare una variabile in un'istruzione separata prima di passarla come argomento `out`.</span><span class="sxs-lookup"><span data-stu-id="3d374-128">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="3d374-129">L'esempio seguente dichiara una variabile denominata `number` prima che venga passata al metodo [Int32.TryParse3](xref:System.Int32.TryParse(System.String,System.Int32@)), che tenta di convertire una stringa in numero.</span><span class="sxs-lookup"><span data-stu-id="3d374-129">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

 [!code-csharp[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]  

<span data-ttu-id="3d374-130">A partire da C# 7, è possibile dichiarare la variabile `out` nell'elenco degli argomenti della chiamata al metodo anziché in una dichiarazione di variabile separata.</span><span class="sxs-lookup"><span data-stu-id="3d374-130">Starting with C# 7, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="3d374-131">Il codice prodotto risulta più compatto e leggibile e viene impedita l'assegnazione accidentale di un valore alla variabile prima della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="3d374-131">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="3d374-132">L'esempio seguente è uguale all'esempio precedente, ad eccezione del fatto che definisce la variabile `number` nella chiamata al metodo [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).</span><span class="sxs-lookup"><span data-stu-id="3d374-132">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

 [!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]  
   
<span data-ttu-id="3d374-133">Nell'esempio precedente la variabile `number` è fortemente tipizzata come `int`.</span><span class="sxs-lookup"><span data-stu-id="3d374-133">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="3d374-134">È anche possibile dichiarare una variabile locale tipizzata in modo implicito, come avviene nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3d374-134">You can also declare an implicitly typed local variable, as the following example does.</span></span>

 [!code-csharp[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]  
   
## <a name="c-language-specification"></a><span data-ttu-id="3d374-135">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="3d374-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3d374-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d374-136">See Also</span></span>  
 [<span data-ttu-id="3d374-137">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="3d374-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="3d374-138">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3d374-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3d374-139">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="3d374-139">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="3d374-140">Parametri dei metodi</span><span class="sxs-lookup"><span data-stu-id="3d374-140">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
