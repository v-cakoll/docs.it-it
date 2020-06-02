---
title: Raccolte generiche in .NET
ms.date: 02/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET], collections
- generic collections [.NET]
- generic types [.NET]
ms.assetid: 5b646751-6ab7-465c-916c-b1a76aefa9f5
ms.openlocfilehash: 5767bac0bb1e3ae9e586e9a10d8452d421519447
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287571"
---
# <a name="generic-collections-in-net"></a><span data-ttu-id="9ed73-102">Raccolte generiche in .NET</span><span class="sxs-lookup"><span data-stu-id="9ed73-102">Generic collections in .NET</span></span>

 <span data-ttu-id="9ed73-103">La libreria di classi .NET offre varie classi di raccolte generiche negli spazi dei nomi <xref:System.Collections.Generic> e <xref:System.Collections.ObjectModel>.</span><span class="sxs-lookup"><span data-stu-id="9ed73-103">The .NET class library provides a number of generic collection classes in the <xref:System.Collections.Generic> and <xref:System.Collections.ObjectModel> namespaces.</span></span> <span data-ttu-id="9ed73-104">Per informazioni più dettagliate su queste classi, vedere [Tipi di raccolte comunemente usate](../collections/commonly-used-collection-types.md).</span><span class="sxs-lookup"><span data-stu-id="9ed73-104">For more detailed information about these classes, see [Commonly Used Collection Types](../collections/commonly-used-collection-types.md).</span></span>  
  
## <a name="systemcollectionsgeneric"></a><span data-ttu-id="9ed73-105">System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="9ed73-105">System.Collections.Generic</span></span>

 <span data-ttu-id="9ed73-106">Diversi tipi di raccolta generici sono analoghi diretti di tipi non generici.</span><span class="sxs-lookup"><span data-stu-id="9ed73-106">Many of the generic collection types are direct analogs of nongeneric types.</span></span> <span data-ttu-id="9ed73-107"><xref:System.Collections.Generic.Dictionary%602> è una versione generica di <xref:System.Collections.Hashtable>. Usa la struttura generica <xref:System.Collections.Generic.KeyValuePair%602> per l'enumerazione invece di <xref:System.Collections.DictionaryEntry>.</span><span class="sxs-lookup"><span data-stu-id="9ed73-107"><xref:System.Collections.Generic.Dictionary%602> is a generic version of <xref:System.Collections.Hashtable>; it uses the generic structure <xref:System.Collections.Generic.KeyValuePair%602> for enumeration instead of <xref:System.Collections.DictionaryEntry>.</span></span>  
  
 <span data-ttu-id="9ed73-108"><xref:System.Collections.Generic.List%601> è una versione generica di <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="9ed73-108"><xref:System.Collections.Generic.List%601> is a generic version of <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="9ed73-109">Esistono classi <xref:System.Collections.Generic.Queue%601> e <xref:System.Collections.Generic.Stack%601> generiche che corrispondono alle versioni non generiche.</span><span class="sxs-lookup"><span data-stu-id="9ed73-109">There are generic <xref:System.Collections.Generic.Queue%601> and <xref:System.Collections.Generic.Stack%601> classes that correspond to the nongeneric versions.</span></span>  
  
 <span data-ttu-id="9ed73-110">Esistono versioni generiche e non generiche di <xref:System.Collections.Generic.SortedList%602>.</span><span class="sxs-lookup"><span data-stu-id="9ed73-110">There are generic and nongeneric versions of <xref:System.Collections.Generic.SortedList%602>.</span></span> <span data-ttu-id="9ed73-111">Entrambe le versioni sono ibridi di un dizionario e di un elenco.</span><span class="sxs-lookup"><span data-stu-id="9ed73-111">Both versions are hybrids of a dictionary and a list.</span></span> <span data-ttu-id="9ed73-112">La classe generica <xref:System.Collections.Generic.SortedDictionary%602> è un dizionario vero e proprio e non ha una controparte non generica.</span><span class="sxs-lookup"><span data-stu-id="9ed73-112">The <xref:System.Collections.Generic.SortedDictionary%602> generic class is a pure dictionary and has no nongeneric counterpart.</span></span>  
  
 <span data-ttu-id="9ed73-113">La classe generica <xref:System.Collections.Generic.LinkedList%601> è un vero elenco collegato.</span><span class="sxs-lookup"><span data-stu-id="9ed73-113">The <xref:System.Collections.Generic.LinkedList%601> generic class is a true linked list.</span></span> <span data-ttu-id="9ed73-114">Non ha una controparte non generica.</span><span class="sxs-lookup"><span data-stu-id="9ed73-114">It has no nongeneric counterpart.</span></span>  
  
