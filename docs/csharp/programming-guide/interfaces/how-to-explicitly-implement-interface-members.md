---
title: 'Procedura: implementare in modo esplicito i membri di interfaccia (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 5f7ae6bae46cdf6596b206abbdeeb94b5c21a13f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332186"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="f3f7c-102">Procedura: implementare in modo esplicito i membri di interfaccia (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="f3f7c-102">How to: Explicitly Implement Interface Members (C# Programming Guide)</span></span>
<span data-ttu-id="f3f7c-103">Questo esempio dichiara un'[interfaccia](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, e una classe, `Box`, che implementa in modo esplicito i membri dell'interfaccia `getLength` e `getWidth`.</span><span class="sxs-lookup"><span data-stu-id="f3f7c-103">This example declares an [interface](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `getLength` and `getWidth`.</span></span> <span data-ttu-id="f3f7c-104">L'accesso ai membri avviene tramite l'istanza di interfaccia `dimensions`.</span><span class="sxs-lookup"><span data-stu-id="f3f7c-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3f7c-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="f3f7c-105">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="f3f7c-106">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="f3f7c-106">Robust Programming</span></span>  
  
-   <span data-ttu-id="f3f7c-107">Si noti che le righe seguenti, nel metodo `Main`, sono impostate come commento perché produrrebbero errori di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f3f7c-107">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="f3f7c-108">Non è possibile accedere a un membro di interfaccia implementato in modo esplicito da un'istanza di una [classe](../../../csharp/language-reference/keywords/class.md):</span><span class="sxs-lookup"><span data-stu-id="f3f7c-108">An interface member that is explicitly implemented cannot be accessed from a [class](../../../csharp/language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]  
  
-   <span data-ttu-id="f3f7c-109">Si noti anche che le righe seguenti, nel metodo `Main`, stampano le dimensioni di una casella, perché i metodi vengono chiamati da un'istanza dell'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="f3f7c-109">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f3f7c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3f7c-110">See Also</span></span>  
 [<span data-ttu-id="f3f7c-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f3f7c-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f3f7c-112">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="f3f7c-112">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="f3f7c-113">Interfacce</span><span class="sxs-lookup"><span data-stu-id="f3f7c-113">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
 [<span data-ttu-id="f3f7c-114">Procedura: Implementare in modo esplicito i membri di due interfacce</span><span class="sxs-lookup"><span data-stu-id="f3f7c-114">How to: Explicitly Implement Members of Two Interfaces</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)
