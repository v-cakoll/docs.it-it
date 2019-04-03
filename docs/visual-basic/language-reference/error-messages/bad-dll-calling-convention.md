---
title: Convenzione di chiamata DLL non valida
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: c4f9917a7fb807cf7da92a3bba2d3edec8045bd2
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813520"
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
