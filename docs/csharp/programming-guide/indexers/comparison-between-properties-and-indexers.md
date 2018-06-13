---
title: Confronto tra proprietà e indicizzatori (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: a8b347be33ea6acbdf8a78a7af45fd3d0c27f8fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330372"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="007b3-102">Confronto tra proprietà e indicizzatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="007b3-102">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>
<span data-ttu-id="007b3-103">Gli indicizzatori sono come proprietà.</span><span class="sxs-lookup"><span data-stu-id="007b3-103">Indexers are like properties.</span></span> <span data-ttu-id="007b3-104">Ad eccezione delle differenze illustrate nella tabella seguente, tutte le regole definite per le funzioni di accesso a proprietà si applicano anche alle funzioni di accesso a indicizzatori.</span><span class="sxs-lookup"><span data-stu-id="007b3-104">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="007b3-105">Proprietà</span><span class="sxs-lookup"><span data-stu-id="007b3-105">Property</span></span>|<span data-ttu-id="007b3-106">Indicizzatore</span><span class="sxs-lookup"><span data-stu-id="007b3-106">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="007b3-107">Consente di chiamare metodi come se fossero membri dati pubblici.</span><span class="sxs-lookup"><span data-stu-id="007b3-107">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="007b3-108">Consente di accedere agli elementi di una raccolta interna di un oggetto tramite la notazione di matrice per l'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="007b3-108">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="007b3-109">Accesso tramite nome semplice.</span><span class="sxs-lookup"><span data-stu-id="007b3-109">Accessed through a simple name.</span></span>|<span data-ttu-id="007b3-110">Accesso tramite indice.</span><span class="sxs-lookup"><span data-stu-id="007b3-110">Accessed through an index.</span></span>|  
|<span data-ttu-id="007b3-111">Può essere un membro statico o un membro di istanza.</span><span class="sxs-lookup"><span data-stu-id="007b3-111">Can be a static or an instance member.</span></span>|<span data-ttu-id="007b3-112">Deve essere un membro di istanza.</span><span class="sxs-lookup"><span data-stu-id="007b3-112">Must be an instance member.</span></span>|  
|<span data-ttu-id="007b3-113">La funzione di accesso [get](../../../csharp/language-reference/keywords/get.md) di una proprietà non ha parametri.</span><span class="sxs-lookup"><span data-stu-id="007b3-113">A [get](../../../csharp/language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="007b3-114">La funzione di accesso `get` di un indicizzatore ha lo stesso elenco di parametri formali dell'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="007b3-114">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="007b3-115">La funzione di accesso [set](../../../csharp/language-reference/keywords/set.md) di una proprietà contiene il parametro `value` implicito.</span><span class="sxs-lookup"><span data-stu-id="007b3-115">A [set](../../../csharp/language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="007b3-116">La funzione di accesso `set` di un indicizzatore ha lo stesso elenco di parametri formali dell'indicizzatore e anche il parametro [value](../../../csharp/language-reference/keywords/value.md).</span><span class="sxs-lookup"><span data-stu-id="007b3-116">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../../csharp/language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="007b3-117">Supporta la sintassi abbreviata con [proprietà implementate automaticamente](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="007b3-117">Supports shortened syntax with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="007b3-118">Non supporta la sintassi abbreviata.</span><span class="sxs-lookup"><span data-stu-id="007b3-118">Does not support shortened syntax.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="007b3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="007b3-119">See Also</span></span>  
 [<span data-ttu-id="007b3-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="007b3-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="007b3-121">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="007b3-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
 [<span data-ttu-id="007b3-122">Proprietà</span><span class="sxs-lookup"><span data-stu-id="007b3-122">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
