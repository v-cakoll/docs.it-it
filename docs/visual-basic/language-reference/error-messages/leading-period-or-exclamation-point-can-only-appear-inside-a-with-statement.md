---
title: Il carattere '.' o '!' iniziale può trovarsi solo all'interno di un'istruzione
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 367da8e7c9fd8c14a16a09b1f023e7637d78309d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259552"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a>Il carattere '.' o '!' iniziale può trovarsi solo all'interno di un'istruzione
Un punto (.) o un punto esclamativo (!) che non è compreso in un `With` blocchi si verifica senza un'espressione a sinistra. Accesso ai membri (`.`) e accesso ai membri dizionario (`!`) richiedono un'espressione che specifica l'elemento che contiene il membro. Questo deve apparire immediatamente a sinistra della funzione di accesso o come destinazione di un `With` blocco che contiene l'accesso al membro.  
  
 **ID errore:** BC30157  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare che il `With` blocco sia formattato correttamente.  
  
2.  Se è presente alcun `With` blocco, aggiungere un'espressione a sinistra della funzione di accesso che restituisce un elemento definito che contiene il membro.  
  
## <a name="see-also"></a>Vedere anche
- [Caratteri speciali nel codice](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [Istruzione With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
