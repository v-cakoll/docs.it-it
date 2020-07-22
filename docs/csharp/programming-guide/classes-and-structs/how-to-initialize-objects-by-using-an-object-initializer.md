---
title: Come inizializzare gli oggetti usando un inizializzatore di oggetto-guida per programmatori C#
description: Informazioni su come usare gli inizializzatori di oggetto per inizializzare gli oggetti di tipo in C# senza richiamare un costruttore. Usare un inizializzatore di oggetto per definire un tipo anonimo.
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 0781b168b0ae8b8383affe19d2721da67f662045
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865034"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="f8b3f-104">Come inizializzare gli oggetti usando un inizializzatore di oggetto (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="f8b3f-104">How to initialize objects by using an object initializer (C# Programming Guide)</span></span>

<span data-ttu-id="f8b3f-105">È possibile usare gli inizializzatori di oggetto per inizializzare gli oggetti tipo in modo dichiarativo, senza richiamare in modo esplicito un costruttore per il tipo.</span><span class="sxs-lookup"><span data-stu-id="f8b3f-105">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
<span data-ttu-id="f8b3f-106">Nell'esempio seguente viene illustrato come usare gli inizializzatori di oggetto con gli oggetti denominati.</span><span class="sxs-lookup"><span data-stu-id="f8b3f-106">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="f8b3f-107">Il compilatore elabora gli inizializzatori di oggetto accedendo al costruttore di istanza predefinito e quindi elaborando le inizializzazioni dei membri.</span><span class="sxs-lookup"><span data-stu-id="f8b3f-107">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="f8b3f-108">Pertanto, se il costruttore senza parametri viene dichiarato come `private` nella classe, gli inizializzatori di oggetto che richiedono l'accesso pubblico avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f8b3f-108">Therefore, if the parameterless constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>
  
<span data-ttu-id="f8b3f-109">Se si definisce un tipo anonimo, è necessario usare un inizializzatore di oggetto.</span><span class="sxs-lookup"><span data-stu-id="f8b3f-109">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="f8b3f-110">Per ulteriori informazioni, vedere [come restituire subset di proprietà degli elementi in una query](how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="f8b3f-110">For more information, see [How to return subsets of element properties in a query](how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8b3f-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8b3f-111">Example</span></span>  

<span data-ttu-id="f8b3f-112">Nell'esempio seguente viene illustrato come inizializzare un nuovo tipo `StudentName` usando inizializzatori di oggetto.</span><span class="sxs-lookup"><span data-stu-id="f8b3f-112">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span> <span data-ttu-id="f8b3f-113">Questo esempio imposta le proprietà nel tipo `StudentName`:</span><span class="sxs-lookup"><span data-stu-id="f8b3f-113">This example sets properties in the `StudentName` type:</span></span>
  
[!code-csharp[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

<span data-ttu-id="f8b3f-114">Gli inizializzatori di oggetto possono essere usati per impostare gli indicizzatori in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="f8b3f-114">Object initializers can be used to set indexers in an object.</span></span> <span data-ttu-id="f8b3f-115">L'esempio seguente definisce una classe `BaseballTeam` che usa un indicizzatore per ottenere e impostare i lettori in posizioni diverse.</span><span class="sxs-lookup"><span data-stu-id="f8b3f-115">The following example defines a `BaseballTeam` class that uses an indexer to get and set players at different positions.</span></span> <span data-ttu-id="f8b3f-116">L'inizializzatore può assegnare lettori, in base all'abbreviazione per la posizione o al numero usato per gli scorecard di baseball di ogni posizione:</span><span class="sxs-lookup"><span data-stu-id="f8b3f-116">The initializer can assign players, based on the abbreviation for the position, or the number used for each position baseball scorecards:</span></span>

[!code-csharp[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a><span data-ttu-id="f8b3f-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f8b3f-117">See also</span></span>

- [<span data-ttu-id="f8b3f-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f8b3f-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f8b3f-119">Inizializzatori di oggetto e di raccolta</span><span class="sxs-lookup"><span data-stu-id="f8b3f-119">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
