---
title: Collection generiche in .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET Framework], collections
- generic collections [.NET Framework]
ms.assetid: 5b646751-6ab7-465c-916c-b1a76aefa9f5
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d7e7d11446c14cffbef1e5cade5f082874187636
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="generic-collections-in-the-net-framework"></a><span data-ttu-id="e7436-102">Collection generiche in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e7436-102">Generic Collections in the .NET Framework</span></span>
<span data-ttu-id="e7436-103">Questo argomento offre una panoramica delle classi Collection generiche e di altri tipi generici in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7436-103">This topic provides an overview of the generic collection classes and other generic types in the .NET Framework.</span></span>  
  
## <a name="generic-collections-in-the-net-framework"></a><span data-ttu-id="e7436-104">Raccolte generiche in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e7436-104">Generic Collections in the .NET Framework</span></span>  
 <span data-ttu-id="e7436-105">La libreria di classi .NET Framework fornisce una serie di classi di raccolte generiche negli spazi dei nomi <xref:System.Collections.Generic> e <xref:System.Collections.ObjectModel>.</span><span class="sxs-lookup"><span data-stu-id="e7436-105">The .NET Framework class library provides a number of generic collection classes in the <xref:System.Collections.Generic> and <xref:System.Collections.ObjectModel> namespaces.</span></span> <span data-ttu-id="e7436-106">Per altre informazioni su queste classi, vedere [Tipi di raccolte comunemente usate](../../../docs/standard/collections/commonly-used-collection-types.md).</span><span class="sxs-lookup"><span data-stu-id="e7436-106">For more information about these classes, see [Commonly Used Collection Types](../../../docs/standard/collections/commonly-used-collection-types.md).</span></span>  
  
### <a name="systemcollectionsgeneric"></a><span data-ttu-id="e7436-107">System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="e7436-107">System.Collections.Generic</span></span>  
 <span data-ttu-id="e7436-108">Diversi tipi di raccolta generici sono analoghi diretti di tipi non generici.</span><span class="sxs-lookup"><span data-stu-id="e7436-108">Many of the generic collection types are direct analogs of nongeneric types.</span></span> <span data-ttu-id="e7436-109"><xref:System.Collections.Generic.Dictionary%602> è una versione generica di <xref:System.Collections.Hashtable>. Usa la struttura generica <xref:System.Collections.Generic.KeyValuePair%602> per l'enumerazione invece di <xref:System.Collections.DictionaryEntry>.</span><span class="sxs-lookup"><span data-stu-id="e7436-109"><xref:System.Collections.Generic.Dictionary%602> is a generic version of <xref:System.Collections.Hashtable>; it uses the generic structure <xref:System.Collections.Generic.KeyValuePair%602> for enumeration instead of <xref:System.Collections.DictionaryEntry>.</span></span>  
  
 <span data-ttu-id="e7436-110"><xref:System.Collections.Generic.List%601> è una versione generica di <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="e7436-110"><xref:System.Collections.Generic.List%601> is a generic version of <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="e7436-111">Esistono classi <xref:System.Collections.Generic.Queue%601> e <xref:System.Collections.Generic.Stack%601> generiche che corrispondono alle versioni non generiche.</span><span class="sxs-lookup"><span data-stu-id="e7436-111">There are generic <xref:System.Collections.Generic.Queue%601> and <xref:System.Collections.Generic.Stack%601> classes that correspond to the nongeneric versions.</span></span>  
  
 <span data-ttu-id="e7436-112">Esistono versioni generiche e non generiche di <xref:System.Collections.Generic.SortedList%602>.</span><span class="sxs-lookup"><span data-stu-id="e7436-112">There are generic and nongeneric versions of <xref:System.Collections.Generic.SortedList%602>.</span></span> <span data-ttu-id="e7436-113">Entrambe le versioni sono ibridi di un dizionario e di un elenco.</span><span class="sxs-lookup"><span data-stu-id="e7436-113">Both versions are hybrids of a dictionary and a list.</span></span> <span data-ttu-id="e7436-114">La classe generica <xref:System.Collections.Generic.SortedDictionary%602> è un dizionario vero e proprio e non ha una controparte non generica.</span><span class="sxs-lookup"><span data-stu-id="e7436-114">The <xref:System.Collections.Generic.SortedDictionary%602> generic class is a pure dictionary and has no nongeneric counterpart.</span></span>  
  
 <span data-ttu-id="e7436-115">La classe generica <xref:System.Collections.Generic.LinkedList%601> è un vero elenco collegato.</span><span class="sxs-lookup"><span data-stu-id="e7436-115">The <xref:System.Collections.Generic.LinkedList%601> generic class is a true linked list.</span></span> <span data-ttu-id="e7436-116">Non ha una controparte non generica.</span><span class="sxs-lookup"><span data-stu-id="e7436-116">It has no nongeneric counterpart.</span></span>  
  
