---
title: Confronti e ordinamenti all'interno delle raccolte
ms.date: 04/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data, collections
- IComparable.CompareTo method
- Collections classes
- Equals method
- collections [.NET Framework], comparisons
ms.assetid: 5e4d3b45-97f0-423c-a65f-c492ed40e73b
ms.openlocfilehash: cb9dd3e8af570251b8bcd2e450e686ad69ab78c4
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287978"
---
# <a name="comparisons-and-sorts-within-collections"></a><span data-ttu-id="3cce4-102">Confronti e ordinamenti all'interno delle raccolte</span><span class="sxs-lookup"><span data-stu-id="3cce4-102">Comparisons and sorts within collections</span></span>

<span data-ttu-id="3cce4-103">Le classi <xref:System.Collections> eseguono confronti in quasi tutti i processi di gestione delle raccolte, ricercando l'elemento da rimuovere o restituendo il valore di una coppia chiave-valore.</span><span class="sxs-lookup"><span data-stu-id="3cce4-103">The <xref:System.Collections> classes perform comparisons in almost all the processes involved in managing collections, whether searching for the element to remove or returning the value of a key-and-value pair.</span></span>

<span data-ttu-id="3cce4-104">Le raccolte in genere usano un operatore di uguaglianza e/o un confronto di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="3cce4-104">Collections typically utilize an equality comparer and/or an ordering comparer.</span></span> <span data-ttu-id="3cce4-105">Vengono usati due costrutti per i confronti.</span><span class="sxs-lookup"><span data-stu-id="3cce4-105">Two constructs are used for comparisons.</span></span>

<a name="BKMK_Checkingforequality"></a>
## <a name="check-for-equality"></a><span data-ttu-id="3cce4-106">Verifica uguaglianza</span><span class="sxs-lookup"><span data-stu-id="3cce4-106">Check for equality</span></span>

<span data-ttu-id="3cce4-107">I metodi come `Contains`, <xref:System.Collections.IList.IndexOf%2A>, <xref:System.Collections.Generic.List%601.LastIndexOf%2A>e `Remove` usano un confronto di uguaglianza per gli elementi della raccolta.</span><span class="sxs-lookup"><span data-stu-id="3cce4-107">Methods such as `Contains`, <xref:System.Collections.IList.IndexOf%2A>, <xref:System.Collections.Generic.List%601.LastIndexOf%2A>, and `Remove` use an equality comparer for the collection elements.</span></span> <span data-ttu-id="3cce4-108">Se la raccolta è generica, gli elementi vengono confrontati per verificarne l'uguaglianza secondo le linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="3cce4-108">If the collection is generic, then items are compared for equality according to the following guidelines:</span></span>

- <span data-ttu-id="3cce4-109">Se il tipo T implementa l'interfaccia generica <xref:System.IEquatable%601> , il confronto di uguaglianza è il metodo <xref:System.IEquatable%601.Equals%2A> di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3cce4-109">If type T implements the <xref:System.IEquatable%601> generic interface, then the equality comparer is the <xref:System.IEquatable%601.Equals%2A> method of that interface.</span></span>

- <span data-ttu-id="3cce4-110">Se il tipo T non implementa <xref:System.IEquatable%601>, viene usato <xref:System.Object.Equals%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3cce4-110">If type T does not implement <xref:System.IEquatable%601>, <xref:System.Object.Equals%2A?displayProperty=nameWithType> is used.</span></span>

<span data-ttu-id="3cce4-111">Inoltre, alcuni overload del costruttore per le raccolte dizionario accettano un'implementazione di <xref:System.Collections.Generic.IEqualityComparer%601>, che viene usata per confrontare l'uguaglianza delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="3cce4-111">In addition, some constructor overloads for dictionary collections accept an <xref:System.Collections.Generic.IEqualityComparer%601> implementation, which is used to compare keys for equality.</span></span> <span data-ttu-id="3cce4-112">Per un esempio, vedere il costruttore <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A> .</span><span class="sxs-lookup"><span data-stu-id="3cce4-112">For an example, see the <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A> constructor.</span></span>

<a name="BKMK_Determiningsortorder"></a>
## <a name="determine-sort-order"></a><span data-ttu-id="3cce4-113">Determinare il tipo di ordinamento</span><span class="sxs-lookup"><span data-stu-id="3cce4-113">Determine sort order</span></span>

<span data-ttu-id="3cce4-114">I metodi come `BinarySearch` e `Sort` usano un confronto di ordinamento per gli elementi della raccolta.</span><span class="sxs-lookup"><span data-stu-id="3cce4-114">Methods such as `BinarySearch` and `Sort` use an ordering comparer for the collection elements.</span></span> <span data-ttu-id="3cce4-115">È possibile eseguire il confronto tra gli elementi della raccolta o tra un elemento e un valore specificato.</span><span class="sxs-lookup"><span data-stu-id="3cce4-115">The comparisons can be between elements of the collection, or between an element and a specified value.</span></span> <span data-ttu-id="3cce4-116">Per confrontare gli oggetti, esiste il concetto di `default comparer` e `explicit comparer`.</span><span class="sxs-lookup"><span data-stu-id="3cce4-116">For comparing objects, there is the concept of a `default comparer` and an `explicit comparer`.</span></span>

