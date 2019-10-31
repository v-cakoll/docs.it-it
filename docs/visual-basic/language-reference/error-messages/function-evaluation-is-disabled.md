---
title: Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: d004c89b742944622ce45e6a2be8d96116252745
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197573"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente
Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente. Per riabilitare la valutazione della funzione, eseguire di nuovo l'istruzione o riavviare il debug.  
  
 Nel debugger di Visual Studio un'espressione specifica una chiamata di routine, ma si è verificato il timeout di un'altra valutazione.  
  
 Le possibili cause di una chiamata di routine a timeout includono *un ciclo infinito o infinito.* Per ulteriori informazioni, vedere [per... Istruzione successiva](../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
 Un caso speciale di un ciclo infinito è la *ricorsione*. Per ulteriori informazioni, vedere [procedure ricorsive](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **ID errore:** BC30957  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Se possibile, determinare la valutazione della funzione precedente e la causa del timeout. In caso contrario, è possibile che si verifichi questo errore.  
  
2. Eseguire di nuovo l'istruzione del debugger oppure terminare e riavviare il debug.  
  
## <a name="see-also"></a>Vedere anche

- [Debug in Visual Studio](/visualstudio/debugger/debugger-feature-tour)
- [Spostarsi nel codice con il Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger)
