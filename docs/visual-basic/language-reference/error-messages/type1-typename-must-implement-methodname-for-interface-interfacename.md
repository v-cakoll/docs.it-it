---
title: <type1>«<typename>'deve implementare'<methodname>'per l'interfaccia'<interfacename>»
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: b8bcb16798284a09608ba6942226ef07c6859d4f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824203"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="00019-102">\<type1 >'\<nomeTipo >' deve implementare '\<NomeMetodo >' per l'interfaccia '\<nomeinterfaccia >'</span><span class="sxs-lookup"><span data-stu-id="00019-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="00019-103">Una classe o struttura dichiara di implementare un'interfaccia, ma non implementa una routine definita dall'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="00019-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="00019-104">Ogni membro dell'interfaccia deve essere implementata.</span><span class="sxs-lookup"><span data-stu-id="00019-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="00019-105">**ID errore:** BC30149</span><span class="sxs-lookup"><span data-stu-id="00019-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="00019-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="00019-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="00019-107">Dichiara una routine con lo stesso nome e firma, come definito nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="00019-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="00019-108">Assicurarsi di includere almeno le `End Function` o `End Sub` istruzione.</span><span class="sxs-lookup"><span data-stu-id="00019-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="00019-109">Aggiungere un `Implements` alla fine della clausola il `Function` o `Sub` istruzione.</span><span class="sxs-lookup"><span data-stu-id="00019-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="00019-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="00019-110">For example:</span></span>  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="00019-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00019-111">See also</span></span>

- [<span data-ttu-id="00019-112">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="00019-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="00019-113">Interfacce</span><span class="sxs-lookup"><span data-stu-id="00019-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