<span data-ttu-id="3cce4-117">L'operatore di confronto predefinito si basa su almeno uno degli oggetti confrontati per implementare l'interfaccia **IComparable** .</span><span class="sxs-lookup"><span data-stu-id="3cce4-117">The default comparer relies on at least one of the objects being compared to implement the **IComparable** interface.</span></span> <span data-ttu-id="3cce4-118">Si consiglia di implementare **IComparable** in tutte le classi che vengono usate come valori in una raccolta di elenchi o come chiavi in una raccolta di dizionari.</span><span class="sxs-lookup"><span data-stu-id="3cce4-118">It is a good practice to implement **IComparable** on all classes are used as values in a list collection or as keys in a dictionary collection.</span></span> <span data-ttu-id="3cce4-119">Per una raccolta generica, il confronto di uguaglianza è determinato come segue:</span><span class="sxs-lookup"><span data-stu-id="3cce4-119">For a generic collection, equality comparison is determined according to the following:</span></span>

- <span data-ttu-id="3cce4-120">Se il tipo T implementa l'interfaccia generica <xref:System.IComparable%601?displayProperty=nameWithType> , l'operatore di confronto predefinito è il metodo <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=nameWithType> di tale interfaccia</span><span class="sxs-lookup"><span data-stu-id="3cce4-120">If type T implements the <xref:System.IComparable%601?displayProperty=nameWithType> generic interface, then the default comparer is the <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=nameWithType> method of that interface</span></span>

- <span data-ttu-id="3cce4-121">Se il tipo T implementa l'interfaccia non generica <xref:System.IComparable?displayProperty=nameWithType> , l'operatore di confronto predefinito è il metodo <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=nameWithType> di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3cce4-121">If type T implements the non-generic <xref:System.IComparable?displayProperty=nameWithType> interface, then the default comparer is the <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=nameWithType> method of that interface.</span></span>

- <span data-ttu-id="3cce4-122">Se il tipo T non implementa alcuna interfaccia, non esiste alcun operatore di confronto predefinito ed è necessario fornire in modo esplicito un delegato di confronto o di confronto.</span><span class="sxs-lookup"><span data-stu-id="3cce4-122">If type T doesn't implement either interface, then there is no default comparer, and a comparer or comparison delegate must be provided explicitly.</span></span>

<span data-ttu-id="3cce4-123">Per fornire i confronti espliciti, alcuni metodi accettano un'implementazione **IComparer** come parametro.</span><span class="sxs-lookup"><span data-stu-id="3cce4-123">To provide explicit comparisons, some methods accept an **IComparer** implementation as a parameter.</span></span> <span data-ttu-id="3cce4-124">Ad esempio, il metodo <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> accetta un'implementazione <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3cce4-124">For example, the <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> method accepts an <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> implementation.</span></span>

<span data-ttu-id="3cce4-125">L'impostazione cultura corrente del sistema può influenzare i confronti e gli ordinamenti all'interno di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="3cce4-125">The current culture setting of the system can affect the comparisons and sorts within a collection.</span></span> <span data-ttu-id="3cce4-126">Per impostazione predefinita, i confronti e gli ordinamenti nelle classi **Collections** classi sono dipendenti dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="3cce4-126">By default, the comparisons and sorts in the **Collections** classes are culture-sensitive.</span></span> <span data-ttu-id="3cce4-127">Per ignorare l'impostazione cultura e quindi ottenere risultati coerenti di confronto e ordinamento, usare il <xref:System.Globalization.CultureInfo.InvariantCulture%2A> con gli overload dei membri che accettano un <xref:System.Globalization.CultureInfo>.</span><span class="sxs-lookup"><span data-stu-id="3cce4-127">To ignore the culture setting and therefore obtain consistent comparison and sorting results, use the <xref:System.Globalization.CultureInfo.InvariantCulture%2A> with member overloads that accept a <xref:System.Globalization.CultureInfo>.</span></span> <span data-ttu-id="3cce4-128">Per altre informazioni, vedere [Performing Culture-Insensitive String Operations in Collections](../globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) e [Performing Culture-Insensitive String Operations in Arrays](../globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="3cce4-128">For more information, see [Performing Culture-Insensitive String Operations in Collections](../globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) and [Performing Culture-Insensitive String Operations in Arrays](../globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md).</span></span>

<a name="BKMK_Equalityandsortexample"></a>
## <a name="equality-and-sort-example"></a><span data-ttu-id="3cce4-129">Esempio di uguaglianza e ordinamento</span><span class="sxs-lookup"><span data-stu-id="3cce4-129">Equality and sort example</span></span>

<span data-ttu-id="3cce4-130">Nel codice seguente viene illustrata un'implementazione di <xref:System.IEquatable%601> e <xref:System.IComparable%601> su un semplice oggetto business.</span><span class="sxs-lookup"><span data-stu-id="3cce4-130">The following code demonstrates an implementation of <xref:System.IEquatable%601> and <xref:System.IComparable%601> on a simple business object.</span></span> <span data-ttu-id="3cce4-131">Inoltre, quando l'oggetto viene memorizzato in un elenco e ordinato, la chiamata al metodo <xref:System.Collections.Generic.List%601.Sort> risulterà nell'uso dell'operatore di confronto predefinito per il tipo `Part` e il metodo <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29> implementato usando un metodo anonimo.</span><span class="sxs-lookup"><span data-stu-id="3cce4-131">In addition, when the object is stored in a list and sorted, you will see that calling the <xref:System.Collections.Generic.List%601.Sort> method results in the use of the default comparer for the `Part` type, and the <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29> method implemented by using an anonymous method.</span></span>

[!code-csharp[System.Collections.Generic.List.Sort#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.collections.generic.list.sort/cs/program.cs#1)]
[!code-vb[System.Collections.Generic.List.Sort#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.collections.generic.list.sort/vb/module1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="3cce4-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cce4-132">See also</span></span>

- <xref:System.Collections.IComparer>
- <xref:System.IEquatable%601>
- <xref:System.Collections.Generic.IComparer%601>
- <xref:System.IComparable>
- <xref:System.IComparable%601>
