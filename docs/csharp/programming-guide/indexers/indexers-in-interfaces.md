---
title: Indicizzatori nelle interfacce (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: 120b6e72a6ab906437c593d6eb33024d1df8f52b
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207965"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="db42b-102">Indicizzatori nelle interfacce (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="db42b-102">Indexers in Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="db42b-103">Gli indicizzatori possono essere dichiarati su una [interfaccia](../../../csharp/language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="db42b-103">Indexers can be declared on an [interface](../../../csharp/language-reference/keywords/interface.md).</span></span> <span data-ttu-id="db42b-104">Le funzioni di accesso degli indicizzatori di interfaccia differiscono dalle funzioni di accesso degli indicizzatori di [classe](../../../csharp/language-reference/keywords/class.md) per gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="db42b-104">Accessors of interface indexers differ from the accessors of [class](../../../csharp/language-reference/keywords/class.md) indexers in the following ways:</span></span>  
  
-   <span data-ttu-id="db42b-105">Le funzioni di accesso di interfaccia non usano modificatori.</span><span class="sxs-lookup"><span data-stu-id="db42b-105">Interface accessors do not use modifiers.</span></span>  
  
-   <span data-ttu-id="db42b-106">Una funzione di accesso di interfaccia non include un corpo.</span><span class="sxs-lookup"><span data-stu-id="db42b-106">An interface accessor does not have a body.</span></span>  
  
 <span data-ttu-id="db42b-107">Lo scopo della funzione di accesso, pertanto, è quello di indicare se l'indicizzatore è in lettura-scrittura, in sola lettura o in sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="db42b-107">Thus, the purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span>  
  
 <span data-ttu-id="db42b-108">Nell'esempio seguente viene illustrata la funzione di accesso di un indicizzatore di interfaccia:</span><span class="sxs-lookup"><span data-stu-id="db42b-108">The following is an example of an interface indexer accessor:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]  
  
 <span data-ttu-id="db42b-109">È necessario che la firma di un indicizzatore sia diversa dalle firme di tutti gli altri indicizzatori dichiarati nella stessa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="db42b-109">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db42b-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="db42b-110">Example</span></span>  
 <span data-ttu-id="db42b-111">Nell'esempio seguente viene illustrato come implementare gli indicizzatori di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="db42b-111">The following example shows how to implement interface indexers.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]  
  
 <span data-ttu-id="db42b-112">Nell'esempio precedente era possibile adottare l'implementazione esplicita del membro dell'interfaccia usando il nome completo del membro dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="db42b-112">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="db42b-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="db42b-113">For example:</span></span>  
  
```  
string ISomeInterface.this[int index]   
{   
}   
```  
  
 <span data-ttu-id="db42b-114">Il nome completo, tuttavia, è necessario soltanto per evitare l'ambiguità quando la classe implementa più di un'interfaccia con la stessa firma di indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="db42b-114">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="db42b-115">Se una classe `Employee` implementa, ad esempio, due interfacce, `ICitizen` e `IEmployee`, ed entrambe le interfacce hanno la stessa firma di indicizzatore, sarà necessaria l'implementazione esplicita del membro dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="db42b-115">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="db42b-116">In altre parole, la dichiarazione di indicizzatore seguente:</span><span class="sxs-lookup"><span data-stu-id="db42b-116">That is, the following indexer declaration:</span></span>  
  
```  
string IEmployee.this[int index]   
{   
}   
```  
  
 <span data-ttu-id="db42b-117">implementa l'indicizzatore nell'interfaccia `IEmployee`, mentre la dichiarazione seguente:</span><span class="sxs-lookup"><span data-stu-id="db42b-117">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>  
  
```  
string ICitizen.this[int index]
{   
}   
```  
  
 <span data-ttu-id="db42b-118">implementa l'indicizzatore nell'interfaccia `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="db42b-118">implements the indexer on the `ICitizen` interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db42b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db42b-119">See Also</span></span>  
 [<span data-ttu-id="db42b-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="db42b-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="db42b-121">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="db42b-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
 [<span data-ttu-id="db42b-122">Proprietà</span><span class="sxs-lookup"><span data-stu-id="db42b-122">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [<span data-ttu-id="db42b-123">Interfacce</span><span class="sxs-lookup"><span data-stu-id="db42b-123">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
