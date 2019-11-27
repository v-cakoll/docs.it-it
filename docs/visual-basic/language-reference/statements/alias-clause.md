---
title: Clausola Alias
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: a7f67224c5d26816bdc1974dc4aa82d796c41284
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349153"
---
# <a name="alias-clause-visual-basic"></a>Clausola Alias (Visual Basic)
Indica che una routine esterna ha un altro nome nella relativa DLL.  
  
## <a name="remarks"></a>Osservazioni  
 Il `Alias` parola chiave può essere usato in questo contesto:  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 Nell'esempio seguente viene usata la parola chiave `Alias` per fornire il nome della funzione in Advapi32. dll, `GetUserNameA`, che `getUserName` viene usato al posto di in questo esempio. La funzione `getUserName` viene chiamata in Sub `getUser`, che Visualizza il nome dell'utente corrente.  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Vedere anche

- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
