---
title: 'Procedura: inizializzare oggetti utilizzando un inizializzatore di oggetto (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
caps.latest.revision: 20
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
ms.openlocfilehash: 01f2391680d9236b42f0d015b944b8f12455d0c8
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="73d99-102">Procedura: inizializzare oggetti utilizzando un inizializzatore di oggetto (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="73d99-102">How to: Initialize Objects by Using an Object Initializer (C# Programming Guide)</span></span>
<span data-ttu-id="73d99-103">È possibile usare gli inizializzatori di oggetto per inizializzare gli oggetti tipo in modo dichiarativo, senza richiamare in modo esplicito un costruttore per il tipo.</span><span class="sxs-lookup"><span data-stu-id="73d99-103">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
 <span data-ttu-id="73d99-104">Nell'esempio seguente viene illustrato come usare gli inizializzatori di oggetto con gli oggetti denominati.</span><span class="sxs-lookup"><span data-stu-id="73d99-104">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="73d99-105">Il compilatore elabora gli inizializzatori di oggetto accedendo al costruttore di istanza predefinito e quindi elaborando le inizializzazioni dei membri.</span><span class="sxs-lookup"><span data-stu-id="73d99-105">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="73d99-106">Pertanto, se il costruttore predefinito viene dichiarato come `private` nella classe, gli inizializzatori di oggetto che richiedono l'accesso pubblico avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="73d99-106">Therefore, if the default constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>  
  
 <span data-ttu-id="73d99-107">Se si definisce un tipo anonimo, è necessario usare un inizializzatore di oggetto.</span><span class="sxs-lookup"><span data-stu-id="73d99-107">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="73d99-108">Per altre informazioni, vedere [Procedura: Restituire sottoinsiemi di proprietà degli elementi in una query](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="73d99-108">For more information, see [How to: Return Subsets of Element Properties in a Query](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="73d99-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="73d99-109">Example</span></span>  
 <span data-ttu-id="73d99-110">Nell'esempio seguente viene illustrato come inizializzare un nuovo tipo `StudentName` usando inizializzatori di oggetto.</span><span class="sxs-lookup"><span data-stu-id="73d99-110">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span>  
  
 <span data-ttu-id="73d99-111">[!code-cs[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="73d99-111">[!code-cs[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="73d99-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="73d99-112">Example</span></span>  
 <span data-ttu-id="73d99-113">Nell'esempio seguente viene illustrato come inizializzare una raccolta di tipi `StudentName` usando un inizializzatore di insieme.</span><span class="sxs-lookup"><span data-stu-id="73d99-113">The following example shows how to initialize a collection of `StudentName` types by using a collection initializer.</span></span> <span data-ttu-id="73d99-114">Si noti che un inizializzatore di insieme è una serie di inizializzatori di oggetto con valori delimitati da virgole.</span><span class="sxs-lookup"><span data-stu-id="73d99-114">Note that a collection initializer is a series of comma-separated object initializers.</span></span>  
  
 <span data-ttu-id="73d99-115">[!code-cs[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="73d99-115">[!code-cs[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="73d99-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="73d99-116">Compiling the Code</span></span>  
 <span data-ttu-id="73d99-117">Per eseguire questo codice, copiare e incollare la classe in un progetto di applicazione console di Visual C# creato in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73d99-117">To run this code, copy and paste the class into a Visual C# console application project that has been created in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="73d99-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73d99-118">See Also</span></span>  
 <span data-ttu-id="73d99-119">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="73d99-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="73d99-120">Inizializzatori di oggetto e di raccolta</span><span class="sxs-lookup"><span data-stu-id="73d99-120">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

