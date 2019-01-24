---
title: Iniziale &#39;. &#39; o &#39;. &#39; può trovarsi solo all'interno di un &#39;con&#39; istruzione
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: e64318d4ececbd887f55a1a202cc2d58c90c8fc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625952"
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a>Iniziale &#39;. &#39; o &#39;. &#39; può trovarsi solo all'interno di un &#39;con&#39; istruzione
Un punto (.) o un punto esclamativo (!) che non è compreso in un `With` blocchi si verifica senza un'espressione a sinistra. Accesso ai membri (`.`) e accesso ai membri dizionario (`!`) richiedono un'espressione che specifica l'elemento che contiene il membro. Questo deve apparire immediatamente a sinistra della funzione di accesso o come destinazione di un `With` blocco che contiene l'accesso al membro.  
  
 **ID errore:** BC30157  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare che il `With` blocco sia formattato correttamente.  
  
2.  Se è presente alcun `With` blocco, aggiungere un'espressione a sinistra della funzione di accesso che restituisce un elemento definito che contiene il membro.  
  
## <a name="see-also"></a>Vedere anche
- [Caratteri speciali nel codice](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [Istruzione With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
