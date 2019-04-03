---
title: 'Procedura: Impostare una variabile oggetto non fa riferimento a qualsiasi istanza (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 373d4ae84c44b212ad02b0b4266af75921e40423
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818689"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Procedura: Impostare una variabile oggetto non fa riferimento a qualsiasi istanza (Visual Basic)
È possibile annullare l'associazione di una variabile di oggetto da qualsiasi istanza dell'oggetto impostandolo su [Nothing](../../../../visual-basic/language-reference/nothing.md).  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>Per annullare l'associazione di una variabile di oggetto da qualsiasi istanza dell'oggetto  
  
-   Impostare la variabile `Nothing` in un'istruzione di assegnazione.  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Se il codice tenta di accedere a un membro di una variabile oggetto che è stata impostata su `Nothing`, un <xref:System.NullReferenceException> si verifica. Se si imposta una variabile oggetto `Nothing` frequentemente, o se è possibile la variabile non è inizializzata, è consigliabile racchiudere gli accessi ai membri in un `Try...Catch...Finally` blocco.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Se si usa una variabile oggetto per gli oggetti che contengono dati riservati o sensibili, è possibile impostare la variabile `Nothing` quando non si attivamente con uno di questi oggetti. In questo modo si riduce la probabilità di codice dannoso di ottenere l'accesso ai dati.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.NullReferenceException>
- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Assegnazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Istruzione Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
