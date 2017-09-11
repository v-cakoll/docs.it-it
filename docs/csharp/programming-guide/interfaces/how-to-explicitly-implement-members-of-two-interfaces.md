---
title: 'Procedura: implementare in modo esplicito i membri di due interfacce (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
caps.latest.revision: 15
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
ms.openlocfilehash: 1446233793e3fd61f09d7da99f4f68cb7b3eabb8
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="bb821-102">Procedura: implementare in modo esplicito i membri di due interfacce (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="bb821-102">How to: Explicitly Implement Members of Two Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="bb821-103">L'implementazione di [interfaccia](../../../csharp/language-reference/keywords/interface.md) esplicita consente inoltre al programmatore di implementare due interfacce con gli stessi nomi di membro e assegnare a ogni membro dell'interfaccia un'implementazione separata.</span><span class="sxs-lookup"><span data-stu-id="bb821-103">Explicit [interface](../../../csharp/language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="bb821-104">Questo esempio mostra le dimensioni di una casella sia in unità metriche che anglosassoni.</span><span class="sxs-lookup"><span data-stu-id="bb821-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="bb821-105">La [classe](../../../csharp/language-reference/keywords/class.md) Box implementa due interfacce, IEnglishDimensions e IMetricDimensions, che rappresentano i diversi sistemi di misura.</span><span class="sxs-lookup"><span data-stu-id="bb821-105">The Box [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="bb821-106">Entrambe le interfacce hanno nomi di membri identici, Length e Width.</span><span class="sxs-lookup"><span data-stu-id="bb821-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb821-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="bb821-107">Example</span></span>  
 <span data-ttu-id="bb821-108">[!code-cs[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb821-108">[!code-cs[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="bb821-109">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="bb821-109">Robust Programming</span></span>  
 <span data-ttu-id="bb821-110">Se si vogliono impostare come predefinite le misure in unità anglosassoni, implementare i metodi Length e Width normalmente e implementare in modo esplicito i metodi Length e Width dall'interfaccia IMetricDimensions:</span><span class="sxs-lookup"><span data-stu-id="bb821-110">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 <span data-ttu-id="bb821-111">[!code-cs[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb821-111">[!code-cs[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_2.cs)]</span></span>  
  
 <span data-ttu-id="bb821-112">In questo caso, è possibile accedere alle unità anglosassoni dall'istanza della classe e alle unità metriche dall'istanza dell'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="bb821-112">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 <span data-ttu-id="bb821-113">[!code-cs[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb821-113">[!code-cs[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb821-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb821-114">See Also</span></span>  
 <span data-ttu-id="bb821-115">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb821-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bb821-116">[Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb821-116">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="bb821-117">[Interfacce](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb821-117">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 [<span data-ttu-id="bb821-118">Procedura: Implementare in modo esplicito i membri di interfaccia</span><span class="sxs-lookup"><span data-stu-id="bb821-118">How to: Explicitly Implement Interface Members</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)

