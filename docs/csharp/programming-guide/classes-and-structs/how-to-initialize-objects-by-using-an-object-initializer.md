---
title: 'Procedura: Inizializzare oggetti usando un inizializzatore di oggetto - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 29987b9ba1f1f18f4e768766bd2391ebb5862f97
ms.sourcegitcommit: d09c77414e9e4fc72c79b04deee7a756a120674e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2019
ms.locfileid: "54084875"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="c0e96-102">Procedura: Inizializzare oggetti usando un inizializzatore di oggetto (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="c0e96-102">How to: Initialize Objects by Using an Object Initializer (C# Programming Guide)</span></span>

<span data-ttu-id="c0e96-103">È possibile usare gli inizializzatori di oggetto per inizializzare gli oggetti tipo in modo dichiarativo, senza richiamare in modo esplicito un costruttore per il tipo.</span><span class="sxs-lookup"><span data-stu-id="c0e96-103">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
<span data-ttu-id="c0e96-104">Nell'esempio seguente viene illustrato come usare gli inizializzatori di oggetto con gli oggetti denominati.</span><span class="sxs-lookup"><span data-stu-id="c0e96-104">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="c0e96-105">Il compilatore elabora gli inizializzatori di oggetto accedendo al costruttore di istanza predefinito e quindi elaborando le inizializzazioni dei membri.</span><span class="sxs-lookup"><span data-stu-id="c0e96-105">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="c0e96-106">Pertanto, se il costruttore predefinito viene dichiarato come `private` nella classe, gli inizializzatori di oggetto che richiedono l'accesso pubblico avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="c0e96-106">Therefore, if the default constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>
  
<span data-ttu-id="c0e96-107">Se si definisce un tipo anonimo, è necessario usare un inizializzatore di oggetto.</span><span class="sxs-lookup"><span data-stu-id="c0e96-107">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="c0e96-108">Per altre informazioni, vedere [Procedura: Restituire sottoinsiemi di proprietà degli elementi in una query](how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="c0e96-108">For more information, see [How to: Return Subsets of Element Properties in a Query](how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0e96-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="c0e96-109">Example</span></span>  

<span data-ttu-id="c0e96-110">Nell'esempio seguente viene illustrato come inizializzare un nuovo tipo `StudentName` usando inizializzatori di oggetto.</span><span class="sxs-lookup"><span data-stu-id="c0e96-110">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span> <span data-ttu-id="c0e96-111">Questo esempio imposta le proprietà nel tipo `StudentName`:</span><span class="sxs-lookup"><span data-stu-id="c0e96-111">This example sets properties in the `StudentName` type:</span></span>
  
[!code-csharp-interactive[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

<span data-ttu-id="c0e96-112">Gli inizializzatori di oggetto possono essere usati per impostare gli indicizzatori in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="c0e96-112">Object initializers can be used to set indexers in an object.</span></span> <span data-ttu-id="c0e96-113">L'esempio seguente definisce una classe `BaseballTeam` che usa un indicizzatore per ottenere e impostare i lettori in posizioni diverse.</span><span class="sxs-lookup"><span data-stu-id="c0e96-113">The following example defines a `BaseballTeam` class that uses an indexer to get and set players at different positions.</span></span> <span data-ttu-id="c0e96-114">L'inizializzatore può assegnare lettori, in base all'abbreviazione per la posizione o al numero usato per gli scorecard di baseball di ogni posizione:</span><span class="sxs-lookup"><span data-stu-id="c0e96-114">The initializer can assign players, based on the abbreviation for the position, or the number used for each position baseball scorecards:</span></span>

[!code-csharp-interactive[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a><span data-ttu-id="c0e96-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0e96-115">See Also</span></span>

- [<span data-ttu-id="c0e96-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c0e96-116">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="c0e96-117">Inizializzatori di oggetto e di raccolta</span><span class="sxs-lookup"><span data-stu-id="c0e96-117">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
