---
title: <type1>'<typename>' deve implementare '<membername>' per l'interfaccia '<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: a824b66eaad964049ced5cae5eb2cc370d00ba7f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696886"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="d9c4b-102">\<type1 >' \<typename >' deve implementare ' \<membername >' per l'interfaccia ' \<interfacename >'</span><span class="sxs-lookup"><span data-stu-id="d9c4b-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="d9c4b-103">' \<typename >' deve implementare ' \<membername >' per l'interfaccia ' \<interfacename >'.</span><span class="sxs-lookup"><span data-stu-id="d9c4b-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="d9c4b-104">La proprietà di implementazione deve avere identificatori ' ReadOnly '/' WriteOnly ' corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="d9c4b-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="d9c4b-105">Una classe o una struttura attestazioni per implementare un'interfaccia ma non implementa una routine, una proprietà o un evento definito dall'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d9c4b-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="d9c4b-106">È necessario implementare tutti i membri dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d9c4b-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="d9c4b-107">**ID errore:** BC30154</span><span class="sxs-lookup"><span data-stu-id="d9c4b-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d9c4b-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d9c4b-108">To correct this error</span></span>  
  
1. <span data-ttu-id="d9c4b-109">Dichiarare un membro con lo stesso nome e la stessa firma definiti nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d9c4b-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="d9c4b-110">Assicurarsi di includere almeno l'istruzione `End Function`, `End Sub` o `End Property`.</span><span class="sxs-lookup"><span data-stu-id="d9c4b-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2. <span data-ttu-id="d9c4b-111">Aggiungere una clausola `Implements` alla fine dell'istruzione `Function`, `Sub`, `Property` o `Event`.</span><span class="sxs-lookup"><span data-stu-id="d9c4b-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="d9c4b-112">Esempio:</span><span class="sxs-lookup"><span data-stu-id="d9c4b-112">For example:</span></span>  
  
    ```vb  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. <span data-ttu-id="d9c4b-113">Quando si implementa una proprietà, assicurarsi che `ReadOnly` o `WriteOnly` venga usato nello stesso modo in cui si trova nella definizione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d9c4b-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4. <span data-ttu-id="d9c4b-114">Quando si implementa una proprietà, dichiarare le procedure `Get` e `Set`, a seconda delle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d9c4b-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9c4b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9c4b-115">See also</span></span>

- [<span data-ttu-id="d9c4b-116">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="d9c4b-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="d9c4b-117">Interfacce</span><span class="sxs-lookup"><span data-stu-id="d9c4b-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
