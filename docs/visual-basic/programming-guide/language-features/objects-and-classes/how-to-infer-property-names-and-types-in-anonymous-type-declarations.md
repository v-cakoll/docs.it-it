---
title: 'Procedura: dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo'
ms.date: 07/20/2015
helpviewer_keywords:
- inferring property names [Visual Basic]
- anonymous types [Visual Basic], inferring property names and types
- inferring property types [Visual Basic]
ms.assetid: 7c748b22-913f-4d9d-b747-6b7bf296a0bc
ms.openlocfilehash: 9ebbbe9d2e6d36f5ab2bc7f7c916d18c9240a06d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404888"
---
# <a name="how-to-infer-property-names-and-types-in-anonymous-type-declarations-visual-basic"></a><span data-ttu-id="4ce7e-102">Procedura: dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ce7e-102">How to: Infer Property Names and Types in Anonymous Type Declarations (Visual Basic)</span></span>

<span data-ttu-id="4ce7e-103">I tipi anonimi non offrono alcun meccanismo per specificare direttamente i tipi di dati delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-103">Anonymous types provide no mechanism for directly specifying the data types of properties.</span></span> <span data-ttu-id="4ce7e-104">I tipi di tutte le proprietà vengono dedotti.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-104">Types of all properties are inferred.</span></span> <span data-ttu-id="4ce7e-105">Nell'esempio seguente, i tipi di `Name` e `Price` vengono dedotti direttamente dai valori usati per inizializzarli.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-105">In the following example, the types of `Name` and `Price` are inferred directly from the values that are used to initialize them.</span></span>

