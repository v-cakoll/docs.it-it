---
title: Clausola Alias (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 9cf97402d0b0a6cd16dd75a970c1d29a2fcc30a7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498570"
---
# <a name="alias-clause-visual-basic"></a>Clausola Alias (Visual Basic)
Indica che una routine esterna ha un altro nome nella relativa DLL.  
  
## <a name="remarks"></a>Note  
 Il `Alias` parola chiave può essere usata in questo contesto:  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 Nell'esempio seguente, il `Alias` parola chiave viene usata per specificare il nome della funzione in advapi32.dll, `GetUserNameA`, che `getUserName` viene usato al posto di questo esempio. Funzione `getUserName` viene chiamato nella sub `getUser`, che consente di visualizzare il nome dell'utente corrente.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/alias-clause_1.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
