---
title: Convenzione di chiamata DLL non valida
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: 70200b38ea3d1497daa091fa407accabaf3c4eda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715777"
---
# <a name="bad-dll-calling-convention"></a>Convenzione di chiamata DLL non valida
Argomenti passati a una libreria di collegamento dinamico (DLL) devono corrispondere esattamente a quelli previsti per la routine. Convenzioni di chiamata riguardano numero, tipo e ordine degli argomenti. Il programma può chiamare una routine in una DLL che viene passata il tipo non corretto o il numero di argomenti.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Assicurarsi che tutti i tipi di argomenti corrispondano a quelli specificati nella dichiarazione della routine che si sta chiamando.  
  
2.  Assicurarsi che si sta passando lo stesso numero di argomenti indicati nella dichiarazione della routine che si sta chiamando.  
  
3.  Se la routine di DLL sono previsti argomenti per valore, assicurarsi che `ByVal` specificato per tali argomenti nella dichiarazione della routine.  
  
## <a name="see-also"></a>Vedere anche
- [Tipi di errore](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Istruzione Call](../../../visual-basic/language-reference/statements/call-statement.md)
- [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
