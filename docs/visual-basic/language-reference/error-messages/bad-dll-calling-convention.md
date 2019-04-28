---
title: Convenzione di chiamata DLL non valida
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: f7b0c3a6edbe0b950195306fa66287ff9b209bfe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935278"
---
# <a name="bad-dll-calling-convention"></a>Convenzione di chiamata DLL non valida
Argomenti passati a una libreria di collegamento dinamico (DLL) devono corrispondere esattamente a quelli previsti per la routine. Convenzioni di chiamata riguardano numero, tipo e ordine degli argomenti. Il programma può chiamare una routine in una DLL che viene passata il tipo non corretto o il numero di argomenti.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Assicurarsi che tutti i tipi di argomenti corrispondano a quelli specificati nella dichiarazione della routine che si sta chiamando.  
  
2. Assicurarsi che si sta passando lo stesso numero di argomenti indicati nella dichiarazione della routine che si sta chiamando.  
  
3. Se la routine di DLL sono previsti argomenti per valore, assicurarsi che `ByVal` specificato per tali argomenti nella dichiarazione della routine.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di errore](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Istruzione Call](../../../visual-basic/language-reference/statements/call-statement.md)
- [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
