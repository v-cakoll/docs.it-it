---
title: Inizializzatori di oggetto e di raccolte - Guida per programmatori C#
description: Gli inizializzatori di oggetto in C# assegnano valori a campi accessibili o proprietà di un oggetto in fase di creazione dopo la chiamata di un costruttore.
ms.date: 12/19/2018
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
ms.openlocfilehash: 81deed8a21bff10364524c3e0784c562d4e727e6
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864774"
---
# <a name="object-and-collection-initializers-c-programming-guide"></a><span data-ttu-id="4ab2f-103">Inizializzatori di oggetto e di raccolte (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="4ab2f-103">Object and Collection Initializers (C# Programming Guide)</span></span>

<span data-ttu-id="4ab2f-104">C# consente di creare un'istanza di un oggetto o di una raccolta e di eseguire le assegnazioni di membri in un'unica istruzione.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-104">C# lets you instantiate an object or collection and perform member assignments in a single statement.</span></span>

## <a name="object-initializers"></a><span data-ttu-id="4ab2f-105">Inizializzatori di oggetto</span><span class="sxs-lookup"><span data-stu-id="4ab2f-105">Object initializers</span></span>

<span data-ttu-id="4ab2f-106">Gli inizializzatori di oggetto consentono di assegnare valori a qualsiasi proprietà o campo accessibile di un oggetto in fase di creazione senza dover richiamare un costruttore seguito da righe di istruzioni di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-106">Object initializers let you assign values to any accessible fields or properties of an object at creation time without having to invoke a constructor followed by lines of assignment statements.</span></span> <span data-ttu-id="4ab2f-107">La sintassi dell'inizializzatore di oggetto consente di specificare gli argomenti per un costruttore o di omettere gli argomenti (e la sintassi di parentesi).</span><span class="sxs-lookup"><span data-stu-id="4ab2f-107">The object initializer syntax enables you to specify arguments for a constructor or omit the arguments (and parentheses syntax).</span></span>  <span data-ttu-id="4ab2f-108">Nell'esempio seguente viene illustrato come usare un inizializzatore di oggetto con un tipo denominato, `Cat` e come richiamare il costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-108">The following example shows how to use an object initializer with a named type, `Cat` and how to invoke the parameterless constructor.</span></span> <span data-ttu-id="4ab2f-109">Si noti l'uso di proprietà implementate automaticamente nella classe `Cat`.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-109">Note the use of auto-implemented properties in the `Cat` class.</span></span> <span data-ttu-id="4ab2f-110">Per altre informazioni, vedere [Proprietà implementate automaticamente](auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4ab2f-110">For more information, see [Auto-Implemented Properties](auto-implemented-properties.md).</span></span>  
  
