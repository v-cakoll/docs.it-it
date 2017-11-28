---
title: 'Procedura: inizializzare oggetti utilizzando un inizializzatore di oggetto (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d1e65f8519062f6bceeb466a3b72c5719c0918f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="a1e5d-102">Procedura: inizializzare oggetti utilizzando un inizializzatore di oggetto (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="a1e5d-102">How to: Initialize Objects by Using an Object Initializer (C# Programming Guide)</span></span>
<span data-ttu-id="a1e5d-103">È possibile usare gli inizializzatori di oggetto per inizializzare gli oggetti tipo in modo dichiarativo, senza richiamare in modo esplicito un costruttore per il tipo.</span><span class="sxs-lookup"><span data-stu-id="a1e5d-103">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
 <span data-ttu-id="a1e5d-104">Nell'esempio seguente viene illustrato come usare gli inizializzatori di oggetto con gli oggetti denominati.</span><span class="sxs-lookup"><span data-stu-id="a1e5d-104">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="a1e5d-105">Il compilatore elabora gli inizializzatori di oggetto accedendo al costruttore di istanza predefinito e quindi elaborando le inizializzazioni dei membri.</span><span class="sxs-lookup"><span data-stu-id="a1e5d-105">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="a1e5d-106">Pertanto, se il costruttore predefinito viene dichiarato come `private` nella classe, gli inizializzatori di oggetto che richiedono l'accesso pubblico avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="a1e5d-106">Therefore, if the default constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>  
  
 <span data-ttu-id="a1e5d-107">Se si definisce un tipo anonimo, è necessario usare un inizializzatore di oggetto.</span><span class="sxs-lookup"><span data-stu-id="a1e5d-107">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="a1e5d-108">Per altre informazioni, vedere [Procedura: Restituire sottoinsiemi di proprietà degli elementi in una query](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="a1e5d-108">For more information, see [How to: Return Subsets of Element Properties in a Query](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1e5d-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="a1e5d-109">Example</span></span>  
 <span data-ttu-id="a1e5d-110">Nell'esempio seguente viene illustrato come inizializzare un nuovo tipo `StudentName` usando inizializzatori di oggetto.</span><span class="sxs-lookup"><span data-stu-id="a1e5d-110">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="a1e5d-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="a1e5d-111">Example</span></span>  
 <span data-ttu-id="a1e5d-112">Nell'esempio seguente viene illustrato come inizializzare una raccolta di tipi `StudentName` usando un inizializzatore di insieme.</span><span class="sxs-lookup"><span data-stu-id="a1e5d-112">The following example shows how to initialize a collection of `StudentName` types by using a collection initializer.</span></span> <span data-ttu-id="a1e5d-113">Si noti che un inizializzatore di insieme è una serie di inizializzatori di oggetto con valori delimitati da virgole.</span><span class="sxs-lookup"><span data-stu-id="a1e5d-113">Note that a collection initializer is a series of comma-separated object initializers.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a1e5d-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a1e5d-114">Compiling the Code</span></span>  
 <span data-ttu-id="a1e5d-115">Per eseguire questo codice, copiare e incollare la classe in un progetto di applicazione console di Visual C# creato in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1e5d-115">To run this code, copy and paste the class into a Visual C# console application project that has been created in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1e5d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1e5d-116">See Also</span></span>  
 [<span data-ttu-id="a1e5d-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a1e5d-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a1e5d-118">Inizializzatori di oggetto e di raccolta</span><span class="sxs-lookup"><span data-stu-id="a1e5d-118">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
