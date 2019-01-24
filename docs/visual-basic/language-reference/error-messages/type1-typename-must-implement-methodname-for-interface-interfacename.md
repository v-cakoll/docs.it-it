---
title: "&lt;type1&gt;&#39;&lt;typename&gt; &#39; devono implementare &#39; &lt;methodname&gt; &#39; per l'interfaccia &#39; &lt;interfacename&gt;&#39;"
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: ff9ffd50f7f21814d5e4c23fd8df50b12bf746f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642441"
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a><span data-ttu-id="25fb6-102">&lt;type1&gt;&#39;&lt;typename&gt; &#39; devono implementare &#39; &lt;methodname&gt; &#39; per l'interfaccia &#39; &lt;interfacename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="25fb6-102">&lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;methodname&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39;</span></span>
<span data-ttu-id="25fb6-103">Una classe o struttura dichiara di implementare un'interfaccia, ma non implementa una routine definita dall'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="25fb6-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="25fb6-104">Ogni membro dell'interfaccia deve essere implementata.</span><span class="sxs-lookup"><span data-stu-id="25fb6-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="25fb6-105">**ID errore:** BC30149</span><span class="sxs-lookup"><span data-stu-id="25fb6-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="25fb6-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="25fb6-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="25fb6-107">Dichiara una routine con lo stesso nome e firma, come definito nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="25fb6-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="25fb6-108">Assicurarsi di includere almeno le `End Function` o `End Sub` istruzione.</span><span class="sxs-lookup"><span data-stu-id="25fb6-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="25fb6-109">Aggiungere un `Implements` alla fine della clausola il `Function` o `Sub` istruzione.</span><span class="sxs-lookup"><span data-stu-id="25fb6-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="25fb6-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="25fb6-110">For example:</span></span>  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="25fb6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25fb6-111">See also</span></span>
- [<span data-ttu-id="25fb6-112">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="25fb6-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="25fb6-113">Interfacce</span><span class="sxs-lookup"><span data-stu-id="25fb6-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
