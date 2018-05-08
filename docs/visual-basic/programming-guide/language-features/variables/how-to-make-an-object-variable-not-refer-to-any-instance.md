---
title: 'Procedura: impostare una variabile oggetto in modo che non faccia riferimento ad alcuna istanza (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: bf918b762261e1dd1fc4161a10203f3d0067e454
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Procedura: impostare una variabile oggetto in modo che non faccia riferimento ad alcuna istanza (Visual Basic)
È possibile annullare l'associazione di una variabile oggetto a qualsiasi istanza dell'oggetto impostandolo su [nulla](../../../../visual-basic/language-reference/nothing.md).  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>Per annullare l'associazione di una variabile oggetto a qualsiasi istanza dell'oggetto  
  
-   Impostare la variabile `Nothing` in un'istruzione di assegnazione.  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Se il codice tenta di accedere a un membro di una variabile oggetto che è stata impostata su `Nothing`, <xref:System.NullReferenceException> si verifica. Se si imposta una variabile oggetto `Nothing` frequentemente o se è possibile che la variabile non viene inizializzata, è consigliabile racchiudere gli accessi ai membri in un `Try...Catch...Finally` blocco.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Se si utilizza una variabile oggetto per gli oggetti che contengono dati riservati o sensibili, è possibile impostare la variabile `Nothing` quando non si attivamente con uno di questi oggetti. Ciò riduce la possibilità di codice dannoso di ottenere l'accesso ai dati.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.NullReferenceException>  
 [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Assegnazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Nothing](../../../../visual-basic/language-reference/nothing.md)  
 [Istruzione Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Risoluzione dei problemi relativi ad eccezioni: System.NullReferenceException](http://msdn.microsoft.com/library/4822b0b4-8105-43fb-887a-3cc51ff02899)
