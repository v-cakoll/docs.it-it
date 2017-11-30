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
ms.openlocfilehash: 7445a2919baaa477b4611c4c5ee5a0031539ca30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="object-and-collection-initializers-c-programming-guide"></a><span data-ttu-id="e56eb-102">Inizializzatori di oggetto e di raccolte (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e56eb-102">Object and Collection Initializers (C# Programming Guide)</span></span>
<span data-ttu-id="e56eb-103">Gli inizializzatori di oggetto consentono di assegnare valori a qualsiasi proprietà o campo accessibile di un oggetto in fase di creazione senza dover richiamare un costruttore seguito da righe di istruzioni di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="e56eb-103">Object initializers let you assign values to any accessible fields or properties of an object at creation time without having to invoke a constructor followed by lines of assignment statements.</span></span> <span data-ttu-id="e56eb-104">La sintassi dell'inizializzatore di oggetto consente di specificare gli argomenti per un costruttore o di omettere gli argomenti (e la sintassi di parentesi).</span><span class="sxs-lookup"><span data-stu-id="e56eb-104">The object initializer syntax enables you to specify arguments for a constructor or omit the arguments (and parentheses syntax).</span></span>  <span data-ttu-id="e56eb-105">Nell'esempio seguente viene illustrato come utilizzare un inizializzatore di oggetto con un tipo denominato, `Cat` e come richiamare il costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="e56eb-105">The following example shows how to use an object initializer with a named type, `Cat` and how to invoke the default constructor.</span></span> <span data-ttu-id="e56eb-106">Si noti l'uso di proprietà implementate automaticamente nella classe `Cat`.</span><span class="sxs-lookup"><span data-stu-id="e56eb-106">Note the use of auto-implemented properties in the `Cat` class.</span></span> <span data-ttu-id="e56eb-107">Per altre informazioni, vedere [Proprietà implementate automaticamente](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e56eb-107">For more information, see [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]  
  
 [!code-csharp[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)] 
 
<span data-ttu-id="e56eb-108">La sintassi di inizializzatori di oggetto consente di creare un'istanza, e dopo che assegna all'oggetto appena creato, con le relative proprietà, assegnata alla variabile nell'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="e56eb-108">The object initializers syntax allows you to create an instance, and after that it assigns the newly created object, with its assigned properties, to the variable in the assignment.</span></span>
  
## <a name="object-initializers-with-anonymous-types"></a><span data-ttu-id="e56eb-109">Inizializzatori di oggetto con tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="e56eb-109">Object Initializers with anonymous types</span></span>  
 <span data-ttu-id="e56eb-110">Anche se gli inizializzatori di oggetto possono essere usati in qualsiasi contesto, sono particolarmente utili nelle espressioni di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e56eb-110">Although object initializers can be used in any context, they are especially useful in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="e56eb-111">Le espressioni di query si avvalgono di frequente di [tipi anonimi](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) che possono essere inizializzati solo con un inizializzatore di oggetto, come illustrato nella dichiarazione seguente.</span><span class="sxs-lookup"><span data-stu-id="e56eb-111">Query expressions make frequent use of [anonymous types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), which can only be initialized by using an object initializer, as shown in the following declaration.</span></span>  
  
```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 <span data-ttu-id="e56eb-112">I tipi anonimi consentono alla clausola `select` in un'espressione di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] di trasformare gli oggetti della sequenza originale in oggetti i cui valori e la cui forma potrebbero essere diversi dall'originale.</span><span class="sxs-lookup"><span data-stu-id="e56eb-112">Anonymous types enable the `select` clause in a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression to transform objects of the original sequence into objects whose value and shape may differ from the original.</span></span> <span data-ttu-id="e56eb-113">Questo è utile se si desidera archiviare solo una parte delle informazioni di ogni oggetto di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="e56eb-113">This is useful if you want to store only a part of the information from each object in a sequence.</span></span> <span data-ttu-id="e56eb-114">Nell'esempio seguente, si supponga che un oggetto prodotto (`p`) contenga diversi campi e metodi e che si sia interessati a creare solo una sequenza di oggetti che contengono il nome e il prezzo unitario del prodotto.</span><span class="sxs-lookup"><span data-stu-id="e56eb-114">In the following example, assume that a product object (`p`) contains many fields and methods, and that you are only interested in creating a sequence of objects that contain the product name and the unit price.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]  
  
 <span data-ttu-id="e56eb-115">Quando questa query verrà eseguita, la variabile `productInfos` conterrà una sequenza di oggetti a cui sarà possibile accedere in un'istruzione `foreach` come illustrato in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="e56eb-115">When this query is executed, the `productInfos` variable will contain a sequence of objects that can be accessed in a `foreach` statement as shown in this example:</span></span>  
  
```csharp
foreach(var p in productInfos){...}  
```  
  
 <span data-ttu-id="e56eb-116">Ogni oggetto nel nuovo tipo anonimo dispone di due proprietà pubbliche che ricevono gli stessi nomi delle proprietà o dei campi nell'oggetto originale.</span><span class="sxs-lookup"><span data-stu-id="e56eb-116">Each object in the new anonymous type has two public properties which receive the same names as the properties or fields in the original object.</span></span> <span data-ttu-id="e56eb-117">È inoltre possibile rinominare un campo mentre si crea un tipo anonimo. Nell'esempio seguente il campo `UnitPrice` viene rinominato in `Price`.</span><span class="sxs-lookup"><span data-stu-id="e56eb-117">You can also rename a field when you are creating an anonymous type; the following example renames the `UnitPrice` field to `Price`.</span></span>  
  
```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```  
  
## <a name="object-initializers-with-nullable-types"></a><span data-ttu-id="e56eb-118">Inizializzatori di oggetto con tipi nullable</span><span class="sxs-lookup"><span data-stu-id="e56eb-118">Object initializers with nullable types</span></span>  
 <span data-ttu-id="e56eb-119">L'uso di un inizializzatore di oggetto con struct nullable genera un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e56eb-119">It is a compile-time error to use an object initializer with a nullable struct.</span></span>  
  
## <a name="collection-initializers"></a><span data-ttu-id="e56eb-120">Inizializzatori di raccolta</span><span class="sxs-lookup"><span data-stu-id="e56eb-120">Collection initializers</span></span>  
 <span data-ttu-id="e56eb-121">Gli inizializzatori di raccolta consentono di specificare uno o più inizializzatori di elemento quando si inizializza un tipo di raccolta che implementa <xref:System.Collections.IEnumerable> e ha un metodo `Add` con una firma appropriata come metodo di istanza o metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="e56eb-121">Collection initializers let you specify one or more element initializers when you initialize a collection type that implements <xref:System.Collections.IEnumerable> and has `Add` with the appropriate signature as an instance method or an extension method.</span></span> <span data-ttu-id="e56eb-122">Gli inizializzatori di elemento possono essere un semplice valore, un'espressione o un inizializzatore di oggetto.</span><span class="sxs-lookup"><span data-stu-id="e56eb-122">The element initializers can be a simple value, an expression or an object initializer.</span></span> <span data-ttu-id="e56eb-123">Se si utilizza un inizializzatore di raccolta, non è necessario specificare più chiamate al metodo `Add` della classe nel codice sorgente, in quanto le chiamate vengono aggiunte dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="e56eb-123">By using a collection initializer you do not have to specify multiple calls to the `Add` method of the class in your source code; the compiler adds the calls.</span></span>  
  
 <span data-ttu-id="e56eb-124">Negli esempi seguenti vengono illustrati due semplici inizializzatori di raccolta:</span><span class="sxs-lookup"><span data-stu-id="e56eb-124">The following examples shows two simple collection initializers:</span></span>  
  
```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```  
  
 <span data-ttu-id="e56eb-125">Nell'inizializzatore di raccolta riportato di seguito vengono utilizzati inizializzatori di oggetto per inizializzare oggetti della classe `Cat` definiti in un esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="e56eb-125">The following collection initializer uses object initializers to initialize objects of the `Cat` class defined in a previous example.</span></span> <span data-ttu-id="e56eb-126">Si noti che i singoli inizializzatori di oggetto sono racchiusi tra parentesi e separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="e56eb-126">Note that the individual object initializers are enclosed in braces and separated by commas.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]  
  
 <span data-ttu-id="e56eb-127">È possibile specificare [null](../../../csharp/language-reference/keywords/null.md) come elemento in un inizializzatore di insieme se il metodo `Add` della raccolta lo consente.</span><span class="sxs-lookup"><span data-stu-id="e56eb-127">You can specify [null](../../../csharp/language-reference/keywords/null.md) as an element in a collection initializer if the collection's `Add` method allows it.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]  
  
 <span data-ttu-id="e56eb-128">È possibile specificare elementi indicizzati se la raccolta supporta l'indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="e56eb-128">You can specify indexed elements if the collection supports indexing.</span></span>  
  
```csharp
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
```  
  
## <a name="example"></a><span data-ttu-id="e56eb-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="e56eb-129">Example</span></span>  
 [!code-csharp[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e56eb-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e56eb-130">See Also</span></span>  
 [<span data-ttu-id="e56eb-131">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e56eb-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e56eb-132">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="e56eb-132">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="e56eb-133">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="e56eb-133">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
