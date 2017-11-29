---
title: Struttura &#39; &lt;nomestruttura&gt;&#39; deve contenere una variabile membro di almeno un'istanza o dichiarazione di evento almeno un'istanza non contrassegnata &#39; Custom &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords: BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b28dd59271bdaca52072710ea797fae6e9168eab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a>Struttura &#39; &lt;nomestruttura&gt;&#39; deve contenere una variabile membro di almeno un'istanza o dichiarazione di evento almeno un'istanza non contrassegnata &#39; Custom &#39;
Definizione di una struttura non include eventuali variabili non condivise o eventi non personalizzati non condivisi.  
  
 Ogni struttura deve essere una variabile o un evento che si applica a ogni istanza specifica (condiviso) anziché a tutte le istanze collettivamente ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)). Routine, proprietà e costanti non condivise non soddisfano questo requisito. Inoltre, se sono presenti un solo evento non condiviso e nessuna variabile non condivisa, tale evento non può essere un `Custom` evento.  
  
 **ID errore:** BC30941  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Definire almeno una variabile o un evento che non `Shared`. Se si definisce un solo evento, è necessario non personalizzati, nonché non condiviso.  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Procedura: Dichiarare una struttura](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
