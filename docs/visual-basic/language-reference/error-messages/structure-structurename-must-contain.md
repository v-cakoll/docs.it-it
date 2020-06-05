---
title: La struttura '<structurename>' deve contenere almeno una dichiarazione di evento o di variabile membro di istanza non contrassegnata 'Custom'
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 7b5bda7b1a2ae37eb509c736deae1652dc5e6ab0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374018"
---
# <a name="structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a>La struttura '\<structurename>' deve contenere almeno una dichiarazione di evento o di variabile membro di istanza non contrassegnata 'Custom'
Una definizione di struttura non include variabili non condivise o eventi non personalizzati non condivisi.  
  
 Ogni struttura deve avere una variabile o un evento che si applica a ogni istanza specifica (non condivisa) invece che a tutte le istanze collettivamente ([condivise](../modifiers/shared.md)). Le costanti, le proprietà e le routine non condivisi non soddisfano questo requisito. Inoltre, se non sono presenti variabili non condivise e un solo evento non condiviso, l'evento non può essere un `Custom` evento.  
  
 **ID errore:** BC30941  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Definire almeno una variabile o un evento diverso da `Shared` . Se si definisce un solo evento, deve essere non personalizzato e non condiviso.  
  
## <a name="see-also"></a>Vedere anche

- [Strutture](../../programming-guide/language-features/data-types/structures.md)
- [Procedura: Dichiarare una struttura](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Istruzione Structure](../statements/structure-statement.md)
