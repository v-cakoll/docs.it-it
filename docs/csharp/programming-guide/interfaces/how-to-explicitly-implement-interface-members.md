---
title: Come implementare in modo esplicito i membri C# di interfaccia-Guida alla programmazione
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: d006db2a7501a3273f5cd11e82bc589b21e1ce9f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712091"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="cd290-102">Come implementare in modo esplicito i membriC# di interfaccia (Guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="cd290-102">How to explicitly implement interface members (C# Programming Guide)</span></span>
<span data-ttu-id="cd290-103">Questo esempio dichiara un'[interfaccia](../../language-reference/keywords/interface.md), `IDimensions`, e una classe, `Box`, che implementa in modo esplicito i membri dell'interfaccia `getLength` e `getWidth`.</span><span class="sxs-lookup"><span data-stu-id="cd290-103">This example declares an [interface](../../language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `getLength` and `getWidth`.</span></span> <span data-ttu-id="cd290-104">L'accesso ai membri avviene tramite l'istanza di interfaccia `dimensions`.</span><span class="sxs-lookup"><span data-stu-id="cd290-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd290-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="cd290-105">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="cd290-106">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="cd290-106">Robust Programming</span></span>  
  
- <span data-ttu-id="cd290-107">Si noti che le righe seguenti, nel metodo `Main`, sono impostate come commento perché produrrebbero errori di compilazione.</span><span class="sxs-lookup"><span data-stu-id="cd290-107">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="cd290-108">Non è possibile accedere a un membro di interfaccia implementato in modo esplicito da un'istanza di una [classe](../../language-reference/keywords/class.md):</span><span class="sxs-lookup"><span data-stu-id="cd290-108">An interface member that is explicitly implemented cannot be accessed from a [class](../../language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- <span data-ttu-id="cd290-109">Si noti anche che le righe seguenti, nel metodo `Main`, stampano le dimensioni di una casella, perché i metodi vengono chiamati da un'istanza dell'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="cd290-109">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a><span data-ttu-id="cd290-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd290-110">See also</span></span>

- [<span data-ttu-id="cd290-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="cd290-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cd290-112">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="cd290-112">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="cd290-113">Interfacce</span><span class="sxs-lookup"><span data-stu-id="cd290-113">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="cd290-114">Come implementare in modo esplicito i membri di due interfacce</span><span class="sxs-lookup"><span data-stu-id="cd290-114">How to explicitly implement members of two interfaces</span></span>](./how-to-explicitly-implement-members-of-two-interfaces.md)