[!code-vb[VbVbalrAnonymousTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#1)]

<span data-ttu-id="4ce7e-106">I tipi anonimi possono anche dedurre i nomi e i tipi delle proprietà da altre origini.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-106">Anonymous types can also infer property names and types from other sources.</span></span> <span data-ttu-id="4ce7e-107">Le sezioni che seguono forniscono un elenco delle circostanze in cui l'inferenza è possibile e alcuni esempi di situazioni in cui non lo è.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-107">The sections that follow provide a list of the circumstances where inference is possible, and examples of situations where it is not.</span></span>

## <a name="successful-inference"></a><span data-ttu-id="4ce7e-108">Inferenza corretta</span><span class="sxs-lookup"><span data-stu-id="4ce7e-108">Successful Inference</span></span>

#### <a name="anonymous-types-can-infer-property-names-and-types-from-the-following-sources"></a><span data-ttu-id="4ce7e-109">I tipi anonimi possono dedurre i nomi e i tipi delle proprietà dalle origini seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ce7e-109">Anonymous types can infer property names and types from the following sources:</span></span>

- <span data-ttu-id="4ce7e-110">Dai nomi di variabili.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-110">From variable names.</span></span> <span data-ttu-id="4ce7e-111">Il tipo anonimo `anonProduct` avrà due proprietà, `productName` e `productPrice`.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-111">Anonymous type `anonProduct` will have two properties, `productName` and `productPrice`.</span></span> <span data-ttu-id="4ce7e-112">I relativi tipi di dati saranno quelli delle variabili originali, `String` e `Double`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-112">Their data types will be those of the original variables, `String` and `Double`, respectively.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#11)]

- <span data-ttu-id="4ce7e-113">Dai nomi di proprietà o di campo di altri oggetti.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-113">From property or field names of other objects.</span></span> <span data-ttu-id="4ce7e-114">Si consideri ad esempio un oggetto `car` di tipo `CarClass` che include le proprietà `Name` e `ID` .</span><span class="sxs-lookup"><span data-stu-id="4ce7e-114">For example, consider a `car` object of a `CarClass` type that includes `Name` and `ID` properties.</span></span> <span data-ttu-id="4ce7e-115">Per creare una nuova istanza di tipo anonimo, `car1`, con le proprietà `Name` e `ID` inizializzate con i valori dell'oggetto `car` , è possibile scrivere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4ce7e-115">To create a new anonymous type instance, `car1`, with `Name` and `ID` properties that are initialized with the values from the `car` object, you can write the following:</span></span>

  [!code-vb[VbVbalrAnonymousTypes#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#34)]

  <span data-ttu-id="4ce7e-116">La dichiarazione precedente è equivalente alla riga di codice più lunga che definisce il tipo anonimo `car2`.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-116">The previous declaration is equivalent to the longer line of code that defines anonymous type `car2`.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#35)]

- <span data-ttu-id="4ce7e-117">Dai nomi di membri XML.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-117">From XML member names.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#12)]

  <span data-ttu-id="4ce7e-118">Il tipo risultante per `anon` avrebbe una proprietà, `Book`, di tipo <xref:System.Collections.IEnumerable>(di XElement).</span><span class="sxs-lookup"><span data-stu-id="4ce7e-118">The resulting type for `anon` would have one property, `Book`, of type <xref:System.Collections.IEnumerable>(Of XElement).</span></span>

- <span data-ttu-id="4ce7e-119">Da una funzione che non ha parametri, ad esempio `SomeFunction` nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-119">From a function that has no parameters, such as `SomeFunction` in the following example.</span></span>

  ```vb
  Dim sc As New SomeClass
  Dim anon1 = New With {Key sc.SomeFunction()}
  ```

  <span data-ttu-id="4ce7e-120">La variabile `anon2` nel codice seguente è un tipo anonimo che ha una proprietà, un carattere denominato `First`.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-120">The variable `anon2` in the following code is an anonymous type that has one property, a character named `First`.</span></span> <span data-ttu-id="4ce7e-121">Questo codice visualizzerà una lettera "E", la lettera restituita dalla funzione <xref:System.Linq.Enumerable.First%2A>.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-121">This code will display a letter "E," the letter that is returned by function <xref:System.Linq.Enumerable.First%2A>.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#13)]

## <a name="inference-failures"></a><span data-ttu-id="4ce7e-122">Inferenze non corrette</span><span class="sxs-lookup"><span data-stu-id="4ce7e-122">Inference Failures</span></span>

#### <a name="name-inference-will-fail-in-many-circumstances-including-the-following"></a><span data-ttu-id="4ce7e-123">In molte circostanze l'inferenza del nome non avrà successo, come illustrato negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ce7e-123">Name inference will fail in many circumstances, including the following:</span></span>

- <span data-ttu-id="4ce7e-124">L'inferenza deriva dalla chiamata di un metodo, di un costruttore o di una proprietà con parametri che richiedono argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-124">The inference derives from the invocation of a method, a constructor, or a parameterized property that requires arguments.</span></span> <span data-ttu-id="4ce7e-125">La dichiarazione precedente di `anon1` ha esito negativo se `someFunction` ha uno o più argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-125">The previous declaration of `anon1` fails if `someFunction` has one or more arguments.</span></span>

  ```vb
  ' Not valid.
  ' Dim anon3 = New With {Key sc.someFunction(someArg)}
  ```

  <span data-ttu-id="4ce7e-126">L'assegnazione a un nuovo nome della proprietà risolve il problema.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-126">Assignment to a new property name solves the problem.</span></span>

  ```vb
  ' Valid.
  Dim anon4 = New With {Key .FunResult = sc.someFunction(someArg)}
  ```

- <span data-ttu-id="4ce7e-127">L'inferenza deriva da un'espressione complessa.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-127">The inference derives from a complex expression.</span></span>

  ```vb
  Dim aString As String = "Act "
  ' Not valid.
  ' Dim label = New With {Key aString & "IV"}
  ```

  <span data-ttu-id="4ce7e-128">L'errore può essere risolto assegnando il risultato dell'espressione a un nome di proprietà.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-128">The error can be resolved by assigning the result of the expression to a property name.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#14)]

- <span data-ttu-id="4ce7e-129">L'inferenza per più proprietà produce due o più proprietà che hanno lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-129">Inference for multiple properties produces two or more properties that have the same name.</span></span> <span data-ttu-id="4ce7e-130">Riferendosi di nuovo alle dichiarazioni illustrate negli esempi precedenti, non è possibile elencare `product.Name` e `car1.Name` come proprietà dello stesso tipo anonimo,</span><span class="sxs-lookup"><span data-stu-id="4ce7e-130">Referring back to declarations in earlier examples, you cannot list both `product.Name` and `car1.Name` as properties of the same anonymous type.</span></span> <span data-ttu-id="4ce7e-131">perché l'identificatore dedotto per ognuno di queste sarebbe `Name`.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-131">This is because the inferred identifier for each of these would be `Name`.</span></span>

  ```vb
  ' Not valid.
  ' Dim anon5 = New With {Key product.Name, Key car1.Name}
  ```

  <span data-ttu-id="4ce7e-132">Il problema può essere risolto assegnando i valori a nomi di proprietà distinti.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-132">The problem can be solved by assigning the values to distinct property names.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#36)]

  <span data-ttu-id="4ce7e-133">Si noti che le differenze di lettere maiuscole o minuscole non differenziano i due nomi.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-133">Note that changes in case (changes between uppercase and lowercase letters) do not make two names distinct.</span></span>

  ```vb
  Dim price = 0
  ' Not valid, because Price and price are the same name.
  ' Dim anon7 = New With {Key product.Price, Key price}
  ```

- <span data-ttu-id="4ce7e-134">Il tipo e il valore iniziale di una proprietà dipendono da un'altra proprietà non ancora stabilita.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-134">The initial type and value of one property depends on another property that is not yet established.</span></span> <span data-ttu-id="4ce7e-135">Ad esempio, `.IDName = .LastName` non è valido in una dichiarazione di tipo anonimo, a meno che `.LastName` non sia già stato inizializzato.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-135">For example, `.IDName = .LastName` is not valid in an anonymous type declaration unless `.LastName` is already initialized.</span></span>

  ```vb
  ' Not valid.
  ' Dim anon8 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}
  ```

  <span data-ttu-id="4ce7e-136">In questo esempio, è possibile risolvere il problema invertendo l'ordine in cui sono dichiarate le proprietà.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-136">In this example, you can fix the problem by reversing the order in which the properties are declared.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#15)]

- <span data-ttu-id="4ce7e-137">Un nome di proprietà del tipo anonimo è uguale al nome di un membro di <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-137">A property name of the anonymous type is the same as the name of a member of <xref:System.Object>.</span></span> <span data-ttu-id="4ce7e-138">Ad esempio, la dichiarazione seguente ha esito negativo perché `Equals` è un metodo di <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="4ce7e-138">For example, the following declaration fails because `Equals` is a method of <xref:System.Object>.</span></span>

  ```vb
  ' Not valid.
  ' Dim relationsLabels1 = New With {Key .Equals = "equals", Key .Greater = _
  '                       "greater than", Key .Less = "less than"}
  ```

  <span data-ttu-id="4ce7e-139">È possibile risolvere il problema modificando il nome della proprietà:</span><span class="sxs-lookup"><span data-stu-id="4ce7e-139">You can fix the problem by changing the property name:</span></span>

  [!code-vb[VbVbalrAnonymousTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#16)]

## <a name="see-also"></a><span data-ttu-id="4ce7e-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ce7e-140">See also</span></span>

- [<span data-ttu-id="4ce7e-141">Inizializzatori di oggetto: tipi denominati e tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="4ce7e-141">Object Initializers: Named and Anonymous Types</span></span>](object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="4ce7e-142">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="4ce7e-142">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="4ce7e-143">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="4ce7e-143">Anonymous Types</span></span>](anonymous-types.md)
- [<span data-ttu-id="4ce7e-144">Codice</span><span class="sxs-lookup"><span data-stu-id="4ce7e-144">Key</span></span>](../../../language-reference/modifiers/key.md)
