---
title: Istruzione REM (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d64ce970e3e74437f5e8c63c8a4d578900902192
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="rem-statement-visual-basic"></a>Istruzione REM (Visual Basic)
Utilizzato per includere note esplicative nel codice sorgente di un programma.  
  
## <a name="syntax"></a>Sintassi  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Parti  
 `comment`  
 Parametro facoltativo. Il testo di qualsiasi commento da includere. Uno spazio è necessario tra il `REM` (parola chiave) e `comment`.  
  
## <a name="remarks"></a>Note  
 È possibile inserire un `REM` istruzione da solo su una riga oppure è possibile inserirlo in una riga dopo un'altra istruzione. Il `REM` istruzione deve essere l'ultima istruzione nella riga. Se segue un'altra istruzione, il `REM` devono essere separati da tale istruzione da uno spazio.  
  
 È possibile utilizzare una virgoletta singola (`'`) anziché `REM`. Ciò è vero se il commento segue un'altra istruzione sulla stessa riga o si trova da sola in una riga.  
  
> [!NOTE]
>  Non è possibile continuare un `REM` tramite l'utilizzo di una sequenza di continuazione di riga (`_`). Una volta avviato un commento, il compilatore non esamina i caratteri per un significato speciale. Per commenti su più righe, utilizzare un altro `REM` istruzione o un simbolo di commento (`'`) per ogni riga.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato il `REM` istruzione, viene utilizzato per includere note esplicative in un programma. Viene inoltre illustrato l'alternativa di utilizzare il carattere virgoletta singola (`'`) anziché `REM`.  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Commenti nel codice](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 [Procedura: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
