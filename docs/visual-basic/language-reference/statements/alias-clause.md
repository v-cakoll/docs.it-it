---
title: Clausola Alias (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f61e738434ea616d751576ef21669545afc41397
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
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
