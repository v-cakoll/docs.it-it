---
title: La variabile '<variablename>' nasconde una variabile in un blocco di inclusione
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 4312abef83728f432e2f6a492e5acad3450719b1
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592056"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a>La variabile ' \<variablename >' nasconde una variabile in un blocco di inclusione
Una variabile racchiusa in un blocco ha lo stesso nome di un'altra variabile locale.  
  
 **ID errore:** BC30616  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Rinominare la variabile nel blocco racchiuso in modo che non corrisponda ad altre variabili locali. Esempio:  
  
    ```vb  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- Una cause comune di questo errore è l'uso di `Catch e As Exception` all'interno di un gestore eventi. In tal caso, denominare la variabile di blocco `Catch` `ex` anziché `e`.  
  
- Un'altra fonte comune di questo errore è un tentativo di accedere a una variabile locale dichiarata all'interno di un blocco `Try` in un blocco `Catch` separato. Per risolvere il problema, dichiarare la variabile all'esterno della struttura `Try...Catch...Finally`.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Dichiarazione di variabile](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
