---
title: Come implementare in modo esplicito i membri di due C# interfacce-Guida alla programmazione
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: 720e265cedcf9ad8be00f5e013365129f38749af
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635249"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="14900-102">Come implementare in modo esplicito i membri di dueC# interfacce (Guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="14900-102">How to explicitly implement members of two interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="14900-103">L'implementazione di [interfaccia](../../language-reference/keywords/interface.md) esplicita consente inoltre al programmatore di implementare due interfacce con gli stessi nomi di membro e assegnare a ogni membro dell'interfaccia un'implementazione separata.</span><span class="sxs-lookup"><span data-stu-id="14900-103">Explicit [interface](../../language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="14900-104">Questo esempio mostra le dimensioni di una casella sia in unità metriche che anglosassoni.</span><span class="sxs-lookup"><span data-stu-id="14900-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="14900-105">La [classe](../../language-reference/keywords/class.md) Box implementa due interfacce, IEnglishDimensions e IMetricDimensions, che rappresentano i diversi sistemi di misura.</span><span class="sxs-lookup"><span data-stu-id="14900-105">The Box [class](../../language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="14900-106">Entrambe le interfacce hanno nomi di membri identici, Length e Width.</span><span class="sxs-lookup"><span data-stu-id="14900-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14900-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="14900-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a><span data-ttu-id="14900-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="14900-108">Robust Programming</span></span>  
 <span data-ttu-id="14900-109">Se si vogliono impostare come predefinite le misure in unità anglosassoni, implementare i metodi Length e Width normalmente e implementare in modo esplicito i metodi Length e Width dall'interfaccia IMetricDimensions:</span><span class="sxs-lookup"><span data-stu-id="14900-109">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 <span data-ttu-id="14900-110">In questo caso, è possibile accedere alle unità anglosassoni dall'istanza della classe e alle unità metriche dall'istanza dell'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="14900-110">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="14900-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14900-111">See also</span></span>

- [<span data-ttu-id="14900-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="14900-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="14900-113">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="14900-113">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="14900-114">Interfacce</span><span class="sxs-lookup"><span data-stu-id="14900-114">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="14900-115">Come implementare in modo esplicito i membri di interfaccia</span><span class="sxs-lookup"><span data-stu-id="14900-115">How to explicitly implement interface members</span></span>](./how-to-explicitly-implement-interface-members.md)
