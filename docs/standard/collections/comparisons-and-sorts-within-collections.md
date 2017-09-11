---
title: Confronti e ordinamenti all'interno delle raccolte
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sorting data, collections
- IComparable.CompareTo method
- Collections classes
- Equals method
- collections [.NET Framework], comparisons
ms.assetid: 5e4d3b45-97f0-423c-a65f-c492ed40e73b
caps.latest.revision: 11
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1033d7ec64641dd5904372bc05bd2076efe60d39
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="comparisons-and-sorts-within-collections"></a><span data-ttu-id="2f447-102">Confronti e ordinamenti all'interno delle raccolte</span><span class="sxs-lookup"><span data-stu-id="2f447-102">Comparisons and Sorts Within Collections</span></span>
<span data-ttu-id="2f447-103">Le classi <xref:System.Collections> eseguono confronti in quasi tutti i processi di gestione delle raccolte, ricercando l'elemento da rimuovere o restituendo il valore di una coppia chiave-valore.</span><span class="sxs-lookup"><span data-stu-id="2f447-103">The <xref:System.Collections> classes perform comparisons in almost all the processes involved in managing collections, whether searching for the element to remove or returning the value of a key-and-value pair.</span></span>  
  
 <span data-ttu-id="2f447-104">Le raccolte in genere usano un operatore di uguaglianza e/o un confronto di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="2f447-104">Collections typically utilize an equality comparer and/or an ordering comparer.</span></span> <span data-ttu-id="2f447-105">Vengono usati due costrutti per i confronti.</span><span class="sxs-lookup"><span data-stu-id="2f447-105">Two constructs are used for comparisons.</span></span>  
  
<a name="BKMK_Checkingforequality"></a>   
## <a name="checking-for-equality"></a><span data-ttu-id="2f447-106">Verifica dell'uguaglianza</span><span class="sxs-lookup"><span data-stu-id="2f447-106">Checking for equality</span></span>  
 <span data-ttu-id="2f447-107">I metodi come `Contains`, <xref:System.Collections.IList.IndexOf%2A>, <xref:System.Collections.Generic.List%601.LastIndexOf%2A>e `Remove` usano un confronto di uguaglianza per gli elementi della raccolta.</span><span class="sxs-lookup"><span data-stu-id="2f447-107">Methods such as `Contains`, <xref:System.Collections.IList.IndexOf%2A>, <xref:System.Collections.Generic.List%601.LastIndexOf%2A>, and `Remove` use an equality comparer for the collection elements.</span></span> <span data-ttu-id="2f447-108">Se la raccolta è generica, viene verificata l'uguaglianza degli elementi secondo le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f447-108">If the collection is generic, than items are compared for equality according to the following guidelines:</span></span>  
  
-   <span data-ttu-id="2f447-109">Se il tipo T implementa l'interfaccia generica <xref:System.IEquatable%601> , il confronto di uguaglianza è il metodo <xref:System.IEquatable%601.Equals%2A> di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2f447-109">If type T implements the <xref:System.IEquatable%601> generic interface, then the equality comparer is the <xref:System.IEquatable%601.Equals%2A> method of that interface.</span></span>  
  
-   <span data-ttu-id="2f447-110">Se il tipo T non implementa <xref:System.IEquatable%601>, viene usato <xref:System.Object.Equals%2A?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="2f447-110">If type T does not implement <xref:System.IEquatable%601>, <xref:System.Object.Equals%2A?displayProperty=fullName> is used.</span></span>  
  
 <span data-ttu-id="2f447-111">Inoltre, alcuni overload del costruttore per le raccolte dizionario accettano un'implementazione di <xref:System.Collections.Generic.IEqualityComparer%601> , che viene usata per confrontare l'uguaglianza delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="2f447-111">In addition, Some constructor overloads for dictionary collections accept an <xref:System.Collections.Generic.IEqualityComparer%601> implementation, which is used to compare keys for equality.</span></span> <span data-ttu-id="2f447-112">Per un esempio, vedere il costruttore <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="2f447-112">For an example, see the <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A?displayProperty=fullName> constructor.</span></span>  
  
