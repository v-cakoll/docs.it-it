---
title: Struttura &#39; &lt;nomestruttura&gt; &#39; deve contenere almeno una variabile membro di istanza o dichiarazione di evento almeno un'istanza non è contrassegnato come &#39;personalizzata&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 85a4babc808e274a99f2c9faf08a02abf8aa4e93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a>Struttura &#39; &lt;nomestruttura&gt; &#39; deve contenere almeno una variabile membro di istanza o dichiarazione di evento almeno un'istanza non è contrassegnato come &#39;personalizzata&#39;
Definizione di una struttura non include eventuali variabili non condivise o eventi non personalizzati non condivisi.  
  
 Ogni struttura deve essere una variabile o un evento che si applica a ogni istanza specifica (condiviso) anziché a tutte le istanze collettivamente ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)). Routine, proprietà e costanti non condivise non soddisfano questo requisito. Inoltre, se sono presenti un solo evento non condiviso e nessuna variabile non condivisa, tale evento non può essere un `Custom` evento.  
  
 **ID errore:** BC30941  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Definire almeno una variabile o un evento che non `Shared`. Se si definisce un solo evento, è necessario non personalizzati, nonché non condiviso.  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Procedura: Dichiarare una struttura](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
