---
title: Risoluzione dei problemi di gestori eventi ereditati in Visual Basic | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- troubleshooting events
- inherited events
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f64395975821226d42664bbf78b04120d49a38bc
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="90660-102">Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="90660-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="90660-103">In questo argomento vengono elencati i problemi che si verificano con i gestori eventi nei componenti ereditati.</span><span class="sxs-lookup"><span data-stu-id="90660-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="90660-104">Procedure</span><span class="sxs-lookup"><span data-stu-id="90660-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="90660-105">Codice nel gestore eventi viene eseguita due volte per ogni chiamata</span><span class="sxs-lookup"><span data-stu-id="90660-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="90660-106">Un gestore eventi ereditato non deve includere un [gestisce](../../../../visual-basic/language-reference/statements/handles-clause.md) clausola.</span><span class="sxs-lookup"><span data-stu-id="90660-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="90660-107">Il metodo nella classe di base è già associato all'evento e verrà generato di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="90660-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="90660-108">Rimuovere il `Handles` clausola dal metodo ereditato.</span><span class="sxs-lookup"><span data-stu-id="90660-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     <span data-ttu-id="90660-109">[!code-vb[VbVbalrEvents n.&32;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="90660-109">[!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]</span></span>  
  
-   <span data-ttu-id="90660-110">Se il metodo ereditato non ha un `Handles` (parola chiave), verificare che il codice non è presente un ulteriore [AddHandler (istruzione)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) o qualsiasi altro metodo che gestisce l'evento stesso.</span><span class="sxs-lookup"><span data-stu-id="90660-110">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90660-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90660-111">See Also</span></span>  
 [<span data-ttu-id="90660-112">Eventi</span><span class="sxs-lookup"><span data-stu-id="90660-112">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
