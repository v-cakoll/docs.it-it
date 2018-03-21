---
title: Modificatore del parametro in (Riferimenti per C#)
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 035aac3e6b902f607e533b709713eb1d07c9774a
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2018
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="e17a3-102">Modificatore del parametro in (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e17a3-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="e17a3-103">La parola chiave `in` fa sì che gli argomenti vengono passati per riferimento.</span><span class="sxs-lookup"><span data-stu-id="e17a3-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="e17a3-104">È simile alle parole chiave [ref](ref.md) o [out](out-parameter-modifier.md), tranne per il fatto che gli argomenti `in` non possono essere modificati dal metodo chiamato, mentre possono essere modificati gli argomenti `ref`; gli argomenti `out` devono essere modificati dal chiamante e tali modifiche possono essere osservate nel contesto di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e17a3-104">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method, whereas `ref` arguments may be modified,  `out` arguments must be modified by the caller, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="e17a3-105">L'esempio precedente dimostra che il modificatore `in` non è necessario nel sito di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e17a3-105">The preceding example demonstrates that the `in` modifier is unnecessary at the call site.</span></span> <span data-ttu-id="e17a3-106">Viene richiesto soltanto nella dichiarazione di metodo.</span><span class="sxs-lookup"><span data-stu-id="e17a3-106">It is only required in the method declaration.</span></span>

> [!NOTE] 
> <span data-ttu-id="e17a3-107">La parola chiave `in` può essere usata anche con un parametro di tipo generico per specificare che il parametro è di tipo controvariante, quale parte di un'istruzione `foreach` o parte di una clausola `join` in una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="e17a3-107">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="e17a3-108">Per altre informazioni sull'uso della parola chiave `in` in questi contesti, vedere [in](in.md), che fornisce collegamenti a tutti gli utilizzi.</span><span class="sxs-lookup"><span data-stu-id="e17a3-108">For more information on the use of the `in` keyword in these contexts, see [in](in.md) which provides links to all those uses.</span></span>
  
 <span data-ttu-id="e17a3-109">Le variabili passate come argomenti `in` devono essere inizializzate prima di essere passate in una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="e17a3-109">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="e17a3-110">Tuttavia, il metodo chiamato non può assegnare un valore o modificare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="e17a3-110">However, the called method may not assign a value or modify the argument.</span></span>  
  
 <span data-ttu-id="e17a3-111">Nonostante le parole chiave `in`, `ref` e `out` determinino un comportamento differente in fase di esecuzione, non sono considerate parte della firma del metodo in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e17a3-111">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="e17a3-112">Non è quindi possibile eseguirne l'overload se l'unica differenza è che un metodo accetta un argomento `ref` o `in` e l'altro un argomento `out`.</span><span class="sxs-lookup"><span data-stu-id="e17a3-112">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="e17a3-113">Il codice seguente, ad esempio, non verrà compilato:</span><span class="sxs-lookup"><span data-stu-id="e17a3-113">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="e17a3-114">L'overload in base alla presenza di `in` è consentito, ma genera un avviso del compilatore:</span><span class="sxs-lookup"><span data-stu-id="e17a3-114">Overloading based on the presence of `in` is allowed, but generates a compiler warning:</span></span>  
  
```csharp
class InOverloads
{
    // Discouraged. Calling SampleMethod(value) is ambiguous.
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

<span data-ttu-id="e17a3-115">Le proprietà o costanti possono essere passate come parametri `in`, perché il metodo di chiamata non può modificare i relativi valori.</span><span class="sxs-lookup"><span data-stu-id="e17a3-115">Properties or constants may be passed as `in` parameters, because the calling method may not modify their values.</span></span>
  
<span data-ttu-id="e17a3-116">Non è possibile usare le parole chiave `in`, `ref` e `out` per i seguenti tipi di metodi:</span><span class="sxs-lookup"><span data-stu-id="e17a3-116">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="e17a3-117">Metodi asincroni definiti usando il modificatore [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="e17a3-117">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
- <span data-ttu-id="e17a3-118">Metodi iteratori che includono un'istruzione [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="e17a3-118">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

<span data-ttu-id="e17a3-119">In genere si dichiarano argomenti `in` per evitare le operazioni di copia necessarie per il passaggio di argomenti per valore.</span><span class="sxs-lookup"><span data-stu-id="e17a3-119">You typically declare `in` arguments to avoid the copy operations necessary for passing arguments by value.</span></span> <span data-ttu-id="e17a3-120">Ciò è particolarmente utile quando gli argomenti sono strutture o matrici di strutture.</span><span class="sxs-lookup"><span data-stu-id="e17a3-120">This is most useful when arguments are structures or arrays of structures.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e17a3-121">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e17a3-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e17a3-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e17a3-122">See Also</span></span>  
 [<span data-ttu-id="e17a3-123">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e17a3-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e17a3-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e17a3-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e17a3-125">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="e17a3-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="e17a3-126">Parametri dei metodi</span><span class="sxs-lookup"><span data-stu-id="e17a3-126">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
