---
title: Prevista dichiarazione
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: e6f8bf2b4ce9789a1715971b8262bdd162ba8035
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619537"
---
# <a name="declaration-expected"></a>Prevista dichiarazione
Un'istruzione non dichiarativa, ad esempio un'assegnazione o un'istruzione di ciclo, si verifica all'esterno di qualsiasi routine. Solo le dichiarazioni sono consentite alle routine esterne.  
  
 In alternativa, un elemento di programmazione è dichiarato senza una parola chiave di dichiarazione, ad esempio `Dim` o `Const`.  
  
 **ID errore:** BC30188  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Spostare l'istruzione non dichiarativa per il corpo di una stored procedure.  
  
- Iniziare la dichiarazione con una parola chiave di dichiarazione appropriata.  
  
- Assicurarsi che una parola chiave di dichiarazione non è errata.  
  
## <a name="see-also"></a>Vedere anche

- [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
