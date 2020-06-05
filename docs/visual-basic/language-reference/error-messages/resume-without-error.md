---
title: Resume senza errore
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: b6b565c88acadca048ade22ab00ac68539725f78
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400370"
---
# <a name="resume-without-error"></a><span data-ttu-id="322ed-102">Resume senza errore</span><span class="sxs-lookup"><span data-stu-id="322ed-102">Resume without error</span></span>
<span data-ttu-id="322ed-103">Un'istruzione è stata rilevata al di `Resume` fuori del codice di gestione degli errori oppure il codice ha saltato un gestore errori anche se non si è verificato alcun errore.</span><span class="sxs-lookup"><span data-stu-id="322ed-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="322ed-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="322ed-104">To correct this error</span></span>  
  
1. <span data-ttu-id="322ed-105">Spostare l' `Resume` istruzione in un gestore errori o eliminarla.</span><span class="sxs-lookup"><span data-stu-id="322ed-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2. <span data-ttu-id="322ed-106">I salti alle etichette non possono essere eseguiti nelle procedure, quindi eseguire una ricerca nella routine per l'etichetta che identifica il gestore errori.</span><span class="sxs-lookup"><span data-stu-id="322ed-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="322ed-107">Se si trova un'etichetta duplicata specificata come destinazione di un' `GoTo` istruzione che non è un' `On Error GoTo` istruzione, modificare l'etichetta della riga in modo che corrisponda alla destinazione prevista.</span><span class="sxs-lookup"><span data-stu-id="322ed-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="322ed-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="322ed-108">See also</span></span>

- [<span data-ttu-id="322ed-109">Istruzione Resume</span><span class="sxs-lookup"><span data-stu-id="322ed-109">Resume Statement</span></span>](../statements/resume-statement.md)
- [<span data-ttu-id="322ed-110">Istruzione On Error</span><span class="sxs-lookup"><span data-stu-id="322ed-110">On Error Statement</span></span>](../statements/on-error-statement.md)
