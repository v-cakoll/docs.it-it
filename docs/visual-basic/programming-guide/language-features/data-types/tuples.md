---
title: Tuple in Visual Basic
ms.custom: 
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2653b9dc8a6ecbcb718c20be8bd6275edf4cfb6e
ms.sourcegitcommit: be1fb5d9447ad459bef22b91a91c72e3e0b2d916
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2018
---
# <a name="tuples-visual-basic"></a><span data-ttu-id="ad2c9-102">Tuple (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad2c9-102">Tuples (Visual Basic)</span></span>

<span data-ttu-id="ad2c9-103">A partire da Visual Basic 2017, il linguaggio Visual Basic offre supporto incorporato per le tuple che rende la creazione di tuple e accedere agli elementi di tuple più semplice.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-103">Starting with Visual Basic 2017, the Visual Basic language offers built-in support for tuples that makes creating tuples and accessing the elements of tuples easier.</span></span> <span data-ttu-id="ad2c9-104">Una tupla è una struttura di dati più semplice con un numero specifico e la sequenza di valori.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-104">A tuple is a light-weight data structure that has a specific number and sequence of values.</span></span> <span data-ttu-id="ad2c9-105">Quando si crea un'istanza di tupla, si definisce il numero e il tipo di dati di ogni valore (o elemento).</span><span class="sxs-lookup"><span data-stu-id="ad2c9-105">When you instantiate the tuple, you define the number and the data type of each value (or element).</span></span> <span data-ttu-id="ad2c9-106">Ad esempio, una tupla con 2 elementi (o coppia) dispone di due elementi.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-106">For example, a 2-tuple (or pair) has two elements.</span></span> <span data-ttu-id="ad2c9-107">Potrebbe essere il primo un `Boolean` valore, mentre il secondo è un `String`.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-107">The first might be a `Boolean` value, while the second is a `String`.</span></span> <span data-ttu-id="ad2c9-108">Poiché le tuple semplificano archiviare più valori in un singolo oggetto, vengono spesso utilizzati come un modo semplice per restituire più valori da un metodo.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-108">Because tuples make it easy to store multiple values in a single object, they are often used as a lightweight way to return multiple values from a method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad2c9-109">Supporto di tuple richiede il <xref:System.ValueTuple> tipo.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-109">Tuple support requires the <xref:System.ValueTuple> type.</span></span> <span data-ttu-id="ad2c9-110">Se non è installato il 4.7 di .NET Framework, è necessario aggiungere il pacchetto NuGet `System.ValueTuple`, che è disponibile nella raccolta NuGet.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-110">If the .NET Framework 4.7 is not installed, you must add the NuGet package `System.ValueTuple`, which is available on the NuGet Gallery.</span></span> <span data-ttu-id="ad2c9-111">Senza questo pacchetto, è possibile che venga visualizzato un errore di compilazione simile a "Tipo predefinito 'ValueTuple(Of,,,)' non è definito né importato."</span><span class="sxs-lookup"><span data-stu-id="ad2c9-111">Without this package, you may get a compilation error similar to, "Predefined type 'ValueTuple(Of,,,)' is not defined or imported."</span></span>

## <a name="instantiating-and-using-a-tuple"></a><span data-ttu-id="ad2c9-112">Creazione e utilizzo di una tupla</span><span class="sxs-lookup"><span data-stu-id="ad2c9-112">Instantiating and using a tuple</span></span>

<span data-ttu-id="ad2c9-113">L'istanza di una tupla racchiudendo le sue parentesi im valori delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-113">You instantiate a tuple by enclosing its comma-delimited values im parentheses.</span></span> <span data-ttu-id="ad2c9-114">Tali valori diventa quindi un campo della tupla.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-114">Each of those values then becomes a field of the tuple.</span></span> <span data-ttu-id="ad2c9-115">Ad esempio, il codice seguente definisce una triple (o una tupla con 3 elementi) con un `Date` come primo valore, un `String` come il secondo e un `Boolean` come il rispettivo terzo.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-115">For example, the following code defines a triple (or 3-tuple) with a `Date` as its first value, a `String` as its second, and a `Boolean` as its third.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

