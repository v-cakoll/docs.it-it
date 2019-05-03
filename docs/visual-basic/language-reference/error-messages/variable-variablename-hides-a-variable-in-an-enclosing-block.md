---
title: La variabile '<variablename>' nasconde una variabile in un blocco di inclusione
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 15c35cbb829bec782771b584ea25b111b81b5e1f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766888"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a>Variabile '\<nomevariabile >' nasconde una variabile in un blocco di inclusione
Una variabile è incluso in un blocco ha lo stesso nome di un'altra variabile locale.  
  
 **ID errore:** BC30616  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Rinominare la variabile nel blocco in modo che non è quello utilizzato per tutte le altre variabili locali. Ad esempio:  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- Una causa comune di questo errore è l'uso di `Catch e As Exception` all'interno di un gestore eventi. In questo caso, denominare il `Catch` variabile del blocco `ex` anziché `e`.  
  
- Un'altra causa comune di questo errore è un tentativo di accedere a una variabile locale dichiarata all'interno di un `Try` blocco in un oggetto separato `Catch` blocco. Per risolvere il problema, dichiarare la variabile all'esterno di `Try...Catch...Finally` struttura.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Dichiarazione di variabile](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
