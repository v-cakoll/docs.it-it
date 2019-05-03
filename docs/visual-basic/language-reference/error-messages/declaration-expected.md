---
title: Prevista dichiarazione
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: 64ee75c93615f57b15fea29f06fff500a395ba0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803831"
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