<a name="BKMK_Determiningsortorder"></a>   
## <a name="determining-sort-order"></a><span data-ttu-id="2f447-113">Determinare il tipo di ordinamento</span><span class="sxs-lookup"><span data-stu-id="2f447-113">Determining sort order</span></span>  
 <span data-ttu-id="2f447-114">I metodi come `BinarySearch` e `Sort` usano un confronto di ordinamento per gli elementi della raccolta.</span><span class="sxs-lookup"><span data-stu-id="2f447-114">Methods such as `BinarySearch` and `Sort` use an ordering comparer for the collection elements.</span></span> <span data-ttu-id="2f447-115">È possibile eseguire il confronto tra gli elementi della raccolta o tra un elemento e un valore specificato.</span><span class="sxs-lookup"><span data-stu-id="2f447-115">The comparisons can be between elements of the collection, or between an element and a specified value.</span></span> <span data-ttu-id="2f447-116">Per confrontare gli oggetti, esiste il concetto di `default comparer` e `explicit comparer`.</span><span class="sxs-lookup"><span data-stu-id="2f447-116">For comparing objects, there is the concept of a `default comparer` and an `explicit comparer`.</span></span>  
  
 <span data-ttu-id="2f447-117">L'operatore di confronto predefinito si basa su almeno uno degli oggetti confrontati per implementare l'interfaccia **IComparable** .</span><span class="sxs-lookup"><span data-stu-id="2f447-117">The default comparer relies on at least one of the objects being compared to implement the **IComparable** interface.</span></span> <span data-ttu-id="2f447-118">Si consiglia di implementare **IComparable** in tutte le classi che vengono usate come valori in una raccolta di elenchi o come chiavi in una raccolta di dizionari.</span><span class="sxs-lookup"><span data-stu-id="2f447-118">It is a good practice to implement **IComparable** on all classes are used as values in a list collection or as keys in a dictionary collection.</span></span> <span data-ttu-id="2f447-119">Per una raccolta generica, il confronto di uguaglianza è determinato come segue:</span><span class="sxs-lookup"><span data-stu-id="2f447-119">For a generic collection, equality comparison is determined according to the following:</span></span>  
  
-   <span data-ttu-id="2f447-120">Se il tipo T implementa l'interfaccia generica <xref:System.IComparable%601?displayProperty=fullName> , l'operatore di confronto predefinito è il metodo <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=fullName> di tale interfaccia</span><span class="sxs-lookup"><span data-stu-id="2f447-120">If type T implements the <xref:System.IComparable%601?displayProperty=fullName> generic interface, then the default comparer is the <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=fullName> method of that interface</span></span>  
  
-   <span data-ttu-id="2f447-121">Se il tipo T implementa l'interfaccia non generica <xref:System.IComparable?displayProperty=fullName> , l'operatore di confronto predefinito è il metodo <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=fullName> di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2f447-121">If type T implements the non-generic <xref:System.IComparable?displayProperty=fullName> interface, then the default comparer is the <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=fullName> method of that interface.</span></span>  
  
