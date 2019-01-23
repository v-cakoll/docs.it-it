---
title: Prevista dichiarazione
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: e776d3d08ff7d63b094a71e6990d87ea454a4428
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638431"
---
# <a name="declaration-expected"></a>Prevista dichiarazione
Un'istruzione non dichiarativa, ad esempio un'assegnazione o un'istruzione di ciclo, si verifica all'esterno di qualsiasi routine. Solo le dichiarazioni sono consentite alle routine esterne.  
  
 In alternativa, un elemento di programmazione è dichiarato senza una parola chiave di dichiarazione, ad esempio `Dim` o `Const`.  
  
 **ID errore:** BC30188  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Spostare l'istruzione non dichiarativa per il corpo di una stored procedure.  
  
-   Iniziare la dichiarazione con una parola chiave di dichiarazione appropriata.  
  
-   Assicurarsi che una parola chiave di dichiarazione non è errata.  
  
## <a name="see-also"></a>Vedere anche
- [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
