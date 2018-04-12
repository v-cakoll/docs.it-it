---
title: "Dichiarazione dell'operatore deve essere uno di: +,-, *,-, -, ^, &amp;, Like, Mod e, Or, Xor, non, &lt; &lt;, &gt; &gt;, =, &lt; &gt;, &lt;, &lt;=, &gt; , &gt;=, CType, IsTrue, IsFalse"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80c8358dd13105c18e73e94735a51b02d5bd22c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a>Dichiarazione dell'operatore deve essere uno di: +,-, *,\,/, ^, &amp;, Like, Mod e, Or, Xor, non, &lt; &lt;, &gt; &gt;...
È possibile dichiarare solo gli operatori che sono idoneo per l'overload. Nella tabella seguente elenca gli operatori che è possibile dichiarare.  
  
|Tipo|Operatori|  
|----------|---------------|  
|Unario|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binario|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Conversione (unario)|`CType`|  
  
 Si noti che il `=` operatore nell'elenco binario è l'operatore di confronto, non l'operatore di assegnazione.  
  
 **ID errore:** BC33000  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Selezionare un operatore dal set di operatori che supportano l'overload.  
  
2.  Se è necessario eseguire l'overload di un operatore che non può essere sottoposto a overload direttamente, creare una routine `Function` che accetti i parametri appropriati e restituisca il valore appropriato.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Procedura: Definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
