---
title: Indicizzatori nelle interfacce - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: 4ac51589ed1680f8484fde797c045d15beed3af9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712117"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="160de-102">Indicizzatori nelle interfacce (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="160de-102">Indexers in Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="160de-103">Gli indicizzatori possono essere dichiarati su una [interfaccia](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="160de-103">Indexers can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="160de-104">Le funzioni di accesso degli indicizzatori di interfaccia differiscono dalle funzioni di accesso degli indicizzatori di [classe](../../language-reference/keywords/class.md) per gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="160de-104">Accessors of interface indexers differ from the accessors of [class](../../language-reference/keywords/class.md) indexers in the following ways:</span></span>  
  
- <span data-ttu-id="160de-105">Le funzioni di accesso di interfaccia non usano modificatori.</span><span class="sxs-lookup"><span data-stu-id="160de-105">Interface accessors do not use modifiers.</span></span>  
  
- <span data-ttu-id="160de-106">Una funzione di accesso di interfaccia non include un corpo.</span><span class="sxs-lookup"><span data-stu-id="160de-106">An interface accessor does not have a body.</span></span>  
  
 <span data-ttu-id="160de-107">Lo scopo della funzione di accesso, pertanto, è quello di indicare se l'indicizzatore è in lettura-scrittura, in sola lettura o in sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="160de-107">Thus, the purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span>  
  
 <span data-ttu-id="160de-108">Nell'esempio seguente viene illustrata la funzione di accesso di un indicizzatore di interfaccia:</span><span class="sxs-lookup"><span data-stu-id="160de-108">The following is an example of an interface indexer accessor:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#3)]  
  
 <span data-ttu-id="160de-109">È necessario che la firma di un indicizzatore sia diversa dalle firme di tutti gli altri indicizzatori dichiarati nella stessa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="160de-109">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="160de-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="160de-110">Example</span></span>  
 <span data-ttu-id="160de-111">Nell'esempio seguente viene illustrato come implementare gli indicizzatori di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="160de-111">The following example shows how to implement interface indexers.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#4)]  
  
 <span data-ttu-id="160de-112">Nell'esempio precedente era possibile adottare l'implementazione esplicita del membro dell'interfaccia usando il nome completo del membro dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="160de-112">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="160de-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="160de-113">For example:</span></span>  
  
```csharp  
string ISomeInterface.this[int index]   
{   
}   
```  
  
 <span data-ttu-id="160de-114">Il nome completo, tuttavia, è necessario soltanto per evitare l'ambiguità quando la classe implementa più di un'interfaccia con la stessa firma di indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="160de-114">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="160de-115">Se una classe `Employee` implementa, ad esempio, due interfacce, `ICitizen` e `IEmployee`, ed entrambe le interfacce hanno la stessa firma di indicizzatore, sarà necessaria l'implementazione esplicita del membro dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="160de-115">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="160de-116">In altre parole, la dichiarazione di indicizzatore seguente:</span><span class="sxs-lookup"><span data-stu-id="160de-116">That is, the following indexer declaration:</span></span>  
  
```csharp  
string IEmployee.this[int index]   
{   
}   
```  
  
 <span data-ttu-id="160de-117">implementa l'indicizzatore nell'interfaccia `IEmployee`, mentre la dichiarazione seguente:</span><span class="sxs-lookup"><span data-stu-id="160de-117">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>  
  
```csharp  
string ICitizen.this[int index]
{   
}   
```  
  
 <span data-ttu-id="160de-118">implementa l'indicizzatore nell'interfaccia `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="160de-118">implements the indexer on the `ICitizen` interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="160de-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="160de-119">See also</span></span>

- [<span data-ttu-id="160de-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="160de-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="160de-121">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="160de-121">Indexers</span></span>](./index.md)
- [<span data-ttu-id="160de-122">Proprietà</span><span class="sxs-lookup"><span data-stu-id="160de-122">Properties</span></span>](../classes-and-structs/properties.md)
- [<span data-ttu-id="160de-123">Interfacce</span><span class="sxs-lookup"><span data-stu-id="160de-123">Interfaces</span></span>](../interfaces/index.md)
