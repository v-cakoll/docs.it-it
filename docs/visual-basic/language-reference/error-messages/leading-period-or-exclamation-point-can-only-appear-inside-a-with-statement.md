---
title: Il carattere '.' o '!' iniziale può trovarsi solo all'interno di un'istruzione
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 149acc2baac0f45fa971a11f254d694526d140d7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397324"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a>Il carattere '.' o '!' iniziale può trovarsi solo all'interno di un'istruzione
Un punto (.) o punto esclamativo (!) che non si trova all'interno di un `With` blocco si verifica senza un'espressione a sinistra. L'accesso ai membri ( `.` ) e l'accesso ai membri del dizionario ( `!` ) richiedono un'espressione che specifica l'elemento che contiene il membro. Deve essere visualizzato immediatamente a sinistra della funzione di accesso o come destinazione di un `With` blocco contenente l'accesso ai membri.  
  
 **ID errore:** BC30157  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che il `With` blocco sia formattato correttamente.  
  
2. Se non è presente alcun `With` blocco, aggiungere un'espressione a sinistra della funzione di accesso che restituisce un elemento definito contenente il membro.  
  
## <a name="see-also"></a>Vedere anche

- [Caratteri speciali nel codice](../../programming-guide/program-structure/special-characters-in-code.md)
- [Istruzione With...End With](../statements/with-end-with-statement.md)
