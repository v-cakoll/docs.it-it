---
title: <type1>'<typename>' deve implementare '<methodname>' per l'interfaccia '<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: c387b0225375f4675042bef593b23a084305b4fd
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591587"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="7b9d7-102">\<type1 >' \<typename >' deve implementare ' \<methodname >' per l'interfaccia ' \<interfacename >'</span><span class="sxs-lookup"><span data-stu-id="7b9d7-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="7b9d7-103">Una classe o una struttura attestazioni per implementare un'interfaccia ma non implementa una routine definita dall'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7b9d7-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="7b9d7-104">È necessario implementare tutti i membri dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7b9d7-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="7b9d7-105">**ID errore:** BC30149</span><span class="sxs-lookup"><span data-stu-id="7b9d7-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7b9d7-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7b9d7-106">To correct this error</span></span>  
  
1. <span data-ttu-id="7b9d7-107">Dichiarare una routine con lo stesso nome e la stessa firma definiti nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7b9d7-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="7b9d7-108">Assicurarsi di includere almeno l'istruzione `End Function` o `End Sub`.</span><span class="sxs-lookup"><span data-stu-id="7b9d7-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="7b9d7-109">Aggiungere una clausola `Implements` alla fine dell'istruzione `Function` o `Sub`.</span><span class="sxs-lookup"><span data-stu-id="7b9d7-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="7b9d7-110">Esempio:</span><span class="sxs-lookup"><span data-stu-id="7b9d7-110">For example:</span></span>  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7b9d7-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b9d7-111">See also</span></span>

- [<span data-ttu-id="7b9d7-112">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="7b9d7-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="7b9d7-113">Interfacce</span><span class="sxs-lookup"><span data-stu-id="7b9d7-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
