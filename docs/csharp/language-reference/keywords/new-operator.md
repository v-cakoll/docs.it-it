---
title: Operatore new (Riferimenti per C#)
ms.date: 03/15/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: ''
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ab582cd14bc649ca8d1678a583a8f95e78c6bf7e
ms.sourcegitcommit: 32172ca05d5dcce7ef3d327b9c8639c736e0fe2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/20/2018
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="55fe3-102">Operatore new (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="55fe3-102">new Operator (C# Reference)</span></span>
<span data-ttu-id="55fe3-103">Usato per creare oggetti e richiamare costruttori.</span><span class="sxs-lookup"><span data-stu-id="55fe3-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="55fe3-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="55fe3-104">For example:</span></span>  
  
```csharp
Class1 obj  = new Class1();  
```  
  
 <span data-ttu-id="55fe3-105">Viene usato anche per creare istanze di tipi anonimi:</span><span class="sxs-lookup"><span data-stu-id="55fe3-105">It is also used to create instances of anonymous types:</span></span>  
  
```csharp
var query = from cust in customers  
            select new { Name = cust.Name, Address = cust.PrimaryAddress };  
```  
  
 <span data-ttu-id="55fe3-106">L'operatore `new` viene usato anche per richiamare il costruttore predefinito per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="55fe3-106">The `new` operator is also used to invoke the default constructor for value types.</span></span> <span data-ttu-id="55fe3-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="55fe3-107">For example:</span></span>  
  
```csharp
int i = new int();  
```  
  
 <span data-ttu-id="55fe3-108">Nell'istruzione precedente `i` viene inizializzato in `0`, ovvero il valore predefinito per il tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="55fe3-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="55fe3-109">L'istruzione ha lo stesso effetto dell'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="55fe3-109">The statement has the same effect as the following:</span></span>  
  
```csharp
int i = 0;  
```  
  
 <span data-ttu-id="55fe3-110">Per un elenco completo dei valori predefiniti, vedere [Tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="55fe3-110">For a complete list of default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="55fe3-111">È utile ricordare che è errato dichiarare un costruttore predefinito per uno [struct](../../../csharp/language-reference/keywords/struct.md) poiché ogni tipo di valore ha implicitamente un costruttore predefinito pubblico.</span><span class="sxs-lookup"><span data-stu-id="55fe3-111">Remember that it is an error to declare a default constructor for a [struct](../../../csharp/language-reference/keywords/struct.md) because every value type implicitly has a public default constructor.</span></span> <span data-ttu-id="55fe3-112">È possibile dichiarare costruttori con parametri su un tipo struct per impostarne i valori iniziali, ma questa operazione è necessaria solo se sono richiesti valori diversi da quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="55fe3-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>  
  
 <span data-ttu-id="55fe3-113">Sia gli oggetti di tipo valore come gli struct che gli oggetti di tipo riferimento come le classi vengono eliminati automaticamente, ma gli oggetti di tipo valore vengono eliminati quando viene eliminato il loro contesto contenitore, mentre gli oggetti di tipo riferimento vengono eliminati da Garbage Collector in un momento non specificato dopo la rimozione dell'ultimo riferimento a essi relativo.</span><span class="sxs-lookup"><span data-stu-id="55fe3-113">Both value-type objects such as structs and reference-type objects such as classes are destroyed automatically, but value-type objects are destroyed when their containing context is destroyed, whereas reference-type objects are destroyed by the garbage collector at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="55fe3-114">Per i tipi che contengono risorse come ad esempio gli handle di file o le connessioni di rete, è consigliabile adottare la pulitura deterministica per garantire che le risorse contenute vengano rilasciate nel più breve tempo possibile.</span><span class="sxs-lookup"><span data-stu-id="55fe3-114">For types that contain resources such as file handles, or network connections, it is desirable to employ deterministic cleanup to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="55fe3-115">Per altre informazioni, vedere [Istruzione using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="55fe3-115">For more information, see [using Statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span>  
  
 <span data-ttu-id="55fe3-116">Non è possibile sottoporre l'operatore `new` a overload.</span><span class="sxs-lookup"><span data-stu-id="55fe3-116">The `new` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="55fe3-117">Se l'operatore `new` non riesce ad allocare memoria, genererà l'eccezione <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="55fe3-117">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55fe3-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="55fe3-118">Example</span></span>  
 <span data-ttu-id="55fe3-119">Nell'esempio seguente vengono creati e inizializzati un oggetto `struct` e un oggetto classe usando l'operatore `new` e vengono quindi assegnati i valori.</span><span class="sxs-lookup"><span data-stu-id="55fe3-119">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="55fe3-120">I valori predefiniti e assegnati sono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="55fe3-120">The default and the assigned values are displayed.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#7](codesnippet/CSharp/new-operator_1.cs)]  
  
 <span data-ttu-id="55fe3-121">Si noti che nell'esempio il valore predefinito di una stringa è `null`</span><span class="sxs-lookup"><span data-stu-id="55fe3-121">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="55fe3-122">e, pertanto, non viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="55fe3-122">Therefore, it is not displayed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="55fe3-123">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="55fe3-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="55fe3-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55fe3-124">See Also</span></span>  
 [<span data-ttu-id="55fe3-125">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="55fe3-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="55fe3-126">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="55fe3-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="55fe3-127">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="55fe3-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="55fe3-128">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="55fe3-128">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="55fe3-129">new</span><span class="sxs-lookup"><span data-stu-id="55fe3-129">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
 [<span data-ttu-id="55fe3-130">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="55fe3-130">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
