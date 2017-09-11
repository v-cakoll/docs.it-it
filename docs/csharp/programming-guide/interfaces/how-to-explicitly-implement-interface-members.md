---
title: 'Procedura: implementare in modo esplicito i membri di interfaccia (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
caps.latest.revision: 16
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
ms.openlocfilehash: 88b96c15f724ee5961c72917308138a045988225
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="470b6-102">Procedura: implementare in modo esplicito i membri di interfaccia (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="470b6-102">How to: Explicitly Implement Interface Members (C# Programming Guide)</span></span>
<span data-ttu-id="470b6-103">Questo esempio dichiara un'[interfaccia](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, e una classe, `Box`, che implementa in modo esplicito i membri dell'interfaccia `getLength` e `getWidth`.</span><span class="sxs-lookup"><span data-stu-id="470b6-103">This example declares an [interface](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `getLength` and `getWidth`.</span></span> <span data-ttu-id="470b6-104">L'accesso ai membri avviene tramite l'istanza di interfaccia `dimensions`.</span><span class="sxs-lookup"><span data-stu-id="470b6-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="470b6-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="470b6-105">Example</span></span>  
 <span data-ttu-id="470b6-106">[!code-cs[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="470b6-106">[!code-cs[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="470b6-107">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="470b6-107">Robust Programming</span></span>  
  
-   <span data-ttu-id="470b6-108">Si noti che le righe seguenti, nel metodo `Main`, sono impostate come commento perché produrrebbero errori di compilazione.</span><span class="sxs-lookup"><span data-stu-id="470b6-108">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="470b6-109">Non è possibile accedere a un membro di interfaccia implementato in modo esplicito da un'istanza di una [classe](../../../csharp/language-reference/keywords/class.md):</span><span class="sxs-lookup"><span data-stu-id="470b6-109">An interface member that is explicitly implemented cannot be accessed from a [class](../../../csharp/language-reference/keywords/class.md) instance:</span></span>  
  
     <span data-ttu-id="470b6-110">[!code-cs[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="470b6-110">[!code-cs[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]</span></span>  
  
-   <span data-ttu-id="470b6-111">Si noti anche che le righe seguenti, nel metodo `Main`, stampano le dimensioni di una casella, perché i metodi vengono chiamati da un'istanza dell'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="470b6-111">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     <span data-ttu-id="470b6-112">[!code-cs[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="470b6-112">[!code-cs[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="470b6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="470b6-113">See Also</span></span>  
 <span data-ttu-id="470b6-114">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="470b6-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="470b6-115">[Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="470b6-115">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="470b6-116">[Interfacce](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="470b6-116">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 [<span data-ttu-id="470b6-117">Procedura: Implementare in modo esplicito i membri di due interfacce</span><span class="sxs-lookup"><span data-stu-id="470b6-117">How to: Explicitly Implement Members of Two Interfaces</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)

