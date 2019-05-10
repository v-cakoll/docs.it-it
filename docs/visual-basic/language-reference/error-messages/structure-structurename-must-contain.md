---
title: La struttura '<structurename>' deve contenere almeno una dichiarazione di evento o di variabile membro di istanza non contrassegnata 'Custom'
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 4ce24073896326bb5a68e563e2d34aafa09ef1c1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593210"
---
# <a name="structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a>Struttura '\<nomestruttura >' deve contenere almeno una variabile membro di istanza o dichiarazione di evento almeno un'istanza non contrassegnata 'Custom'
Una definizione di struttura non include eventuali variabili non condivise o eventi non personalizzati non condivisi.  
  
 Ogni struttura deve essere una variabile o un evento che si applica a ogni istanza specifica (non condivisa) invece che a tutte le istanze collettivamente ([condiviso](../../../visual-basic/language-reference/modifiers/shared.md)). Procedure, le proprietà e le costanti non condivise non soddisfano questo requisito. Inoltre, se sono presenti un solo evento non condiviso e nessuna variabile non condivisa, tale evento non può essere un `Custom` evento.  
  
 **ID errore:** BC30941  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Definire almeno una variabile o un evento che non è `Shared`. Se si definisce un solo evento, deve essere non personalizzati, nonché non condivisa.  
  
## <a name="see-also"></a>Vedere anche

- [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Procedura: Dichiarare una struttura](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
