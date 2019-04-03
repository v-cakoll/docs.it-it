---
title: <type1>«<typename>'deve implementare'<membername>'per l'interfaccia'<interfacename>»
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 485680a2984a29037b2836fcba13cf1aa1e2e699
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822752"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="f5674-102">\<type1 >'\<nomeTipo >' deve implementare '\<nomeMembro >' per l'interfaccia '\<nomeinterfaccia >'</span><span class="sxs-lookup"><span data-stu-id="f5674-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="f5674-103">'\<nomeTipo >' deve implementare '\<nomeMembro >' per l'interfaccia '\<nomeinterfaccia >'.</span><span class="sxs-lookup"><span data-stu-id="f5674-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="f5674-104">Implementazione della proprietà deve contenere corrispondenti 'ReadOnly' o 'WriteOnly' identificatori.</span><span class="sxs-lookup"><span data-stu-id="f5674-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="f5674-105">Una classe o struttura dichiara di implementare un'interfaccia, ma non implementa una routine, proprietà o eventi definiti dall'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f5674-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="f5674-106">Ogni membro dell'interfaccia deve essere implementata.</span><span class="sxs-lookup"><span data-stu-id="f5674-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="f5674-107">**ID errore:** BC30154</span><span class="sxs-lookup"><span data-stu-id="f5674-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f5674-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f5674-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="f5674-109">Dichiarare un membro con lo stesso nome e firma, come definito nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f5674-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="f5674-110">Assicurarsi di includere almeno le `End Function`, `End Sub`, o `End Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f5674-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2.  <span data-ttu-id="f5674-111">Aggiungere un `Implements` alla fine della clausola il `Function`, `Sub`, `Property`, o `Event` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f5674-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="f5674-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f5674-112">For example:</span></span>  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  <span data-ttu-id="f5674-113">Quando si implementa una proprietà, assicurarsi che `ReadOnly` o `WriteOnly` viene usato in modo analogo la definizione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f5674-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4.  <span data-ttu-id="f5674-114">Quando si implementa una proprietà, dichiarare `Get` e `Set` procedure, come appropriato.</span><span class="sxs-lookup"><span data-stu-id="f5674-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5674-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5674-115">See also</span></span>

- [<span data-ttu-id="f5674-116">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="f5674-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="f5674-117">Interfacce</span><span class="sxs-lookup"><span data-stu-id="f5674-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
