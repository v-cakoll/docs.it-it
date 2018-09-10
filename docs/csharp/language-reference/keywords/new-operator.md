---
title: Operatore new (Riferimenti per C#)
ms.date: 03/15/2018
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 362217b247bd2ab7a2eec2f86cbaaf1a0652a3ad
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44079565"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="1a5e8-102">Operatore new (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1a5e8-102">new operator (C# Reference)</span></span>

<span data-ttu-id="1a5e8-103">Usato per creare oggetti e richiamare costruttori.</span><span class="sxs-lookup"><span data-stu-id="1a5e8-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="1a5e8-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a5e8-104">For example:</span></span>

```csharp
Class1 obj  = new Class1();
```

<span data-ttu-id="1a5e8-105">Viene usato anche per creare istanze di tipi anonimi:</span><span class="sxs-lookup"><span data-stu-id="1a5e8-105">It is also used to create instances of anonymous types:</span></span>

```csharp
var query = from cust in customers
            select new { Name = cust.Name, Address = cust.PrimaryAddress };
```

<span data-ttu-id="1a5e8-106">L'operatore `new` viene usato anche per richiamare il costruttore predefinito per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="1a5e8-106">The `new` operator is also used to invoke the default constructor for value types.</span></span> <span data-ttu-id="1a5e8-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1a5e8-107">For example:</span></span>

```csharp
int i = new int();
```

<span data-ttu-id="1a5e8-108">Nell'istruzione precedente `i` viene inizializzato in `0`, ovvero il valore predefinito per il tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="1a5e8-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="1a5e8-109">L'istruzione ha lo stesso effetto dell'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="1a5e8-109">The statement has the same effect as the following:</span></span>

```csharp
int i = 0;
```

<span data-ttu-id="1a5e8-110">Per un elenco completo dei valori predefiniti, vedere [Tabella dei valori predefiniti](default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="1a5e8-110">For a complete list of default values, see [Default Values Table](default-values-table.md).</span></span>

<span data-ttu-id="1a5e8-111">È utile ricordare che è errato dichiarare un costruttore predefinito per uno [struct](struct.md) poiché ogni tipo di valore ha implicitamente un costruttore predefinito pubblico.</span><span class="sxs-lookup"><span data-stu-id="1a5e8-111">Remember that it is an error to declare a default constructor for a [struct](struct.md) because every value type implicitly has a public default constructor.</span></span> <span data-ttu-id="1a5e8-112">È possibile dichiarare costruttori con parametri su un tipo struct per impostarne i valori iniziali, ma questa operazione è necessaria solo se sono richiesti valori diversi da quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="1a5e8-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>

<span data-ttu-id="1a5e8-113">Sia gli oggetti di tipo valore come gli struct che gli oggetti di tipo riferimento come le classi vengono eliminati automaticamente, ma gli oggetti di tipo valore vengono eliminati quando viene eliminato il loro contesto contenitore, mentre gli oggetti di tipo riferimento vengono eliminati da Garbage Collector in un momento non specificato dopo la rimozione dell'ultimo riferimento a essi relativo.</span><span class="sxs-lookup"><span data-stu-id="1a5e8-113">Both value-type objects such as structs and reference-type objects such as classes are destroyed automatically, but value-type objects are destroyed when their containing context is destroyed, whereas reference-type objects are destroyed by the garbage collector at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="1a5e8-114">Per i tipi che contengono risorse come ad esempio gli handle di file o le connessioni di rete, è consigliabile adottare la pulitura deterministica per garantire che le risorse contenute vengano rilasciate nel più breve tempo possibile.</span><span class="sxs-lookup"><span data-stu-id="1a5e8-114">For types that contain resources such as file handles, or network connections, it is desirable to employ deterministic cleanup to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="1a5e8-115">Per altre informazioni, vedere [Istruzione using](using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1a5e8-115">For more information, see [using Statement](using-statement.md).</span></span>

<span data-ttu-id="1a5e8-116">Non è possibile sottoporre l'operatore `new` a overload.</span><span class="sxs-lookup"><span data-stu-id="1a5e8-116">The `new` operator cannot be overloaded.</span></span>

<span data-ttu-id="1a5e8-117">Se l'operatore `new` non riesce ad allocare memoria, genererà l'eccezione <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="1a5e8-117">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>

## <a name="example"></a><span data-ttu-id="1a5e8-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="1a5e8-118">Example</span></span>

<span data-ttu-id="1a5e8-119">Nell'esempio seguente vengono creati e inizializzati un oggetto `struct` e un oggetto classe usando l'operatore `new` e vengono quindi assegnati i valori.</span><span class="sxs-lookup"><span data-stu-id="1a5e8-119">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="1a5e8-120">I valori predefiniti e assegnati sono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="1a5e8-120">The default and the assigned values are displayed.</span></span>

[!code-csharp[csrefKeywordsOperator#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#7)]

<span data-ttu-id="1a5e8-121">Si noti che nell'esempio il valore predefinito di una stringa è `null`</span><span class="sxs-lookup"><span data-stu-id="1a5e8-121">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="1a5e8-122">e, pertanto, non viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="1a5e8-122">Therefore, it is not displayed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1a5e8-123">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="1a5e8-123">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1a5e8-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a5e8-124">See also</span></span>

- [<span data-ttu-id="1a5e8-125">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="1a5e8-125">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="1a5e8-126">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="1a5e8-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1a5e8-127">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="1a5e8-127">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="1a5e8-128">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="1a5e8-128">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="1a5e8-129">new</span><span class="sxs-lookup"><span data-stu-id="1a5e8-129">new</span></span>](new.md)
- [<span data-ttu-id="1a5e8-130">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="1a5e8-130">Anonymous Types</span></span>](../../programming-guide/classes-and-structs/anonymous-types.md)