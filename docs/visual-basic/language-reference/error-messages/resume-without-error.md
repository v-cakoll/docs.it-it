---
title: Resume senza errore
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f86361b1e5310359288a97c5f41f017a344c30b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="resume-without-error"></a><span data-ttu-id="4afea-102">Resume senza errore</span><span class="sxs-lookup"><span data-stu-id="4afea-102">Resume without error</span></span>
<span data-ttu-id="4afea-103">Oggetto `Resume` istruzione all'esterno di codice di gestione degli errori, o il codice è passato in un gestore errori anche se si è verificato alcun errore.</span><span class="sxs-lookup"><span data-stu-id="4afea-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4afea-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="4afea-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="4afea-105">Spostare il `Resume` istruzione in un gestore di errori, o eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="4afea-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2.  <span data-ttu-id="4afea-106">Salti per le etichette non sono consentiti in procedure, quindi è necessario cercare la procedura per l'etichetta che identifica il gestore degli errori.</span><span class="sxs-lookup"><span data-stu-id="4afea-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="4afea-107">Se un'etichetta duplicata specificata come destinazione di un `GoTo` istruzione che non è un `On Error GoTo` istruzione, modificare l'etichetta di riga per accettare la destinazione prevista.</span><span class="sxs-lookup"><span data-stu-id="4afea-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4afea-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4afea-108">See Also</span></span>  
 [<span data-ttu-id="4afea-109">Istruzione Resume</span><span class="sxs-lookup"><span data-stu-id="4afea-109">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [<span data-ttu-id="4afea-110">Istruzione On Error</span><span class="sxs-lookup"><span data-stu-id="4afea-110">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
