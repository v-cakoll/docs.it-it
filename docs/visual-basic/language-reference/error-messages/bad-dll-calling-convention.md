---
title: Convenzione di chiamata DLL non valida
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: d8c7f7aea46162215115689305f4010cb513b020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="bad-dll-calling-convention"></a>Convenzione di chiamata DLL non valida
Gli argomenti passati a una libreria di collegamento dinamico (DLL) devono corrispondere esattamente a quelli previsti per la routine. Convenzioni di chiamata affrontare numero, tipo e ordine degli argomenti. Il programma può chiamare una routine in una DLL che viene passata il tipo non corretto o il numero di argomenti.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Assicurarsi che tutti i tipi di argomento corrispondano a quelli specificati nella dichiarazione di routine che si sta chiamando.  
  
2.  Verificare che si sta passando lo stesso numero di argomenti indicati nella dichiarazione della routine che si sta chiamando.  
  
3.  Se la routine della DLL prevede gli argomenti per valore, assicurarsi che `ByVal` viene specificato per gli argomenti nella dichiarazione della routine.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di errore](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [Istruzione Call](../../../visual-basic/language-reference/statements/call-statement.md)  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
