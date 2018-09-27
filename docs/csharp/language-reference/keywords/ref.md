---
title: Parola chiave ref (Riferimenti per C#)
ms.date: 03/06/2018
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: e0b82de125246e95d8dce2a7afc20119a8a1fe4f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44200553"
---
# <a name="ref-c-reference"></a><span data-ttu-id="9eb0c-102">ref (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="9eb0c-102">ref (C# Reference)</span></span>

<span data-ttu-id="9eb0c-103">La parola chiave `ref` indica un valore che viene passato per riferimento.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="9eb0c-104">Viene usata in quattro contesti diversi:</span><span class="sxs-lookup"><span data-stu-id="9eb0c-104">It is used in four different contexts:</span></span>

- <span data-ttu-id="9eb0c-105">Nella firma di un metodo e in una chiamata al metodo, per passare un argomento a un metodo per riferimento.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="9eb0c-106">Per altre informazioni, vedere [Passaggio di un argomento per riferimento](#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="9eb0c-106">See [Passing an argument by reference](#passing-an-argument-by-reference) for more information.</span></span>
- <span data-ttu-id="9eb0c-107">Nella firma di un metodo, per restituire un valore al chiamante per riferimento.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="9eb0c-108">Per altre informazioni, vedere [Valori restituiti di riferimento](#reference-return-values).</span><span class="sxs-lookup"><span data-stu-id="9eb0c-108">See [Reference return values](#reference-return-values) for more information.</span></span>
- <span data-ttu-id="9eb0c-109">Nel corpo di un membro, per indicare che un valore restituito di riferimento è archiviato in locale come un riferimento che il chiamante intende modificare o, in generale, che una variabile locale accede a un altro valore per riferimento.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify or, in general, a local variable accesses another value by reference.</span></span> <span data-ttu-id="9eb0c-110">Per altre informazioni, vedere [Variabili locali ref](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="9eb0c-110">See [Ref locals](#ref-locals) for more information.</span></span>
- <span data-ttu-id="9eb0c-111">In una dichiarazione `struct` per dichiarare `ref struct` o `ref readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-111">In a `struct` declaration to declare a `ref struct` or a `ref readonly struct`.</span></span> <span data-ttu-id="9eb0c-112">Per altre informazioni, vedere [Semantica di riferimento con i tipi valore](../../reference-semantics-with-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="9eb0c-112">For more information, see [Reference semantics with value types](../../reference-semantics-with-value-types.md).</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="9eb0c-113">Passaggio di un argomento per riferimento</span><span class="sxs-lookup"><span data-stu-id="9eb0c-113">Passing an argument by reference</span></span>

<span data-ttu-id="9eb0c-114">Quando viene usata nell'elenco di parametri di un metodo, la parola chiave `ref` indica che un argomento viene passato per riferimento, non per valore.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-114">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="9eb0c-115">L'effetto del passaggio per riferimento è che qualsiasi modifica all'argomento nel metodo chiamato viene riflessa nel metodo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-115">The effect of passing by reference is that any change to the argument in the called method is reflected in the calling method.</span></span> <span data-ttu-id="9eb0c-116">Ad esempio, se il chiamante passa un'espressione variabile locale o un'espressione di accesso dell'elemento della matrice e il metodo chiamato sostituisce l'oggetto a cui fa riferimento il parametro ref, l'elemento della matrice o la variabile locale del chiamante fa riferimento al nuovo oggetto quando viene restituito il risultato del metodo.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-116">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller’s local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
> <span data-ttu-id="9eb0c-117">Non confondere il concetto di passaggio per riferimento con il concetto di tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-117">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="9eb0c-118">I due concetti non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-118">The two concepts are not the same.</span></span> <span data-ttu-id="9eb0c-119">Un parametro di metodo può essere modificato da `ref` che si tratti di un tipo di valore o di un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-119">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="9eb0c-120">Non viene eseguito il boxing di un tipo di valore quando viene passato per riferimento.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-120">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="9eb0c-121">Per usare un parametro `ref`, la definizione del metodo e il metodo chiamante devono usare in modo esplicito la parola chiave `ref`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-121">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="9eb0c-122">Un argomento passato a un parametro `ref` o `in` deve essere inizializzato prima di essere passato.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-122">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="9eb0c-123">Questo comportamento è diverso dai parametri [out](out-parameter-modifier.md), i cui argomenti non devono essere inizializzati in modo esplicito prima di essere passati.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-123">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="9eb0c-124">I membri di una classe non possono avere firme che differiscono solo per `ref`, `in` o `out`.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-124">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="9eb0c-125">Un errore del compilatore si verifica se l'unica differenza tra due membri di un tipo è che uno di essi ha un parametro `ref` e l'altro ha un parametro `out` o `in`.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-125">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="9eb0c-126">Il codice seguente, ad esempio, non viene compilato.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-126">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

<span data-ttu-id="9eb0c-127">È tuttavia possibile eseguire l'overload dei metodi quando un metodo ha un parametro `ref`, `in` o `out` e l'altro ha un parametro di valore, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-127">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="9eb0c-128">In altre situazioni che richiedono la firma corrispondente, ad esempio nascondere o sottoporre a override, `in`, `ref` e `out` fanno parte della firma e non sono corrispondenti tra loro.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-128">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="9eb0c-129">Le proprietà non sono variabili.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-129">Properties are not variables.</span></span> <span data-ttu-id="9eb0c-130">Sono metodi e non possono essere passate ai parametri `ref`.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-130">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="9eb0c-131">Non è possibile usare le parole chiave `ref`, `in` e `out` per i seguenti tipi di metodi:</span><span class="sxs-lookup"><span data-stu-id="9eb0c-131">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="9eb0c-132">Metodi asincroni definiti usando il modificatore [async](async.md).</span><span class="sxs-lookup"><span data-stu-id="9eb0c-132">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="9eb0c-133">Metodi iteratori che includono un'istruzione [yield return](yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-133">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>  

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="9eb0c-134">Passaggio di un argomento per riferimento: un esempio</span><span class="sxs-lookup"><span data-stu-id="9eb0c-134">Passing an argument by reference: An example</span></span>

<span data-ttu-id="9eb0c-135">Negli esempi precedenti vengono passati tipi valore per riferimento.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-135">The previous examples pass value types by reference.</span></span> <span data-ttu-id="9eb0c-136">È anche possibile usare la parola chiave `ref` per passare tipi riferimento per riferimento.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-136">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="9eb0c-137">Il passaggio di un tipo riferimento per riferimento consente al metodo chiamato di sostituire l'oggetto a cui fa riferimento il parametro per riferimento nel chiamante.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-137">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="9eb0c-138">Il percorso di archiviazione dell'oggetto viene passato al metodo come valore del parametro referenziato.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-138">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="9eb0c-139">Se si modifica il valore nella posizione di archiviazione del parametro (in modo che punti a un nuovo oggetto), è anche possibile modificare il percorso di archiviazione a cui fa riferimento il chiamante.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-139">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="9eb0c-140">Nell'esempio seguente viene passata un'istanza di un tipo di riferimento come parametro `ref`.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-140">The following example passes an instance of a reference type as a `ref` parameter.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="9eb0c-141">Per altre informazioni su come passare i tipi di riferimento per valore e per riferimento, vedere [Passaggio di parametri di tipi di riferimento](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="9eb0c-141">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="9eb0c-142">Valori restituiti di riferimento</span><span class="sxs-lookup"><span data-stu-id="9eb0c-142">Reference return values</span></span>

<span data-ttu-id="9eb0c-143">I valori restituiti di riferimento (o valori restituiti ref) sono i valori che un metodo restituisce per riferimento al chiamante.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-143">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="9eb0c-144">In altre parole, il chiamante può modificare il valore restituito da un metodo e tale modifica viene riflessa nello stato dell'oggetto che contiene il metodo.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-144">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object that contains the method.</span></span>

<span data-ttu-id="9eb0c-145">Un valore restituito di riferimento viene definito mediante la parola chiave `ref`:</span><span class="sxs-lookup"><span data-stu-id="9eb0c-145">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="9eb0c-146">Nella firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-146">In the method signature.</span></span> <span data-ttu-id="9eb0c-147">Ad esempio, la firma del metodo seguente indica che il metodo `GetCurrentPrice` restituisce un valore <xref:System.Decimal> per riferimento.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-147">For example, the following method signature indicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

```csharp
public ref decimal GetCurrentPrice()
```

- <span data-ttu-id="9eb0c-148">Tra il token `return` e la variabile restituita in un'istruzione `return` nel metodo.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-148">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="9eb0c-149">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9eb0c-149">For example:</span></span>

```csharp
return ref DecimalArray[0];
```

<span data-ttu-id="9eb0c-150">Affinché il chiamante modifichi lo stato dell'oggetto, il valore restituito di riferimento deve essere archiviato in una variabile definita in modo esplicito come [variabile locale ref](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="9eb0c-150">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span>

<span data-ttu-id="9eb0c-151">Per un esempio, vedere [Esempio di valori restituiti e variabili locali ref](#a-ref-returns-and-ref-locals-example)</span><span class="sxs-lookup"><span data-stu-id="9eb0c-151">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example)</span></span>

## <a name="ref-locals"></a><span data-ttu-id="9eb0c-152">Variabili locali ref</span><span class="sxs-lookup"><span data-stu-id="9eb0c-152">Ref locals</span></span>

<span data-ttu-id="9eb0c-153">Una variabile locale ref viene usata per fare riferimento ai valori restituiti mediante `return ref`.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-153">A ref local variable is used to refer to values returned using `return ref`.</span></span> <span data-ttu-id="9eb0c-154">Non è possibile inizializzare una variabile locale ref in un valore restituito non ref.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-154">A ref local variable cannot be initialized to a non-ref return value.</span></span> <span data-ttu-id="9eb0c-155">In altre parole, il lato destro dell'inizializzazione deve essere un riferimento.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-155">In other words, the right hand side of the initialization must be a reference.</span></span> <span data-ttu-id="9eb0c-156">Tutte le modifiche apportate al valore della variabile locale ref vengono riflesse nello stato dell'oggetto di cui metodo ha restituito il valore per riferimento.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-156">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="9eb0c-157">Per definire una variabile locale ref, usare la parola chiave `ref` prima della dichiarazione di variabile, nonché immediatamente prima della chiamata al metodo che restituisce il valore per riferimento.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-157">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span>

<span data-ttu-id="9eb0c-158">Ad esempio, l'istruzione seguente definisce un valore di variabile locale ref restituito da un metodo denominato `GetEstimatedValue`:</span><span class="sxs-lookup"><span data-stu-id="9eb0c-158">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="9eb0c-159">È possibile accedere a un valore per riferimento nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-159">You can access a value by reference in the same way.</span></span> <span data-ttu-id="9eb0c-160">In alcuni casi, l'accesso a un valore per riferimento migliora le prestazioni evitando un'operazione di copia potenzialmente dispendiosa.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-160">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="9eb0c-161">L'istruzione seguente, ad esempio, spiega come sia possibile definire un valore locale di riferimento usato per fare riferimento a un valore.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-161">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="9eb0c-162">Si noti che nei due esempi la parola chiave `ref` deve essere usata in entrambe le posizioni. In caso contrario, il compilatore genera l'errore CS8172, "Non è possibile inizializzare una variabile per riferimento con un valore".</span><span class="sxs-lookup"><span data-stu-id="9eb0c-162">Note that in both examples the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span>

## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="9eb0c-163">Esempio di valori restituiti e variabili locali ref</span><span class="sxs-lookup"><span data-stu-id="9eb0c-163">A ref returns and ref locals example</span></span>

<span data-ttu-id="9eb0c-164">Nell'esempio seguente viene definita una classe `Book` che ha due campi <xref:System.String>, `Title` e `Author`.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-164">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="9eb0c-165">Definisce inoltre una classe `BookCollection` che include una matrice privata di oggetti `Book`.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-165">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="9eb0c-166">I singoli oggetti book vengono restituiti per riferimento chiamando il relativo metodo `GetBookByTitle`.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-166">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="9eb0c-167">Quando il chiamante archivia il valore restituito dal metodo `GetBookByTitle` come una variabile locale ref, le modifiche apportate al valore restituito dal chiamante vengono riflesse nell'oggetto `BookCollection`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9eb0c-167">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="9eb0c-168">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="9eb0c-168">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9eb0c-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9eb0c-169">See also</span></span>

- [<span data-ttu-id="9eb0c-170">Semantica di riferimento con i tipi valore</span><span class="sxs-lookup"><span data-stu-id="9eb0c-170">Reference semantics with value types</span></span>](../../reference-semantics-with-value-types.md)  
- [<span data-ttu-id="9eb0c-171">Passaggio di parametri</span><span class="sxs-lookup"><span data-stu-id="9eb0c-171">Passing Parameters</span></span>](../../programming-guide/classes-and-structs/passing-parameters.md)  
- [<span data-ttu-id="9eb0c-172">Parametri dei metodi</span><span class="sxs-lookup"><span data-stu-id="9eb0c-172">Method Parameters</span></span>](method-parameters.md)  
- [<span data-ttu-id="9eb0c-173">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="9eb0c-173">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="9eb0c-174">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="9eb0c-174">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="9eb0c-175">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="9eb0c-175">C# Keywords</span></span>](index.md)