<span data-ttu-id="ad2c9-116">Per impostazione predefinita, il nome di ogni campo in una tupla è costituita da stringa `Item` insieme posizione in base 1 del campo nella tupla.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-116">By default, the name of each field in a tuple consists of the string `Item` along with the field's one-based position in the tuple.</span></span> <span data-ttu-id="ad2c9-117">Per questo tupla con 3 elementi, il `Date` campo è `Item1`, `String` campo è `Item2`e `Boolean` campo è `Item3`.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-117">For this 3-tuple, the `Date` field is `Item1`, the `String` field is `Item2`, and the `Boolean` field is `Item3`.</span></span> <span data-ttu-id="ad2c9-118">L'esempio seguente mostra i valori dei campi della tupla creata nella riga di codice precedente</span><span class="sxs-lookup"><span data-stu-id="ad2c9-118">The following example displays the values of fields of the tuple instantiated in the previous line of code</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

<span data-ttu-id="ad2c9-119">I campi di una tupla di Visual Basic sono di lettura-scrittura. Dopo aver creato l'istanza di una tupla, è possibile modificare i relativi valori.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-119">The fields of a Visual Basic tuple are read-write; after you've instantiated a tuple, you can modify its values.</span></span> <span data-ttu-id="ad2c9-120">Nell'esempio seguente modifica due dei tre campi della tupla creata nell'esempio precedente e viene visualizzato il risultato.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-120">The following example modifies two of the three fields of the tuple created in the previous example and displays the result.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a><span data-ttu-id="ad2c9-121">Creazione di un'istanza e l'utilizzo di una tupla denominata</span><span class="sxs-lookup"><span data-stu-id="ad2c9-121">Instantiating and using a named tuple</span></span>

<span data-ttu-id="ad2c9-122">Anziché utilizzare i nomi predefiniti per i campi di una tupla, è possibile creare un'istanza di un *denominato tupla* assegnando nomi personalizzati agli elementi della tupla.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-122">Rather than using default names for a tuple's fields, you can instantiate a *named tuple* by assigning your own names to the tuple's elements.</span></span> <span data-ttu-id="ad2c9-123">I campi della tupla è possibile accedere tramite i nomi assegnati *o* con i relativi nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-123">The tuple's fields can then be accessed by their assigned names *or* by their default names.</span></span> <span data-ttu-id="ad2c9-124">Nell'esempio seguente viene creata un'istanza la tupla di 3 stesso come in precedenza, ad eccezione del fatto che determina in modo esplicito il nome del primo campo `EventDate`, il secondo `Name`e il terzo `IsHoliday`.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-124">The following example instantiates the same 3-tuple as previously, except that it explicitly names the first field `EventDate`, the second `Name`, and the third `IsHoliday`.</span></span> <span data-ttu-id="ad2c9-125">Quindi Visualizza i valori dei campi, li modifica e visualizza i valori dei campi nuovamente.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-125">It then displays the field values, modifies them, and displays the field values again.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="ad2c9-126">Nomi di elemento dedotto tupla</span><span class="sxs-lookup"><span data-stu-id="ad2c9-126">Inferred tuple element names</span></span>

<span data-ttu-id="ad2c9-127">A partire da 15.3 Visual Basic, Visual Basic in grado di dedurre i nomi di elementi di tupla. non è necessario assegnare loro in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-127">Starting with Visual Basic 15.3, Visual Basic can infer the names of tuple elements; you do not have to assign them explicitly.</span></span> <span data-ttu-id="ad2c9-128">Nomi derivati tupla sono utili quando si Inizializza una tupla da un set di variabili e si desidera che il nome dell'elemento tupla per corrispondere al nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-128">Inferred tuple names are useful when you initialize a tuple from a set of variables, and you want the tuple element name to be the same as the variable name.</span></span> 

