---
title: ref (Riferimenti per C#)
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 427045317e9d7d0fe3435a486b9f761908ab5e78
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2018
---
# <a name="ref-c-reference"></a><span data-ttu-id="79ad9-102">ref (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="79ad9-102">ref (C# Reference)</span></span>

<span data-ttu-id="79ad9-103">La parola chiave `ref` indica un valore che viene passato per riferimento.</span><span class="sxs-lookup"><span data-stu-id="79ad9-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="79ad9-104">Viene usata in tre contesti diversi:</span><span class="sxs-lookup"><span data-stu-id="79ad9-104">It is used in three different contexts:</span></span> 

- <span data-ttu-id="79ad9-105">Nella firma di un metodo e in una chiamata al metodo, per passare un argomento a un metodo per riferimento.</span><span class="sxs-lookup"><span data-stu-id="79ad9-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="79ad9-106">Per altre informazioni, vedere [Passaggio di un argomento per riferimento](#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="79ad9-106">See [Passing an argument by reference](#passing-an-argument-by-reference) for more information.</span></span>

- <span data-ttu-id="79ad9-107">Nella firma di un metodo, per restituire un valore al chiamante per riferimento.</span><span class="sxs-lookup"><span data-stu-id="79ad9-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="79ad9-108">Per altre informazioni, vedere [Valori restituiti di riferimento](#reference-return-values).</span><span class="sxs-lookup"><span data-stu-id="79ad9-108">See [Reference return values](#reference-return-values) for more information.</span></span>

- <span data-ttu-id="79ad9-109">Nel corpo di un membro, per indicare che un valore restituito di riferimento è archiviato in locale come un riferimento che il chiamante intende modificare.</span><span class="sxs-lookup"><span data-stu-id="79ad9-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify.</span></span> <span data-ttu-id="79ad9-110">Per altre informazioni, vedere [Variabili locali ref](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="79ad9-110">See [Ref locals](#ref-locals) for more information.</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="79ad9-111">Passaggio di un argomento per riferimento</span><span class="sxs-lookup"><span data-stu-id="79ad9-111">Passing an argument by reference</span></span>

<span data-ttu-id="79ad9-112">Quando viene usata nell'elenco di parametri di un metodo, la parola chiave `ref` indica che un argomento viene passato per riferimento, non per valore.</span><span class="sxs-lookup"><span data-stu-id="79ad9-112">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="79ad9-113">L'effetto del passaggio per riferimento è che qualsiasi modifica all'argomento nel metodo chiamato viene riflessa nel metodo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="79ad9-113">The effect of passing by reference is that any change to the argument in the called method is reflected in the calling method.</span></span> <span data-ttu-id="79ad9-114">Ad esempio, se il chiamante passa un'espressione variabile locale o un'espressione di accesso dell'elemento della matrice e il metodo chiamato sostituisce l'oggetto a cui fa riferimento il parametro ref, l'elemento della matrice o la variabile locale del chiamante fa riferimento al nuovo oggetto quando viene restituito il risultato del metodo.</span><span class="sxs-lookup"><span data-stu-id="79ad9-114">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller’s local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
>  <span data-ttu-id="79ad9-115">Non confondere il concetto di passaggio per riferimento con il concetto di tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="79ad9-115">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="79ad9-116">I due concetti non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="79ad9-116">The two concepts are not the same.</span></span> <span data-ttu-id="79ad9-117">Un parametro di metodo può essere modificato da `ref` che si tratti di un tipo di valore o di un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="79ad9-117">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="79ad9-118">Non viene eseguito il boxing di un tipo di valore quando viene passato per riferimento.</span><span class="sxs-lookup"><span data-stu-id="79ad9-118">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="79ad9-119">Per usare un parametro `ref`, la definizione del metodo e il metodo chiamante devono usare in modo esplicito la parola chiave `ref`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="79ad9-119">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="79ad9-120">Un argomento passato a un parametro `ref` o `in` deve essere inizializzato prima di essere passato.</span><span class="sxs-lookup"><span data-stu-id="79ad9-120">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="79ad9-121">Questo comportamento è diverso dai parametri [out](out-parameter-modifier.md), i cui argomenti non devono essere inizializzati in modo esplicito prima di essere passati.</span><span class="sxs-lookup"><span data-stu-id="79ad9-121">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="79ad9-122">I membri di una classe non possono avere firme che differiscono solo per `ref`, `in` o `out`.</span><span class="sxs-lookup"><span data-stu-id="79ad9-122">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="79ad9-123">Un errore del compilatore si verifica se l'unica differenza tra due membri di un tipo è che uno di essi ha un parametro `ref` e l'altro ha un parametro `out` o `in`.</span><span class="sxs-lookup"><span data-stu-id="79ad9-123">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="79ad9-124">Il codice seguente, ad esempio, non viene compilato.</span><span class="sxs-lookup"><span data-stu-id="79ad9-124">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
<span data-ttu-id="79ad9-125">È tuttavia possibile eseguire l'overload dei metodi quando un metodo ha un parametro `ref`, `in` o `out` e l'altro ha un parametro di valore, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="79ad9-125">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="79ad9-126">In altre situazioni che richiedono la firma corrispondente, ad esempio nascondere o sottoporre a override, `in`, `ref` e `out` fanno parte della firma e non sono corrispondenti tra loro.</span><span class="sxs-lookup"><span data-stu-id="79ad9-126">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="79ad9-127">Le proprietà non sono variabili.</span><span class="sxs-lookup"><span data-stu-id="79ad9-127">Properties are not variables.</span></span> <span data-ttu-id="79ad9-128">Sono metodi e non possono essere passate ai parametri `ref`.</span><span class="sxs-lookup"><span data-stu-id="79ad9-128">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="79ad9-129">Per informazioni su come passare le matrici, vedere [Passaggio di matrici usando ref e out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="79ad9-129">For information about how to pass arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="79ad9-130">Non è possibile usare le parole chiave `ref`, `in` e `out` per i seguenti tipi di metodi:</span><span class="sxs-lookup"><span data-stu-id="79ad9-130">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="79ad9-131">Metodi asincroni definiti usando il modificatore [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="79ad9-131">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
- <span data-ttu-id="79ad9-132">Metodi iteratori che includono un'istruzione [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="79ad9-132">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="79ad9-133">Passaggio di un argomento per riferimento: un esempio</span><span class="sxs-lookup"><span data-stu-id="79ad9-133">Passing an argument by reference: An example</span></span>

<span data-ttu-id="79ad9-134">Negli esempi precedenti vengono passati tipi valore per riferimento.</span><span class="sxs-lookup"><span data-stu-id="79ad9-134">The previous examples pass value types by reference.</span></span> <span data-ttu-id="79ad9-135">È anche possibile usare la parola chiave `ref` per passare tipi riferimento per riferimento.</span><span class="sxs-lookup"><span data-stu-id="79ad9-135">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="79ad9-136">Il passaggio di un tipo riferimento per riferimento consente al metodo chiamato di sostituire l'oggetto a cui fa riferimento il parametro per riferimento nel chiamante.</span><span class="sxs-lookup"><span data-stu-id="79ad9-136">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="79ad9-137">Il percorso di archiviazione dell'oggetto viene passato al metodo come valore del parametro referenziato.</span><span class="sxs-lookup"><span data-stu-id="79ad9-137">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="79ad9-138">Se si modifica il valore nella posizione di archiviazione del parametro (in modo che punti a un nuovo oggetto), è anche possibile modificare il percorso di archiviazione a cui fa riferimento il chiamante.</span><span class="sxs-lookup"><span data-stu-id="79ad9-138">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="79ad9-139">Nell'esempio seguente viene passata un'istanza di un tipo di riferimento come parametro `ref`.</span><span class="sxs-lookup"><span data-stu-id="79ad9-139">The following example passes an instance of a reference type as a `ref` parameter.</span></span>   
  
[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="79ad9-140">Per altre informazioni su come passare i tipi di riferimento per valore e per riferimento, vedere [Passaggio di parametri di tipi di riferimento](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="79ad9-140">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="79ad9-141">Valori restituiti di riferimento</span><span class="sxs-lookup"><span data-stu-id="79ad9-141">Reference return values</span></span>

<span data-ttu-id="79ad9-142">I valori restituiti di riferimento (o valori restituiti ref) sono i valori che un metodo restituisce per riferimento al chiamante.</span><span class="sxs-lookup"><span data-stu-id="79ad9-142">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="79ad9-143">In altre parole, il chiamante può modificare il valore restituito da un metodo e tale modifica viene riflessa nello stato dell'oggetto che contiene il metodo.</span><span class="sxs-lookup"><span data-stu-id="79ad9-143">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object that contains the method.</span></span> 

<span data-ttu-id="79ad9-144">Un valore restituito di riferimento viene definito mediante la parola chiave `ref`:</span><span class="sxs-lookup"><span data-stu-id="79ad9-144">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="79ad9-145">Nella firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="79ad9-145">In the method signature.</span></span> <span data-ttu-id="79ad9-146">Ad esempio, la firma del metodo seguente indica che il metodo `GetCurrentPrice` restituisce un valore <xref:System.Decimal> per riferimento.</span><span class="sxs-lookup"><span data-stu-id="79ad9-146">For example, the following method signature inidicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

   ```csharp
   public ref decimal GetCurrentValue()
   ``` 
- <span data-ttu-id="79ad9-147">Tra il token `return` e la variabile restituita in un'istruzione `return` nel metodo.</span><span class="sxs-lookup"><span data-stu-id="79ad9-147">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="79ad9-148">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="79ad9-148">For example:</span></span>
 
   ```csharp
   return ref DecimalArray[0];
   ``` 

<span data-ttu-id="79ad9-149">Affinché il chiamante modifichi lo stato dell'oggetto, il valore restituito di riferimento deve essere archiviato in una variabile definita in modo esplicito come [variabile locale ref](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="79ad9-149">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span> 

<span data-ttu-id="79ad9-150">Per un esempio, vedere [Esempio di valori restituiti e variabili locali ref](#a-ref-returns-and-ref-locals-example)</span><span class="sxs-lookup"><span data-stu-id="79ad9-150">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example)</span></span>

## <a name="ref-locals"></a><span data-ttu-id="79ad9-151">Variabili locali ref</span><span class="sxs-lookup"><span data-stu-id="79ad9-151">Ref locals</span></span>

<span data-ttu-id="79ad9-152">Una variabile locale ref viene usata per fare riferimento ai valori restituiti mediante `return ref`.</span><span class="sxs-lookup"><span data-stu-id="79ad9-152">A ref local variable is used to refer to values returned using `return ref`.</span></span>  <span data-ttu-id="79ad9-153">Una variabile locale ref deve essere inizializzata e assegnata a un valore restituito ref.</span><span class="sxs-lookup"><span data-stu-id="79ad9-153">A ref local variable must be initialized and assigned to a ref return value.</span></span> <span data-ttu-id="79ad9-154">Tutte le modifiche apportate al valore della variabile locale ref vengono riflesse nello stato dell'oggetto di cui metodo ha restituito il valore per riferimento.</span><span class="sxs-lookup"><span data-stu-id="79ad9-154">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="79ad9-155">Per definire una variabile locale ref, usare la parola chiave `ref` prima della dichiarazione di variabile, nonché immediatamente prima della chiamata al metodo che restituisce il valore per riferimento.</span><span class="sxs-lookup"><span data-stu-id="79ad9-155">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span> 

<span data-ttu-id="79ad9-156">Ad esempio, l'istruzione seguente definisce un valore di variabile locale ref restituito da un metodo denominato `GetEstimatedValue`:</span><span class="sxs-lookup"><span data-stu-id="79ad9-156">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="79ad9-157">Si noti che la parola chiave `ref` deve essere usata in entrambe le posizioni. In caso contrario, il compilatore genererà l'errore CS8172, "Non è possibile inizializzare una variabile per riferimento con un valore".</span><span class="sxs-lookup"><span data-stu-id="79ad9-157">Note that the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span> 
 
## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="79ad9-158">Esempio di valori restituiti e variabili locali ref</span><span class="sxs-lookup"><span data-stu-id="79ad9-158">A ref returns and ref locals example</span></span>

<span data-ttu-id="79ad9-159">Nell'esempio seguente viene definita una classe `Book` che ha due campi <xref:System.String>, `Title` e `Author`.</span><span class="sxs-lookup"><span data-stu-id="79ad9-159">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="79ad9-160">Definisce inoltre una classe `BookCollection` che include una matrice privata di oggetti `Book`.</span><span class="sxs-lookup"><span data-stu-id="79ad9-160">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="79ad9-161">I singoli oggetti book vengono restituiti per riferimento chiamando il relativo metodo `GetBookByTitle`.</span><span class="sxs-lookup"><span data-stu-id="79ad9-161">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="79ad9-162">Quando il chiamante archivia il valore restituito dal metodo `GetBookByTitle` come una variabile locale ref, le modifiche apportate al valore restituito dal chiamante vengono riflesse nell'oggetto `BookCollection`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="79ad9-162">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="79ad9-163">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="79ad9-163">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="79ad9-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79ad9-164">See Also</span></span>  
 [<span data-ttu-id="79ad9-165">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="79ad9-165">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="79ad9-166">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="79ad9-166">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="79ad9-167">Passaggio di parametri</span><span class="sxs-lookup"><span data-stu-id="79ad9-167">Passing Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)  
 [<span data-ttu-id="79ad9-168">Parametri dei metodi</span><span class="sxs-lookup"><span data-stu-id="79ad9-168">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)  
 [<span data-ttu-id="79ad9-169">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="79ad9-169">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
