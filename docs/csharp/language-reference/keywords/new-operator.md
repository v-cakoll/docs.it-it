---
title: Operatore new (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3c2b484b9872a54ce42520de77a723b9edb441a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="7c549-102">Operatore new (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7c549-102">new Operator (C# Reference)</span></span>
<span data-ttu-id="7c549-103">Usato per creare oggetti e richiamare costruttori.</span><span class="sxs-lookup"><span data-stu-id="7c549-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="7c549-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7c549-104">For example:</span></span>  
  
```  
Class1 obj  = new Class1();  
```  
  
 <span data-ttu-id="7c549-105">Viene usato anche per creare istanze di tipi anonimi:</span><span class="sxs-lookup"><span data-stu-id="7c549-105">It is also used to create instances of anonymous types:</span></span>  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 <span data-ttu-id="7c549-106">L'operatore `new` viene usato anche per richiamare il costruttore predefinito per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="7c549-106">The `new` operator is also used to invoke the default constructor for value types.</span></span> <span data-ttu-id="7c549-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7c549-107">For example:</span></span>  
  
```  
int i = new int();  
```  
  
 <span data-ttu-id="7c549-108">Nell'istruzione precedente `i` viene inizializzato in `0`, ovvero il valore predefinito per il tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="7c549-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="7c549-109">L'istruzione ha lo stesso effetto dell'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="7c549-109">The statement has the same effect as the following:</span></span>  
  
```  
int i = 0;  
```  
  
 <span data-ttu-id="7c549-110">Per un elenco completo dei valori predefiniti, vedere [Tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="7c549-110">For a complete list of default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="7c549-111">È utile ricordare che è errato dichiarare un costruttore predefinito per uno [struct](../../../csharp/language-reference/keywords/struct.md) poiché ogni tipo di valore ha implicitamente un costruttore predefinito pubblico.</span><span class="sxs-lookup"><span data-stu-id="7c549-111">Remember that it is an error to declare a default constructor for a [struct](../../../csharp/language-reference/keywords/struct.md) because every value type implicitly has a public default constructor.</span></span> <span data-ttu-id="7c549-112">È possibile dichiarare costruttori con parametri su un tipo struct per impostarne i valori iniziali, ma questa operazione è necessaria solo se sono richiesti valori diversi da quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="7c549-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>  
  
 <span data-ttu-id="7c549-113">Gli oggetti di tipo valore, ad esempio gli struct, vengono creati nello stack, mentre gli oggetti di tipo riferimento, ad esempio le classi, vengono creati nell'heap.</span><span class="sxs-lookup"><span data-stu-id="7c549-113">Value-type objects such as structs are created on the stack, while reference-type objects such as classes are created on the heap.</span></span> <span data-ttu-id="7c549-114">Entrambi i tipi di oggetti vengono eliminati automaticamente in modo definitivo, mentre gli oggetti basati su tipi di valori vengono eliminati definitivamente quando escono dall'ambito di validità e quelli basati su tipi di riferimento vengono eliminati definitivamente in un momento non specificato dopo che è stato rimosso l'ultimo riferimento ad essi.</span><span class="sxs-lookup"><span data-stu-id="7c549-114">Both types of objects are destroyed automatically, but objects based on value types are destroyed when they go out of scope, whereas objects based on reference types are destroyed at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="7c549-115">Per i tipi di riferimento che usano risorse fisse, ad esempio grandi quantità di memoria, handle di file o connessioni di rete, può risultare preferibile adottare la finalizzazione deterministica per assicurarsi che l'oggetto venga eliminato definitivamente prima possibile.</span><span class="sxs-lookup"><span data-stu-id="7c549-115">For reference types that consume fixed resources such as large amounts of memory, file handles, or network connections, it is sometimes desirable to employ deterministic finalization to ensure that the object is destroyed as soon as possible.</span></span> <span data-ttu-id="7c549-116">Per altre informazioni, vedere [Istruzione using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7c549-116">For more information, see [using Statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span>  
  
 <span data-ttu-id="7c549-117">Non è possibile sottoporre l'operatore `new` a overload.</span><span class="sxs-lookup"><span data-stu-id="7c549-117">The `new` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="7c549-118">Se l'operatore `new` non riesce ad allocare memoria, genererà l'eccezione <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="7c549-118">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c549-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="7c549-119">Example</span></span>  
 <span data-ttu-id="7c549-120">Nell'esempio seguente vengono creati e inizializzati un oggetto `struct` e un oggetto classe usando l'operatore `new` e vengono quindi assegnati i valori.</span><span class="sxs-lookup"><span data-stu-id="7c549-120">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="7c549-121">I valori predefiniti e assegnati sono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="7c549-121">The default and the assigned values are displayed.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]  
  
 <span data-ttu-id="7c549-122">Si noti che nell'esempio il valore predefinito di una stringa è `null`</span><span class="sxs-lookup"><span data-stu-id="7c549-122">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="7c549-123">e, pertanto, non viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="7c549-123">Therefore, it is not displayed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7c549-124">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7c549-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7c549-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c549-125">See Also</span></span>  
 [<span data-ttu-id="7c549-126">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="7c549-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7c549-127">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7c549-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7c549-128">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="7c549-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="7c549-129">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="7c549-129">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="7c549-130">new</span><span class="sxs-lookup"><span data-stu-id="7c549-130">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
 [<span data-ttu-id="7c549-131">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="7c549-131">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
