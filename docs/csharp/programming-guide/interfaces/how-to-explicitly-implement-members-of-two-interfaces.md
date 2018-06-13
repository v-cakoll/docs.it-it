---
title: 'Procedura: implementare in modo esplicito i membri di due interfacce (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: c73089fdbf1350c1aff68ac3e8e78be00e21b931
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339040"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="d53eb-102">Procedura: implementare in modo esplicito i membri di due interfacce (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d53eb-102">How to: Explicitly Implement Members of Two Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="d53eb-103">L'implementazione di [interfaccia](../../../csharp/language-reference/keywords/interface.md) esplicita consente inoltre al programmatore di implementare due interfacce con gli stessi nomi di membro e assegnare a ogni membro dell'interfaccia un'implementazione separata.</span><span class="sxs-lookup"><span data-stu-id="d53eb-103">Explicit [interface](../../../csharp/language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="d53eb-104">Questo esempio mostra le dimensioni di una casella sia in unità metriche che anglosassoni.</span><span class="sxs-lookup"><span data-stu-id="d53eb-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="d53eb-105">La [classe](../../../csharp/language-reference/keywords/class.md) Box implementa due interfacce, IEnglishDimensions e IMetricDimensions, che rappresentano i diversi sistemi di misura.</span><span class="sxs-lookup"><span data-stu-id="d53eb-105">The Box [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="d53eb-106">Entrambe le interfacce hanno nomi di membri identici, Length e Width.</span><span class="sxs-lookup"><span data-stu-id="d53eb-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d53eb-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="d53eb-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="d53eb-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="d53eb-108">Robust Programming</span></span>  
 <span data-ttu-id="d53eb-109">Se si vogliono impostare come predefinite le misure in unità anglosassoni, implementare i metodi Length e Width normalmente e implementare in modo esplicito i metodi Length e Width dall'interfaccia IMetricDimensions:</span><span class="sxs-lookup"><span data-stu-id="d53eb-109">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_2.cs)]  
  
 <span data-ttu-id="d53eb-110">In questo caso, è possibile accedere alle unità anglosassoni dall'istanza della classe e alle unità metriche dall'istanza dell'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="d53eb-110">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d53eb-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d53eb-111">See Also</span></span>  
 [<span data-ttu-id="d53eb-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d53eb-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d53eb-113">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="d53eb-113">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="d53eb-114">Interfacce</span><span class="sxs-lookup"><span data-stu-id="d53eb-114">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
 [<span data-ttu-id="d53eb-115">Procedura: Implementare in modo esplicito i membri di interfaccia</span><span class="sxs-lookup"><span data-stu-id="d53eb-115">How to: Explicitly Implement Interface Members</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)
