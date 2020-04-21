---
title: Parola chiave ref - Riferimenti per C#
ms.date: 04/21/2020
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: 494a46040d6cc33c5284449779fae89705fd29c2
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738831"
---
# <a name="ref-c-reference"></a><span data-ttu-id="6bd3d-102">ref (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="6bd3d-102">ref (C# Reference)</span></span>

<span data-ttu-id="6bd3d-103">La parola chiave `ref` indica un valore che viene passato per riferimento.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="6bd3d-104">Viene usata in quattro contesti diversi:</span><span class="sxs-lookup"><span data-stu-id="6bd3d-104">It is used in four different contexts:</span></span>

- <span data-ttu-id="6bd3d-105">Nella firma di un metodo e in una chiamata al metodo, per passare un argomento a un metodo per riferimento.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="6bd3d-106">Per altre informazioni, vedere [Passaggio di un argomento per riferimento](#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="6bd3d-106">For more information, see [Passing an argument by reference](#passing-an-argument-by-reference).</span></span>
- <span data-ttu-id="6bd3d-107">Nella firma di un metodo, per restituire un valore al chiamante per riferimento.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="6bd3d-108">Per altre informazioni, vedere [Valori di riferimento restituiti](#reference-return-values).</span><span class="sxs-lookup"><span data-stu-id="6bd3d-108">For more information, see [Reference return values](#reference-return-values).</span></span>
- <span data-ttu-id="6bd3d-109">Nel corpo di un membro, per indicare che un valore restituito di riferimento è archiviato in locale come un riferimento che il chiamante intende modificare o, in generale, che una variabile locale accede a un altro valore per riferimento.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify or, in general, a local variable accesses another value by reference.</span></span> <span data-ttu-id="6bd3d-110">Per altre informazioni, vedere [Variabili locali ref](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="6bd3d-110">For more information, see [Ref locals](#ref-locals).</span></span>
- <span data-ttu-id="6bd3d-111">In una dichiarazione `struct` per dichiarare `ref struct` o `readonly ref struct`.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-111">In a `struct` declaration to declare a `ref struct` or a `readonly ref struct`.</span></span> <span data-ttu-id="6bd3d-112">Per altre informazioni, [ `ref` ](../builtin-types/struct.md#ref-struct) vedere la sezione struct dell'articolo [Tipi di struttura.](../builtin-types/struct.md)</span><span class="sxs-lookup"><span data-stu-id="6bd3d-112">For more information, see the [`ref` struct](../builtin-types/struct.md#ref-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="6bd3d-113">Passaggio di un argomento per riferimento</span><span class="sxs-lookup"><span data-stu-id="6bd3d-113">Passing an argument by reference</span></span>

<span data-ttu-id="6bd3d-114">Quando viene usata nell'elenco di parametri di un metodo, la parola chiave `ref` indica che un argomento viene passato per riferimento, non per valore.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-114">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="6bd3d-115">La parola chiave `ref` imposta il parametro formale come alias dell'argomento, che deve essere una variabile.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-115">The `ref` keyword makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="6bd3d-116">In altre parole, qualsiasi operazione sul parametro viene eseguita sull'argomento.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-116">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="6bd3d-117">Ad esempio, se il chiamante passa un'espressione di accesso a una variabile locale o un'espressione di accesso all'elemento di matrice e il metodo chiamato sostituisce l'oggetto a cui fa riferimento il parametro ref, la variabile locale del chiamante o l'elemento della matrice fa ora riferimento al nuovo oggetto quando il metodo restituisce .</span><span class="sxs-lookup"><span data-stu-id="6bd3d-117">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller's local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
> <span data-ttu-id="6bd3d-118">Non confondere il concetto di passaggio per riferimento con il concetto di tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-118">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="6bd3d-119">I due concetti non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-119">The two concepts are not the same.</span></span> <span data-ttu-id="6bd3d-120">Un parametro di metodo può essere modificato da `ref` che si tratti di un tipo di valore o di un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-120">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="6bd3d-121">Non viene eseguito il boxing di un tipo di valore quando viene passato per riferimento.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-121">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="6bd3d-122">Per usare un parametro `ref`, la definizione del metodo e il metodo chiamante devono usare in modo esplicito la parola chiave `ref`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-122">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="6bd3d-123">Un argomento passato a un parametro `ref` o `in` deve essere inizializzato prima di essere passato.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-123">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="6bd3d-124">Questo comportamento è diverso dai parametri [out](out-parameter-modifier.md), i cui argomenti non devono essere inizializzati in modo esplicito prima di essere passati.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-124">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="6bd3d-125">I membri di una classe non possono avere firme che differiscono solo per `ref`, `in` o `out`.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-125">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="6bd3d-126">Un errore del compilatore si verifica se l'unica differenza tra due membri di un tipo è che uno di essi ha un parametro `ref` e l'altro ha un parametro `out` o `in`.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-126">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="6bd3d-127">Il codice seguente, ad esempio, non viene compilato.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-127">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

<span data-ttu-id="6bd3d-128">È tuttavia possibile eseguire l'overload dei metodi quando un metodo ha un parametro `ref`, `in` o `out` e l'altro ha un parametro di valore, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-128">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="6bd3d-129">In altre situazioni che richiedono la firma corrispondente, ad esempio nascondere o sottoporre a override, `in`, `ref` e `out` fanno parte della firma e non sono corrispondenti tra loro.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-129">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="6bd3d-130">Le proprietà non sono variabili.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-130">Properties are not variables.</span></span> <span data-ttu-id="6bd3d-131">Sono metodi e non possono essere passate ai parametri `ref`.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-131">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="6bd3d-132">Non è possibile usare le parole chiave `ref`, `in` e `out` per i seguenti tipi di metodi:</span><span class="sxs-lookup"><span data-stu-id="6bd3d-132">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="6bd3d-133">Metodi asincroni definiti usando il modificatore [async](async.md).</span><span class="sxs-lookup"><span data-stu-id="6bd3d-133">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="6bd3d-134">Metodi iteratori che includono un'istruzione [yield return](yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-134">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>

<span data-ttu-id="6bd3d-135">Inoltre, i metodi di [estensione](../../programming-guide/classes-and-structs/extension-methods.md) hanno le seguenti restrizioni:</span><span class="sxs-lookup"><span data-stu-id="6bd3d-135">In addition, [extension methods](../../programming-guide/classes-and-structs/extension-methods.md) have the following restrictions:</span></span>

- <span data-ttu-id="6bd3d-136">La `out` parola chiave non può essere utilizzata sul primo argomento di un metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-136">The `out` keyword cannot be used on the first argument of an extension method.</span></span>
- <span data-ttu-id="6bd3d-137">La `ref` parola chiave non può essere utilizzata sul primo argomento di un metodo di estensione quando l'argomento non è uno struct o un tipo generico non vincolato a essere uno struct.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-137">The `ref` keyword cannot be used on the first argument of an extension method when the argument is not a struct, or a generic type not constrained to be a struct.</span></span>
- <span data-ttu-id="6bd3d-138">La `in` parola chiave non può essere utilizzata a meno che il primo argomento non sia uno struct.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-138">The `in` keyword cannot be used unless the first argument is a struct.</span></span> <span data-ttu-id="6bd3d-139">La `in` parola chiave non può essere utilizzata su qualsiasi tipo generico, anche quando vincolata a essere uno struct.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-139">The `in` keyword cannot be used on any generic type, even when constrained to be a struct.</span></span>

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="6bd3d-140">Passaggio di un argomento per riferimento: un esempio</span><span class="sxs-lookup"><span data-stu-id="6bd3d-140">Passing an argument by reference: An example</span></span>

<span data-ttu-id="6bd3d-141">Negli esempi precedenti vengono passati tipi valore per riferimento.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-141">The previous examples pass value types by reference.</span></span> <span data-ttu-id="6bd3d-142">È anche possibile usare la parola chiave `ref` per passare tipi riferimento per riferimento.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-142">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="6bd3d-143">Il passaggio di un tipo riferimento per riferimento consente al metodo chiamato di sostituire l'oggetto a cui fa riferimento il parametro per riferimento nel chiamante.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-143">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="6bd3d-144">Il percorso di archiviazione dell'oggetto viene passato al metodo come valore del parametro referenziato.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-144">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="6bd3d-145">Se si modifica il valore nella posizione di archiviazione del parametro (in modo che punti a un nuovo oggetto), è anche possibile modificare il percorso di archiviazione a cui fa riferimento il chiamante.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-145">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="6bd3d-146">Nell'esempio seguente viene passata un'istanza di un tipo di riferimento come parametro `ref`.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-146">The following example passes an instance of a reference type as a `ref` parameter.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="6bd3d-147">Per altre informazioni su come passare i tipi di riferimento per valore e per riferimento, vedere [Passaggio di parametri di tipi di riferimento](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="6bd3d-147">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="6bd3d-148">Valori restituiti di riferimento</span><span class="sxs-lookup"><span data-stu-id="6bd3d-148">Reference return values</span></span>

<span data-ttu-id="6bd3d-149">I valori restituiti di riferimento (o valori restituiti ref) sono i valori che un metodo restituisce per riferimento al chiamante.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-149">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="6bd3d-150">In altre parole, il chiamante può modificare il valore restituito da un metodo e tale modifica viene riflessa nello stato dell'oggetto che contiene il metodo.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-150">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object that contains the method.</span></span>

<span data-ttu-id="6bd3d-151">Un valore restituito di riferimento viene definito mediante la parola chiave `ref`:</span><span class="sxs-lookup"><span data-stu-id="6bd3d-151">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="6bd3d-152">Nella firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-152">In the method signature.</span></span> <span data-ttu-id="6bd3d-153">Ad esempio, la firma del metodo seguente indica che il metodo `GetCurrentPrice` restituisce un valore <xref:System.Decimal> per riferimento.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-153">For example, the following method signature indicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

```csharp
public ref decimal GetCurrentPrice()
```

- <span data-ttu-id="6bd3d-154">Tra il token `return` e la variabile restituita in un'istruzione `return` nel metodo.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-154">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="6bd3d-155">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6bd3d-155">For example:</span></span>

```csharp
return ref DecimalArray[0];
```

<span data-ttu-id="6bd3d-156">Affinché il chiamante modifichi lo stato dell'oggetto, il valore restituito di riferimento deve essere archiviato in una variabile definita in modo esplicito come [variabile locale ref](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="6bd3d-156">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span>

<span data-ttu-id="6bd3d-157">Il metodo chiamato può anche dichiarare il valore restituito come `ref readonly` per restituire il valore per riferimento e specificare che il codice chiamante non può modificare il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-157">The called method may also declare the return value as `ref readonly` to return the value by reference, and enforce that the calling code cannot modify the returned value.</span></span> <span data-ttu-id="6bd3d-158">Il metodo chiamante può evitare la copia del valore restituito archiviando il valore in una variabile [ref readonly](#ref-readonly-locals) locale.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-158">The calling method can avoid copying the returned valued by storing the value in a local [ref readonly](#ref-readonly-locals) variable.</span></span>

<span data-ttu-id="6bd3d-159">Per un esempio, vedere A ref returns and ref locals example (Esempio di [valori restituiti ref e variabili locali di riferimento).](#a-ref-returns-and-ref-locals-example)</span><span class="sxs-lookup"><span data-stu-id="6bd3d-159">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example).</span></span>

## <a name="ref-locals"></a><span data-ttu-id="6bd3d-160">Variabili locali ref</span><span class="sxs-lookup"><span data-stu-id="6bd3d-160">Ref locals</span></span>

<span data-ttu-id="6bd3d-161">Una variabile locale ref viene usata per fare riferimento ai valori restituiti mediante `return ref`.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-161">A ref local variable is used to refer to values returned using `return ref`.</span></span> <span data-ttu-id="6bd3d-162">Non è possibile inizializzare una variabile locale ref in un valore restituito non ref.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-162">A ref local variable cannot be initialized to a non-ref return value.</span></span> <span data-ttu-id="6bd3d-163">In altre parole, il lato destro dell'inizializzazione deve essere un riferimento.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-163">In other words, the right-hand side of the initialization must be a reference.</span></span> <span data-ttu-id="6bd3d-164">Tutte le modifiche apportate al valore della variabile locale ref vengono riflesse nello stato dell'oggetto di cui metodo ha restituito il valore per riferimento.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-164">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="6bd3d-165">Per definire una variabile locale ref, usare la parola chiave `ref` prima della dichiarazione di variabile, nonché immediatamente prima della chiamata al metodo che restituisce il valore per riferimento.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-165">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span>

<span data-ttu-id="6bd3d-166">Ad esempio, l'istruzione seguente definisce un valore di variabile locale ref restituito da un metodo denominato `GetEstimatedValue`:</span><span class="sxs-lookup"><span data-stu-id="6bd3d-166">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="6bd3d-167">È possibile accedere a un valore per riferimento nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-167">You can access a value by reference in the same way.</span></span> <span data-ttu-id="6bd3d-168">In alcuni casi, l'accesso a un valore per riferimento migliora le prestazioni evitando un'operazione di copia potenzialmente dispendiosa.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-168">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="6bd3d-169">L'istruzione seguente, ad esempio, spiega come sia possibile definire un valore locale di riferimento usato per fare riferimento a un valore.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-169">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="6bd3d-170">In entrambi `ref` gli esempi la parola chiave deve essere utilizzata in entrambe le posizioni oppure il compilatore genera l'errore CS8172, "Impossibile inizializzare una variabile per riferimento con un valore".</span><span class="sxs-lookup"><span data-stu-id="6bd3d-170">In both examples the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span>

<span data-ttu-id="6bd3d-171">A partire da C# 7.3, la variabile di iterazione dell'istruzione `foreach` può essere una variabile locale ref o locale ref readonly.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-171">Beginning with C# 7.3, the iteration variable of the `foreach` statement can be ref local or ref readonly local variable.</span></span> <span data-ttu-id="6bd3d-172">Per altre informazioni, vedere l'articolo sull'[istruzione foreach](foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="6bd3d-172">For more information, see the [foreach statement](foreach-in.md) article.</span></span>

<span data-ttu-id="6bd3d-173">Inoltre, a partire dalla versione 7.3 di C, è possibile riassegnare una variabile locale ref o ref readonly con l'operatore di [assegnazione ref](../operators/assignment-operator.md#ref-assignment-operator).</span><span class="sxs-lookup"><span data-stu-id="6bd3d-173">Also beginning with C# 7.3, you can reassign a ref local or ref readonly local variable with the [ref assignment operator](../operators/assignment-operator.md#ref-assignment-operator).</span></span>

## <a name="ref-readonly-locals"></a><span data-ttu-id="6bd3d-174">Variabili ref readonly</span><span class="sxs-lookup"><span data-stu-id="6bd3d-174">Ref readonly locals</span></span>

<span data-ttu-id="6bd3d-175">Una variabile locale ref readonly viene usata per fare riferimento ai valori restituiti dal metodo o dalla proprietà che include `ref readonly` nella propria firma e usa `return ref`.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-175">A ref readonly local is used to refer to values returned by the method or property that has `ref readonly` in its signature and uses `return ref`.</span></span> <span data-ttu-id="6bd3d-176">Una variabile `ref readonly` combina le proprietà di una variabile locale `ref` con una variabile `readonly`: è un alias per l'archiviazione cui è assegnata e non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-176">A `ref readonly` variable combines the properties of a `ref` local variable with a `readonly` variable: it is an alias to the storage it's assigned to, and it cannot be modified.</span></span>

## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="6bd3d-177">Esempio di valori restituiti e variabili locali ref</span><span class="sxs-lookup"><span data-stu-id="6bd3d-177">A ref returns and ref locals example</span></span>

<span data-ttu-id="6bd3d-178">Nell'esempio seguente viene definita una classe `Book` che ha due campi <xref:System.String>, `Title` e `Author`.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-178">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="6bd3d-179">Definisce inoltre una classe `BookCollection` che include una matrice privata di oggetti `Book`.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-179">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="6bd3d-180">I singoli oggetti book vengono restituiti per riferimento chiamando il relativo metodo `GetBookByTitle`.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-180">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="6bd3d-181">Quando il chiamante archivia il valore restituito dal metodo `GetBookByTitle` come una variabile locale ref, le modifiche apportate al valore restituito dal chiamante vengono riflesse nell'oggetto `BookCollection`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6bd3d-181">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="6bd3d-182">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="6bd3d-182">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6bd3d-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bd3d-183">See also</span></span>

- [<span data-ttu-id="6bd3d-184">Scrivere codice efficiente sicuro</span><span class="sxs-lookup"><span data-stu-id="6bd3d-184">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)
- [<span data-ttu-id="6bd3d-185">Valori restituiti e variabili locali ref</span><span class="sxs-lookup"><span data-stu-id="6bd3d-185">Ref returns and ref locals</span></span>](../../programming-guide/classes-and-structs/ref-returns.md)
- [<span data-ttu-id="6bd3d-186">Espressione condizionale ref</span><span class="sxs-lookup"><span data-stu-id="6bd3d-186">Conditional ref expression</span></span>](../operators/conditional-operator.md#conditional-ref-expression)
- [<span data-ttu-id="6bd3d-187">Passaggio di parametriPassing Parameters</span><span class="sxs-lookup"><span data-stu-id="6bd3d-187">Passing Parameters</span></span>](../../programming-guide/classes-and-structs/passing-parameters.md)
- [<span data-ttu-id="6bd3d-188">Parametri di metodo</span><span class="sxs-lookup"><span data-stu-id="6bd3d-188">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="6bd3d-189">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="6bd3d-189">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6bd3d-190">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="6bd3d-190">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6bd3d-191">Parole chiave di C</span><span class="sxs-lookup"><span data-stu-id="6bd3d-191">C# Keywords</span></span>](index.md)
