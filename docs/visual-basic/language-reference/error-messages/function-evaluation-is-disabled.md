---
title: Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: bc4d05e52434cf62fa90671d29b407c83114b5d2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801946"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente
Valutazione della funzione disabilitata a causa del timeout di una valutazione della funzione precedente. Per riabilitare la valutazione della funzione, ripetere l'operazione o riavviare il debug.  
  
 Nel debugger di Visual Studio, un'espressione specifica una chiamata di routine, ma un altro valutazione è scaduta.  
  
 Possibili cause per una chiamata di procedura timeout includono un ciclo infinito oppure *un ciclo infinito*. Per altre informazioni, vedere [per... Istruzione Next](../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
 È un caso speciale di un ciclo infinito *ricorsione*. Per altre informazioni, vedere [routine ricorsive](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **ID errore:** BC30957  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Se possibile, determinare qual è la valutazione della funzione precedente e che lo ha generato al timeout. In caso contrario, questo errore potrebbe verificarsi nuovamente.  
  
2. Passaggio del debugger, oppure interrompere e riavviare il debug.  
  
## <a name="see-also"></a>Vedere anche

- [Debug in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)
- [Spostarsi nel codice con il Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger)
