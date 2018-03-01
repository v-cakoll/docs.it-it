---
title: Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 05067e730486b443b7a508adb499f34c060d5093
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente
La valutazione della funzione è disabilitata a causa del timeout di una valutazione della funzione precedente. Per riabilitare la valutazione della funzione, riprovare o riavviare il debug.  
  
 Nel debugger di Visual Studio, un'espressione specifica una chiamata di routine, ma un'altra valutazione è scaduta.  
  
 Possibili cause per una chiamata di routine timeout includono un ciclo infinito o *ciclo infinito*. Per ulteriori informazioni, vedere [per... Istruzione successiva](../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
 È un caso speciale di un ciclo infinito *ricorsione*. Per ulteriori informazioni, vedere [routine ricorsive](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **ID errore:** BC30957  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Se possibile, determinare qual era la valutazione della funzione precedente e la relativa causa il timeout. In caso contrario, questo errore potrebbe verificarsi nuovamente.  
  
2.  Eseguire nuovamente il debugger o terminare e riavviare il debug.  
  
## <a name="see-also"></a>Vedere anche  
 [Debug in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)  
 [Spostarsi nel codice con il Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger)