<span data-ttu-id="ad2c9-129">Nell'esempio seguente viene creato un `stateInfo` tupla che contiene tre in modo esplicito elementi, denominati `state`, `stateName`, e `capital`.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-129">The following example creates a `stateInfo` tuple that contains three explicitly named elements, `state`, `stateName`, and `capital`.</span></span> <span data-ttu-id="ad2c9-130">Si noti che, quando si assegna gli elementi, l'istruzione di inizializzazione di tupla, viene semplicemente assegnata agli elementi denominati i valori delle variabili denominate in modo identico.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-130">Note that, in naming the elements, the tuple initialization statement simply assigns the named elements the values of the identically named variables.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
<span data-ttu-id="ad2c9-131">Poiché gli elementi e le variabili hanno lo stesso nome, il compilatore Visual Basic può dedurre i nomi dei campi, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-131">Because elements and variables have the same name, the Visual Basic compiler can infer the names of the fields, as the following example shows.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

<span data-ttu-id="ad2c9-132">Per abilitare i nomi degli elementi interred tupla, è necessario definire la versione del compilatore Visual Basic da utilizzare nel progetto Visual Basic (\*. vbproj) file:</span><span class="sxs-lookup"><span data-stu-id="ad2c9-132">To enable interred tuple element names, you must define the version of the Visual Basic compiler to use in your Visual Basic project (\*.vbproj) file:</span></span> 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 

The version number can be any version of the Visual Basic compiler starting with 15.3. Rather than hard-coding a specific compiler version, you can also specify "Latest" as the value of `LangVersion` to compile with the most recent version of the Visual Basic compiler installed on your system.

In some cases, the Visual Basic compiler cannot infer the tuple element name from the candidate name, and the tuple field can only be referenced using its default name, such as `Item1`, `Item2`, etc. These include:

- The candidate name is the same as the name of a tuple member, such as `Item3`, `Rest`, or `ToString`.

- The candidate name is duplicated in the tuple.
 
When field name inference fails, Visual Basic does not generate a compiler error, nor is an exception thrown at runtime. Instead, tuple fields must be referenced by their predefined names, such as `Item1` and `Item2`. 
  
## Tuples versus structures

A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types. For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure. It is designed to be a lightweight container for data. Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have. These include:

- Customer members. You cannot define your own properties, methods, or events for a tuple.

- Validation. You cannot validate the data assigned to fields.

- Immutability. Visual Basic tuples are mutable. In contrast, a custom structure allows you to control whether an instance is mutable or immutable.

If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.

A Visual Basic tuple does inherit the members of its **ValueTuple** type. In addition to its fields, these include the following methods:

| Member | Description |
| ---|---|
| CompareTo | Compares the current tuple to another tuple with the same number of elements. |
| Equals | Determines whether the current tuple is equal to another tuple or object. |
| GetHashCode | Calculates the hash code for the current instance. |
| ToString | Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields. |

In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.

## Assignment and tuples

Visual Basic supports assignment between tuple types that have the same number of fields. The field types can be converted if one of the following is true:

- The source and target field are of the same type.

- A widening (or implicit) conversion of the source type to the target type is defined. 

- `Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined. This conversion can throw an exception if the source value is outside the range of the target type.

Other conversions are not considered for assignments. Let's look at the kinds of assignments that are allowed between tuple types.

Consider these variables used in the following examples:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields. Their field names are the default `Item1` and `Item2`. The last two variables, `named` and `differentName` have semantic field names. Note that these two tuples have different names for the fields.

All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical. Therefore, all of these assignments work:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Notice that the names of the tuples are not assigned. The values of the fields are assigned following the order of the fields in the tuple.

Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`. This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Tuples with different numbers of fields are not assignable:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a><span data-ttu-id="ad2c9-133">Tuple come valori restituiti dal metodo</span><span class="sxs-lookup"><span data-stu-id="ad2c9-133">Tuples as method return values</span></span>

