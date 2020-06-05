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
# <a name="resume-without-error"></a>Resume senza errore
Un'istruzione è stata rilevata al di `Resume` fuori del codice di gestione degli errori oppure il codice ha saltato un gestore errori anche se non si è verificato alcun errore.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Spostare l' `Resume` istruzione in un gestore errori o eliminarla.  
  
2. I salti alle etichette non possono essere eseguiti nelle procedure, quindi eseguire una ricerca nella routine per l'etichetta che identifica il gestore errori. Se si trova un'etichetta duplicata specificata come destinazione di un' `GoTo` istruzione che non è un' `On Error GoTo` istruzione, modificare l'etichetta della riga in modo che corrisponda alla destinazione prevista.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Resume](../statements/resume-statement.md)
- [Istruzione On Error](../statements/on-error-statement.md)
