---
title: Modificatore del parametro out (Riferimenti per C#)
ms.date: 03/06/2018
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: bc31ae202ccbfee467dc0f6fa2cf515c751825ed
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46696508"
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="bf0c1-102">Modificatore del parametro out (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="bf0c1-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="bf0c1-103">La parola chiave `out` fa sì che gli argomenti vengono passati per riferimento.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="bf0c1-104">È come la parola chiave [ref](ref.md), con la differenza che `ref` richiede l'inizializzazione della variabile prima di essere passato.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-104">It is like the [ref](ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="bf0c1-105">È anche come la parola chiave [in](in-parameter-modifier.md), con la differenza che `in` non consente al metodo chiamato di modificare il valore dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-105">It is also like the [in](in-parameter-modifier.md) keyword, except that `in` does not allow the called method to modify the argument value.</span></span> <span data-ttu-id="bf0c1-106">Per usare un parametro `out`, la definizione del metodo e il metodo chiamante devono usare in modo esplicito la parola chiave `out`.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-106">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="bf0c1-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bf0c1-107">For example:</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE] 
> <span data-ttu-id="bf0c1-108">La parola chiave `out` può essere usata anche con un parametro di tipo generico per specificare che il parametro tipo è covariante.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-108">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="bf0c1-109">Per altre informazioni sull'uso della parola chiave `out` in questo contesto, vedere [out (Modificatore generico)](out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="bf0c1-109">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](out-generic-modifier.md).</span></span>
  
<span data-ttu-id="bf0c1-110">Le variabili passate come argomenti `out` non devono essere inizializzate prima di essere passate in una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-110">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="bf0c1-111">È necessario tuttavia che il metodo chiamato assegni un valore prima della restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-111">However, the called method is required to assign a value before the method returns.</span></span>  
  
<span data-ttu-id="bf0c1-112">Nonostante le parole chiave `in`, `ref` e `out` determinino un comportamento differente in fase di esecuzione, non sono considerate parte della firma del metodo in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-112">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="bf0c1-113">Non è quindi possibile eseguirne l'overload se l'unica differenza è che un metodo accetta un argomento `ref` o `in` e l'altro un argomento `out`.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-113">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="bf0c1-114">Il codice seguente, ad esempio, non verrà compilato:</span><span class="sxs-lookup"><span data-stu-id="bf0c1-114">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="bf0c1-115">L'overload è consentito, tuttavia, se un metodo accetta un argomento `ref`, `in` o `out` e l'altro non ha alcuno di questi modificatori, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bf0c1-115">Overloading is legal, however, if one method takes a `ref`, `in`, or `out` argument and the other has none of those modifiers, like this:</span></span>  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

<span data-ttu-id="bf0c1-116">Il compilatore sceglie il miglior overload creando una corrispondenza tra i modificatori di parametro nel sito di chiamata e i modificatori di parametro utilizzati nella chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-116">The compiler chooses the best overload by matching the parameter modifiers at the call site to the parameter modifiers used in the method call.</span></span>
 
<span data-ttu-id="bf0c1-117">Le proprietà non sono variabili e quindi non possono essere passate come parametri `out`.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-117">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>
  
<span data-ttu-id="bf0c1-118">Non è possibile usare le parole chiave `in`, `ref` e `out` per i seguenti tipi di metodi:</span><span class="sxs-lookup"><span data-stu-id="bf0c1-118">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="bf0c1-119">Metodi asincroni definiti usando il modificatore [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="bf0c1-119">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="bf0c1-120">Metodi iteratori che includono un'istruzione [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-120">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-arguments"></a><span data-ttu-id="bf0c1-121">Dichiarazione di argomenti `out`</span><span class="sxs-lookup"><span data-stu-id="bf0c1-121">Declaring `out` arguments</span></span>   

 <span data-ttu-id="bf0c1-122">La dichiarazione di un metodo con argomenti `out` è utile quando si vuole che un metodo restituisca più valori.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-122">Declaring a method with `out` arguments is useful when you want a method to return multiple values.</span></span> <span data-ttu-id="bf0c1-123">Nell'esempio seguente viene usato `out` per restituire tre variabili con una sola chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-123">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="bf0c1-124">Notare che il terzo argomento è assegnato a null.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-124">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="bf0c1-125">In questo modo i metodi restituiscono i valori facoltativamente.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-125">This enables methods to return values optionally.</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

 <span data-ttu-id="bf0c1-126">Il [modello Try](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) prevede la restituzione di `bool` per indicare se l'operazione è riuscita e la restituzione del valore prodotto dall'operazione in un argomento `out`.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-126">The [Try pattern](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) involves returning a `bool` to indicate whether an operation succeeded or failed, and returning the value produced by the operation in an `out` argument.</span></span> <span data-ttu-id="bf0c1-127">Numerosi metodi di analisi, ad esempio il metodo [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)), usano questo modello.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-127">A number of parsing methods, such as the [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) method, use this pattern.</span></span>
   
## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="bf0c1-128">Chiamata a un metodo con un argomento `out`</span><span class="sxs-lookup"><span data-stu-id="bf0c1-128">Calling a method with an `out` argument</span></span>

<span data-ttu-id="bf0c1-129">In C# 6 e nelle versioni precedenti è necessario dichiarare una variabile in un'istruzione separata prima di passarla come argomento `out`.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-129">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="bf0c1-130">L'esempio seguente dichiara una variabile denominata `number` prima che venga passata al metodo [Int32.TryParse3](xref:System.Int32.TryParse(System.String,System.Int32@)), che tenta di convertire una stringa in numero.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-130">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

<span data-ttu-id="bf0c1-131">A partire da C# 7.0, è possibile dichiarare la variabile `out` nell'elenco degli argomenti della chiamata al metodo anziché in una dichiarazione di variabile separata.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-131">Starting with C# 7.0, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="bf0c1-132">Il codice prodotto risulta più compatto e leggibile e viene impedita l'assegnazione accidentale di un valore alla variabile prima della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-132">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="bf0c1-133">L'esempio seguente è uguale all'esempio precedente, ad eccezione del fatto che definisce la variabile `number` nella chiamata al metodo [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).</span><span class="sxs-lookup"><span data-stu-id="bf0c1-133">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  
   
<span data-ttu-id="bf0c1-134">Nell'esempio precedente la variabile `number` è fortemente tipizzata come `int`.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-134">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="bf0c1-135">È anche possibile dichiarare una variabile locale tipizzata in modo implicito, come avviene nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="bf0c1-135">You can also declare an implicitly typed local variable, as the following example does.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  
   
## <a name="c-language-specification"></a><span data-ttu-id="bf0c1-136">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="bf0c1-136">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bf0c1-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf0c1-137">See Also</span></span>

- [<span data-ttu-id="bf0c1-138">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="bf0c1-138">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="bf0c1-139">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="bf0c1-139">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="bf0c1-140">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="bf0c1-140">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="bf0c1-141">Parametri dei metodi</span><span class="sxs-lookup"><span data-stu-id="bf0c1-141">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
