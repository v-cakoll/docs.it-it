---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords: WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 68a58fd130c04f2ed0cb1f2e5b9250f6c85f120d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Specifica che uno o più variabili di membro dichiarate fanno riferimento a un'istanza di una classe che può generare eventi.  
  
## <a name="remarks"></a>Note  
 Quando una variabile viene definita con `WithEvents`, è possibile specificare in modo dichiarativo che un metodo gestisce gli eventi della variabile utilizzando il `Handles` (parola chiave).  
  
 È possibile utilizzare `WithEvents` solo a livello di classe o modulo. Ciò significa che il contesto della dichiarazione per un `WithEvents` variabile deve essere una classe o un modulo e non può essere un file di origine, lo spazio dei nomi, struttura o stored procedure.  
  
 Non è possibile utilizzare `WithEvents` su un membro della struttura.  
  
 È possibile dichiarare solo variabili singole, non le matrici, ovvero con `WithEvents`.  
  
## <a name="rules"></a>Regole  
  
-   **Tipi di elemento.** È necessario dichiarare `WithEvents` le variabili come variabili oggetto in modo che accettino le istanze di classe. Tuttavia, non è possibile dichiarare come `Object`. È necessario dichiararle come la classe specifica in grado di generare gli eventi.  
  
 Il `WithEvents` modificatore può essere utilizzato in questo contesto: [Dim (istruzione)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)  
 [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)
