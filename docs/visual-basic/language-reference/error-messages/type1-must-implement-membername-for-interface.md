---
title: <type1>«<typename>'deve implementare'<membername>'per l'interfaccia'<interfacename>»
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 86b0d46e0e27b2fd8d1fccb37f4a3c45e95f5f63
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295328"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="80ddd-102">\<type1 >'\<nomeTipo >' deve implementare '\<nomeMembro >' per l'interfaccia '\<nomeinterfaccia >'</span><span class="sxs-lookup"><span data-stu-id="80ddd-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="80ddd-103">'\<nomeTipo >' deve implementare '\<nomeMembro >' per l'interfaccia '\<nomeinterfaccia >'.</span><span class="sxs-lookup"><span data-stu-id="80ddd-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="80ddd-104">Implementazione della proprietà deve contenere corrispondenti 'ReadOnly' o 'WriteOnly' identificatori.</span><span class="sxs-lookup"><span data-stu-id="80ddd-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="80ddd-105">Una classe o struttura dichiara di implementare un'interfaccia, ma non implementa una routine, proprietà o eventi definiti dall'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="80ddd-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="80ddd-106">Ogni membro dell'interfaccia deve essere implementata.</span><span class="sxs-lookup"><span data-stu-id="80ddd-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="80ddd-107">**ID errore:** BC30154</span><span class="sxs-lookup"><span data-stu-id="80ddd-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="80ddd-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="80ddd-108">To correct this error</span></span>  
  
1. <span data-ttu-id="80ddd-109">Dichiarare un membro con lo stesso nome e firma, come definito nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="80ddd-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="80ddd-110">Assicurarsi di includere almeno le `End Function`, `End Sub`, o `End Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="80ddd-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2. <span data-ttu-id="80ddd-111">Aggiungere un `Implements` alla fine della clausola il `Function`, `Sub`, `Property`, o `Event` istruzione.</span><span class="sxs-lookup"><span data-stu-id="80ddd-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="80ddd-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="80ddd-112">For example:</span></span>  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. <span data-ttu-id="80ddd-113">Quando si implementa una proprietà, assicurarsi che `ReadOnly` o `WriteOnly` viene usato in modo analogo la definizione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="80ddd-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4. <span data-ttu-id="80ddd-114">Quando si implementa una proprietà, dichiarare `Get` e `Set` procedure, come appropriato.</span><span class="sxs-lookup"><span data-stu-id="80ddd-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80ddd-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80ddd-115">See also</span></span>

- [<span data-ttu-id="80ddd-116">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="80ddd-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="80ddd-117">Interfacce</span><span class="sxs-lookup"><span data-stu-id="80ddd-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
