---
title: 'Procedura: Definire una classe che può fornire funzionalità identiche con tipi di dati diversi (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- data type arguments [Visual Basic], using
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- data type parameters [Visual Basic], using
- generics [Visual Basic], defining classes with type parameters
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- type arguments
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
- parameters [Visual Basic], data type
- generics [Visual Basic], defining generic types
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: a914adf8-e68f-4819-a6b1-200d1cf1c21c
ms.openlocfilehash: e40890835ddd50d25106e318ee05a874ce355d9b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977799"
---
# <a name="how-to-define-a-class-that-can-provide-identical-functionality-on-different-data-types-visual-basic"></a><span data-ttu-id="0eada-102">Procedura: Definire una classe che può fornire funzionalità identiche con tipi di dati diversi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0eada-102">How to: Define a Class That Can Provide Identical Functionality on Different Data Types (Visual Basic)</span></span>
<span data-ttu-id="0eada-103">È possibile definire una classe dalla quale creare oggetti in grado di fornire funzionalità identiche su tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="0eada-103">You can define a class from which you can create objects that provide identical functionality on different data types.</span></span> <span data-ttu-id="0eada-104">A questo scopo, specificare uno o più *parametri di tipo* nella definizione.</span><span class="sxs-lookup"><span data-stu-id="0eada-104">To do this, you specify one or more *type parameters* in the definition.</span></span> <span data-ttu-id="0eada-105">La classe potrà quindi servire come modello per gli oggetti che usano tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="0eada-105">The class can then serve as a template for objects that use various data types.</span></span> <span data-ttu-id="0eada-106">Una classe definita in questo modo viene denominata *classe generica*.</span><span class="sxs-lookup"><span data-stu-id="0eada-106">A class defined in this way is called a *generic class*.</span></span>  
  
 <span data-ttu-id="0eada-107">Il vantaggio della definizione di una classe generica sta nel fatto che viene definita un'unica volta e che può essere usata dal codice per la creazione di molti oggetti che usano una vasta gamma di tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="0eada-107">The advantage of defining a generic class is that you define it just once, and your code can use it to create many objects that use a wide variety of data types.</span></span> <span data-ttu-id="0eada-108">Questo comporta prestazioni superiori rispetto alla definizione della classe con il tipo `Object` .</span><span class="sxs-lookup"><span data-stu-id="0eada-108">This results in better performance than defining the class with the `Object` type.</span></span>  
  
 <span data-ttu-id="0eada-109">Oltre alle classi, è possibile definire e usare anche strutture, interfacce, routine e delegati generici.</span><span class="sxs-lookup"><span data-stu-id="0eada-109">In addition to classes, you can also define and use generic structures, interfaces, procedures, and delegates.</span></span>  
  
### <a name="to-define-a-class-with-a-type-parameter"></a><span data-ttu-id="0eada-110">Per definire una classe con un parametro di tipo</span><span class="sxs-lookup"><span data-stu-id="0eada-110">To define a class with a type parameter</span></span>  
  
1.  <span data-ttu-id="0eada-111">Definire la classe nel modo normale.</span><span class="sxs-lookup"><span data-stu-id="0eada-111">Define the class in the normal way.</span></span>  
  
2.  <span data-ttu-id="0eada-112">Aggiungere `(Of` *parametrotipo*`)` subito dopo il nome della classe per specificare il parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="0eada-112">Add `(Of` *typeparameter*`)` immediately after the class name to specify a type parameter.</span></span>  
  
3.  <span data-ttu-id="0eada-113">Se esiste più di un parametro di tipo, creare un elenco separato da virgole all'interno delle parentesi.</span><span class="sxs-lookup"><span data-stu-id="0eada-113">If you have more than one type parameter, make a comma-separated list inside the parentheses.</span></span> <span data-ttu-id="0eada-114">Non ripetere la parola chiave `Of` .</span><span class="sxs-lookup"><span data-stu-id="0eada-114">Do not repeat the `Of` keyword.</span></span>  
  
