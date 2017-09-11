---
title: Operatore new (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 59e1cc2006548df9a7a10283a34044040e5c2fef
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="new-operator-c-reference"></a><span data-ttu-id="18131-102">Operatore new (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="18131-102">new Operator (C# Reference)</span></span>
<span data-ttu-id="18131-103">Usato per creare oggetti e richiamare costruttori.</span><span class="sxs-lookup"><span data-stu-id="18131-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="18131-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="18131-104">For example:</span></span>  
  
```  
Class1 obj  = new Class1();  
```  
  
 <span data-ttu-id="18131-105">Viene usato anche per creare istanze di tipi anonimi:</span><span class="sxs-lookup"><span data-stu-id="18131-105">It is also used to create instances of anonymous types:</span></span>  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 <span data-ttu-id="18131-106">L'operatore `new` viene usato anche per richiamare il costruttore predefinito per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="18131-106">The `new` operator is also used to invoke the default constructor for value types.</span></span> <span data-ttu-id="18131-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="18131-107">For example:</span></span>  
  
```  
int i = new int();  
```  
  
 <span data-ttu-id="18131-108">Nell'istruzione precedente `i` viene inizializzato in `0`, ovvero il valore predefinito per il tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="18131-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="18131-109">L'istruzione ha lo stesso effetto dell'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="18131-109">The statement has the same effect as the following:</span></span>  
  
```  
int i = 0;  
```  
  
 <span data-ttu-id="18131-110">Per un elenco completo dei valori predefiniti, vedere [Tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="18131-110">For a complete list of default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="18131-111">È utile ricordare che è errato dichiarare un costruttore predefinito per uno [struct](../../../csharp/language-reference/keywords/struct.md) poiché ogni tipo di valore ha implicitamente un costruttore predefinito pubblico.</span><span class="sxs-lookup"><span data-stu-id="18131-111">Remember that it is an error to declare a default constructor for a [struct](../../../csharp/language-reference/keywords/struct.md) because every value type implicitly has a public default constructor.</span></span> <span data-ttu-id="18131-112">È possibile dichiarare costruttori con parametri su un tipo struct per impostarne i valori iniziali, ma questa operazione è necessaria solo se sono richiesti valori diversi da quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="18131-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>  
  
 <span data-ttu-id="18131-113">Gli oggetti di tipo valore, ad esempio gli struct, vengono creati nello stack, mentre gli oggetti di tipo riferimento, ad esempio le classi, vengono creati nell'heap.</span><span class="sxs-lookup"><span data-stu-id="18131-113">Value-type objects such as structs are created on the stack, while reference-type objects such as classes are created on the heap.</span></span> <span data-ttu-id="18131-114">Entrambi i tipi di oggetti vengono eliminati automaticamente in modo definitivo, mentre gli oggetti basati su tipi di valori vengono eliminati definitivamente quando escono dall'ambito di validità e quelli basati su tipi di riferimento vengono eliminati definitivamente in un momento non specificato dopo che è stato rimosso l'ultimo riferimento ad essi.</span><span class="sxs-lookup"><span data-stu-id="18131-114">Both types of objects are destroyed automatically, but objects based on value types are destroyed when they go out of scope, whereas objects based on reference types are destroyed at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="18131-115">Per i tipi di riferimento che usano risorse fisse, ad esempio grandi quantità di memoria, handle di file o connessioni di rete, può risultare preferibile adottare la finalizzazione deterministica per assicurarsi che l'oggetto venga eliminato definitivamente prima possibile.</span><span class="sxs-lookup"><span data-stu-id="18131-115">For reference types that consume fixed resources such as large amounts of memory, file handles, or network connections, it is sometimes desirable to employ deterministic finalization to ensure that the object is destroyed as soon as possible.</span></span> <span data-ttu-id="18131-116">Per altre informazioni, vedere [Istruzione using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="18131-116">For more information, see [using Statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span>  
  
 <span data-ttu-id="18131-117">Non è possibile eseguire l'overload dell'operatore `new`.</span><span class="sxs-lookup"><span data-stu-id="18131-117">The `new` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="18131-118">Se l'operatore `new` non riesce ad allocare memoria, genererà l'eccezione <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="18131-118">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18131-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="18131-119">Example</span></span>  
 <span data-ttu-id="18131-120">Nell'esempio seguente vengono creati e inizializzati un oggetto `struct` e un oggetto classe usando l'operatore `new` e vengono quindi assegnati i valori.</span><span class="sxs-lookup"><span data-stu-id="18131-120">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="18131-121">I valori predefiniti e assegnati sono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="18131-121">The default and the assigned values are displayed.</span></span>  
  
 <span data-ttu-id="18131-122">[!code-cs[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="18131-122">[!code-cs[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="18131-123">Si noti che nell'esempio il valore predefinito di una stringa è `null`</span><span class="sxs-lookup"><span data-stu-id="18131-123">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="18131-124">e, pertanto, non viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="18131-124">Therefore, it is not displayed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="18131-125">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="18131-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="18131-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18131-126">See Also</span></span>  
 <span data-ttu-id="18131-127">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="18131-127">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="18131-128">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="18131-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="18131-129">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="18131-129">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="18131-130">[Parole chiave per operatori](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="18131-130">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 <span data-ttu-id="18131-131">[new](../../../csharp/language-reference/keywords/new.md) </span><span class="sxs-lookup"><span data-stu-id="18131-131">[new](../../../csharp/language-reference/keywords/new.md) </span></span>  
 [<span data-ttu-id="18131-132">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="18131-132">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)

