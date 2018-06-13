---
title: Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: f6355cf7fc2e43651c1112d048220a8179968c76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646326"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="5ba43-102">Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5ba43-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="5ba43-103">In questo argomento vengono elencati i problemi che si verificano con i gestori eventi nei componenti ereditati.</span><span class="sxs-lookup"><span data-stu-id="5ba43-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="5ba43-104">Procedure</span><span class="sxs-lookup"><span data-stu-id="5ba43-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="5ba43-105">Il codice nel gestore eventi eseguito due volte per ogni chiamata</span><span class="sxs-lookup"><span data-stu-id="5ba43-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="5ba43-106">Un gestore eventi ereditato non deve includere un [gestisce](../../../../visual-basic/language-reference/statements/handles-clause.md) clausola.</span><span class="sxs-lookup"><span data-stu-id="5ba43-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="5ba43-107">Il metodo nella classe base è già associato all'evento e verrà generato di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="5ba43-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="5ba43-108">Rimuovere il `Handles` clausola dal metodo ereditato.</span><span class="sxs-lookup"><span data-stu-id="5ba43-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   <span data-ttu-id="5ba43-109">Se il metodo ereditato non ha un `Handles` (parola chiave), verificare che il codice non contenga un'ulteriore [istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) o qualsiasi altro metodo che gestisce l'evento stesso.</span><span class="sxs-lookup"><span data-stu-id="5ba43-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ba43-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ba43-110">See Also</span></span>  
 [<span data-ttu-id="5ba43-111">Eventi</span><span class="sxs-lookup"><span data-stu-id="5ba43-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
