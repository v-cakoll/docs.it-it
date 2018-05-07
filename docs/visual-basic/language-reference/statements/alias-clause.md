---
title: Clausola Alias (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 62b34f5860b35104b6a8caa82c359383999dd61b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="alias-clause-visual-basic"></a>Clausola Alias (Visual Basic)
Indica che una routine esterna ha un altro nome nella relativa DLL.  
  
## <a name="remarks"></a>Note  
 Il `Alias` parola chiave può essere utilizzata in questo contesto:  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 Nell'esempio seguente, il `Alias` parola chiave viene utilizzata per fornire il nome della funzione in advapi32.dll, `GetUserNameA`che `getUserName` in questo esempio viene usato al posto di. Funzione `getUserName` viene chiamato in sub `getUser`, che visualizza il nome dell'utente corrente.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/alias-clause_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
