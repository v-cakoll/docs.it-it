---
title: <type1>'<typename>' deve implementare '<membername>' per l'interfaccia '<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 4ffe18e11c388a8c69ef0592bde1b78f5b219680
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386854"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="ea8b3-102">\<type1>'\<typename>' deve implementare '\<membername>' per l'interfaccia '\<interfacename>'</span><span class="sxs-lookup"><span data-stu-id="ea8b3-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="ea8b3-103">' \<typename> ' deve implementare '' \<membername> per l'interfaccia ' \<interfacename> '.</span><span class="sxs-lookup"><span data-stu-id="ea8b3-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="ea8b3-104">La proprietà di implementazione deve avere identificatori ' ReadOnly '/' WriteOnly ' corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="ea8b3-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="ea8b3-105">Una classe o una struttura attestazioni per implementare un'interfaccia ma non implementa una routine, una proprietà o un evento definito dall'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ea8b3-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="ea8b3-106">È necessario implementare tutti i membri dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ea8b3-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="ea8b3-107">**ID errore:** BC30154</span><span class="sxs-lookup"><span data-stu-id="ea8b3-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ea8b3-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ea8b3-108">To correct this error</span></span>  
  
1. <span data-ttu-id="ea8b3-109">Dichiarare un membro con lo stesso nome e la stessa firma definiti nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ea8b3-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="ea8b3-110">Assicurarsi di includere almeno l' `End Function` `End Sub` istruzione, o `End Property` .</span><span class="sxs-lookup"><span data-stu-id="ea8b3-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2. <span data-ttu-id="ea8b3-111">Aggiungere una `Implements` clausola alla fine dell' `Function` `Sub` istruzione,, `Property` o `Event` .</span><span class="sxs-lookup"><span data-stu-id="ea8b3-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="ea8b3-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ea8b3-112">For example:</span></span>  
  
    ```vb  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. <span data-ttu-id="ea8b3-113">Quando si implementa una proprietà, assicurarsi che `ReadOnly` o `WriteOnly` venga usato nello stesso modo in cui si trova nella definizione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ea8b3-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4. <span data-ttu-id="ea8b3-114">Quando si implementa una proprietà, `Get` dichiarare `Set` le routine e, a seconda delle esigenze.</span><span class="sxs-lookup"><span data-stu-id="ea8b3-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8b3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea8b3-115">See also</span></span>

- [<span data-ttu-id="ea8b3-116">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="ea8b3-116">Implements Statement</span></span>](../statements/implements-statement.md)
- [<span data-ttu-id="ea8b3-117">Interfacce</span><span class="sxs-lookup"><span data-stu-id="ea8b3-117">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
