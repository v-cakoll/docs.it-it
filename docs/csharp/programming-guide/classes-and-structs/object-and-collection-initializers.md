---
title: Inizializzatori di oggetto e di raccolte (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
caps.latest.revision: "27"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 628f08aaebfa209fc9cb7cfb2b506fc67d5424f9
ms.sourcegitcommit: 6a9030eb5bd0f00e1d144f81958adb195cfb1f6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/10/2018
---
# <a name="object-and-collection-initializers-c-programming-guide"></a><span data-ttu-id="8ca38-102">Inizializzatori di oggetto e di raccolte (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="8ca38-102">Object and Collection Initializers (C# Programming Guide)</span></span>
<span data-ttu-id="8ca38-103">Gli inizializzatori di oggetto consentono di assegnare valori a qualsiasi proprietà o campo accessibile di un oggetto in fase di creazione senza dover richiamare un costruttore seguito da righe di istruzioni di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="8ca38-103">Object initializers let you assign values to any accessible fields or properties of an object at creation time without having to invoke a constructor followed by lines of assignment statements.</span></span> <span data-ttu-id="8ca38-104">La sintassi dell'inizializzatore di oggetto consente di specificare gli argomenti per un costruttore o di omettere gli argomenti (e la sintassi di parentesi).</span><span class="sxs-lookup"><span data-stu-id="8ca38-104">The object initializer syntax enables you to specify arguments for a constructor or omit the arguments (and parentheses syntax).</span></span>  <span data-ttu-id="8ca38-105">Nell'esempio seguente viene illustrato come utilizzare un inizializzatore di oggetto con un tipo denominato, `Cat` e come richiamare il costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="8ca38-105">The following example shows how to use an object initializer with a named type, `Cat` and how to invoke the default constructor.</span></span> <span data-ttu-id="8ca38-106">Si noti l'uso di proprietà implementate automaticamente nella classe `Cat`.</span><span class="sxs-lookup"><span data-stu-id="8ca38-106">Note the use of auto-implemented properties in the `Cat` class.</span></span> <span data-ttu-id="8ca38-107">Per altre informazioni, vedere [Proprietà implementate automaticamente](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="8ca38-107">For more information, see [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]  
  
 [!code-csharp[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)] 
 
<span data-ttu-id="8ca38-108">La sintassi degli inizializzatori di oggetto consente di creare un'istanza e dopo assegna l'oggetto appena creato, con le relative proprietà assegnate, alla variabile nell'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="8ca38-108">The object initializers syntax allows you to create an instance, and after that it assigns the newly created object, with its assigned properties, to the variable in the assignment.</span></span>
  
## <a name="object-initializers-with-anonymous-types"></a><span data-ttu-id="8ca38-109">Inizializzatori di oggetto con tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="8ca38-109">Object Initializers with anonymous types</span></span>  
 <span data-ttu-id="8ca38-110">Anche se gli inizializzatori di oggetto possono essere usati in qualsiasi contesto, sono particolarmente utili nelle espressioni di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ca38-110">Although object initializers can be used in any context, they are especially useful in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="8ca38-111">Le espressioni di query si avvalgono di frequente di [tipi anonimi](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) che possono essere inizializzati solo con un inizializzatore di oggetto, come illustrato nella dichiarazione seguente.</span><span class="sxs-lookup"><span data-stu-id="8ca38-111">Query expressions make frequent use of [anonymous types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), which can only be initialized by using an object initializer, as shown in the following declaration.</span></span>  
  
```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 <span data-ttu-id="8ca38-112">I tipi anonimi consentono alla clausola `select` in un'espressione di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] di trasformare gli oggetti della sequenza originale in oggetti i cui valori e la cui forma potrebbero essere diversi dall'originale.</span><span class="sxs-lookup"><span data-stu-id="8ca38-112">Anonymous types enable the `select` clause in a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression to transform objects of the original sequence into objects whose value and shape may differ from the original.</span></span> <span data-ttu-id="8ca38-113">Questo è utile se si desidera archiviare solo una parte delle informazioni di ogni oggetto di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="8ca38-113">This is useful if you want to store only a part of the information from each object in a sequence.</span></span> <span data-ttu-id="8ca38-114">Nell'esempio seguente, si supponga che un oggetto prodotto (`p`) contenga diversi campi e metodi e che si sia interessati a creare solo una sequenza di oggetti che contengono il nome e il prezzo unitario del prodotto.</span><span class="sxs-lookup"><span data-stu-id="8ca38-114">In the following example, assume that a product object (`p`) contains many fields and methods, and that you are only interested in creating a sequence of objects that contain the product name and the unit price.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]  
  
 <span data-ttu-id="8ca38-115">Quando questa query verrà eseguita, la variabile `productInfos` conterrà una sequenza di oggetti a cui sarà possibile accedere in un'istruzione `foreach` come illustrato in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="8ca38-115">When this query is executed, the `productInfos` variable will contain a sequence of objects that can be accessed in a `foreach` statement as shown in this example:</span></span>  
  
```csharp
foreach(var p in productInfos){...}  
```  
  
 <span data-ttu-id="8ca38-116">Ogni oggetto nel nuovo tipo anonimo dispone di due proprietà pubbliche che ricevono gli stessi nomi delle proprietà o dei campi nell'oggetto originale.</span><span class="sxs-lookup"><span data-stu-id="8ca38-116">Each object in the new anonymous type has two public properties which receive the same names as the properties or fields in the original object.</span></span> <span data-ttu-id="8ca38-117">È inoltre possibile rinominare un campo mentre si crea un tipo anonimo. Nell'esempio seguente il campo `UnitPrice` viene rinominato in `Price`.</span><span class="sxs-lookup"><span data-stu-id="8ca38-117">You can also rename a field when you are creating an anonymous type; the following example renames the `UnitPrice` field to `Price`.</span></span>  
  
```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```  
  
## <a name="object-initializers-with-nullable-types"></a><span data-ttu-id="8ca38-118">Inizializzatori di oggetto con tipi nullable</span><span class="sxs-lookup"><span data-stu-id="8ca38-118">Object initializers with nullable types</span></span>  
 <span data-ttu-id="8ca38-119">L'uso di un inizializzatore di oggetto con struct nullable genera un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="8ca38-119">It is a compile-time error to use an object initializer with a nullable struct.</span></span>  
  
## <a name="collection-initializers"></a><span data-ttu-id="8ca38-120">Inizializzatori di raccolta</span><span class="sxs-lookup"><span data-stu-id="8ca38-120">Collection initializers</span></span>  
 <span data-ttu-id="8ca38-121">Gli inizializzatori di raccolta consentono di specificare uno o più inizializzatori di elemento quando si inizializza un tipo di raccolta che implementa <xref:System.Collections.IEnumerable> e ha un metodo `Add` con una firma appropriata come metodo di istanza o metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="8ca38-121">Collection initializers let you specify one or more element initializers when you initialize a collection type that implements <xref:System.Collections.IEnumerable> and has `Add` with the appropriate signature as an instance method or an extension method.</span></span> <span data-ttu-id="8ca38-122">Gli inizializzatori di elemento possono essere un semplice valore, un'espressione o un inizializzatore di oggetto.</span><span class="sxs-lookup"><span data-stu-id="8ca38-122">The element initializers can be a simple value, an expression or an object initializer.</span></span> <span data-ttu-id="8ca38-123">Se si utilizza un inizializzatore di raccolta, non è necessario specificare più chiamate al metodo `Add` della classe nel codice sorgente, in quanto le chiamate vengono aggiunte dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="8ca38-123">By using a collection initializer you do not have to specify multiple calls to the `Add` method of the class in your source code; the compiler adds the calls.</span></span>  
  
 <span data-ttu-id="8ca38-124">Negli esempi seguenti vengono illustrati due semplici inizializzatori di raccolta:</span><span class="sxs-lookup"><span data-stu-id="8ca38-124">The following examples shows two simple collection initializers:</span></span>  
  
```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```  
  
 <span data-ttu-id="8ca38-125">Nell'inizializzatore di raccolta riportato di seguito vengono utilizzati inizializzatori di oggetto per inizializzare oggetti della classe `Cat` definiti in un esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="8ca38-125">The following collection initializer uses object initializers to initialize objects of the `Cat` class defined in a previous example.</span></span> <span data-ttu-id="8ca38-126">Si noti che i singoli inizializzatori di oggetto sono racchiusi tra parentesi e separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="8ca38-126">Note that the individual object initializers are enclosed in braces and separated by commas.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]  
  
 <span data-ttu-id="8ca38-127">È possibile specificare [null](../../../csharp/language-reference/keywords/null.md) come elemento in un inizializzatore di insieme se il metodo `Add` della raccolta lo consente.</span><span class="sxs-lookup"><span data-stu-id="8ca38-127">You can specify [null](../../../csharp/language-reference/keywords/null.md) as an element in a collection initializer if the collection's `Add` method allows it.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]  
  
 <span data-ttu-id="8ca38-128">È possibile specificare elementi indicizzati se la raccolta supporta l'indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="8ca38-128">You can specify indexed elements if the collection supports indexing.</span></span>  
  
```csharp
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
```  
  
## <a name="examples"></a><span data-ttu-id="8ca38-129">Esempi</span><span class="sxs-lookup"><span data-stu-id="8ca38-129">Examples</span></span>

 <span data-ttu-id="8ca38-130">L'esempio seguente unisce i concetti di inizializzatori di oggetto e di insieme.</span><span class="sxs-lookup"><span data-stu-id="8ca38-130">The following example combines the concepts of object and collection initializers.</span></span>

 [!code-csharp[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]  
 
 <span data-ttu-id="8ca38-131">Come mostrato nell'esempio seguente, un oggetto che implementa <xref:System.Collections.IEnumerable> contenente un metodo `Add` con più parametri consente inizializzatori di insieme con più elementi per ogni elemento nell'elenco corrispondente alla firma del metodo `Add`.</span><span class="sxs-lookup"><span data-stu-id="8ca38-131">Shown in the following example, an object which implements <xref:System.Collections.IEnumerable> containing an `Add` method with multiple parameters allows for collection initializers with multiple elements per item in the list corresponding to the signature of the `Add` method.</span></span> 
 
 [!code-csharp[csProgGuideLINQ#84](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_7.cs)]
 
 <span data-ttu-id="8ca38-132">I metodi `Add` possono usare la parola chiave `params` per accettare un numero variabile di argomenti, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8ca38-132">`Add` methods can use the `params` keyword to take a variable number of arguments as shown in the following example.</span></span> <span data-ttu-id="8ca38-133">Questo esempio illustra l'implementazione personalizzata di un indicizzatore nonché l'inizializzazione di un insieme tramite indici.</span><span class="sxs-lookup"><span data-stu-id="8ca38-133">This example demonstrates the custom implementation of an indexer as well to initialize a collection using indexes.</span></span>
 
 [!code-csharp[csProgGuideLINQ#85](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_8.cs)]
 
## <a name="see-also"></a><span data-ttu-id="8ca38-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ca38-134">See Also</span></span>  
 [<span data-ttu-id="8ca38-135">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="8ca38-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8ca38-136">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="8ca38-136">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="8ca38-137">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="8ca38-137">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
