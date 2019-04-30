---
title: Resume senza errore
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 61332486b20af66af24eac06b222a38353578c16
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62055160"
---
# <a name="resume-without-error"></a><span data-ttu-id="7a0bc-102">Resume senza errore</span><span class="sxs-lookup"><span data-stu-id="7a0bc-102">Resume without error</span></span>
<span data-ttu-id="7a0bc-103">Oggetto `Resume` istruzione all'esterno di codice di gestione degli errori, o il codice passato in un gestore degli errori, anche se si è verificato alcun errore.</span><span class="sxs-lookup"><span data-stu-id="7a0bc-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7a0bc-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7a0bc-104">To correct this error</span></span>  
  
1. <span data-ttu-id="7a0bc-105">Spostare il `Resume` istruzione in un gestore di errori, oppure eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="7a0bc-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2. <span data-ttu-id="7a0bc-106">Passa alle etichette non sono consentiti tra le procedure, quindi è necessario cercare la procedura per l'etichetta che identifica il gestore degli errori.</span><span class="sxs-lookup"><span data-stu-id="7a0bc-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="7a0bc-107">Se si trova un'etichetta duplicata specificata come destinazione di una `GoTo` istruzione che non sia un `On Error GoTo` istruzione, modificare l'etichetta di riga per essere conforme alla destinazione prevista.</span><span class="sxs-lookup"><span data-stu-id="7a0bc-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a0bc-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a0bc-108">See also</span></span>

- [<span data-ttu-id="7a0bc-109">Istruzione Resume</span><span class="sxs-lookup"><span data-stu-id="7a0bc-109">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="7a0bc-110">Istruzione On Error</span><span class="sxs-lookup"><span data-stu-id="7a0bc-110">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