<span data-ttu-id="ad2c9-134">Un metodo può restituire un solo valore.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-134">A method can return only a single value.</span></span> <span data-ttu-id="ad2c9-135">Spesso, tuttavia, si desidera che una chiamata al metodo per restituire più valori.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-135">Frequently, though, you'd like a method call to return multiple values.</span></span> <span data-ttu-id="ad2c9-136">Esistono diversi modi per risolvere questa limitazione:</span><span class="sxs-lookup"><span data-stu-id="ad2c9-136">There are several ways to work around this limitation:</span></span>

- <span data-ttu-id="ad2c9-137">È possibile creare una classe personalizzata o una struttura le cui proprietà o campi rappresentano i valori restituiti dal metodo.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-137">You can create a custom class or structure whose properties or fields represent values returned by the method.</span></span> <span data-ttu-id="ad2c9-138">In questo modo è una soluzione ad alta densità; è necessario definire un tipo personalizzato, il cui unico scopo consiste nel recuperare i valori da una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-138">Thus is a heavyweight solution; it requires that you define a custom type whose only purpose is to retrieve values from a method call.</span></span>

- <span data-ttu-id="ad2c9-139">È possibile restituire un solo valore dal metodo e restituire i valori rimanenti dal passaggio per riferimento al metodo.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-139">You can return a single value from the method, and return the remaining values by passing them by reference to the method.</span></span> <span data-ttu-id="ad2c9-140">Ciò comporta l'overhead di un'istanza di una variabile e i rischi per la sovrascrittura accidentale del valore della variabile che viene passato per riferimento.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-140">This involves the overhead of instantiating a variable and risks inadvertently overwriting the value of the variable that you pass by reference.</span></span>

- <span data-ttu-id="ad2c9-141">È possibile utilizzare una tupla, che fornisce una soluzione semplice per il recupero di più valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-141">You can use a tuple, which provides a lightweight solution to retrieving multiple return values.</span></span>

<span data-ttu-id="ad2c9-142">Ad esempio, il **TryParse** metodi ritorno .NET un `Boolean` valore che indica se l'operazione di analisi ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-142">For example, the **TryParse** methods in .NET return a `Boolean` value that indicates whether the parsing operation succeeded.</span></span> <span data-ttu-id="ad2c9-143">In una variabile passata per riferimento al metodo viene restituito il risultato dell'operazione di analisi.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-143">The result of the parsing operation is returned in a variable passed by reference to the method.</span></span> <span data-ttu-id="ad2c9-144">In genere, una chiamata a di un metodo di analisi, ad esempio <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> sarà simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="ad2c9-144">Normally, a call to the a parsing method such as <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> looks like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

<span data-ttu-id="ad2c9-145">È possibile tornare una tupla da operazione di analisi, si esegue il wrapping della chiamata al <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> nel metodo di un metodo.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-145">We can return a tuple from the parsing operation if we wrap the call to the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method in our own method.</span></span> <span data-ttu-id="ad2c9-146">Nell'esempio seguente, `NumericLibrary.ParseInteger` chiamate di <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> (metodo) e restituisce una tupla con due elementi denominata.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-146">In the following example, `NumericLibrary.ParseInteger` calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method and returns a named tuple with two elements.</span></span> 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

<span data-ttu-id="ad2c9-147">È quindi possibile chiamare il metodo con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ad2c9-147">You can then call the method with code like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a><span data-ttu-id="ad2c9-148">Tuple di Visual Basic e le tuple in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ad2c9-148">Visual Basic tuples and tuples in the .NET Framework</span></span>

<span data-ttu-id="ad2c9-149">Una tupla di Visual Basic è un'istanza di uno del **System.ValueTuple** tipi generici, che sono stati introdotti i 4.7 di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-149">A Visual Basic tuple is an instance of one of the **System.ValueTuple** generic types, which were introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="ad2c9-150">.NET Framework include anche un set di generico **System. Tuple** classi.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-150">The .NET Framework also includes a set of generic **System.Tuple** classes.</span></span> <span data-ttu-id="ad2c9-151">Queste classi, tuttavia, diversi da tuple di Visual Basic e **System.ValueTuple** tipi generici in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="ad2c9-151">These classes, however, differ from Visual Basic tuples and the **System.ValueTuple** generic types in a number of ways:</span></span>

