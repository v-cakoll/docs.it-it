---
title: 'Procedura: Fare in modo che una variabile oggetto non faccia riferimento ad alcuna istanza (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: e647f2f891b06aa1767faac49b01df98ea31ec1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004911"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Procedura: Fare in modo che una variabile oggetto non faccia riferimento ad alcuna istanza (Visual Basic)
È possibile annullare l'associazione di una variabile oggetto da qualsiasi istanza di oggetto impostandola su [Nothing](../../../../visual-basic/language-reference/nothing.md).  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>Per annullare l'associazione di una variabile oggetto da qualsiasi istanza di oggetto  
  
- Impostare la variabile su `Nothing` in un'istruzione di assegnazione.  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Se il codice tenta di accedere a un membro di una variabile oggetto impostata su `Nothing`, viene generato un <xref:System.NullReferenceException>. Se si imposta una variabile oggetto su `Nothing` di frequente o se è possibile che la variabile non sia inizializzata, è consigliabile racchiudere gli accessi dei membri in un blocco `Try...Catch...Finally`.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Se si usa una variabile oggetto per gli oggetti che contengono dati riservati o sensibili, è possibile impostare la variabile su `Nothing` quando non si occupa attivamente di uno di questi oggetti. In questo modo si riduce la probabilità che il codice dannoso ottenga l'accesso ai dati.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.NullReferenceException>
- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Assegnazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Istruzione Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
