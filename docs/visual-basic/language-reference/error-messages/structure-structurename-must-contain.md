---
title: Struttura &#39; &lt;nomestruttura&gt; &#39; deve contenere almeno una variabile membro di istanza o dichiarazione di evento almeno un'istanza non contrassegnata &#39;personalizzata&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: d8c654c212a459d40c6cf20cd62c3e0fcda8511b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603781"
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a>Struttura &#39; &lt;nomestruttura&gt; &#39; deve contenere almeno una variabile membro di istanza o dichiarazione di evento almeno un'istanza non contrassegnata &#39;personalizzata&#39;
Una definizione di struttura non include eventuali variabili non condivise o eventi non personalizzati non condivisi.  
  
 Ogni struttura deve essere una variabile o un evento che si applica a ogni istanza specifica (non condivisa) invece che a tutte le istanze collettivamente ([condiviso](../../../visual-basic/language-reference/modifiers/shared.md)). Procedure, le proprietà e le costanti non condivise non soddisfano questo requisito. Inoltre, se sono presenti un solo evento non condiviso e nessuna variabile non condivisa, tale evento non può essere un `Custom` evento.  
  
 **ID errore:** BC30941  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Definire almeno una variabile o un evento che non è `Shared`. Se si definisce un solo evento, deve essere non personalizzati, nonché non condivisa.  
  
## <a name="see-also"></a>Vedere anche
- [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Procedura: Dichiarare una struttura](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
