---
title: La variabile '<variablename>' nasconde una variabile in un blocco di inclusione
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 474a920c9cfdfba7a8157320d9c88b8677958425
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406521"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a>La variabile '\<variablename>' nasconde una variabile in un blocco di inclusione
Una variabile racchiusa in un blocco ha lo stesso nome di un'altra variabile locale.  
  
 **ID errore:** BC30616  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Rinominare la variabile nel blocco racchiuso in modo che non corrisponda ad altre variabili locali. Ad esempio:  
  
    ```vb  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- Una cause comune di questo errore è l'uso di `Catch e As Exception` all'interno di un gestore eventi. In tal caso, denominare la `Catch` variabile Block `ex` anziché `e` .  
  
- Un'altra fonte comune di questo errore è un tentativo di accedere a una variabile locale dichiarata all'interno di un `Try` blocco in un `Catch` blocco separato. Per risolvere il problema, dichiarare la variabile all'esterno della `Try...Catch...Finally` struttura.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Try...Catch...Finally](../statements/try-catch-finally-statement.md)
- [Dichiarazione di variabile](../../programming-guide/language-features/variables/variable-declaration.md)
