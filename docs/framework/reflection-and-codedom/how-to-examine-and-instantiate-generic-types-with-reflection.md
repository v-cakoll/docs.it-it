---
title: 'Procedura: Esaminare e creare istanze di tipi generici tramite reflection'
description: Vedere come esaminare e creare istanze di tipi generici con Reflection. Usare le proprietà IsGenericType, IsGenericParameter e GenericParameterPosition.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, generic types
- generics [.NET Framework], reflection
ms.assetid: f93b03b0-1778-43fc-bc6d-35983d210e74
ms.openlocfilehash: b57a0ed0c809da442dc9fcf202ad364060971f80
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865099"
---
# <a name="how-to-examine-and-instantiate-generic-types-with-reflection"></a><span data-ttu-id="85100-104">Procedura: Esaminare e creare istanze di tipi generici tramite reflection</span><span class="sxs-lookup"><span data-stu-id="85100-104">How to: Examine and Instantiate Generic Types with Reflection</span></span>
<span data-ttu-id="85100-105">Le informazioni sui tipi generici vengono ottenute esattamente come quelle relative ad altri tipi, ovvero esaminando un oggetto <xref:System.Type> che rappresenta il tipo generico.</span><span class="sxs-lookup"><span data-stu-id="85100-105">Information about generic types is obtained in the same way as information about other types: by examining a <xref:System.Type> object that represents the generic type.</span></span> <span data-ttu-id="85100-106">La differenza principale è data dal fatto che un tipo generico dispone di un elenco di oggetti <xref:System.Type> che rappresentano i relativi parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="85100-106">The principle difference is that a generic type has a list of <xref:System.Type> objects representing its generic type parameters.</span></span> <span data-ttu-id="85100-107">La prima procedura in questa sezione esamina i tipi generici.</span><span class="sxs-lookup"><span data-stu-id="85100-107">The first procedure in this section examines generic types.</span></span>  
  
 <span data-ttu-id="85100-108">È possibile creare un oggetto <xref:System.Type> che rappresenta un tipo costruito associando argomenti di tipo ai parametri di tipo di una definizione di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="85100-108">You can create a <xref:System.Type> object that represents a constructed type by binding type arguments to the type parameters of a generic type definition.</span></span> <span data-ttu-id="85100-109">Questo concetto è illustrato nella seconda procedura.</span><span class="sxs-lookup"><span data-stu-id="85100-109">The second procedure demonstrates this.</span></span>  
  
### <a name="to-examine-a-generic-type-and-its-type-parameters"></a><span data-ttu-id="85100-110">Per esaminare un tipo generico e i relativi parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="85100-110">To examine a generic type and its type parameters</span></span>  
  
