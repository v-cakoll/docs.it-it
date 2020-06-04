---
title: Clausola Alias
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: c28e931a376b20b2058a7187551405cd9523d4fe
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408471"
---
# <a name="alias-clause-visual-basic"></a>Clausola Alias (Visual Basic)
Indica che una routine esterna ha un altro nome nella relativa DLL.  
  
## <a name="remarks"></a>Commenti  
 La `Alias` parola chiave può essere usata in questo contesto:  
  
 [Declare Statement](declare-statement.md)  
  
 Nell'esempio seguente `Alias` viene usata la parola chiave per specificare il nome della funzione in Advapi32. dll, `GetUserNameA` , che `getUserName` viene usata al posto di in questo esempio. `getUserName`La funzione viene chiamata in Sub `getUser` , che Visualizza il nome dell'utente corrente.  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Vedere anche

- [Parole chiave](../keywords/index.md)