- <span data-ttu-id="ad2c9-152">Gli elementi del **tupla** classi sono le proprietà denominate `Item1`, `Item2`e così via.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-152">The elements of the **Tuple** classes are properties named `Item1`, `Item2`, and so on.</span></span> <span data-ttu-id="ad2c9-153">In Visual Basic tuple e **ValueTuple** campi sono i tipi, degli elementi della tupla.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-153">In Visual Basic tuples and the **ValueTuple** types, tuple elements are fields.</span></span>

- <span data-ttu-id="ad2c9-154">Non è possibile assegnare nomi significativi per gli elementi di un **tupla** istanza o di un **ValueTuple** istanza.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-154">You cannot assign meaningful names to the elements of a **Tuple** instance or of a **ValueTuple** instance.</span></span> <span data-ttu-id="ad2c9-155">Visual Basic consente di assegnare i nomi con comunicano il significato dei campi.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-155">Visual Basic allows you to assign names that communicate the meaning of the fields.</span></span>

- <span data-ttu-id="ad2c9-156">Le proprietà di un **tupla** istanza sono di sola lettura; le tuple sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-156">The properties of a **Tuple** instance are read-only; the tuples are immutable.</span></span> <span data-ttu-id="ad2c9-157">In Visual Basic tuple e **ValueTuple** tipi, campi di tupla sono di lettura / scrittura; le tuple sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-157">In Visual Basic tuples and the **ValueTuple** types, tuple fields are read-write; the tuples are mutable.</span></span>

- <span data-ttu-id="ad2c9-158">Il tipo generico **tupla** tipi sono tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-158">The generic **Tuple** types are reference types.</span></span> <span data-ttu-id="ad2c9-159">Utilizzo di queste **tupla** tipi significa allocazione di oggetti.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-159">Using these **Tuple** types means allocating objects.</span></span> <span data-ttu-id="ad2c9-160">Nei percorsi critici, ciò può avere un impatto notevole sulle prestazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-160">On hot paths, this can have a measurable impact on your application's performance.</span></span> <span data-ttu-id="ad2c9-161">Visual Basic tuple e **ValueTuple** tipi sono tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-161">Visual Basic tuples and the **ValueTuple** types are value types.</span></span>

<span data-ttu-id="ad2c9-162">Metodi di estensione di <xref:System.TupleExtensions> classe rendono più facile eseguire la conversione tra .NET e Visual Basic Tuple **tupla** oggetti.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-162">Extension methods in the <xref:System.TupleExtensions> class make it easy to convert between Visual Basic tuples and .NET **Tuple** objects.</span></span> <span data-ttu-id="ad2c9-163">Il **ToTuple** metodo converte una tupla di Visual Basic .NET **tupla** oggetto e **ToValueTuple** metodo converte .NET **tupla** oggetto da una tupla di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-163">The **ToTuple** method converts a Visual Basic tuple to a .NET **Tuple** object, and the **ToValueTuple** method converts a .NET **Tuple** object to a Visual Basic tuple.</span></span>

<span data-ttu-id="ad2c9-164">L'esempio seguente crea una tupla, viene convertito in .NET **tupla** oggetto e converte di nuovo in una tupla di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-164">The following example creates a tuple, converts it to a .NET **Tuple** object, and converts it back to a Visual Basic tuple.</span></span> <span data-ttu-id="ad2c9-165">Nell'esempio viene quindi confrontato con questo tupla con quello originale per verificare che siano uguali.</span><span class="sxs-lookup"><span data-stu-id="ad2c9-165">The example then compares this tuple with the original one to ensure that they are equal.</span></span>

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a><span data-ttu-id="ad2c9-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad2c9-166">See also</span></span>

[<span data-ttu-id="ad2c9-167">Riferimenti per il linguaggio Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad2c9-167">Visual Basic Language Reference</span></span>](index.md)  