[!code-csharp[ObjectInitializer1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#CatDeclaration)]  
[!code-csharp[ObjectInitializer1a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ObjectPropertyInitialization)]  

<span data-ttu-id="4ab2f-111">La sintassi degli inizializzatori di oggetto consente di creare un'istanza e dopo assegna l'oggetto appena creato, con le relative proprietà assegnate, alla variabile nell'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-111">The object initializers syntax allows you to create an instance, and after that it assigns the newly created object, with its assigned properties, to the variable in the assignment.</span></span>

<span data-ttu-id="4ab2f-112">A partire da C# 6, gli inizializzatori di oggetto possono impostare gli indicizzatori, oltre ad assegnare campi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-112">Starting with C# 6, object initializers can set indexers, in addition to assigning fields and properties.</span></span> <span data-ttu-id="4ab2f-113">Si consideri questa classe `Matrix` di base:</span><span class="sxs-lookup"><span data-stu-id="4ab2f-113">Consider this basic `Matrix` class:</span></span>

[!code-csharp[ObjectInitializer2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixDeclaration)]  

<span data-ttu-id="4ab2f-114">È possibile inizializzare la matrice di identità con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4ab2f-114">You could initialize the identity matrix with the following code:</span></span>

[!code-csharp[ObjectInitializer2a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixInitialization)]  

<span data-ttu-id="4ab2f-115">Qualsiasi indicizzatore accessibile che contiene un setter accessibile è utilizzabile come espressione in un inizializzatore di oggetto, indipendentemente dal numero o dai tipi degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-115">Any accessible indexer that contains an accessible setter can be used as one of the expressions in an object initializer, regardless of the number or types of arguments.</span></span> <span data-ttu-id="4ab2f-116">Gli argomenti di indice formano il lato sinistro dell'assegnazione e il valore corrisponde al lato destro dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-116">The index arguments form the left side of the assignment, and the value is the right side of the expression.</span></span>  <span data-ttu-id="4ab2f-117">Questi, ad esempio sono tutti validi se `IndexersExample` ha gli indicizzatori appropriati:</span><span class="sxs-lookup"><span data-stu-id="4ab2f-117">For example, these are all valid if `IndexersExample` has the appropriate indexers:</span></span>

```csharp
var thing = new IndexersExample {
    name = "object one",
    [1] = '1',
    [2] = '4',
    [3] = '9',
    Size = Math.PI,
    ['C',4] = "Middle C"
}
```

<span data-ttu-id="4ab2f-118">Perché la compilazione del codice precedente riesca, il tipo `IndexersExample` deve avere i membri seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ab2f-118">For the preceding code to compile, the `IndexersExample` type must have the following members:</span></span>

```csharp
public string name;
public double Size { set { ... }; }
public char this[int i] { set { ... }; }
public string this[char c, int i] {  set { ... }; }
```

## <a name="object-initializers-with-anonymous-types"></a><span data-ttu-id="4ab2f-119">Inizializzatori di oggetto con tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="4ab2f-119">Object Initializers with anonymous types</span></span>

<span data-ttu-id="4ab2f-120">Anche se gli inizializzatori di oggetto possono essere usati in qualsiasi contesto, sono particolarmente utili nelle espressioni di query LINQ.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-120">Although object initializers can be used in any context, they are especially useful in LINQ query expressions.</span></span> <span data-ttu-id="4ab2f-121">Le espressioni di query si avvalgono di frequente di [tipi anonimi](./anonymous-types.md) che possono essere inizializzati solo con un inizializzatore di oggetto, come illustrato nella dichiarazione seguente.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-121">Query expressions make frequent use of [anonymous types](./anonymous-types.md), which can only be initialized by using an object initializer, as shown in the following declaration.</span></span>  

```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```

<span data-ttu-id="4ab2f-122">I tipi anonimi consentono alla `select` clausola in un'espressione di query LINQ di trasformare gli oggetti della sequenza originale in oggetti i cui valori e la cui forma potrebbero essere diversi dall'originale.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-122">Anonymous types enable the `select` clause in a LINQ query expression to transform objects of the original sequence into objects whose value and shape may differ from the original.</span></span> <span data-ttu-id="4ab2f-123">Questo è utile se si desidera archiviare solo una parte delle informazioni di ogni oggetto di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-123">This is useful if you want to store only a part of the information from each object in a sequence.</span></span> <span data-ttu-id="4ab2f-124">Nell'esempio seguente, si supponga che un oggetto prodotto (`p`) contenga diversi campi e metodi e che si sia interessati a creare solo una sequenza di oggetti che contengono il nome e il prezzo unitario del prodotto.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-124">In the following example, assume that a product object (`p`) contains many fields and methods, and that you are only interested in creating a sequence of objects that contain the product name and the unit price.</span></span>  
  
[!code-csharp[ObjectInitializer3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#AnonymousUse)]  

<span data-ttu-id="4ab2f-125">Quando questa query verrà eseguita, la variabile `productInfos` conterrà una sequenza di oggetti a cui sarà possibile accedere in un'istruzione `foreach` come illustrato in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="4ab2f-125">When this query is executed, the `productInfos` variable will contain a sequence of objects that can be accessed in a `foreach` statement as shown in this example:</span></span>  

```csharp
foreach(var p in productInfos){...}  
```

<span data-ttu-id="4ab2f-126">Ogni oggetto nel nuovo tipo anonimo dispone di due proprietà pubbliche che ricevono gli stessi nomi delle proprietà o dei campi nell'oggetto originale.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-126">Each object in the new anonymous type has two public properties that receive the same names as the properties or fields in the original object.</span></span> <span data-ttu-id="4ab2f-127">È inoltre possibile rinominare un campo mentre si crea un tipo anonimo. Nell'esempio seguente il campo `UnitPrice` viene rinominato in `Price`.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-127">You can also rename a field when you are creating an anonymous type; the following example renames the `UnitPrice` field to `Price`.</span></span>  

```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```

## <a name="collection-initializers"></a><span data-ttu-id="4ab2f-128">Inizializzatori di raccolta</span><span class="sxs-lookup"><span data-stu-id="4ab2f-128">Collection initializers</span></span>

<span data-ttu-id="4ab2f-129">Gli inizializzatori di raccolta consentono di specificare uno o più inizializzatori di elemento quando si inizializza un tipo di raccolta che implementa <xref:System.Collections.IEnumerable> e ha un metodo `Add` con una firma appropriata come metodo di istanza o metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-129">Collection initializers let you specify one or more element initializers when you initialize a collection type that implements <xref:System.Collections.IEnumerable> and has `Add` with the appropriate signature as an instance method or an extension method.</span></span> <span data-ttu-id="4ab2f-130">Gli inizializzatori di elemento possono essere valori semplici, espressioni o inizializzatori di oggetto.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-130">The element initializers can be a simple value, an expression, or an object initializer.</span></span> <span data-ttu-id="4ab2f-131">Se si usa un inizializzatore di insieme, non è necessario specificare più chiamate, in quanto le chiamate vengono aggiunte dal compilatore automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-131">By using a collection initializer, you do not have to specify multiple calls; the compiler adds the calls automatically.</span></span>  
  
<span data-ttu-id="4ab2f-132">L'esempio seguente illustrati due inizializzatori di insieme semplici:</span><span class="sxs-lookup"><span data-stu-id="4ab2f-132">The following example shows two simple collection initializers:</span></span>  

```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```

<span data-ttu-id="4ab2f-133">Nell'inizializzatore di raccolta riportato di seguito vengono utilizzati inizializzatori di oggetto per inizializzare oggetti della classe `Cat` definiti in un esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-133">The following collection initializer uses object initializers to initialize objects of the `Cat` class defined in a previous example.</span></span> <span data-ttu-id="4ab2f-134">Si noti che i singoli inizializzatori di oggetto sono racchiusi tra parentesi e separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-134">Note that the individual object initializers are enclosed in braces and separated by commas.</span></span>  
  
[!code-csharp[ListInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitializer)]  
  
<span data-ttu-id="4ab2f-135">È possibile specificare [null](../../language-reference/keywords/null.md) come elemento in un inizializzatore di insieme se il metodo `Add` della raccolta lo consente.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-135">You can specify [null](../../language-reference/keywords/null.md) as an element in a collection initializer if the collection's `Add` method allows it.</span></span>  
  
[!code-csharp[ListInitializerNull](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitialerWithNull)]  
  
 <span data-ttu-id="4ab2f-136">È possibile specificare elementi indicizzati se la raccolta supporta l'indicizzazione in lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-136">You can specify indexed elements if the collection supports read / write indexing.</span></span>
  
[!code-csharp[DictionaryInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryIndexerInitializer)]  

<span data-ttu-id="4ab2f-137">L'esempio precedente genera codice che chiama <xref:System.Collections.Generic.Dictionary%602.Item(%600)> per impostare i valori.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-137">The preceding sample generates code that calls the <xref:System.Collections.Generic.Dictionary%602.Item(%600)> to set the values.</span></span> <span data-ttu-id="4ab2f-138">Prima di C# 6, era possibile inizializzare dizionari e altri contenitori associativi usando la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-138">Before C# 6, you could initialize dictionaries and other associative containers using the following syntax.</span></span> <span data-ttu-id="4ab2f-139">Si noti che anziché la sintassi degli indicizzatori, con le parentesi e un'assegnazione, viene usato un oggetto con più valori:</span><span class="sxs-lookup"><span data-stu-id="4ab2f-139">Notice that instead of indexer syntax, with parentheses and an assignment, it uses an object with multiple values:</span></span>

[!code-csharp[DictionaryAddInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryAddInitializer)]  

<span data-ttu-id="4ab2f-140">Questo esempio di inizializzatore chiama <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)> per aggiungere i tre elementi nel dizionario.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-140">This initializer example calls <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)> to add the three items into the dictionary.</span></span> <span data-ttu-id="4ab2f-141">Questi due modi diversi di inizializzazione delle raccolte associative hanno un comportamento leggermente diverso a causa delle chiamate di metodo generate dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-141">These two different ways to initialize associative collections have slightly different behavior because of the method calls the compiler generates.</span></span> <span data-ttu-id="4ab2f-142">Con la classe `Dictionary` funzionano entrambe le varianti.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-142">Both variants work with the `Dictionary` class.</span></span> <span data-ttu-id="4ab2f-143">È possibile che altri tipi supportino l'uno o l'altro in base all'API pubblica usata.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-143">Other types may only support one or the other based on their public API.</span></span>

## <a name="examples"></a><span data-ttu-id="4ab2f-144">Esempi</span><span class="sxs-lookup"><span data-stu-id="4ab2f-144">Examples</span></span>

<span data-ttu-id="4ab2f-145">L'esempio seguente unisce i concetti di inizializzatori di oggetto e di insieme.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-145">The following example combines the concepts of object and collection initializers.</span></span>

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullExample)]  

<span data-ttu-id="4ab2f-146">L'esempio seguente illustra un oggetto che implementa <xref:System.Collections.IEnumerable> e contiene un metodo `Add` con più parametri. Usa un inizializzatore di insieme con più elementi per ogni voce nell'elenco corrispondente alla firma del metodo `Add`.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-146">The following example shows an object that implements <xref:System.Collections.IEnumerable> and contains an `Add` method with multiple parameters, It uses a collection initializer with multiple elements per item in the list that correspond to the signature of the `Add` method.</span></span>

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullListExample)]  

<span data-ttu-id="4ab2f-147">I metodi `Add` possono usare la parola chiave `params` per accettare un numero variabile di argomenti, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-147">`Add` methods can use the `params` keyword to take a variable number of arguments, as shown in the following example.</span></span> <span data-ttu-id="4ab2f-148">Questo esempio illustra anche l'implementazione personalizzata di un indicizzatore per l'inizializzazione di un insieme tramite indici.</span><span class="sxs-lookup"><span data-stu-id="4ab2f-148">This example also demonstrates the custom implementation of an indexer to initialize a collection using indexes.</span></span>

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullDictionaryInitializer)]  

## <a name="see-also"></a><span data-ttu-id="4ab2f-149">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4ab2f-149">See also</span></span>

- [<span data-ttu-id="4ab2f-150">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4ab2f-150">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4ab2f-151">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="4ab2f-151">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="4ab2f-152">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="4ab2f-152">Anonymous Types</span></span>](anonymous-types.md)
