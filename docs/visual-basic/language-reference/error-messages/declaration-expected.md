---
title: Prevista dichiarazione
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: 237622d0dc6c57f66d402f491a6191a5911574e2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409738"
---
# <a name="declaration-expected"></a>Prevista dichiarazione
Un'istruzione non dichiarativa, ad esempio un'istruzione di assegnazione o ciclo, si verifica all'esterno di qualsiasi routine. Solo le dichiarazioni sono consentite all'esterno delle procedure.  
  
 In alternativa, un elemento di programmazione viene dichiarato senza una parola chiave di dichiarazione, ad esempio `Dim` o `Const` .  
  
 **ID errore:** BC30188  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Spostare l'istruzione non dichiarativa nel corpo di una routine.  
  
- Iniziare la dichiarazione con una parola chiave di dichiarazione appropriata.  
  
- Assicurarsi che una parola chiave di dichiarazione non sia digitata in modo errato.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](../../programming-guide/language-features/procedures/index.md)
- [Istruzione Dim](../statements/dim-statement.md)