-   <span data-ttu-id="2f447-122">Se il tipo T non implementa alcuna interfaccia, non sarà presente nessun operatore di confronto predefinito e sarà necessario fornire in modo esplicito un delegato di confronto un o operatore di confronto.</span><span class="sxs-lookup"><span data-stu-id="2f447-122">If type T doesn’t implement either interface, then there is no default comparer, and a comparer or comparison delegate must be provided explicitly.</span></span>  
  
 <span data-ttu-id="2f447-123">Per fornire i confronti espliciti, alcuni metodi accettano un'implementazione **IComparer** come parametro.</span><span class="sxs-lookup"><span data-stu-id="2f447-123">To provide explicit comparisons, some methods accept an **IComparer** implementation as a parameter.</span></span> <span data-ttu-id="2f447-124">Ad esempio, il metodo <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=fullName> accetta un'implementazione <xref:System.Collections.Generic.IComparer%601?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="2f447-124">For example, the <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=fullName> method accepts an <xref:System.Collections.Generic.IComparer%601?displayProperty=fullName> implementation.</span></span>  
  
 <span data-ttu-id="2f447-125">L'impostazione cultura corrente del sistema può influenzare i confronti e gli ordinamenti all'interno di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="2f447-125">The current culture setting of the system can affect the comparisons and sorts within a collection.</span></span> <span data-ttu-id="2f447-126">Per impostazione predefinita, i confronti e gli ordinamenti nelle classi **Collections** classi sono dipendenti dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="2f447-126">By default, the comparisons and sorts in the **Collections** classes are culture-sensitive.</span></span> <span data-ttu-id="2f447-127">Per ignorare l'impostazione cultura e quindi ottenere risultati coerenti di confronto e ordinamento, usare il <xref:System.Globalization.CultureInfo.InvariantCulture%2A> con gli overload dei membri che accettano un <xref:System.Globalization.CultureInfo>.</span><span class="sxs-lookup"><span data-stu-id="2f447-127">To ignore the culture setting and therefore obtain consistent comparison and sorting results, use the <xref:System.Globalization.CultureInfo.InvariantCulture%2A> with member overloads that accept a <xref:System.Globalization.CultureInfo>.</span></span> <span data-ttu-id="2f447-128">Per altre informazioni, vedere [Performing Culture-Insensitive String Operations in Collections](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) e [Performing Culture-Insensitive String Operations in Arrays](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="2f447-128">For more information, see [Performing Culture-Insensitive String Operations in Collections](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) and [Performing Culture-Insensitive String Operations in Arrays](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md).</span></span>  
  
<a name="BKMK_Equalityandsortexample"></a>   
## <a name="equality-and-sort-example"></a><span data-ttu-id="2f447-129">Esempio di uguaglianza e ordinamento</span><span class="sxs-lookup"><span data-stu-id="2f447-129">Equality and sort example</span></span>  
 <span data-ttu-id="2f447-130">Nel codice seguente viene illustrata un'implementazione di <xref:System.IEquatable%601> e <xref:System.IComparable%601> su un semplice oggetto business.</span><span class="sxs-lookup"><span data-stu-id="2f447-130">The following code demonstrates an implementation of <xref:System.IEquatable%601> and <xref:System.IComparable%601> on a simple business object.</span></span> <span data-ttu-id="2f447-131">Inoltre, quando l'oggetto viene memorizzato in un elenco e ordinato, la chiamata al metodo <xref:System.Collections.Generic.List%601.Sort> risulterà nell'uso dell'operatore di confronto predefinito per il tipo `Part` e il metodo <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29> implementato usando un metodo anonimo.</span><span class="sxs-lookup"><span data-stu-id="2f447-131">In addition, when the object is stored in a list and sorted, you will see that calling the <xref:System.Collections.Generic.List%601.Sort> method results in the use of the default comparer for the `Part` type, and the <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29> method implemented by using an anonymous method.</span></span>  
  
 <span data-ttu-id="2f447-132">[!code-csharp[System.Collections.Generic.List.Sort#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.collections.generic.list.sort/cs/program.cs#1)] [!code-vb[System.Collections.Generic.List.Sort#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.collections.generic.list.sort/vb/module1.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="2f447-132">[!code-csharp[System.Collections.Generic.List.Sort#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.collections.generic.list.sort/cs/program.cs#1)] [!code-vb[System.Collections.Generic.List.Sort#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.collections.generic.list.sort/vb/module1.vb#1)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f447-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f447-133">See Also</span></span>  
 <xref:System.Collections.IComparer>   
 <xref:System.IEquatable%601>   
 <xref:System.Collections.Generic.IComparer%601>   
 <xref:System.IComparable>   
 <xref:System.IComparable%601>

