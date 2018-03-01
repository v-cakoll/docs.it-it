---
title: Prevista dichiarazione
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 97bd1701a8a07c39d08a9276cdb929bc9425c1f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="declaration-expected"></a>Prevista dichiarazione
Un'istruzione non dichiarativa, ad esempio un'assegnazione o istruzione di ciclo, si verifica all'esterno di qualsiasi routine. Solo le dichiarazioni sono consentite alle routine esterne.  
  
 In alternativa, un elemento di programmazione è dichiarato senza una parola chiave di dichiarazione, ad esempio `Dim` o `Const`.  
  
 **ID errore:** BC30188  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Spostare l'istruzione non dichiarativa nel corpo di una stored procedure.  
  
-   Iniziare la dichiarazione con una parola chiave di dichiarazione appropriata.  
  
-   Verificare che una parola chiave di dichiarazione non sia digitato correttamente.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