### <a name="systemcollectionsobjectmodel"></a><span data-ttu-id="e7436-117">System.Collections.ObjectModel</span><span class="sxs-lookup"><span data-stu-id="e7436-117">System.Collections.ObjectModel</span></span>  
 <span data-ttu-id="e7436-118">La classe generica <xref:System.Collections.ObjectModel.Collection%601> fornisce una classe base da cui derivare i propri tipi di raccolta generici.</span><span class="sxs-lookup"><span data-stu-id="e7436-118">The <xref:System.Collections.ObjectModel.Collection%601> generic class provides a base class for deriving your own generic collection types.</span></span> <span data-ttu-id="e7436-119">La classe <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> consente di creare facilmente una raccolta di sola lettura dai tipi che implementano l'interfaccia generica <xref:System.Collections.Generic.IList%601>.</span><span class="sxs-lookup"><span data-stu-id="e7436-119">The <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class provides an easy way to produce a read-only collection from any type that implements the <xref:System.Collections.Generic.IList%601> generic interface.</span></span> <span data-ttu-id="e7436-120">La classe generica <xref:System.Collections.ObjectModel.KeyedCollection%602> consente di archiviare oggetti contenenti le relative chiavi.</span><span class="sxs-lookup"><span data-stu-id="e7436-120">The <xref:System.Collections.ObjectModel.KeyedCollection%602> generic class provides a way to store objects that contain their own keys.</span></span>  
  
## <a name="other-generic-types"></a><span data-ttu-id="e7436-121">Altri tipi generici</span><span class="sxs-lookup"><span data-stu-id="e7436-121">Other Generic Types</span></span>  
 <span data-ttu-id="e7436-122">La struttura generica <xref:System.Nullable%601> consente di usare tipi di valore come se potessero essere impostati su `null`.</span><span class="sxs-lookup"><span data-stu-id="e7436-122">The <xref:System.Nullable%601> generic structure allows you to use value types as if they could be assigned `null`.</span></span> <span data-ttu-id="e7436-123">Può risultare utile quando si usano query di database, dove possono mancare campi che contengono tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="e7436-123">This can be useful when working with database queries, where fields that contain value types can be missing.</span></span> <span data-ttu-id="e7436-124">Il parametro di un tipo generico può essere qualsiasi tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="e7436-124">The generic type parameter can be any value type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7436-125">In C# non è necessario usare <xref:System.Nullable%601> in modo esplicito perché questo linguaggio dispone della sintassi per i tipi nullable.</span><span class="sxs-lookup"><span data-stu-id="e7436-125">In C# it is not necessary to use <xref:System.Nullable%601> explicitly because the language has syntax for nullable types.</span></span>  
  
 <span data-ttu-id="e7436-126">La struttura generica <xref:System.ArraySegment%601> consente di delimitare un intervallo di elementi in una matrice unidimensionale in base zero di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="e7436-126">The <xref:System.ArraySegment%601> generic structure provides a way to delimit a range of elements within a one-dimensional, zero-based array of any type.</span></span> <span data-ttu-id="e7436-127">Il parametro di tipo generico è il tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="e7436-127">The generic type parameter is the type of the array's elements.</span></span>  
  
 <span data-ttu-id="e7436-128">Con il delegato generico <xref:System.EventHandler%601> non è più necessario dichiarare un tipo di delegato per gestire gli eventi, se l'evento segue il modello di gestione degli eventi usato da [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7436-128">The <xref:System.EventHandler%601> generic delegate eliminates the need to declare a delegate type to handle events, if your event follows the event-handling pattern used by the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="e7436-129">Si supponga, ad esempio, di aver creato una classe `MyEventArgs`, derivata da <xref:System.EventArgs>, in cui includere i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="e7436-129">For example, suppose you have created a `MyEventArgs` class, derived from <xref:System.EventArgs>, to hold the data for your event.</span></span> <span data-ttu-id="e7436-130">È quindi possibile dichiarare l'evento come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e7436-130">You can then declare the event as follows:</span></span>  
  
 [!code-cpp[Conceptual.Generics.Overview#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Generics.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source2.cs#7)]
 [!code-vb[Conceptual.Generics.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="e7436-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7436-131">See Also</span></span>  
 <xref:System.Collections.Generic?displayProperty=nameWithType>  
 <xref:System.Collections.ObjectModel?displayProperty=nameWithType>  
 [<span data-ttu-id="e7436-132">Generics</span><span class="sxs-lookup"><span data-stu-id="e7436-132">Generics</span></span>](../../../docs/standard/generics/index.md)  
 [<span data-ttu-id="e7436-133">Delegati generici per la modifica di matrici ed elenchi</span><span class="sxs-lookup"><span data-stu-id="e7436-133">Generic Delegates for Manipulating Arrays and Lists</span></span>](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)  
 [<span data-ttu-id="e7436-134">Interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="e7436-134">Generic Interfaces</span></span>](../../../docs/standard/generics/interfaces.md)
