---
title: <type1>'<typename>' deve implementare '<methodname>' per l'interfaccia '<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: c5dd7c6889a3fb5344142ee9914f98e8922d748b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55264434"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="22af9-102">\<type1 >'\<nomeTipo >' deve implementare '\<NomeMetodo >' per l'interfaccia '\<nomeinterfaccia >'</span><span class="sxs-lookup"><span data-stu-id="22af9-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="22af9-103">Una classe o struttura dichiara di implementare un'interfaccia, ma non implementa una routine definita dall'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="22af9-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="22af9-104">Ogni membro dell'interfaccia deve essere implementata.</span><span class="sxs-lookup"><span data-stu-id="22af9-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="22af9-105">**ID errore:** BC30149</span><span class="sxs-lookup"><span data-stu-id="22af9-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="22af9-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="22af9-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="22af9-107">Dichiara una routine con lo stesso nome e firma, come definito nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="22af9-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="22af9-108">Assicurarsi di includere almeno le `End Function` o `End Sub` istruzione.</span><span class="sxs-lookup"><span data-stu-id="22af9-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="22af9-109">Aggiungere un `Implements` alla fine della clausola il `Function` o `Sub` istruzione.</span><span class="sxs-lookup"><span data-stu-id="22af9-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="22af9-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="22af9-110">For example:</span></span>  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="22af9-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22af9-111">See also</span></span>
- [<span data-ttu-id="22af9-112">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="22af9-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="22af9-113">Interfacce</span><span class="sxs-lookup"><span data-stu-id="22af9-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
