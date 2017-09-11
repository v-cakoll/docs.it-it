---
title: Indicizzatori nelle interfacce (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
caps.latest.revision: 18
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
ms.openlocfilehash: 2715602dadea40324f613bb07b5dd332ed18c25c
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="a8907-102">Indicizzatori nelle interfacce (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="a8907-102">Indexers in Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="a8907-103">Gli indicizzatori possono essere dichiarati su una [interfaccia](../../../csharp/language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="a8907-103">Indexers can be declared on an [interface](../../../csharp/language-reference/keywords/interface.md).</span></span> <span data-ttu-id="a8907-104">Le funzioni di accesso degli indicizzatori di interfaccia differiscono dalle funzioni di accesso degli indicizzatori di [classe](../../../csharp/language-reference/keywords/class.md) per gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8907-104">Accessors of interface indexers differ from the accessors of [class](../../../csharp/language-reference/keywords/class.md) indexers in the following ways:</span></span>  
  
-   <span data-ttu-id="a8907-105">Le funzioni di accesso di interfaccia non usano modificatori.</span><span class="sxs-lookup"><span data-stu-id="a8907-105">Interface accessors do not use modifiers.</span></span>  
  
-   <span data-ttu-id="a8907-106">Una funzione di accesso di interfaccia non include un corpo.</span><span class="sxs-lookup"><span data-stu-id="a8907-106">An interface accessor does not have a body.</span></span>  
  
 <span data-ttu-id="a8907-107">Lo scopo della funzione di accesso, pertanto, è quello di indicare se l'indicizzatore è in lettura-scrittura, in sola lettura o in sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="a8907-107">Thus, the purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span>  
  
 <span data-ttu-id="a8907-108">Nell'esempio seguente viene illustrata la funzione di accesso di un indicizzatore di interfaccia:</span><span class="sxs-lookup"><span data-stu-id="a8907-108">The following is an example of an interface indexer accessor:</span></span>  
  
 <span data-ttu-id="a8907-109">[!code-cs[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8907-109">[!code-cs[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]</span></span>  
  
 <span data-ttu-id="a8907-110">È necessario che la firma di un indicizzatore sia diversa dalle firme di tutti gli altri indicizzatori dichiarati nella stessa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a8907-110">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8907-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="a8907-111">Example</span></span>  
 <span data-ttu-id="a8907-112">Nell'esempio seguente viene illustrato come implementare gli indicizzatori di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a8907-112">The following example shows how to implement interface indexers.</span></span>  
  
 <span data-ttu-id="a8907-113">[!code-cs[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8907-113">[!code-cs[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]</span></span>  
  
 <span data-ttu-id="a8907-114">Nell'esempio precedente era possibile adottare l'implementazione esplicita del membro dell'interfaccia usando il nome completo del membro dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a8907-114">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="a8907-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a8907-115">For example:</span></span>  
  
```  
public string ISomeInterface.this   
{   
}   
```  
  
 <span data-ttu-id="a8907-116">Il nome completo, tuttavia, è necessario soltanto per evitare l'ambiguità quando la classe implementa più di un'interfaccia con la stessa firma di indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="a8907-116">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="a8907-117">Se una classe `Employee` implementa, ad esempio, due interfacce, `ICitizen` e `IEmployee`, ed entrambe le interfacce hanno la stessa firma di indicizzatore, sarà necessaria l'implementazione esplicita del membro dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a8907-117">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="a8907-118">In altre parole, la dichiarazione di indicizzatore seguente:</span><span class="sxs-lookup"><span data-stu-id="a8907-118">That is, the following indexer declaration:</span></span>  
  
```  
public string IEmployee.this   
{   
}   
```  
  
 <span data-ttu-id="a8907-119">implementa l'indicizzatore nell'interfaccia `IEmployee`, mentre la dichiarazione seguente:</span><span class="sxs-lookup"><span data-stu-id="a8907-119">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>  
  
```  
public string ICitizen.this   
{   
}   
```  
  
 <span data-ttu-id="a8907-120">implementa l'indicizzatore nell'interfaccia `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="a8907-120">implements the indexer on the `ICitizen` interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8907-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8907-121">See Also</span></span>  
 <span data-ttu-id="a8907-122">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a8907-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a8907-123">[Indicizzatori](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="a8907-123">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="a8907-124">[Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="a8907-124">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 [<span data-ttu-id="a8907-125">Interfacce</span><span class="sxs-lookup"><span data-stu-id="a8907-125">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

