---
title: 'Procedura: impostare una variabile oggetto in modo che non faccia riferimento ad alcuna istanza'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: cce2e59cb76652937868a731ad308872d1aba2f3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410451"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Procedura: impostare una variabile oggetto in modo che non faccia riferimento ad alcuna istanza (Visual Basic)
È possibile annullare l'associazione di una variabile oggetto da qualsiasi istanza di oggetto impostandola su [Nothing](../../../language-reference/nothing.md).  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>Per annullare l'associazione di una variabile oggetto da qualsiasi istanza di oggetto  
  
- Impostare la variabile su `Nothing` in un'istruzione di assegnazione.  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Se il codice tenta di accedere a un membro di una variabile oggetto impostata su `Nothing` , <xref:System.NullReferenceException> si verifica un. Se si imposta una variabile oggetto su di `Nothing` frequente o se è possibile che la variabile non sia inizializzata, è consigliabile racchiudere gli accessi dei membri in un `Try...Catch...Finally` blocco.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Se si usa una variabile oggetto per gli oggetti che contengono dati riservati o sensibili, è possibile impostare la variabile su `Nothing` quando non si sta lavorando attivamente a uno di questi oggetti. In questo modo si riduce la probabilità che il codice dannoso ottenga l'accesso ai dati.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.NullReferenceException>
- [Variabili oggetto](object-variables.md)
- [Assegnazione di variabili oggetto](object-variable-assignment.md)
- [Nothing](../../../language-reference/nothing.md)
- [Istruzione Try...Catch...Finally](../../../language-reference/statements/try-catch-finally-statement.md)