1. <span data-ttu-id="85100-111">Ottenere un'istanza di <xref:System.Type> che rappresenta il tipo generico.</span><span class="sxs-lookup"><span data-stu-id="85100-111">Get an instance of <xref:System.Type> that represents the generic type.</span></span> <span data-ttu-id="85100-112">Nel codice seguente il tipo viene ottenuto usando l'operatore `typeof` C# (`GetType` in Visual Basic, `typeid` in Visual C++).</span><span class="sxs-lookup"><span data-stu-id="85100-112">In the following code, the type is obtained using the C# `typeof` operator (`GetType` in Visual Basic, `typeid` in Visual C++).</span></span> <span data-ttu-id="85100-113">Per informazioni su come ottenere un oggetto <xref:System.Type>, vedere l'argomento relativo alla classe <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="85100-113">See the <xref:System.Type> class topic for other ways to get a <xref:System.Type> object.</span></span> <span data-ttu-id="85100-114">Si noti che nella parte restante di questa procedura il tipo è contenuto in un parametro di metodo denominato `t`.</span><span class="sxs-lookup"><span data-stu-id="85100-114">Note that in the rest of this procedure, the type is contained in a method parameter named `t`.</span></span>  
  
     [!code-cpp[HowToGeneric#2](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#2)]
     [!code-csharp[HowToGeneric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#2)]
     [!code-vb[HowToGeneric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#2)]  
  
2. <span data-ttu-id="85100-115">Usare la proprietà <xref:System.Type.IsGenericType%2A> per determinare se il tipo è generico e la proprietà <xref:System.Type.IsGenericTypeDefinition%2A> per determinare se il tipo è una definizione di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="85100-115">Use the <xref:System.Type.IsGenericType%2A> property to determine whether the type is generic, and use the <xref:System.Type.IsGenericTypeDefinition%2A> property to determine whether the type is a generic type definition.</span></span>  
  
     [!code-cpp[HowToGeneric#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#3)]
     [!code-csharp[HowToGeneric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#3)]
     [!code-vb[HowToGeneric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#3)]  
  
3. <span data-ttu-id="85100-116">Ottenere una matrice contenente gli argomenti di tipo generico usando il metodo <xref:System.Type.GetGenericArguments%2A>.</span><span class="sxs-lookup"><span data-stu-id="85100-116">Get an array that contains the generic type arguments, using the <xref:System.Type.GetGenericArguments%2A> method.</span></span>  
  
     [!code-cpp[HowToGeneric#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#4)]
     [!code-csharp[HowToGeneric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#4)]
     [!code-vb[HowToGeneric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#4)]  
  
4. <span data-ttu-id="85100-117">Per ogni argomento di tipo, determinare se è un parametro di tipo, ad esempio in una definizione di tipo generico, oppure un tipo specificato per un parametro di tipo, ad esempio in un tipo costruito, usando la proprietà <xref:System.Type.IsGenericParameter%2A>.</span><span class="sxs-lookup"><span data-stu-id="85100-117">For each type argument, determine whether it is a type parameter (for example, in a generic type definition) or a type that has been specified for a type parameter (for example, in a constructed type), using the <xref:System.Type.IsGenericParameter%2A> property.</span></span>  
  
     [!code-cpp[HowToGeneric#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#5)]
     [!code-csharp[HowToGeneric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#5)]
     [!code-vb[HowToGeneric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#5)]  
  
5. <span data-ttu-id="85100-118">Nell'ambito del sistema di tipi un parametro di tipo generico è rappresentato da un'istanza di <xref:System.Type>, esattamente come i tipi ordinari.</span><span class="sxs-lookup"><span data-stu-id="85100-118">In the type system, a generic type parameter is represented by an instance of <xref:System.Type>, just as ordinary types are.</span></span> <span data-ttu-id="85100-119">Il codice seguente visualizza il nome e la posizione del parametro di un oggetto <xref:System.Type> che rappresenta un parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="85100-119">The following code displays the name and parameter position of a <xref:System.Type> object that represents a generic type parameter.</span></span> <span data-ttu-id="85100-120">In questo contesto la posizione del parametro non è un'informazione rilevante, ma rappresenta un dato significativo per l'esame di un parametro di tipo usato come argomento di tipo di un altro tipo generico.</span><span class="sxs-lookup"><span data-stu-id="85100-120">The parameter position is trivial information here; it is of more interest when you are examining a type parameter that has been used as a type argument of another generic type.</span></span>  
  
     [!code-cpp[HowToGeneric#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#6)]
     [!code-csharp[HowToGeneric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#6)]
     [!code-vb[HowToGeneric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#6)]  
  
6. <span data-ttu-id="85100-121">Individuare i vincoli del tipo base e dell'interfaccia di un parametro di tipo generico usando il metodo <xref:System.Type.GetGenericParameterConstraints%2A> per ottenere tutti i vincoli in una singola matrice.</span><span class="sxs-lookup"><span data-stu-id="85100-121">Determine the base type constraint and the interface constraints of a generic type parameter by using the <xref:System.Type.GetGenericParameterConstraints%2A> method to obtain all the constraints in a single array.</span></span> <span data-ttu-id="85100-122">I vincoli non vengono necessariamente restituiti in un ordine specifico.</span><span class="sxs-lookup"><span data-stu-id="85100-122">Constraints are not guaranteed to be in any particular order.</span></span>  
  
     [!code-cpp[HowToGeneric#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#7)]
     [!code-csharp[HowToGeneric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#7)]
     [!code-vb[HowToGeneric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#7)]  
  
7. <span data-ttu-id="85100-123">Usare la proprietà <xref:System.Type.GenericParameterAttributes%2A> per individuare i vincoli speciali applicati a un parametro di tipo, ad esempio quelli necessari perché il parametro sia un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="85100-123">Use the <xref:System.Type.GenericParameterAttributes%2A> property to discover the special constraints on a type parameter, such as requiring that it be a reference type.</span></span> <span data-ttu-id="85100-124">La proprietà include anche valori che rappresentano la varianza, che è possibile nascondere come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="85100-124">The property also includes values that represent variance, which you can mask off as shown in the following code.</span></span>  
  
     [!code-cpp[HowToGeneric#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#8)]
     [!code-csharp[HowToGeneric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#8)]
     [!code-vb[HowToGeneric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#8)]  
  
8. <span data-ttu-id="85100-125">Gli attributi di vincolo speciale sono flag e lo stesso flag (<xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>) non rappresenta né i vincoli speciali né covarianza e controvarianza.</span><span class="sxs-lookup"><span data-stu-id="85100-125">The special constraint attributes are flags, and the same flag (<xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>) that represents no special constraints also represents no covariance or contravariance.</span></span> <span data-ttu-id="85100-126">Per questa ragione, per eseguire il test di queste condizioni, è necessario usare la maschera appropriata.</span><span class="sxs-lookup"><span data-stu-id="85100-126">Thus, to test for either of these conditions you must use the appropriate mask.</span></span> <span data-ttu-id="85100-127">In questo case usare <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> per isolare i flag di vincolo speciale.</span><span class="sxs-lookup"><span data-stu-id="85100-127">In this case, use <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> to isolate the special constraint flags.</span></span>  
  
     [!code-cpp[HowToGeneric#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#9)]
     [!code-csharp[HowToGeneric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#9)]
     [!code-vb[HowToGeneric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#9)]  
  
## <a name="constructing-an-instance-of-a-generic-type"></a><span data-ttu-id="85100-128">Costruzione di un'istanza di un tipo generico</span><span class="sxs-lookup"><span data-stu-id="85100-128">Constructing an Instance of a Generic Type</span></span>  
 <span data-ttu-id="85100-129">Un tipo generico è analogo a un modello.</span><span class="sxs-lookup"><span data-stu-id="85100-129">A generic type is like a template.</span></span> <span data-ttu-id="85100-130">Non è possibile crearne istanze, se non specificando i tipi reali associati ai relativi parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="85100-130">You cannot create instances of it unless you specify real types for its generic type parameters.</span></span> <span data-ttu-id="85100-131">Per eseguire questa operazione in fase di esecuzione usando la reflection, è necessario usare il metodo <xref:System.Type.MakeGenericType%2A>.</span><span class="sxs-lookup"><span data-stu-id="85100-131">To do this at run time, using reflection, requires the <xref:System.Type.MakeGenericType%2A> method.</span></span>  
  
#### <a name="to-construct-an-instance-of-a-generic-type"></a><span data-ttu-id="85100-132">Per costruire un'istanza di un tipo generico</span><span class="sxs-lookup"><span data-stu-id="85100-132">To construct an instance of a generic type</span></span>  
  
1. <span data-ttu-id="85100-133">Ottenere un oggetto <xref:System.Type> che rappresenta il tipo generico.</span><span class="sxs-lookup"><span data-stu-id="85100-133">Get a <xref:System.Type> object that represents the generic type.</span></span> <span data-ttu-id="85100-134">Il codice seguente ottiene il tipo generico <xref:System.Collections.Generic.Dictionary%602> in due modi diversi: usando l'overload del metodo <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType> con una stringa che descrive il tipo e chiamando il metodo <xref:System.Type.GetGenericTypeDefinition%2A> nel tipo costruito `Dictionary\<String, Example>` (`Dictionary(Of String, Example)` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="85100-134">The following code gets the generic type <xref:System.Collections.Generic.Dictionary%602> in two different ways: by using the <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType> method overload with a string describing the type, and by calling the <xref:System.Type.GetGenericTypeDefinition%2A> method on the constructed type `Dictionary\<String, Example>` (`Dictionary(Of String, Example)` in Visual Basic).</span></span> <span data-ttu-id="85100-135">Il metodo <xref:System.Type.MakeGenericType%2A> richiede una definizione di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="85100-135">The <xref:System.Type.MakeGenericType%2A> method requires a generic type definition.</span></span>  
  
     [!code-cpp[HowToGeneric#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#10)]
     [!code-csharp[HowToGeneric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#10)]
     [!code-vb[HowToGeneric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#10)]  
  
2. <span data-ttu-id="85100-136">Costruire una matrice di argomenti di tipo da sostituire ai parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="85100-136">Construct an array of type arguments to substitute for the type parameters.</span></span> <span data-ttu-id="85100-137">La matrice deve contenere il numero corretto di oggetti <xref:System.Type> nello stesso ordine in cui sono visualizzati nell'elenco di parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="85100-137">The array must contain the correct number of <xref:System.Type> objects, in the same order as they appear in the type parameter list.</span></span> <span data-ttu-id="85100-138">In questo caso la chiave (il primo parametro di tipo) è di tipo <xref:System.String> e i valori nel dizionario sono istanze di una classe denominata `Example`.</span><span class="sxs-lookup"><span data-stu-id="85100-138">In this case, the key (first type parameter) is of type <xref:System.String>, and the values in the dictionary are instances of a class named `Example`.</span></span>  
  
     [!code-cpp[HowToGeneric#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#11)]
     [!code-csharp[HowToGeneric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#11)]
     [!code-vb[HowToGeneric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#11)]  
  
3. <span data-ttu-id="85100-139">Chiamare il metodo <xref:System.Type.MakeGenericType%2A> per associare gli argomenti di tipo ai parametri di tipo e costruire il tipo.</span><span class="sxs-lookup"><span data-stu-id="85100-139">Call the <xref:System.Type.MakeGenericType%2A> method to bind the type arguments to the type parameters and construct the type.</span></span>  
  
     [!code-cpp[HowToGeneric#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#12)]
     [!code-csharp[HowToGeneric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#12)]
     [!code-vb[HowToGeneric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#12)]  
  
4. <span data-ttu-id="85100-140">Usare l'overload del metodo <xref:System.Activator.CreateInstance%28System.Type%29> per creare un oggetto del tipo costruito.</span><span class="sxs-lookup"><span data-stu-id="85100-140">Use the <xref:System.Activator.CreateInstance%28System.Type%29> method overload to create an object of the constructed type.</span></span> <span data-ttu-id="85100-141">Il codice seguente archivia due istanze della classe `Example` nell'oggetto `Dictionary<String, Example>` risultante.</span><span class="sxs-lookup"><span data-stu-id="85100-141">The following code stores two instances of the `Example` class in the resulting `Dictionary<String, Example>` object.</span></span>  
  
     [!code-cpp[HowToGeneric#13](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#13)]
     [!code-csharp[HowToGeneric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#13)]
     [!code-vb[HowToGeneric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="85100-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="85100-142">Example</span></span>  
 <span data-ttu-id="85100-143">L'esempio di codice seguente definisce un metodo `DisplayGenericType` che consente di esaminare le definizioni di tipo generico e i tipi costruiti usati nel codice, nonché di visualizzare le relative informazioni.</span><span class="sxs-lookup"><span data-stu-id="85100-143">The following code example defines a `DisplayGenericType` method to examine the generic type definitions and constructed types used in the code and display their information.</span></span> <span data-ttu-id="85100-144">Il metodo `DisplayGenericType` illustra come usare le proprietà <xref:System.Type.IsGenericType%2A>, <xref:System.Type.IsGenericParameter%2A> e <xref:System.Type.GenericParameterPosition%2A> e il metodo <xref:System.Type.GetGenericArguments%2A>.</span><span class="sxs-lookup"><span data-stu-id="85100-144">The `DisplayGenericType` method shows how to use the <xref:System.Type.IsGenericType%2A>, <xref:System.Type.IsGenericParameter%2A>, and <xref:System.Type.GenericParameterPosition%2A> properties and the <xref:System.Type.GetGenericArguments%2A> method.</span></span>  
  
 <span data-ttu-id="85100-145">L'esempio definisce anche un metodo `DisplayGenericParameter` per esaminare un parametro di tipo generico e visualizzarne i vincoli.</span><span class="sxs-lookup"><span data-stu-id="85100-145">The example also defines a `DisplayGenericParameter` method to examine a generic type parameter and display its constraints.</span></span>  
  
 <span data-ttu-id="85100-146">L'esempio di codice definisce un insieme di tipi di test, contenente un tipo generico che indica i vincoli di parametro di tipo e illustra come visualizzare informazioni su questi tipi.</span><span class="sxs-lookup"><span data-stu-id="85100-146">The code example defines a set of test types, including a generic type that illustrates type parameter constraints, and shows how to display information about these types.</span></span>  
  
 <span data-ttu-id="85100-147">L'esempio costruisce un tipo dalla classe <xref:System.Collections.Generic.Dictionary%602> creando una matrice di argomenti di tipo e chiamando il metodo <xref:System.Type.MakeGenericType%2A>.</span><span class="sxs-lookup"><span data-stu-id="85100-147">The example constructs a type from the <xref:System.Collections.Generic.Dictionary%602> class by creating an array of type arguments and calling the <xref:System.Type.MakeGenericType%2A> method.</span></span> <span data-ttu-id="85100-148">Il programma confronta l'oggetto <xref:System.Type> costruito usando <xref:System.Type.MakeGenericType%2A> con un oggetto <xref:System.Type> ottenuto usando `typeof` (`GetType` in Visual Basic), dimostrando che i due oggetti sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="85100-148">The program compares the <xref:System.Type> object constructed using <xref:System.Type.MakeGenericType%2A> with a <xref:System.Type> object obtained using `typeof` (`GetType` in Visual Basic), demonstrating that they are the same.</span></span> <span data-ttu-id="85100-149">Analogamente, il programma usa il metodo <xref:System.Type.GetGenericTypeDefinition%2A> per ottenere la definizione di tipo generico del tipo costruito e la confronta con l'oggetto <xref:System.Type> che rappresenta la classe <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="85100-149">Similarly, the program uses the <xref:System.Type.GetGenericTypeDefinition%2A> method to obtain the generic type definition of the constructed type, and compares it to the <xref:System.Type> object representing the <xref:System.Collections.Generic.Dictionary%602> class.</span></span>  
  
 [!code-cpp[HowToGeneric#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#1)]
 [!code-csharp[HowToGeneric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#1)]
 [!code-vb[HowToGeneric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="85100-150">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="85100-150">See also</span></span>

- <xref:System.Type>
- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="85100-151">Reflection e tipi generici</span><span class="sxs-lookup"><span data-stu-id="85100-151">Reflection and Generic Types</span></span>](reflection-and-generic-types.md)
- [<span data-ttu-id="85100-152">Visualizzazione delle informazioni sul tipo</span><span class="sxs-lookup"><span data-stu-id="85100-152">Viewing Type Information</span></span>](viewing-type-information.md)
- [<span data-ttu-id="85100-153">Generics</span><span class="sxs-lookup"><span data-stu-id="85100-153">Generics</span></span>](../../standard/generics/index.md)
