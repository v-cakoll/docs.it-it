---
title: Modificatore del parametro out (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.assetid: 3fce0dc5-03f4-4faa-bd61-36c41bc6baf1
caps.latest.revision: 9
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
ms.sourcegitcommit: 59e445ac27f07c85d9e98c5f595cf5f935f75443
ms.openlocfilehash: 9a0a488c6f444608a335cd990847774fb6fe9e3f
ms.contentlocale: it-it
ms.lasthandoff: 08/31/2017

---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="00e61-102">Modificatore del parametro out (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="00e61-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="00e61-103">La parola chiave `out` fa sì che gli argomenti vengono passati per riferimento.</span><span class="sxs-lookup"><span data-stu-id="00e61-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="00e61-104">È come la parola chiave [ref](../../../csharp/language-reference/keywords/ref.md), con la differenza che `ref` richiede l'inizializzazione della variabile prima di essere passato.</span><span class="sxs-lookup"><span data-stu-id="00e61-104">It is like the [ref](../../../csharp/language-reference/keywords/ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="00e61-105">Per usare un parametro `out`, la definizione del metodo e il metodo chiamante devono usare in modo esplicito la parola chiave `out`.</span><span class="sxs-lookup"><span data-stu-id="00e61-105">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="00e61-106">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="00e61-106">For example:</span></span>  
  
 <span data-ttu-id="00e61-107">[!code-cs[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="00e61-107">[!code-cs[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="00e61-108">La parola chiave `out` può essere usata anche con un parametro di tipo generico per specificare che il parametro tipo è covariante.</span><span class="sxs-lookup"><span data-stu-id="00e61-108">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="00e61-109">Per altre informazioni sull'uso della parola chiave `out` in questo contesto, vedere [out (Modificatore generico)](../../../csharp/language-reference/keywords/out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="00e61-109">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](../../../csharp/language-reference/keywords/out-generic-modifier.md).</span></span>
  
 <span data-ttu-id="00e61-110">Le variabili passate come argomenti `out` non devono essere inizializzate prima di essere passate in una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="00e61-110">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="00e61-111">È necessario tuttavia che il metodo chiamato assegni un valore prima della restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="00e61-111">However, the called method is required to assign a value before the method returns.</span></span>  
  
 <span data-ttu-id="00e61-112">Nonostante le parole chiave `ref` e `out` determinino un comportamento differente in fase di esecuzione, non sono considerate parte della firma del metodo in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="00e61-112">Although the `ref` and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="00e61-113">Non è quindi possibile eseguirne l'overload se l'unica differenza è che un metodo accetta un argomento `ref` e l'altro un argomento `out`.</span><span class="sxs-lookup"><span data-stu-id="00e61-113">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="00e61-114">Il codice seguente, ad esempio, non verrà compilato:</span><span class="sxs-lookup"><span data-stu-id="00e61-114">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="00e61-115">L'overload può essere eseguito, tuttavia, se un metodo accetta un argomento `ref` o `out` e l'altro non ne usa, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="00e61-115">Overloading is legal, however, if one method takes a `ref` or `out` argument and the other uses neither, like this:</span></span>  
  
 <span data-ttu-id="00e61-116">[!code-cs[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="00e61-116">[!code-cs[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]</span></span>  
  
 <span data-ttu-id="00e61-117">Le proprietà non sono variabili e quindi non possono essere passate come parametri `out`.</span><span class="sxs-lookup"><span data-stu-id="00e61-117">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>  
  
 <span data-ttu-id="00e61-118">Per informazioni sul passaggio di matrici, vedere [Passaggio di matrici mediante ref e out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="00e61-118">For information about passing arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="00e61-119">Non è possibile usare le parole chiave `ref` e `out` per i seguenti tipi di metodi:</span><span class="sxs-lookup"><span data-stu-id="00e61-119">You can't use the `ref` and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="00e61-120">Metodi asincroni definiti usando il modificatore [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="00e61-120">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="00e61-121">Metodi iteratori che includono un'istruzione [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="00e61-121">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-arguments"></a><span data-ttu-id="00e61-122">Dichiarazione di argomenti `out`</span><span class="sxs-lookup"><span data-stu-id="00e61-122">Declaring `out` arguments</span></span>   

 <span data-ttu-id="00e61-123">La dichiarazione di un metodo con argomenti `out` è utile quando si vuole che un metodo restituisca più valori.</span><span class="sxs-lookup"><span data-stu-id="00e61-123">Declaring a method with `out` arguments is useful when you want a method to return multiple values.</span></span> <span data-ttu-id="00e61-124">Nell'esempio seguente viene usato `out` per restituire tre variabili con una sola chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="00e61-124">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="00e61-125">Notare che il terzo argomento è assegnato a null.</span><span class="sxs-lookup"><span data-stu-id="00e61-125">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="00e61-126">In questo modo i metodi restituiscono i valori facoltativamente.</span><span class="sxs-lookup"><span data-stu-id="00e61-126">This enables methods to return values optionally.</span></span>  
  
 <span data-ttu-id="00e61-127">[!code-cs[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]</span><span class="sxs-lookup"><span data-stu-id="00e61-127">[!code-cs[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]</span></span>  

 <span data-ttu-id="00e61-128">Il [modello Try](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) prevede la restituzione di `bool` per indicare se l'operazione è riuscita e la restituzione del valore prodotto dall'operazione in un argomento `out`.</span><span class="sxs-lookup"><span data-stu-id="00e61-128">The [Try pattern](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) involves returning a `bool` to indicate whether an operation succeeded and failed, and returning the value produced by the operation in an `out` argument.</span></span> <span data-ttu-id="00e61-129">Numerosi metodi di analisi, ad esempio il metodo [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)), usano questo modello.</span><span class="sxs-lookup"><span data-stu-id="00e61-129">A number of parsing methods, such as the [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) method, use this pattern.</span></span>
   
## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="00e61-130">Chiamata a un metodo con un argomento `out`</span><span class="sxs-lookup"><span data-stu-id="00e61-130">Calling a method with an `out` argument</span></span>

<span data-ttu-id="00e61-131">In C# 6 e nelle versioni precedenti è necessario dichiarare una variabile in un'istruzione separata prima di passarla come argomento `out`.</span><span class="sxs-lookup"><span data-stu-id="00e61-131">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="00e61-132">L'esempio seguente dichiara una variabile denominata `number` prima che venga passata al metodo [Int32.TryParse3](xref:System.Int32.TryParse(System.String,System.Int32@)), che tenta di convertire una stringa in numero.</span><span class="sxs-lookup"><span data-stu-id="00e61-132">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

 <span data-ttu-id="00e61-133">[!code-cs[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]</span><span class="sxs-lookup"><span data-stu-id="00e61-133">[!code-cs[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]</span></span>  

<span data-ttu-id="00e61-134">A partire da C# 7, è possibile dichiarare la variabile `out` nell'elenco degli argomenti della chiamata al metodo anziché in una dichiarazione di variabile separata.</span><span class="sxs-lookup"><span data-stu-id="00e61-134">Starting with C# 7, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="00e61-135">Il codice prodotto risulta più compatto e leggibile e viene impedita l'assegnazione accidentale di un valore alla variabile prima della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="00e61-135">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="00e61-136">L'esempio seguente è uguale all'esempio precedente, ad eccezione del fatto che definisce la variabile `number` nella chiamata al metodo [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).</span><span class="sxs-lookup"><span data-stu-id="00e61-136">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

 <span data-ttu-id="00e61-137">[!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]</span><span class="sxs-lookup"><span data-stu-id="00e61-137">[!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]</span></span>  
   
<span data-ttu-id="00e61-138">Nell'esempio precedente la variabile `number` è fortemente tipizzata come `int`.</span><span class="sxs-lookup"><span data-stu-id="00e61-138">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="00e61-139">È anche possibile dichiarare una variabile locale tipizzata in modo implicito, come avviene nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="00e61-139">You can also declare an implicitly typed local variable, as the following example does.</span></span>

 <span data-ttu-id="00e61-140">[!code-cs[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]</span><span class="sxs-lookup"><span data-stu-id="00e61-140">[!code-cs[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]</span></span>  
   
## <a name="c-language-specification"></a><span data-ttu-id="00e61-141">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="00e61-141">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="00e61-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00e61-142">See Also</span></span>  
 <span data-ttu-id="00e61-143">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="00e61-143">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="00e61-144">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="00e61-144">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="00e61-145">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="00e61-145">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="00e61-146">Parametri dei metodi</span><span class="sxs-lookup"><span data-stu-id="00e61-146">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)

