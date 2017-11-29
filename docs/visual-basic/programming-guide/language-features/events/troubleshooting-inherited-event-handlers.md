---
title: Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e0e8f0b669566bbee6530931bfba9808fad0c085
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="baff3-102">Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="baff3-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="baff3-103">In questo argomento vengono elencati i problemi che si verificano con i gestori eventi nei componenti ereditati.</span><span class="sxs-lookup"><span data-stu-id="baff3-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="baff3-104">Procedure</span><span class="sxs-lookup"><span data-stu-id="baff3-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="baff3-105">Il codice nel gestore eventi eseguito due volte per ogni chiamata</span><span class="sxs-lookup"><span data-stu-id="baff3-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="baff3-106">Un gestore eventi ereditato non deve includere un [gestisce](../../../../visual-basic/language-reference/statements/handles-clause.md) clausola.</span><span class="sxs-lookup"><span data-stu-id="baff3-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="baff3-107">Il metodo nella classe base è già associato all'evento e verrà generato di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="baff3-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="baff3-108">Rimuovere il `Handles` clausola dal metodo ereditato.</span><span class="sxs-lookup"><span data-stu-id="baff3-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   <span data-ttu-id="baff3-109">Se il metodo ereditato non ha un `Handles` (parola chiave), verificare che il codice non contenga un'ulteriore [istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) o qualsiasi altro metodo che gestisce l'evento stesso.</span><span class="sxs-lookup"><span data-stu-id="baff3-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baff3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baff3-110">See Also</span></span>  
 [<span data-ttu-id="baff3-111">Eventi</span><span class="sxs-lookup"><span data-stu-id="baff3-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
