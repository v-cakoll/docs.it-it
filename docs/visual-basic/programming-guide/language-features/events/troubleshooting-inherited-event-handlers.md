---
title: Risoluzione dei problemi relativi ai gestori eventi ereditati
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: fd2ef1c25233cc1eaad6bcde68923688393b471d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345099"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="28eb7-102">Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="28eb7-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="28eb7-103">In questo argomento vengono elencati i problemi comuni che si verificano con i gestori eventi nei componenti ereditati.</span><span class="sxs-lookup"><span data-stu-id="28eb7-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="28eb7-104">Procedure</span><span class="sxs-lookup"><span data-stu-id="28eb7-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="28eb7-105">Il codice nel gestore eventi viene eseguito due volte per ogni chiamata</span><span class="sxs-lookup"><span data-stu-id="28eb7-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
- <span data-ttu-id="28eb7-106">Un gestore eventi ereditato non deve includere una clausola [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="28eb7-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="28eb7-107">Il metodo nella classe base è già associato all'evento e verrà attivato di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="28eb7-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="28eb7-108">Rimuovere la clausola `Handles` dal metodo ereditato.</span><span class="sxs-lookup"><span data-stu-id="28eb7-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
- <span data-ttu-id="28eb7-109">Se il metodo ereditato non dispone di una parola chiave `Handles`, verificare che il codice non contenga un' [istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) aggiuntiva o altri metodi che gestiscono lo stesso evento.</span><span class="sxs-lookup"><span data-stu-id="28eb7-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28eb7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28eb7-110">See also</span></span>

- [<span data-ttu-id="28eb7-111">Eventi</span><span class="sxs-lookup"><span data-stu-id="28eb7-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
