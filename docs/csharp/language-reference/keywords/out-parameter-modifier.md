---
title: Modificatore del parametro out - Riferimenti per C#
ms.date: 03/19/2020
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: 57308992268e1285cfeb82b28e2abf213e7a831b
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805866"
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="4ed2e-102">Modificatore del parametro out (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4ed2e-102">out parameter modifier (C# Reference)</span></span>

<span data-ttu-id="4ed2e-103">La parola chiave `out` fa sì che gli argomenti vengono passati per riferimento.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="4ed2e-104">Imposta il parametro formale come alias dell'argomento, che deve essere una variabile.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-104">It makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="4ed2e-105">In altre parole, qualsiasi operazione sul parametro viene eseguita sull'argomento.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-105">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="4ed2e-106">È come la parola chiave [ref](ref.md), con la differenza che `ref` richiede l'inizializzazione della variabile prima di essere passato.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-106">It is like the [ref](ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="4ed2e-107">È anche come la parola chiave [in](in-parameter-modifier.md), con la differenza che `in` non consente al metodo chiamato di modificare il valore dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-107">It is also like the [in](in-parameter-modifier.md) keyword, except that `in` does not allow the called method to modify the argument value.</span></span> <span data-ttu-id="4ed2e-108">Per usare un parametro `out`, la definizione del metodo e il metodo chiamante devono usare in modo esplicito la parola chiave `out`.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-108">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="4ed2e-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4ed2e-109">For example:</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE]
> <span data-ttu-id="4ed2e-110">La parola chiave `out` può essere usata anche con un parametro di tipo generico per specificare che il parametro tipo è covariante.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-110">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="4ed2e-111">Per altre informazioni sull'uso della parola chiave `out` in questo contesto, vedere [out (Modificatore generico)](out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="4ed2e-111">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](out-generic-modifier.md).</span></span>
  
<span data-ttu-id="4ed2e-112">Le variabili passate come argomenti `out` non devono essere inizializzate prima di essere passate in una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-112">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="4ed2e-113">È necessario tuttavia che il metodo chiamato assegni un valore prima della restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-113">However, the called method is required to assign a value before the method returns.</span></span>  
  
<span data-ttu-id="4ed2e-114">Le parole chiave `in`, `ref` e `out` non sono considerate parte della firma del metodo ai fini della risoluzione dell'overload.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-114">The `in`, `ref`, and `out` keywords are not considered part of the method signature for the purpose of overload resolution.</span></span> <span data-ttu-id="4ed2e-115">Non è quindi possibile eseguirne l'overload se l'unica differenza è che un metodo accetta un argomento `ref` o `in` e l'altro un argomento `out`.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-115">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="4ed2e-116">Il codice seguente, ad esempio, non verrà compilato:</span><span class="sxs-lookup"><span data-stu-id="4ed2e-116">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="4ed2e-117">L'overload è consentito, tuttavia, se un metodo accetta un argomento `ref`, `in` o `out` e l'altro non ha alcuno di questi modificatori, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4ed2e-117">Overloading is legal, however, if one method takes a `ref`, `in`, or `out` argument and the other has none of those modifiers, like this:</span></span>  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

<span data-ttu-id="4ed2e-118">Il compilatore sceglie il miglior overload creando una corrispondenza tra i modificatori di parametro nel sito di chiamata e i modificatori di parametro utilizzati nella chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-118">The compiler chooses the best overload by matching the parameter modifiers at the call site to the parameter modifiers used in the method call.</span></span>

<span data-ttu-id="4ed2e-119">Le proprietà non sono variabili e quindi non possono essere passate come parametri `out`.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-119">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>
  
<span data-ttu-id="4ed2e-120">Non è possibile usare le parole chiave `in`, `ref` e `out` per i seguenti tipi di metodi:</span><span class="sxs-lookup"><span data-stu-id="4ed2e-120">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="4ed2e-121">Metodi asincroni definiti usando il modificatore [async](./async.md).</span><span class="sxs-lookup"><span data-stu-id="4ed2e-121">Async methods, which you define by using the [async](./async.md) modifier.</span></span>  
  
- <span data-ttu-id="4ed2e-122">Metodi iteratori che includono un'istruzione [yield return](./yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-122">Iterator methods, which include a [yield return](./yield.md) or `yield break` statement.</span></span>  

<span data-ttu-id="4ed2e-123">Inoltre, i metodi di [estensione](../../programming-guide/classes-and-structs/extension-methods.md) hanno le seguenti restrizioni:</span><span class="sxs-lookup"><span data-stu-id="4ed2e-123">In addition, [extension methods](../../programming-guide/classes-and-structs/extension-methods.md) have the following restrictions:</span></span>

- <span data-ttu-id="4ed2e-124">La `out` parola chiave non può essere utilizzata sul primo argomento di un metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-124">The `out` keyword cannot be used on the first argument of an extension method.</span></span>
- <span data-ttu-id="4ed2e-125">La `ref` parola chiave non può essere utilizzata sul primo argomento di un metodo di estensione quando l'argomento non è uno struct o un tipo generico non vincolato a essere uno struct.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-125">The `ref` keyword cannot be used on the first argument of an extension method when the argument is not a struct, or a generic type not constrained to be a struct.</span></span>
- <span data-ttu-id="4ed2e-126">La `in` parola chiave non può essere utilizzata a meno che il primo argomento non sia uno struct.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-126">The `in` keyword cannot be used unless the first argument is a struct.</span></span> <span data-ttu-id="4ed2e-127">La `in` parola chiave non può essere utilizzata su qualsiasi tipo generico, anche quando vincolata a essere uno struct.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-127">The `in` keyword cannot be used on any generic type, even when constrained to be a struct.</span></span>

## <a name="declaring-out-parameters"></a><span data-ttu-id="4ed2e-128">Dichiarazione di parametri `out`</span><span class="sxs-lookup"><span data-stu-id="4ed2e-128">Declaring `out` parameters</span></span>

<span data-ttu-id="4ed2e-129">La dichiarazione di un metodo con argomenti `out` è un classico espediente per restituire più valori.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-129">Declaring a method with `out` arguments is a classic workaround to return multiple values.</span></span> <span data-ttu-id="4ed2e-130">A partire da C# 7.0 è possibile usare le [tuple](../../tuples.md) per scenari analoghi.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-130">Beginning with C# 7.0, consider [tuples](../../tuples.md) for similar scenarios.</span></span> <span data-ttu-id="4ed2e-131">Nell'esempio seguente viene usato `out` per restituire tre variabili con una sola chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-131">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="4ed2e-132">Il terzo argomento viene assegnato a null.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-132">The third argument is assigned to null.</span></span> <span data-ttu-id="4ed2e-133">In questo modo i metodi restituiscono i valori facoltativamente.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-133">This enables methods to return values optionally.</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="4ed2e-134">Chiamata a un metodo con un argomento `out`</span><span class="sxs-lookup"><span data-stu-id="4ed2e-134">Calling a method with an `out` argument</span></span>

<span data-ttu-id="4ed2e-135">In C# 6 e nelle versioni precedenti è necessario dichiarare una variabile in un'istruzione separata prima di passarla come argomento `out`.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-135">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="4ed2e-136">L'esempio seguente dichiara una variabile denominata `number` prima che venga passata al metodo [Int32.TryParse3](xref:System.Int32.TryParse(System.String,System.Int32@)), che tenta di convertire una stringa in numero.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-136">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

<span data-ttu-id="4ed2e-137">A partire da C# 7.0, è possibile dichiarare la variabile `out` nell'elenco degli argomenti della chiamata al metodo anziché in una dichiarazione di variabile separata.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-137">Starting with C# 7.0, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="4ed2e-138">Il codice prodotto risulta più compatto e leggibile e viene impedita l'assegnazione accidentale di un valore alla variabile prima della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-138">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="4ed2e-139">L'esempio seguente è uguale all'esempio precedente, ad eccezione del fatto che definisce la variabile `number` nella chiamata al metodo [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).</span><span class="sxs-lookup"><span data-stu-id="4ed2e-139">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  

<span data-ttu-id="4ed2e-140">Nell'esempio precedente la variabile `number` è fortemente tipizzata come `int`.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-140">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="4ed2e-141">È anche possibile dichiarare una variabile locale tipizzata in modo implicito, come avviene nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4ed2e-141">You can also declare an implicitly typed local variable, as the following example does.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="4ed2e-142">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="4ed2e-142">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4ed2e-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ed2e-143">See also</span></span>

- [<span data-ttu-id="4ed2e-144">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="4ed2e-144">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4ed2e-145">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="4ed2e-145">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4ed2e-146">Parole chiave di C</span><span class="sxs-lookup"><span data-stu-id="4ed2e-146">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="4ed2e-147">Parametri di metodo</span><span class="sxs-lookup"><span data-stu-id="4ed2e-147">Method Parameters</span></span>](./method-parameters.md)
