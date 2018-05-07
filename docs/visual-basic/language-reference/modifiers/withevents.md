---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 240058a534456ae20c9c129a068bae575ac45eda
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
