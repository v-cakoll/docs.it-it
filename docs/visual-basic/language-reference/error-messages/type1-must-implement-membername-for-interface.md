---
title: '&lt;type1&gt;&#39;&lt; TypeName&gt;&#39; deve implementare &#39;&lt; MemberName&gt;&#39; per l''interfaccia &#39;&lt; InterfaceName&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords: BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 05e0229d0259c519d4db265c017a5040b425c79a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmembernamegt39-for-interface-39ltinterfacenamegt39"></a><span data-ttu-id="fcc72-102">&lt;type1&gt;&#39;&lt; TypeName&gt;&#39; deve implementare &#39;&lt; MemberName&gt;&#39; per l'interfaccia &#39;&lt; InterfaceName&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="fcc72-102">&lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;membername&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39;</span></span>
<span data-ttu-id="fcc72-103">'\<nomeTipo >' deve implementare '\<nomeMembro >' per l'interfaccia '\<nomeinterfaccia >'.</span><span class="sxs-lookup"><span data-stu-id="fcc72-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="fcc72-104">Implementazione della proprietà deve contenere corrispondenti 'ReadOnly' o 'WriteOnly' identificatori.</span><span class="sxs-lookup"><span data-stu-id="fcc72-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="fcc72-105">Una classe o struttura dichiara di implementare un'interfaccia, ma non implementa una routine, proprietà o evento definito dall'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="fcc72-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="fcc72-106">Ogni membro dell'interfaccia deve essere implementata.</span><span class="sxs-lookup"><span data-stu-id="fcc72-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="fcc72-107">**ID errore:** BC30154</span><span class="sxs-lookup"><span data-stu-id="fcc72-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fcc72-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="fcc72-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="fcc72-109">Dichiarare un membro con lo stesso nome e firma, come definito nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="fcc72-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="fcc72-110">Assicurarsi di includere almeno le `End Function`, `End Sub`, o `End Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="fcc72-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2.  <span data-ttu-id="fcc72-111">Aggiungere un `Implements` clausola alla fine del `Function`, `Sub`, `Property`, o `Event` istruzione.</span><span class="sxs-lookup"><span data-stu-id="fcc72-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="fcc72-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fcc72-112">For example:</span></span>  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  <span data-ttu-id="fcc72-113">Quando si implementa una proprietà, assicurarsi che `ReadOnly` o `WriteOnly` viene utilizzato in modo analogo la definizione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="fcc72-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4.  <span data-ttu-id="fcc72-114">Quando si implementa una proprietà, dichiarare `Get` e `Set` procedure, come appropriato.</span><span class="sxs-lookup"><span data-stu-id="fcc72-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc72-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcc72-115">See Also</span></span>  
 [<span data-ttu-id="fcc72-116">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="fcc72-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="fcc72-117">Interfacce</span><span class="sxs-lookup"><span data-stu-id="fcc72-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