## <a name="systemcollectionsobjectmodel"></a><span data-ttu-id="9ed73-115">System.Collections.ObjectModel</span><span class="sxs-lookup"><span data-stu-id="9ed73-115">System.Collections.ObjectModel</span></span>

 <span data-ttu-id="9ed73-116">La classe generica <xref:System.Collections.ObjectModel.Collection%601> fornisce una classe base da cui derivare i propri tipi di raccolta generici.</span><span class="sxs-lookup"><span data-stu-id="9ed73-116">The <xref:System.Collections.ObjectModel.Collection%601> generic class provides a base class for deriving your own generic collection types.</span></span> <span data-ttu-id="9ed73-117">La classe <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> consente di creare facilmente una raccolta di sola lettura dai tipi che implementano l'interfaccia generica <xref:System.Collections.Generic.IList%601>.</span><span class="sxs-lookup"><span data-stu-id="9ed73-117">The <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class provides an easy way to produce a read-only collection from any type that implements the <xref:System.Collections.Generic.IList%601> generic interface.</span></span> <span data-ttu-id="9ed73-118">La classe generica <xref:System.Collections.ObjectModel.KeyedCollection%602> consente di archiviare oggetti contenenti le relative chiavi.</span><span class="sxs-lookup"><span data-stu-id="9ed73-118">The <xref:System.Collections.ObjectModel.KeyedCollection%602> generic class provides a way to store objects that contain their own keys.</span></span>  
  
## <a name="other-generic-types"></a><span data-ttu-id="9ed73-119">Altri tipi generici</span><span class="sxs-lookup"><span data-stu-id="9ed73-119">Other generic types</span></span>

 <span data-ttu-id="9ed73-120">La struttura generica <xref:System.Nullable%601> consente di usare tipi di valore come se potessero essere impostati su `null`.</span><span class="sxs-lookup"><span data-stu-id="9ed73-120">The <xref:System.Nullable%601> generic structure allows you to use value types as if they could be assigned `null`.</span></span> <span data-ttu-id="9ed73-121">Può risultare utile quando si usano query di database, dove possono mancare campi che contengono tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="9ed73-121">This can be useful when working with database queries, where fields that contain value types can be missing.</span></span> <span data-ttu-id="9ed73-122">Il parametro di un tipo generico può essere qualsiasi tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="9ed73-122">The generic type parameter can be any value type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ed73-123">In C# e Visual Basic non è necessario usare <xref:System.Nullable%601> in modo esplicito perché questo linguaggio dispone della sintassi per i tipi nullable.</span><span class="sxs-lookup"><span data-stu-id="9ed73-123">In C# and Visual Basic, it is not necessary to use <xref:System.Nullable%601> explicitly because the language has syntax for nullable types.</span></span> <span data-ttu-id="9ed73-124">Vedere [tipi di valore Nullable (riferimenti per C#)](../../csharp/language-reference/builtin-types/nullable-value-types.md) e [tipi di valore Nullable (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="9ed73-124">See [Nullable value types (C# reference)](../../csharp/language-reference/builtin-types/nullable-value-types.md) and [Nullable value types (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span></span>
  
 <span data-ttu-id="9ed73-125">La struttura generica <xref:System.ArraySegment%601> consente di delimitare un intervallo di elementi in una matrice unidimensionale in base zero di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="9ed73-125">The <xref:System.ArraySegment%601> generic structure provides a way to delimit a range of elements within a one-dimensional, zero-based array of any type.</span></span> <span data-ttu-id="9ed73-126">Il parametro di tipo generico è il tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="9ed73-126">The generic type parameter is the type of the array's elements.</span></span>  
  
 <span data-ttu-id="9ed73-127">Con il delegato generico <xref:System.EventHandler%601> non è più necessario dichiarare un tipo di delegato per gestire gli eventi, se l'evento segue il modello di gestione degli eventi usato da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9ed73-127">The <xref:System.EventHandler%601> generic delegate eliminates the need to declare a delegate type to handle events, if your event follows the event-handling pattern used by the .NET Framework.</span></span> <span data-ttu-id="9ed73-128">Si supponga, ad esempio, di aver creato una classe `MyEventArgs`, derivata da <xref:System.EventArgs>, in cui includere i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="9ed73-128">For example, suppose you have created a `MyEventArgs` class, derived from <xref:System.EventArgs>, to hold the data for your event.</span></span> <span data-ttu-id="9ed73-129">È quindi possibile dichiarare l'evento come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ed73-129">You can then declare the event as follows:</span></span>  
  
 [!code-cpp[Conceptual.Generics.Overview#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Generics.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source2.cs#7)]
 [!code-vb[Conceptual.Generics.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="9ed73-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ed73-130">See also</span></span>

- <xref:System.Collections.Generic?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel?displayProperty=nameWithType>
- [<span data-ttu-id="9ed73-131">Generics</span><span class="sxs-lookup"><span data-stu-id="9ed73-131">Generics</span></span>](index.md)
- [<span data-ttu-id="9ed73-132">Delegati generici per la modifica di matrici ed elenchi</span><span class="sxs-lookup"><span data-stu-id="9ed73-132">Generic Delegates for Manipulating Arrays and Lists</span></span>](delegates-for-manipulating-arrays-and-lists.md)
- [<span data-ttu-id="9ed73-133">Interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="9ed73-133">Generic Interfaces</span></span>](interfaces.md)
