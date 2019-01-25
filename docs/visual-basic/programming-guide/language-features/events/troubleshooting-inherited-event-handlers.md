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
ms.openlocfilehash: e7c56757d18a22a65b4ef8e81d2a05e5f4f4dffc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680198"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="d6a74-102">Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d6a74-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="d6a74-103">Questo argomento elenca i problemi comuni che si verificano con i gestori eventi nei componenti ereditati.</span><span class="sxs-lookup"><span data-stu-id="d6a74-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="d6a74-104">Procedure</span><span class="sxs-lookup"><span data-stu-id="d6a74-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="d6a74-105">Viene eseguito due volte per ogni chiamata di codice nel gestore eventi</span><span class="sxs-lookup"><span data-stu-id="d6a74-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="d6a74-106">Non deve includere un gestore eventi ereditato un [gestisce](../../../../visual-basic/language-reference/statements/handles-clause.md) clausola.</span><span class="sxs-lookup"><span data-stu-id="d6a74-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="d6a74-107">Il metodo nella classe di base è già associato all'evento e verrà generato di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="d6a74-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="d6a74-108">Rimuovere il `Handles` clausola dal metodo ereditato.</span><span class="sxs-lookup"><span data-stu-id="d6a74-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   <span data-ttu-id="d6a74-109">Se il metodo ereditato non ha un `Handles` parola chiave, verificare che il codice non contenga un ulteriore [istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) o qualsiasi altro metodo che gestisce l'evento stesso.</span><span class="sxs-lookup"><span data-stu-id="d6a74-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6a74-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6a74-110">See also</span></span>
- [<span data-ttu-id="d6a74-111">Eventi</span><span class="sxs-lookup"><span data-stu-id="d6a74-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
