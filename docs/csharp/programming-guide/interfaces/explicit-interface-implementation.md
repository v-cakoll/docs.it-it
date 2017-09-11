---
title: Implementazione esplicita dell'interfaccia (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6baf985e8031e1e859d20570168222ca8f368eff
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="1765e-102">Implementazione esplicita dell'interfaccia (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="1765e-102">Explicit Interface Implementation (C# Programming Guide)</span></span>
<span data-ttu-id="1765e-103">Se [class](../../../csharp/language-reference/keywords/class.md) implementa due interfacce che contengono un membro con la stessa firma e quest'ultimo viene implementato nella classe, entrambe le interfacce useranno il membro come propria implementazione.</span><span class="sxs-lookup"><span data-stu-id="1765e-103">If a [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="1765e-104">Nell'esempio seguente tutte le chiamate a `Paint` richiamano lo stesso metodo.</span><span class="sxs-lookup"><span data-stu-id="1765e-104">In the following example, all the calls to `Paint` invoke the same method.</span></span>  
  
 <span data-ttu-id="1765e-105">[!code-cs[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1765e-105">[!code-cs[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]</span></span>  
  
 <span data-ttu-id="1765e-106">Se tuttavia i due membri di [interface](../../../csharp/language-reference/keywords/interface.md) non eseguono la stessa funzione, l'implementazione di una o di entrambe le interfacce potrebbe non risultare corretta.</span><span class="sxs-lookup"><span data-stu-id="1765e-106">If the two [interface](../../../csharp/language-reference/keywords/interface.md) members do not perform the same function, however, this can lead to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="1765e-107">È possibile implementare un membro di interfaccia in modo esplicito, ovvero creando un membro di classe che viene chiamato solo tramite l'interfaccia e che è specifico di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1765e-107">It is possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="1765e-108">Per questa operazione è necessario assegnare al membro di classe il nome dell'interfaccia seguito da un punto.</span><span class="sxs-lookup"><span data-stu-id="1765e-108">This is accomplished by naming the class member with the name of the interface and a period.</span></span> <span data-ttu-id="1765e-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1765e-109">For example:</span></span>  
  
 <span data-ttu-id="1765e-110">[!code-cs[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1765e-110">[!code-cs[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]</span></span>  
  
 <span data-ttu-id="1765e-111">Il membro di classe `IControl.Paint` è disponibile solo tramite l'interfaccia`IControl` e `ISurface.Paint` è disponibile solo tramite `ISurface`.</span><span class="sxs-lookup"><span data-stu-id="1765e-111">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="1765e-112">Entrambe le implementazioni del metodo sono separate e nessuna delle due è disponibile direttamente nella classe.</span><span class="sxs-lookup"><span data-stu-id="1765e-112">Both method implementations are separate, and neither is available directly on the class.</span></span> <span data-ttu-id="1765e-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1765e-113">For example:</span></span>  
  
 <span data-ttu-id="1765e-114">[!code-cs[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="1765e-114">[!code-cs[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]</span></span>  
  
 <span data-ttu-id="1765e-115">L'implementazione esplicita viene usata anche per risolvere i casi in cui due interfacce dichiarano ognuna membri diversi con lo stesso nome, ad esempio una proprietà e un metodo:</span><span class="sxs-lookup"><span data-stu-id="1765e-115">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method:</span></span>  
  
 <span data-ttu-id="1765e-116">[!code-cs[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="1765e-116">[!code-cs[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]</span></span>  
  
 <span data-ttu-id="1765e-117">Per implementare entrambe le interfacce, una classe deve usare l'implementazione esplicita per la proprietà P o il metodo P oppure per entrambi, in modo da evitare un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="1765e-117">To implement both interfaces, a class has to use explicit implementation either for the property P, or the method P, or both, to avoid a compiler error.</span></span> <span data-ttu-id="1765e-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1765e-118">For example:</span></span>  
  
 <span data-ttu-id="1765e-119">[!code-cs[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="1765e-119">[!code-cs[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1765e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1765e-120">See Also</span></span>  
 <span data-ttu-id="1765e-121">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1765e-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1765e-122">[Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="1765e-122">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="1765e-123">[Interfacce](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="1765e-123">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 [<span data-ttu-id="1765e-124">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="1765e-124">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)

