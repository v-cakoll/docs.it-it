---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: e8a8fb571fa65228f3a0acec1f902d21eb9bfe04
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268313"
---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Specifica che una o più variabili membro dichiarate fanno riferimento a un'istanza di una classe che può generare eventi.  
  
## <a name="remarks"></a>Note  
 Quando una variabile viene definita tramite `WithEvents`, è possibile specificare in modo dichiarativo in cui un metodo gestisce gli eventi della variabile usando la `Handles` (parola chiave).  
  
 È possibile usare `WithEvents` solo a livello di classe o modulo. Ciò significa che il contesto della dichiarazione per un `WithEvents` variabile deve essere una classe o un modulo e non può essere un file di origine, lo spazio dei nomi, struttura o procedura.  
  
 Non è possibile usare `WithEvents` su un membro della struttura.  
  
 È possibile dichiarare solo singole variabili, ovvero non matrici, ovvero con `WithEvents`.  
  
## <a name="rules"></a>Regole  
  
- **Tipi di elemento.** È necessario dichiarare `WithEvents` variabili come variabili oggetto in modo che accettino le istanze di classe. Tuttavia, non è possibile dichiarare come `Object`. È necessario dichiararli come la classe specifica in grado di generare gli eventi.  
  
 Il `WithEvents` modificatore può essere usato in questo contesto: [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
 
## <a name="example"></a>Esempio

```VB
Dim WithEvents app As Application
```
  
## <a name="see-also"></a>Vedere anche

- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
- [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)
