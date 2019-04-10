---
title: Resume senza errore
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 61332486b20af66af24eac06b222a38353578c16
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300905"
---
# <a name="resume-without-error"></a>Resume senza errore
Oggetto `Resume` istruzione all'esterno di codice di gestione degli errori, o il codice passato in un gestore degli errori, anche se si è verificato alcun errore.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Spostare il `Resume` istruzione in un gestore di errori, oppure eliminarlo.  
  
2. Passa alle etichette non sono consentiti tra le procedure, quindi è necessario cercare la procedura per l'etichetta che identifica il gestore degli errori. Se si trova un'etichetta duplicata specificata come destinazione di una `GoTo` istruzione che non sia un `On Error GoTo` istruzione, modificare l'etichetta di riga per essere conforme alla destinazione prevista.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Resume](../../../visual-basic/language-reference/statements/resume-statement.md)
- [Istruzione On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