4.  <span data-ttu-id="0eada-115">Se le operazioni eseguite dal codice su un parametro di tipo sono diverse da una semplice assegnazione, far seguire il parametro di tipo da una clausola `As` per l'aggiunta di uno o più *vincoli*.</span><span class="sxs-lookup"><span data-stu-id="0eada-115">If your code performs operations on a type parameter other than simple assignment, follow that type parameter with an `As` clause to add one or more *constraints*.</span></span> <span data-ttu-id="0eada-116">Un vincolo garantisce che il tipo fornito per tale parametro di tipo soddisfi un requisito, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0eada-116">A constraint guarantees that the type supplied for that type parameter satisfies a requirement such as the following:</span></span>  
  
    -   <span data-ttu-id="0eada-117">Supporta un'operazione, quale `>`, eseguita dal codice</span><span class="sxs-lookup"><span data-stu-id="0eada-117">Supports an operation, such as `>`, that your code performs</span></span>  
  
    -   <span data-ttu-id="0eada-118">Supporta un membro, quale un metodo, a cui accede il codice</span><span class="sxs-lookup"><span data-stu-id="0eada-118">Supports a member, such as a method, that your code accesses</span></span>  
  
    -   <span data-ttu-id="0eada-119">Espone un costruttore senza parametri</span><span class="sxs-lookup"><span data-stu-id="0eada-119">Exposes a parameterless constructor</span></span>  
  
     <span data-ttu-id="0eada-120">Se non si specifica alcun vincolo, le uniche operazioni e gli unici membri usati dal codice sono quelli supportati dal [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="0eada-120">If you do not specify any constraints, the only operations and members your code can use are those supported by the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="0eada-121">Per altre informazioni, vedere [Type List](../../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="0eada-121">For more information, see [Type List](../../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
5.  <span data-ttu-id="0eada-122">Identificare ogni membro di classi da dichiarare con un tipo fornito e dichiararlo `As` `typeparameter`.</span><span class="sxs-lookup"><span data-stu-id="0eada-122">Identify every class member that is to be declared with a supplied type, and declare it `As` `typeparameter`.</span></span> <span data-ttu-id="0eada-123">Questo vale per l'archiviazione interna, i parametri di routine e i valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="0eada-123">This applies to internal storage, procedure parameters, and return values.</span></span>  
  
6.  <span data-ttu-id="0eada-124">Accertarsi che il codice usi solo operazioni e metodi supportati da qualsiasi tipo di dati che può fornire a `itemType`.</span><span class="sxs-lookup"><span data-stu-id="0eada-124">Be sure your code uses only operations and methods that are supported by any data type it can supply to `itemType`.</span></span>  
  
     <span data-ttu-id="0eada-125">Nell'esempio riportato di seguito viene definita una classe che gestisce un elenco molto semplice.</span><span class="sxs-lookup"><span data-stu-id="0eada-125">The following example defines a class that manages a very simple list.</span></span> <span data-ttu-id="0eada-126">L'elenco è contenuto negli `items`della matrice interna e il tipo di dati degli elementi dell'elenco può essere dichiarato dal codice.</span><span class="sxs-lookup"><span data-stu-id="0eada-126">It holds the list in the internal array `items`, and the using code can declare the data type of the list elements.</span></span> <span data-ttu-id="0eada-127">Un costruttore con parametri consente al codice di impostare il limite superiore di `items`, quindi il costruttore predefinito lo imposta a 9 (per un totale di 10 elementi).</span><span class="sxs-lookup"><span data-stu-id="0eada-127">A parameterized constructor allows the using code to set the upper bound of `items`, and the default constructor sets this to 9 (for a total of 10 items).</span></span>  
  
     [!code-vb[VbVbalrDataTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#7)]  
  
     <span data-ttu-id="0eada-128">È possibile dichiarare una classe da `simpleList` per contenere un elenco di valori `Integer` , un'altra classe per contenere un elenco di valori `String` e un'altra per contenere valori `Date` .</span><span class="sxs-lookup"><span data-stu-id="0eada-128">You can declare a class from `simpleList` to hold a list of `Integer` values, another class to hold a list of `String` values, and another to hold `Date` values.</span></span> <span data-ttu-id="0eada-129">Ad eccezione del tipo di dati dei membri dell'elenco, gli oggetti creati da tutte queste classi si comportano in maniera identica.</span><span class="sxs-lookup"><span data-stu-id="0eada-129">Except for the data type of the list members, objects created from all these classes behave identically.</span></span>  
  
     <span data-ttu-id="0eada-130">L'argomento di tipo fornito dal codice a `itemType` può essere di tipo intrinseco come `Boolean` o `Double`, una struttura, un'enumerazione o qualsiasi tipo di classe, compresa una di quelle definite dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0eada-130">The type argument that the using code supplies to `itemType` can be an intrinsic type such as `Boolean` or `Double`, a structure, an enumeration, or any type of class, including one that your application defines.</span></span>  
  
     <span data-ttu-id="0eada-131">È possibile verificare la classe `simpleList` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="0eada-131">You can test the class `simpleList` with the following code.</span></span>  
  
     [!code-vb[VbVbalrDataTypes#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="0eada-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0eada-132">See also</span></span>
- [<span data-ttu-id="0eada-133">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="0eada-133">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="0eada-134">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0eada-134">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="0eada-135">Indipendenza del linguaggio e componenti indipendenti dal linguaggio</span><span class="sxs-lookup"><span data-stu-id="0eada-135">Language Independence and Language-Independent Components</span></span>](../../../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="0eada-136">Of</span><span class="sxs-lookup"><span data-stu-id="0eada-136">Of</span></span>](../../../../visual-basic/language-reference/statements/of-clause.md)
- [<span data-ttu-id="0eada-137">Elenco dei tipi</span><span class="sxs-lookup"><span data-stu-id="0eada-137">Type List</span></span>](../../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="0eada-138">Procedura: Usare una classe generica</span><span class="sxs-lookup"><span data-stu-id="0eada-138">How to: Use a Generic Class</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="0eada-139">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="0eada-139">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
