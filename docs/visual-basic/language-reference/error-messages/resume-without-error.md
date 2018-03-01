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
# <a name="resume-without-error"></a>Resume senza errore
Oggetto `Resume` istruzione all'esterno di codice di gestione degli errori, o il codice è passato in un gestore errori anche se si è verificato alcun errore.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Spostare il `Resume` istruzione in un gestore di errori, o eliminarlo.  
  
2.  Salti per le etichette non sono consentiti in procedure, quindi è necessario cercare la procedura per l'etichetta che identifica il gestore degli errori. Se un'etichetta duplicata specificata come destinazione di un `GoTo` istruzione che non è un `On Error GoTo` istruzione, modificare l'etichetta di riga per accettare la destinazione prevista.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Resume](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [Istruzione On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
